<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/190548475-104b22c9-e767-477b-8366-d811a2dc5bf2.png" width="600"/>
</p>

## 1. Tạo MongoDB repository

Để thêm kho lưu trữ MongoDB vào hệ thống, cần tạp file `mongodb-org.repo` trong thư mục /etc/yum.repos.d/:

```
nano /etc/yum.repos.d/mongodb-org.repo
```

Dán nội dung sau vào:

```
[mongodb-org-4.2]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.2.asc
```

## 2. Cài đặt MongoDB

Bước 1: Bây giờ kho lưu trữ đã được thêm, ta tiến hành cài đặt gói mongodb-org.

```
yum install mongodb-org -y
```

Các gói sau sẽ được cài đặt trên hệ thống của bạn như là một phần của gói mongodb-org:

- `mongodb-org-server` – Trình nền mongod, và các tập lệnh và cấu hình init tương ứng.
- `mongodb-org-mongos` – Daemon mongos.
- `mongodb-org-shell` – Shell mongo, giao diện JavaScript tương tác với MongoDB, được sử dụng để thực hiện các tác vụ quản trị dòng lệnh.
- `mongodb-org-tools` – Chứa một số công cụ MongoDB để nhập và xuất dữ liệu, số liệu thống kê, cũng như các tiện ích khác.

Bước 2: Khởi động MongoDB

Sau khi cài đặt hoàn tất, khởi động MongoDB

```
systemctl start mongod
systemctl enable mongod
```

Bước 3: Xác minh cài đặt 

```
mongo
```

Hiển thị phiên bản MongoDB

```
db.version()
```

Như vậy ta đã cài đặt xong MongoDB trên CentOS 7.

## 3. Cấu hình MongoDB

Thiết lập cấu hình MongoDB bằng cách chỉnh sửa tệp cấu hình /etc/mongod.conf.

Các thiết lập cấu hình mặc định khá đầy đủ trong hầu hết các trường hợp. Để tìm thêm thông tin về các tùy chọn cấu hình có sẵn trong MongoDB, truy cập: mongodb.com/docs/manual/reference/configuration-options/

