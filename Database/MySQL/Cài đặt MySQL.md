[Cài đặt MySQL](#caidat)

[Cấu hình MySQL)(#cauhinh)

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

Như vậy ta đã thay đổi mật khẩu MySQL root user thành công. 
