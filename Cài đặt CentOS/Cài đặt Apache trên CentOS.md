### 1. Truy cập Teminal CentOS 7 với quyền root với câu lệnh
```
sudo -i
```
![image](https://user-images.githubusercontent.com/111716161/188358270-ca6f7bc9-2a10-4148-916b-8bbfc22feac3.png)

### 2. Do Apache đã có sẵn trong kho lưu trữ CentOS mặc định nên việc cài đặt khá đơn giản. Để cài đặt Apache hãy chạy lệnh sau:

```
yum install httpd -y
```

![image](https://user-images.githubusercontent.com/111716161/188358417-d00f34e4-f0c2-4e86-b340-94c4373a7411.png)

### 3. Sau khi cài đặt hoàn tất, tiến hành khởi động Apache bằng cách khởi động lại nó bằng các lệnh sau :
```
systemctl enable httpd
systemctl start httpd
```

![image](https://user-images.githubusercontent.com/111716161/188358524-4ebccdd3-ea77-40d7-a566-6772c2d55139.png)

*Để kiểm tra trạng thái apache chúng ta sử dụng câu lệnh ``systemctl status httpd``*

![image](https://user-images.githubusercontent.com/111716161/188358612-daaa8c7f-f825-4da5-ac68-0aaa89a925b5.png)

### 4. Cấu hình firewall (nếu có)

Nếu các bạn sử dụng Firewall để có thể truy cập được website các bạn sẽ cần mở port bằng các lệnh sau đây:
```
firewall-cmd --permanent --zone=public --add-service=http
firewall-cmd --permanent --zone=public --add-service=https
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/188358800-d3531ad8-f707-4311-8354-d7032b2fff0e.png)

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

### 5. Tạo Virtualhost (Vhost)
5.1. Bật userdir bằng lệnh : ``nano /etc/httpd/conf.d/userdir.conf``

![image](https://user-images.githubusercontent.com/111716161/188361388-6f02c2ac-fd81-423d-9432-5ace2705bcf4.png)

5.2. Tại đây, chúng ta cần sửa bằng cách nhập ``UserDir public_html``

![image](https://user-images.githubusercontent.com/111716161/188361703-3a9b1212-897c-496f-a8f0-ef3135bf7227.png)

5.3. Tiếp theo tìm đoạn rule

![image](https://user-images.githubusercontent.com/111716161/188361964-5dd6d54b-31de-4d38-a0f9-cfe2b3f28e89.png)

Sửa thành

![image](https://user-images.githubusercontent.com/111716161/188363102-15dc4306-4dd0-456c-8cf6-051732129f75.png)

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
Screenshot_113
```
**Vì CentOS là mã nguồn mở, nên Apache có sẵn trong kho lưu trữ, trước tiên cần cập nhật httpd package index để cập nhật những thay đổi mới nhất**

Sử dụng lệnh `sudo yum update httpd`
    
![image](https://user-images.githubusercontent.com/111716161/188391364-45725d7f-c70c-46b7-9c73-2ef9e0c89911.png)

Sau đó thực hiện gói cài đặt phần mềm `sudo yum install httpd`

![image](https://user-images.githubusercontent.com/111716161/188393990-bb0b2250-d88e-4c9c-b060-031bf652efa8.png)

Tiếp theo cài đặt tường lửa "Firewall" trên server và mở cổng port 80 để phục vụ cho nhu cầu qua http `sudo firewall-cmd --permanent --add-service=http`

![image](https://user-images.githubusercontent.com/111716161/188394117-382673b9-8e09-417f-bad4-60a3031412fd.png)

Để cấu hình Apache web theo giao thức https, cổng 443:

![image](https://user-images.githubusercontent.com/111716161/188394236-fee33179-8918-4dcb-b996-c3cf5be3ce7d.png)

Như vậy đã hoàn thành cài Apache trên CentOS 7
