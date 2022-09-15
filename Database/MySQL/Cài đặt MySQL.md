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

### 2. Cài đặt MySQL

Bước 1: Cài đặt MySQL bằng dòng lệnh yum install:

```
sudo yum install mysql-server
```

![image](https://user-images.githubusercontent.com/111716161/190305498-a3747c0c-0d3c-485c-97eb-63bbf7f9ae1d.png)

Bước 2: Danh sách file cài sẽ được đưa ra và cần xác nhận để tải chúng. Gõ Y rồi nhấn ENTER. Sau khi tải file xong, 
