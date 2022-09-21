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

Bước 1: Thêm repository

```
nano /etc/yum.repos.d/nginx.repo
```

Dán nội dung dưới đây vào

```
[nginx-stable]
name=nginx stable repo
baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
gpgcheck=1
enabled=1
gpgkey=https://nginx.org/keys/nginx_signing.key
module_hotfixes=true
```

![image](https://user-images.githubusercontent.com/111716161/191454285-0079a703-c2dd-48c0-9ba5-8126486c10c6.png)

Bước 2: Cài đặt các gói cần thiết

```
yum install yum-utils -y
```

![image](https://user-images.githubusercontent.com/111716161/191454418-6bb18d4a-966a-4b2b-8406-ff82fce0fe4b.png)

Update những thay đổi mới nhất

```
yum -y update
```


# Bước 3: Cài đặt Nginx

```
yum install nginx -y
```

![image](https://user-images.githubusercontent.com/111716161/191454622-cfbac531-1124-40f0-80d7-6765fd817b28.png)

Bước 3: Khởi động dịch vụ

```
systemctl start nginx
systemctl enable nginx
```

![image](https://user-images.githubusercontent.com/111716161/191454800-43d27291-b32a-49a0-b7d8-a07e6567b773.png)

Các lệnh quản lý Nginx:

```
systemctl start nginx      // Khởi động dịch vụ Nginx
systemctl stop nginx       // Dừng dịch vụ Nginx
systemctl reload nginx     // Tải lại dịch vụ Nginx
systemctl restart nginx    // Khởi động lại dịch vụ Nginx
systemctl enable nginx     // Thiết lập Nginx khởi động cùng hệ thống
systemctl disable nginx    // Vô hiệu hoá Nginx khởi động cùng hệ thống
systemctl status nginx     // Xem trạng thái dịch vụ Nginx
```

# Bước 4: Mở dịch vụ trên Firewalld

```
firewall-cmd --permanent --add=service=http
firewall-cmd --permanent --add=service=https
firewall-cmd --reload
```


- Kiểm tra, hãy truy cập http://IP-VPS bằng trình duyệt sẽ thấy trang chào mừng của Nginx


