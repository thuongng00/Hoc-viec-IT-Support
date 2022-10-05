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

