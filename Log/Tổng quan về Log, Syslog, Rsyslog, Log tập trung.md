# Log

**Log** ghi lại liên tục các thông báo về hoạt động của cả hệ thống hoặc của các dịch vụ được triển khai trên hệ thống và file tương ứng. 

Log file thường là các file văn bản thông thường dưới dạng “clear text” tức là bạn có thể dễ dàng đọc được nó, vì thế có thể sử dụng các trình soạn thảo văn bản (vi, vim, nano…) hoặc các trình xem văn bản thông thường (cat, tailf, head…) là có thể xem được file log.

Các file log có thể nói cho bạn bất cứ thứ gì bạn cần biết, để giải quyết các rắc rối mà bạn gặp phải miễn là bạn biết ứng dụng nào. Mỗi ứng dụng được cài đặt trên hệ thống có cơ chế tạo log file riêng của mình để bất cứ khi nào bạn cần thông tin cụ thể thì các log file là nơi tốt nhất để tìm.

Các tập tin log được đặt trong thư mục /var/log. Bất kỳ ứng dụng khác mà sau này bạn có thể cài đặt trên hệ thống của bạn có thể sẽ tạo tập tin log của chúng tại /var/log. Dùng lệnh ls -l /var/log để xem nội dung của thư mục này.

## Ý nghĩa một số file log thông dụng có mặc định trên /var/log

`/var/log/messages` – Chứa dữ liệu log của hầu hết các thông báo hệ thống nói chung, bao gồm cả các thông báo trong quá trình khởi động hệ thống.

`/var/log/cron` – Chứa dữ liệu log của cron deamon. Bắt đầu và dừng cron cũng như cronjob thất bại.

`/var/log/maillog` hoặc `/var/log/mail.log` – Thông tin log từ các máy chủ mail chạy trên máy chủ.

`/var/log/wtmp` – Chứa tất cả các đăng nhập và đăng xuất lịch sử.

`/var/log/btmp` – Thông tin đăng nhập không thành công

`/var/run/utmp` – Thông tin log trạng thái đăng nhập hiện tại của mỗi người dùng.

`/var/log/dmesg` – Thư mục này có chứa thông điệp rất quan trọng về kernel ring buffer. Lệnh dmesg có thể được sử dụng để xem các tin nhắn của tập tin này.

`/var/log/secure` – Thông điệp an ninh liên quan sẽ được lưu trữ ở đây. Điều này bao gồm thông điệp từ SSH daemon, mật khẩu thất bại, người dùng không tồn tại...

## Một số log thường gặp

### Log SSH: /var/log/secure

```
tailf /var/log/secure | grep ssh 
```

![image](https://user-images.githubusercontent.com/111716161/193736363-f2100b99-9276-4c78-a180-96f3c462031c.png)

### Access log Apache:

```
tailf /var/log/httpd/access_log
```

![image](https://user-images.githubusercontent.com/111716161/193736781-b537144c-20e6-444e-b694-4b22a98c68a6.png)

### Error log Apache:

```
tailf error_log
```

### Log ghi lại những lần đăng nhập thành công:

```
last -f /var/log/wtmp

utmpdump /var/log/wtmp
```

![image](https://user-images.githubusercontent.com/111716161/193737102-3aa9f97a-d2e7-461b-85a2-c1958a659362.png)

![image](https://user-images.githubusercontent.com/111716161/193737172-7b45ccf5-0ee5-4bfa-bd8c-43d189a2ab6d.png)

### Log ghi lại những lần đăng nhập thất bại:

```
lastb -f /var/log/btmp | more
```

![image](https://user-images.githubusercontent.com/111716161/193737227-c4347354-c23c-45d6-accb-c754d8c77d02.png)
