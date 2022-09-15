### 1. Tải và chuẩn bị MySQL repository

Bước 1: Kiểm tra hệ thống có được cập nhật chưa và cập nhật nếu cần. Gõ lệnh sau:

```
sudo yum update
```

Bước 2: Đợi hệ thống cập nhật, sau đó cài đặt MySQL repositories. 

Xem các phiên bản cập nhật tại đây: https://dev.mysql.com/downloads/repo/yum/

```
wget http://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm
```

Bước 3: Sau khi tải xong, file .rpm đã được lưu lại. Bây giờ có thể prepare repository rồi cài đặt MySQL packages từ nó.

```
sudo rpm -Uvh mysql57-community-release-el7-9.noarch.rpm
```

