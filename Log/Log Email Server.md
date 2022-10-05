# Zimbra Log

Tất cả log nội bộ của server Zimbra được lưu trong thư mục /otp/zimbra/log, trong đó mailbox.log là nowiluwu trữ thời gian sự việc, mức độ của sự việc, tác vụ, tên tài khoản và địa chỉ IP cũng như mô tả liên quan đến sự việc. 

Log level thể hiện mức độ ảnh hưởng của event đến server. Mặc định có 4 mức độ được sử dụng:
- INFO: Các event tại mức độ này có mục đích thông báo về các tiến trình của Zimbra như việc tạo, xóa message, v.v...
- ERROR: Thể hiện lỗi xảy ra và không ảnh hưởng đến hoạt động của server, ví dụ như cảnh báo về việc index dữ liệu của một người dùng đang bị lỗi.
- FATAL: Thể hiện rằng server không thể hoạt động bình thường, ví dụ như thông báo không thể kết nối đến cơ sở dữ liệu.

Các file log được cập nhật hằng ngày, phiên bản sau cùng luôn có tên là mailbox.log, các file trước đó được nén và đặt tên theo ngày. 

## 

Thư mục /opt/zimbra/log còn chứa các file log khác, lưu lại các thông tin đặc thù như audit.log thể hiện đăng nhập thành công hoặc không. Dùng lệnh `grep -ir "invalid password" /opt/zimbra/log/audit.log` để xem. 

Tìm theo từ khóa FATAL khi server bị các sự cố nghiêm trọng, hoặc tìm theo từ khóa ImapServer, Pop3Server khi muốn tìm thông tin liên quan đến giao thức pop3 hay imap. 

```
grep -iE 'fatal|error' mailbox.log

grep -iEv -C3 'info|warn' mailbox.log   #Hiển thị thêm một số dòng xung quanh

grep -iEv -A3 'info|warn' mailbox.log   #Hiển thị thêm một số dòng sau đó

grep -iE 'user1.*user2' /var/log/zimbra.log   #Lọc theo từ khóa từ trái sang phải, đầu tiên là user1 sau đó là user2

grep -iE user1 /var/log/zimbra.log | grep user2

grep -i smtp /var/log/zimbra.log | grep -ioE 'to=.*status=.*[ \t] ' | head -5

zgrep -i "triggers filter" /var/log/zimbra.* | grep -ioE 'from=.*to=.*>[ \t]' | grep example | uniq

tail -f mailbox.log -f trace_log.2015_03_11 -f access_log.2015-03-11 -f sync.log -f ews.log | grep -i user1   #giám sát user1 từ nhiều log file khác nhau theo thời gian thực
```

Zimbra cung cấp công cụ giúp theo dấu các email đã gửi nhận: zmmsgtrace, chạy với quyền root.

```
/opt/zimbra/libexec/zmmsgtrace -s user@example.com  #Trace theo địa chỉ gửi

/opt/zimbra/libexec/zmmsgtrace -r '@gmail.com'  #Trace theo địa chỉ nhận

/opt/zimbra/libexec/zmmsgtrace -r '@gmail.com' /var/log/zimbra*   #Trace từ các file log khác nhau
```

## 

Để thiết lập ghi log tập trung trong một hệ thống Zimbra có nhiều server bạn cần cấu hình một host để thu nhận log. Thường bạn sẽ dùng mailbox server, cài đặt logger để thu thập log.

Logger server sẽ thu thập thông tin thống kê, trạng thái của các service trên các server khác, zimbra.log được lưu tập trung nhưng các log khác như mailbox.log và audit.log được lưu theo kiểu round robin trên các mailstore server. Muốn tập trung các log này về một log server riêng, zimico khuyến cáo bạo dùng 1 giải pháp lưu và phân tích log tập trung của bên thứ 3 như Graylog.

# Kiểm tra log gửi/nhận email Zimbra

Việc kiểm tra log gửi/nhận của email server zimbra là rất cần thiết, giúp xác định được một email đã gửi/nhận thành công hay chưa và nếu chưa thành công thì bị dừng ở bước nào và báo lỗi ra sao.

- Truy cập file log:

```
/var/log/maillog
```

- Chu trình gửi: Khi click gửi thư -> Connect tới email server -> MTA kiểm tra địa chỉ người nhận -> Kiểm tra qua các rule filter, đánh giá spam, virus -> Xếp vào queue -> Gửi thư -> Xóa khỏi queue -> Thông báo Message accepted for delivery

- Chu trình nhận: Chấp nhận kết nối từ email server gửi -> Kiểm tra qua các rule filter, đánh giá spam, virus -> Xếp vào queue => Nhận thư và xóa khỏi queue -> Thông báo nhận thư 250 2.1.5 Delivery OK

