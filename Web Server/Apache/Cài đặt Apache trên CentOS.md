[Apache](#apache)

[Cài đặt Apache](#caidat)

<a name="apache"></a>
# Apache

Apache là phần mềm web server miễn phí mã nguồn mở được sử dụng phổ biến trên toàn thế giới. Tên gọi đầy đủ của Apache là Apache HTTP Server, được sáng lập và điều hành bởi Apache Software Foundation.

![image](https://user-images.githubusercontent.com/111716161/188768202-5ca28752-ef3b-4a66-b64e-a3cfd8d24a59.png)

Apache giúp người quản trị website có thể đưa nội dung lên web – chính vì vậy mà có tên gọi là “web server“. Apache là một trong số những web server uy tín và lâu đời nhất, phiên bản đầu tiên đã được ra mắt từ hơn 20 năm trước, vào những năm 1995.

Apache chạy trên các hệ điều hành tương tự như Unix, Microsoft Windows, Novell Netware và các hệ điều hành khác. Đóng vai trò quan trọng trong quá trình phát triển của mạng web thế giới (World Wide Web).

*Các Web Server có thể cài lên CentOS 7 là :*
- Apache HTTP Server
- Apache Tomcat
- nginx
- OpenLiteSpeed

## Apache HTTP Server
Trang chủ: http://httpd.apache.org/

Apache là phần mềm web server mã nguồn mở đa nền tảng miễn phí , sử dụng giấy phép Apache License 2.0

Ra đời năm 1995 bởi Robert McCool.

Phiên bản ổn định mới nhất: 2.4.54 (08-06-2022).

Apache được phát triển và duy trì bởi một cộng đồng các nhà phát triển dưới sự bảo trợ của Quỹ phần mềm Apache (Apache Software Foundation).

Phần lớn các phiên bản Apache chạy trên bản phân phối Linux , nhưng các phiên bản hiện tại cũng chạy trên Microsoft Windows và nhiều hệ thống tương tự Unix. Các phiên bản trước đây cũng chạy trên OpenVMS , NetWare và các hệ điều hành khác.

Là 1 thành phần của LAMP Stack – (Linux, Apache, MariaDB, Perl/Python/PHP).

### Ưu điểm

- Phần mềm mã nguồn mở và miễn phí, kể cả cho mục đích thương mại
- Phần mềm đáng tin cậy, ổn định
- Được cập nhật thường xuyên, nhiều bản vá lỗi bảo mật liên tục
- Linh hoạt vì có cấu trúc module
- Dễ cấu hình, thân thiện với người mới bắt đầu
- Đa nền tảng (hoạt động được cả với server Unix và Windows )
- Hoạt động cực kỳ hiệu quả với WordPress sites
- Có cộng đồng lớn và sẵn sàng hỗ trợ với bất kỳ vấn đề nào

### Nhược điểm 

- Gặp vấn đề hiệu năng nếu website có lượng truy cập cực lớn
- Quá nhiều lựa chọn thiết lập có thể gây ra các điểm yếu bảo mật

<a name="caidat"></a>
# Cài đặt Apache trên CentOS 7

### 1. Truy cập Teminal CentOS 7 với quyền root với câu lệnh
```
su
```
![image](https://user-images.githubusercontent.com/111716161/188358270-ca6f7bc9-2a10-4148-916b-8bbfc22feac3.png)

Tắt Selinux

```
sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config && setenforce 0
```


### 2. Do Apache đã có sẵn trong kho lưu trữ CentOS mặc định nên việc cài đặt khá đơn giản. 

Trước tiên cần cập nhật những thay đổi mới nhất

```
yum -y install epel-release
yum -y update
```

![image](https://user-images.githubusercontent.com/111716161/189017122-efa75b7e-165c-4cee-9be7-629b1552abe5.png)

Để cài đặt Apache hãy chạy lệnh sau:

```
yum install httpd -y
```

![image](https://user-images.githubusercontent.com/111716161/188358417-d00f34e4-f0c2-4e86-b340-94c4373a7411.png)

### 3. Cấu hình firewall (nếu có)

Nếu sử dụng Firewalld để có thể truy cập được website sẽ cần mở cổng (port) bằng các lệnh sau đây:
```
firewall-cmd --permanent --zone=public --add-service=http
firewall-cmd --permanent --zone=public --add-service=https
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/188358800-d3531ad8-f707-4311-8354-d7032b2fff0e.png)

### 4. Tiến hành khởi động Apache bằng cách khởi động lại nó bằng các lệnh sau :

```
systemctl start httpd
systemctl enable httpd
```

![image](https://user-images.githubusercontent.com/111716161/191462192-501e0e1a-acd0-4b04-b751-7966c60f77c6.png)

*Để kiểm tra trạng thái apache chúng ta sử dụng câu lệnh ``systemctl status httpd``*

![image](https://user-images.githubusercontent.com/111716161/188358612-daaa8c7f-f825-4da5-ac68-0aaa89a925b5.png)

Các câu lệnh quản lý apache với systemctl :

- Để dừng apache dùng lệnh : ``systemctl stop httpd``
- Để khởi động apache dùng lệnh : ``systemctl start httpd``
- Lệnh khởi động lại apache: ``systemctl restart httpd``
- Tải lại dịch vụ apache sau khi thay đổi cấu hình : ``systemctl reload httpd``
- Nếu không muốn Apache tự động chạy mỗi khi khởi động lại VPS sử dụng lệnh sau: ``systemctl disable httpd``
- Nếu muốn Apache tự động chạy mỗi khi khởi động lại VPS sử dụng lệnh sau: ``systemctl enable httpd``

Các file cấu hình :

- Tất cả các file cấu hình của Apache đều nằm trong thư mục ``/etc/httpd``.
- File cấu hình chính của Apache là ``/etc/httpd/conf/httpd.conf``.
- Tất cả các tệp cấu hình đều phải kết thúc bằng .conf và nằm trong thư mục ``/etc/httpd/conf.d``.
- Các tệp cấu hình chịu trách nhiệm tải các modules Apache được đặt trong thư mục ``/etc/httpd/conf.modules.d``.
- Để quản lý tốt hơn, nên tạo một tệp cấu hình riêng (vhost) cho mỗi tên miền.
- Các tệp vhost Apache phải kết thúc bằng ``.conf`` và được lưu trữ trong thư mục ``/etc/httpd/conf.d``. Ví dụ: nếu tên miền của bạn là mydomain.com thì tệp cấu hình sẽ được đặt tên ``/etc/httpd/conf.d/mydomain.com.conf``
- Các file log của Apache (access_log và error_log) nằm trong thư mục ``/var/log/httpd/``. Bạn nên có file log riêng cho mỗi vhost.

![image](https://user-images.githubusercontent.com/111716161/191659522-0a7f08f7-82b9-40a8-b3db-71930302a1d6.png)

Như vậy đã hoàn thành cài Apache trên CentOS 7

### 5. Tạo Virtualhost (Vhost)
5.1. Bật userdir bằng lệnh : ``nano /etc/httpd/conf.d/userdir.conf``

![image](https://user-images.githubusercontent.com/111716161/188361388-6f02c2ac-fd81-423d-9432-5ace2705bcf4.png)

5.2. Tại đây cần sửa các rules sau

```
UserDir disabled
#UserDir public_html
```

Sửa lại thành như sau

```
#UserDir disabled
UserDir public_html
```

![image](https://user-images.githubusercontent.com/111716161/189019805-f3b5c0ce-9ef4-4413-adc1-3ad728a667be.png)


Tiếp theo các bạn tìm đoạn rule sau

```
<Directory "/home/*/public_html">
    AllowOverride FileInfo AuthConfig Limit Indexes
    Options MultiViews Indexes SymLinksIfOwnerMatch IncludesNoExec
    Require method GET POST OPTIONS
</Directory>
```

Sửa nó lại thành như sau

```
<Directory "/home/*/public_html">
    AllowOverride All
    Options None
    Require method GET POST OPTIONS
</Directory>
```

![image](https://user-images.githubusercontent.com/111716161/188361964-5dd6d54b-31de-4d38-a0f9-cfe2b3f28e89.png)

Sửa thành

![image](https://user-images.githubusercontent.com/111716161/189020131-f248f572-18ea-42d4-a1f9-a713636c3bc0.png)

5.3. Truy cập file cấu hình Apache

`` nano /etc/httpd/conf/httpd.conf ``

Thêm 2 rules sau phía dưới dòng Listen 80

```
ServerTokens Prod
KeepAlive On
ServerSignature Off
```

5.4 Chặn truy cập IP VPS tự động 

Theo mặc định thì khi truy cập IP của VPS hoặc khi trỏ một tên miền về VPS mà tên miền này không được cấu hình vhost thì bạn sẽ được redirect tới một website bất kỳ trên VPS, điều này là không nên và để hạn chế điều này các bạn mở file /etc/httpd/conf/httpd.conf

`` nano /etc/httpd/conf/httpd.conf ``

Thêm phía trên dòng IncludeOptional conf.d/*.conf rules sau:
   
```
<VirtualHost *:80>
	DocumentRoot /var/www/html
  
	ServerName www.example.com
  
	<Directory "/var/www/html">
  
		AllowOverride All
    
    		Options None
    
    		Require method GET POST OPTIONS
    
	</Directory>
  
</VirtualHost>

```
5.5 Tạo virtual host (vhost) cho website

Virtual Host là file cấu hình trong Apache để cho phép nhiều domain cùng chạy trên một máy chủ. Có một khái niệm khác được đề cập tới trong Nginx cũng có chức năng tương tự như Virtual Host được gọi là Server Block.

Tất cả các file vhost sẽ nằm trong thư mục /etc/httpd/conf.d/. Để tiện quản lý mỗi website nên có một vhost riêng, ví dụ: hostvn.net.conf

Trong ví dụ này sẽ tạo website nganthuong.com với vhost tương ứng là /etc/httpd/conf.d/nganthuong.com.conf

`nano /etc/httpd/conf.d/nganthuong.com.conf`

Dán nội dung sau vào
```
<VirtualHost *:80>
	ServerName nganthuong.com
	ServerAlias www.nganthuong.com
	DocumentRoot /home/nganthuong.com/public_html
	ErrorLog /home/nganthuong.com/logs/error.log
	CustomLog /home/nganthuong.com/logs/access.log combined
</VirtualHost>
```
Tiếp theo các bạn cần tạo thư mục chứa mã nguồn website và thư mục chứa file log bằng các lệnh sau:

`mkdir -p /home/nganthuong.com/public_html`

`mkdir -p /home/nganthuong.com/logs`

`chown -R apache:apache /home/nganthuong.com`

Reload lại Apache để cập nhật cấu hình

`systemctl reload httpd`

Sau khi cấu hình hoàn tất các bạn trỏ tên miền về vps

` nano /etc/hosts`

![image](https://user-images.githubusercontent.com/111716161/189029848-537702bb-ba7e-453b-a510-1d2b83fcdf77.png)

sau đó tạo file /home/hostvn.net/public_html/index.html

`nano /home/nganthuong.com/public_html/index.html`

Dán nội dung sau vào
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>NGANTHUONG.COM - Hướng dẫn cài đặt Apache trên CentOS 7</title>
</head>
<body>
	<p><center> Hello World</center></p>
</body>
</html>
```
Chạy website: 

![image](https://user-images.githubusercontent.com/111716161/189029899-125353e9-f36f-4641-8f5a-b8cd190f15bf.png)
