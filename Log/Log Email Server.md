# Zimbra Log

Tất cả log nội bộ của server Zimbra được lưu trong thư mục /opt/zimbra/log, trong đó mailbox.log là nơi lưu trữ thời gian sự việc, mức độ của sự việc, tác vụ, tên tài khoản và địa chỉ IP cũng như mô tả liên quan đến sự việc. 

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

![image](https://user-images.githubusercontent.com/111716161/193978787-5c069d4a-4dcb-438e-877c-be5a39c80d2d.png)

![image](https://user-images.githubusercontent.com/111716161/193978964-eadb4302-d9f6-438c-9e60-b210544354d6.png)

Zimbra cung cấp công cụ giúp theo dấu các email đã gửi nhận: zmmsgtrace, chạy với quyền root.

```
/opt/zimbra/libexec/zmmsgtrace -s user@example.com  #Trace theo địa chỉ gửi

/opt/zimbra/libexec/zmmsgtrace -r '@gmail.com'  #Trace theo địa chỉ nhận

/opt/zimbra/libexec/zmmsgtrace -r '@gmail.com' /var/log/zimbra*   #Trace từ các file log khác nhau
```

## 

Để thiết lập ghi log tập trung trong một hệ thống Zimbra có nhiều server bạn cần cấu hình một host để thu nhận log. Thường bạn sẽ dùng mailbox server, cài đặt logger để thu thập log.

Logger server sẽ thu thập thông tin thống kê, trạng thái của các service trên các server khác, zimbra.log được lưu tập trung nhưng các log khác như mailbox.log và audit.log được lưu theo kiểu round robin trên các mailstore server. Muốn tập trung các log này về một log server riêng, zimico khuyến cáo bạo dùng 1 giải pháp lưu và phân tích log tập trung của bên thứ 3 như Graylog.

Bước 1: Cài đặt logger của zimbra trên mailbox server này.

Bước 2: Chỉnh sửa file `/etc/sysconfig/rsyslog`, cấu hình `SYSLOGD_OPTIONS="-r -c 2"`

![image](https://user-images.githubusercontent.com/111716161/193980165-cbffd5df-0bf7-4e77-859b-c5864870ce1f.png)

Bước 3: Chỉnh sửa file `/etc/rsyslog.conf` và kích hoạt 2 dòng sau:
```
$ModLoad imupd
$UDPServerRun 514
```

Bước 3: Khởi động lại rsyslog

```
systemctl restart rsyslog
```

Bước 4: Chạy các lệnh sau:

```
su - zimbra

/opt/zimbra/bin/zmsshkeygen

/opt/zimbra/bin/zmupdateauthkeys

/opt/zimbra/libexec/zmloggerinit
```

![image](https://user-images.githubusercontent.com/111716161/193980297-e02c1e63-f297-4d74-b29a-c623ce815be6.png)

![image](https://user-images.githubusercontent.com/111716161/193980370-b20a5085-e541-428c-8fb6-044f84b59d7b.png)

Bước 5: Kiểm tra thông số:

```
zmprov gacf | grep zimbraLogHostname
```

![image](https://user-images.githubusercontent.com/111716161/193980424-e0c5d4e8-1cac-4cab-b6d9-f5340ca3dbc5.png)

# Kiểm tra log gửi/nhận email Zimbra

Việc kiểm tra log gửi/nhận của email server zimbra là rất cần thiết, giúp xác định được một email đã gửi/nhận thành công hay chưa và nếu chưa thành công thì bị dừng ở bước nào và báo lỗi ra sao.

- Để kiểm tra việc gửi email của 1 địa chỉ email:

```
/opt/zimbra/libexec/zmmsgtrace -s user1@xn--thng-mgb3g.vn
```

![image](https://user-images.githubusercontent.com/111716161/193975709-a6f9eaa0-dae5-4bcb-ac5b-1ff34a953386.png)

- Để kiểm tra việc gửi email tới một domain cụ thể (kiểm tra theo địa chỉ nhận):

```
/opt/zimbra/libexec/zmmsgtrace -r '@xn--thng-mgb3g.vn'
```

![image](https://user-images.githubusercontent.com/111716161/193976503-b63f9bc3-659c-4a24-8601-889516e85d56.png)

- Để kiểm tra từ các file log khác nhau:

```
/opt/zimbra/libexec/zmmsgtrace -r '@xn--thng-mgb3g.vn' /var/log/zimbra*
```

![image](https://user-images.githubusercontent.com/111716161/193979324-dcfbbbf2-4541-4db0-a110-29ebabc6ffb1.png)

