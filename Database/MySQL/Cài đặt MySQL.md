[Cài đặt MySQL](#caidat)

[Cấu hình MySQL](#cauhinh)

[Gỡ MySQL](#go)

<a name="caidat"></a>
# Cài đặt MySQL

### 1. Tải và chuẩn bị MySQL repository

Bước 1: Kiểm tra hệ thống có được cập nhật chưa và cập nhật nếu cần. Gõ lệnh sau:

```
sudo yum update
```

![image](https://user-images.githubusercontent.com/111716161/190305052-5b5a345b-8373-4a2f-b3c0-55fc9fcaebe9.png)

Bước 2: Đợi hệ thống cập nhật, sau đó cài đặt MySQL repositories. 

Xem các phiên bản cập nhật tại đây: https://dev.mysql.com/downloads/repo/yum/

```
wget http://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm
```

![image](https://user-images.githubusercontent.com/111716161/190305141-91fd9651-92fa-43dc-b6ab-3389eb31e0ce.png)

Bước 3: Sau khi tải xong, file .rpm đã được lưu lại. Bây giờ có thể prepare repository rồi cài đặt MySQL packages từ nó.

```
sudo rpm -Uvh mysql57-community-release-el7-9.noarch.rpm
```

![image](https://user-images.githubusercontent.com/111716161/190305229-7689acc6-3724-47f3-b9bf-33e0058e3269.png)

Bước 4: Các khóa GPG cho bản phát hành mới đã được thay đổi, cần nhập khóa trước khi chạy trình cài đặt.

```
rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2022
```

### 2. Cài đặt MySQL

Bước 1: Cài đặt MySQL bằng dòng lệnh yum install:

```
sudo yum install mysql-server
```

![image](https://user-images.githubusercontent.com/111716161/190305498-a3747c0c-0d3c-485c-97eb-63bbf7f9ae1d.png)

Bước 2: Danh sách file cài sẽ được đưa ra và cần xác nhận để tải chúng. Gõ Y rồi nhấn ENTER. Sau khi tải file xong cần nhấn Y để cài đặt. Kết quả Complete! ở cuối trang nghĩa là MySQL đã được cài đặt thành công. 

![image](https://user-images.githubusercontent.com/111716161/190308070-5ba52174-5fba-46dc-a69e-fae1f4a80ac1.png)

### 3. Khởi động MySQL 

Bước 1: MySQL chưa được khởi động sau khi cài đặt nên cần gõ lệnh sau:

```
sudo systemctl start mysqld
```

Bước 2: Kiểm tra tình trạng MySQL sau khi khởi động

```
sudo systemctl status mysqld
```

![image](https://user-images.githubusercontent.com/111716161/190308798-7caaa17a-6026-4a93-8c9a-d6c27212006f.png)

MySQL active và chạy thành công, như vậy ta đã cài đạt và khởi động được MySQL trên CentOS 7.

<a name="cauhinh"></a>

# Cấu hình MySQL

### 1. Đổi mật khẩu MySQL root user

Khi cài MySQL CentOS 7, một mật khẩu tạm cho root được tạo ra. Để xem mật khẩu, gõ lệnh:

```
sudo grep 'password' /var/log/mysqld.log
```

![image](https://user-images.githubusercontent.com/111716161/190309405-e0208358-e767-4c8c-aac1-a2eeb76ee066.png)

Để thay đổi mật khẩu root, làm theo các bước sau:

Bước 1: Chạy lệnh

```
sudo mysql_secure_installation
```

Bước 2: Nhập mật khẩu tạm và điền mật khẩu tạm.

Bước 3: Nhập mật khẩu mới, chú ý các chính sách mật khẩu. 

(Abcd.1234)

![image](https://user-images.githubusercontent.com/111716161/190310085-0b926337-933a-475b-88b8-ad2d7e88e24b.png)

Bước 4: Nhấn Y sau đó Enter để hoàn tất.

![image](https://user-images.githubusercontent.com/111716161/190310612-3d3aa6bb-5871-4586-8f44-b181578acaf3.png)

![image](https://user-images.githubusercontent.com/111716161/190310646-232b1461-6005-4cbe-81aa-2f9f8575f078.png)

![image](https://user-images.githubusercontent.com/111716161/190310687-cf1b3cd1-6563-4aca-a0e2-f29be4eb50dc.png)

Như vậy ta đã thay đổi mật khẩu MySQL root user thành công. 

### 2. Kiểm tra phiên bản MySQL hiện hành

```
mysql -u root -p
```

![image](https://user-images.githubusercontent.com/111716161/190310871-3dfd2072-6609-4f6a-af5f-372a161dfd41.png)

### 3. Đặt lại MySQL Root Password

Trong trường hợp quên mật khẩu và muốn reset password, ta thực hiện các bước sau:

Bước 1: Dừng MySQL server

```
sudo systemctl stop mysqld
```

Bước 2: Cài đặt tùy chọn môi trường MySQL

```
sudo systemctl set-environment MYSQLD_OPTS="--skip-grant-tables"
```

Bước 3: Khởi động MySQL sử dụng các tùy chọn vừa cài đặt

```
sudo systemctl start mysqld
```

Bước 4: Đăng nhập với root

```
mysql -u root
```

![image](https://user-images.githubusercontent.com/111716161/190318241-592073c3-a7b5-4a27-a892-300f29e60da0.png)

Bước 5: Cập nhật mật khẩu người dùng root bằng các lệnh MySQL

```
mysql> UPDATE mysql.user SET authentication_string = PASSWORD('NewPassword')
    -> WHERE User = 'root' AND Host = 'localhost';
mysql> FLUSH PRIVILEGES;
mysql> quit
```

![image](https://user-images.githubusercontent.com/111716161/190332320-2e9cbb99-3fda-41f7-bfbe-b995a29e69a4.png)

Bước 6: Dừng MySQL

```
sudo systemctl stop mysqld
```

Bước 7: Bỏ cài đặt tùy chọn môi trường MySQL để nó khởi động bình thường vào lần sau

```
sudo systemctl unset-environment MYSQLD_OPTS
```

Bước 8: Khởi động MySQL bình thường

```
sudo systemctl start mysqld
```

Bước 9: Đăng nhập bằng mật khẩu mới

```
mysql -u root -p
```

![image](https://user-images.githubusercontent.com/111716161/190332495-a12d0dc6-a3c1-4586-b5d6-6e86faf6d1b5.png)

Như vậy ta đã reset password cho MySQL root user thành công. 

<a name="go"></a>
# Gỡ MySQL khỏi CentOS 7

Bước 1: Gỡ tất cả các phụ thuộc của MySQL

```
yum list installed | grep mysql
```

![image](https://user-images.githubusercontent.com/111716161/190600269-00a71e8a-f435-4be0-a5b2-172270d3f9e8.png)

- Để loại bỏ một gói, cần cài đặt plugin yum:

```
yum install yum-plugin-remove-with-leaves
```

![image](https://user-images.githubusercontent.com/111716161/190600633-06f3dfcd-2761-4ca5-9e66-18a260801167.png)

- Để loại bỏ một gói với các phụ thuộc của nó: 
```
yum remove mysql-server --remove-leaves
```

![image](https://user-images.githubusercontent.com/111716161/190600951-882682b5-4d4f-46f4-9e06-f34b0e1e5377.png)

- Gỡ cài đặt repo mysql-community-release

```
yum remove mysql57-community-release-el7-9
```

![image](https://user-images.githubusercontent.com/111716161/190601412-856085fa-cdf7-4ee9-ae70-c945ecdb51aa.png)

Bước 2: Xóa thư mục MySQL

```
rm -rf /var/lib/mysql/
rm -rf /etc/my.cnf
```

![image](https://user-images.githubusercontent.com/111716161/190601630-6bbe92b0-8da7-4c2b-9449-41d82b887e50.png)

Bước 3: Kiểm tra xem MySQL đã bị gỡ hay chưa

![image](https://user-images.githubusercontent.com/111716161/190602928-7c0458eb-4025-47ac-89d2-743aa435033a.png)
