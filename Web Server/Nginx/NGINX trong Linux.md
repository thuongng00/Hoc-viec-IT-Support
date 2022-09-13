# Mục lục

[NGINX](#nginx)

[So sánh NGINX và APACHE](#sosanh)

[Cài đặt Nginx trên CentOS 7](#caidat)

<a name="nginx"></a>

# NGINX

**NGINX** là một web server mạnh mẽ mã nguồn mở. Nginx sử dụng kiến trúc đơn luồng, hướng sự kiện vì thế nó hiệu quả hơn Apache server. Nó cũng có thể làm những thứ quan trọng khác, chẳng hạn như load balancing, HTTP caching, hay sử dụng như một reverse proxy, media streaming và email proxy như IMAP, POP3, và SMTP….  

Vì NGINX server đáng tin cậy, tốc độ và có khả năng mở rộng lớn nên những ông lớn công nghệ dùng nó là Google, Netflix, Adobe, Cloudflare, WordPress,..đã lựa chọn NGINX.

### Các tính năng chính của Nginx

Nginx có thể triển khai phục vụ nội dung HTTP động trên internet bằng cách sử dụng giao thức Fash, SCGI cho tập lệnh, máy chủ ứng dụng WSGI hoặc các module Phusion Passenger. Ngoài ra còn đóng vai trò là bộ cân bằng tải phần mềm. 

Nginx áp dụng cách tiếp cận theo hướng sự kiện không đồng bộ thay vì các luồng để xử lý các yêu cầu. Kiến trúc hướng sự kiện cung cấp hiệu suất dễ dự đoán hơn dưới tải trọng cao. Tệp cấu hình mặc định của Nginx có dạng là nginx.conf.

### Các tính năng máy chủ web và HTTP proxy
- Khả năng xử ký lên đến tối đa hơn 10000 kết nối đồng thời mức dung lượng bộ nhớ vô cùng thấp (~2.5MB mỗi 10000 kết nối HTTP không hoạt động).
- Xử lý tập tin tĩnh (static file), index file và lập chỉ mục tập tin. 
- Tăng tốc Reverse proxy với bộ nhớ đệm. 
- Cân bằng tải đơn giản (load balancing) và khả năng chịu lỗi. 
- Hỗ trợ mã hóa TLS/SSL với SNI và OCSP, thông qua OpenSSL. 
- Hỗ trợ giao thức FastCGI, SCGI, uWSGI với bộ nhớ đệm. 
- Máy chủ ảo hoạt động dựa trên địa chỉ IP và tên.
- Khả năng tương thích IPv6.
- Hỗ trợ WebSockets kể từ 1.3.13, bao gồm hoạt động như một proxy ngược và thực hiện cân bằng tải cho các ứng dụng WebSocket.
- Nâng cấp giao thức HTTP/1.1, hỗ trợ HTTP/2.
- Hỗ trợ nhúng mã PERL.

### Các tính năng Mail proxy
- Hỗ trợ TLS/SSL, STARTTLS.
- POP3: USER/PASS, APOP, AUTH LOGIN/PLAIN/CRAM-MD5.
- IMAP: LOGIN, AUTH LOGIN/PLAIN/CRAM-MD5.
- SMTP: AUTH LOGIN/PLAIN,CRAM-MD5.

<a name="sosanh"></a>

# So sánh NGINX và APACHE

![image](https://user-images.githubusercontent.com/111716161/188770245-b53e3cec-e4e2-47b7-98f7-af5a02de4567.png)

| Vai trò |Apache|Nginx| Kết luận |
|---|---|---|---|
|Mức độ phổ biến|Năm 2012 tổng số web sử dụng Apache chiếm hơn 65% |Năm 2012 chiếm khoảng 44%|Với thời đại phát triển thì người dùng chuyển sang Nginx nhiều hơn nên con số này không chênh lệch quá cao|
|Tốc độ|Tốc độ truy cập vào web sử dụng Apache còn xử lí chậm hơn, nên cần được cải thiện| Trái lại với Apache, Nginx được xếp hạng là nhanh chóng hơn|
|Kết nối đồng thời|![image](https://user-images.githubusercontent.com/105496635/183549108-52682f28-8584-40ee-be09-533dedc616cc.png)| ![image](https://user-images.githubusercontent.com/105496635/183549067-4d38181d-8d99-48c2-95ca-0627d02c79f5.png)| Đối với 25 người dùng ảo, trang web Nginx có thể ghi 200 yêu cầu mỗi giây, cao hơn 2,5 lần so với Apache (80 yêu cầu mỗi giây). Rõ ràng, nếu bạn có một trang web lưu lượng truy cập cao chuyên dụng, Nginx là một lựa chọn an toàn hơn.|
|Tính linh hoạt|Với việc sử dụng .htaccess nên Apache có thể linh hoạt tùy chỉnh|Nginx không hỗ trợ .htaccess||
|Các thông số khác|||Trước đây, Nginx không hỗ trợ tốt lắm cho hệ điều hành Windows, không giống như Apache. Tuy nhiên, điều này không còn nữa. Ngoài ra, Apache cũng từng bị coi là khá yếu về cân bằng tải và reserve proxy. Nhưng mọi thứ bây giờ đã thay đổi|
||||Với những so sánh trên thì thấy được cả hai dạng máy chủ thì vẫn dùng hữu ích theo cách riêng của chúng ta|

## Nên sử dụng Apache hay Nginx?
Cả hai web server hiện nay đều có thể cạnh tranh với nhau trong hầu hết các tiêu chí. Đối với nội dung tĩnh NGINX là vua, nhưng đối với nội dung động thì nó kém hơn một chút. NGINX nổi bật với một số tính năng cao cấp của nó (media streaming, reverse proxying for non-HTTP protocols).

Người dùng shared hositng có thể thích sự tiện lợi của file .htaccess Apache. Và Apache có khá nhiều dynamic module (NGINX mới chỉ bắt đầu thêm dynamic module). NGINX được sử dụng chủ yếu cho VPS hosting, dedicated hosting, hoặc container cluster. Với các website có lượt truy cập cao có nhu cầu phục vụ rất nhiều nội dung tĩnh và / hoặc streaming media sẽ hướng tới NGINX. Nhưng đa phần cả 2 sẽ hoạt động tốt trong hầu hết mọi trường hợp.

Bất kể với web server nào, hãy chọn một nhà cung cấp hosting tốt nhất trên nền tảng Linux.

<a name="caidat"></a>

# Cài đặt Nginx trên CentOS 7

Bước 1: Đăng nhập với quyền root.

Bước 2 : Dừng SELinux nhằm tránh trường hợp nó chặn Nginx

Truy cập SELinux bằng câu lệnh :

```
nano /etc/sysconfig/selinux
```

![image](https://user-images.githubusercontent.com/111716161/188775311-33133b0b-0aae-4c2b-8f6f-4490e818762d.png)

Thay đổi ``enforcing`` thành ``disabled`` như hình trên.

Sau đó dùng lệnh ``reboot`` để khởi động lại hệ thống.

Tiếp theo dùng lệnh ``sestatus`` để kiểm tra SELinux đã dừng chưa (Nếu như hình dưới là đã thành công)

![image](https://user-images.githubusercontent.com/111716161/188775705-d6dcf264-757e-4581-a466-c734aae8d5a4.png)

Bước 3 : Cài đặt các gói cần thiết hỗ trợ NginX

Để cài Nginx trên CentOS, chúng ta sẽ cần thêm EPEL repository giúp tạo, duy trì và quản lý các gói bổ sung.

```
sudo yum install epel-release -y
```

![image](https://user-images.githubusercontent.com/111716161/188775852-b3982f37-2894-4452-a423-d91616a6a377.png)

Bước 3 : Tiến hành cài đặt NginX

Chúng ta cài đặt nginx với câu lệnh :

```
yum install nginx -y
```

![image](https://user-images.githubusercontent.com/111716161/188775963-915145e4-e11c-4a45-b641-ed90bee5878c.png)

Bước 4 : Khởi động Nginx

`systemctl enable nginx` : Câu lệnh đặt mặc định khỏi động Nginx cùng với hệ thống

`systemctl start nginx` : Câu lệnh khởi chạy Nginx

`systemctl status nginx` : Câu lệnh kiểm tra trạng thái Nginx

![image](https://user-images.githubusercontent.com/111716161/188776143-40bb96ab-95d7-49fc-9fc8-d033e58c2cf3.png)

Sau đó truy cập IP/Domain hệ thống.

![image](https://user-images.githubusercontent.com/111716161/188779933-669d8026-80ed-48ca-8bee-7c44203aa582.png)

Nếu các bạn sử dụng Firewall để có thể truy cập được website các bạn sẽ cần mở port bằng các lệnh sau đây

```
firewall-cmd --permanent --zone=public --add-service=http
firewall-cmd --permanent --zone=public --add-service=https
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/188776689-75f6b602-86b2-4883-a6ca-a09782fda1a7.png)
