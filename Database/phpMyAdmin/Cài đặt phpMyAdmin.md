[Cài đặt PHP](#php)

[Cài đặt phpMyAdmin](#phpmyadmin)

<a name="php"></a>
# Cài đặt PHP 7.3

### Bước 1: 
Cài đặt máy chủ Web Apache

### Bước 2: 
Cài đặt Remi Repository

```
yum -y install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
```

![image](https://user-images.githubusercontent.com/111716161/191648602-ba95806b-b6c2-4bc7-82f4-b64ba25753b7.png)

### Bước 3: 
Cài đặt yum-utils và kích hoạt kho lưu trữ EPEL repository

```
yum -y install epel-release yum-utils
```

![image](https://user-images.githubusercontent.com/111716161/191648729-1837c70c-0784-441f-9f56-330dfc8eddd0.png)

### Bước 4: 
- Disable php 5.4 

```
yum-config-manager --disable remi-php54 
```

![image](https://user-images.githubusercontent.com/111716161/191648900-121941bb-865e-4798-b394-4f341d37b1d7.png)

- Enable php 7.3

```
yum-config-manager --enable remi-php73
```

![image](https://user-images.githubusercontent.com/111716161/191649020-eba201be-bb77-4c06-a63f-c38a52603c77.png)

### Bước 5:
Cài đặt php 7.3

```
yum -y install php php-cli php-mysqlnd php-zip php-devel php-gd php-mcrypt php-mbstring php-curl php-xml php-pear php-bcmath php-json
```

![image](https://user-images.githubusercontent.com/111716161/191649251-951c57a9-7274-4736-9880-a86839d3ad6b.png)

### Bước 6:
Sau khi cài đặt thành công có thể kiểm tra phiên bản php bằng lệnh:

```
php -v
```

![image](https://user-images.githubusercontent.com/111716161/191649369-72128c43-9229-4c52-9d51-5df9d5254d0e.png)

### Bước 7:
Khởi động lại Apache

```
systemctl restart httpd
```

### Bước 8: 
Tạo file info.php tại thư mục `/var/www/html`

```
nano /var/www/html/info.php
```

Thêm nội dung sau:

```
<?php
phpinfo();
?>
```

### Bước 9: Truy cập đường dẫn `http://IP-VPS/info.php`

![image](https://user-images.githubusercontent.com/111716161/191649960-47ec414f-6dd3-4638-a17e-f91b08198cf0.png)

<a name="phpmyadmin"></a>
# Cài đặt phpMyAdmin

### Bước 1:
Kiểm tra trạng thái của Apache

![image](https://user-images.githubusercontent.com/111716161/191640990-f76e194e-5040-4192-a553-1498310cb152.png)

### Bước 2: 
Cài đặt phpMyAdmin

```
sudo yum install phpmyadmin
```

![image](https://user-images.githubusercontent.com/111716161/191650293-c7f93c8b-1252-449c-b078-deb90754f1c2.png)

### Bước 3:
Cấu hình tệp phpMyAdmin.conf

```
nano /etc/httpd/conf.d/phpMyAdmin.conf
```

Thêm các dòng `Require all granted` để cho phép mọi máy có thể vào phpMyAdmin

![image](https://user-images.githubusercontent.com/111716161/191650469-e5f207d8-417b-45c4-a381-76afab892c48.png)

![image](https://user-images.githubusercontent.com/111716161/191650550-7bb631ee-1388-4e77-af08-7682e12ea89b.png)

### Bước 4: 
Khởi động lại máy chủ Web Apache

```
systemctl restart httpd
```

![image](https://user-images.githubusercontent.com/111716161/191638464-cebbe8ce-6380-4291-a482-72f1ab92245b.png)

### Bước 5:
Kiểm tra xem phpMyAdmin có hoạt động hay không.

Mở tiện ích phpMyAdmin bằng cách nhập địa chỉ IP máy chủ vào thanh địa chỉ của trình duyệt bằng thêm chuỗi bổ sung /phpmyadmin. 

`http://IP-VPS/phpmyadmin`

Màn hình đăng nhập hiển thị.

![image](https://user-images.githubusercontent.com/111716161/191650709-e490cc72-274c-451f-94a1-f7c13e350487.png)

### Bước 6: 
Xác định tên người dùng và mật khẩu

Tên người dùng và mật khẩu sẽ nằm trong tệp config.inc.php. Tệp sẽ nằm trong thư mục phpMyAdmin installation. 

Mở tệp:

```
cd /etc/phpMyAdmin
nano config.inc.php
```

Đặt tên người dùng và mật khẩu.

![image](https://user-images.githubusercontent.com/111716161/191651728-08b053a1-6aa4-45de-8e4d-566c20066744.png)

