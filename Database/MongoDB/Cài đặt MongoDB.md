<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/190937247-23f326fd-0703-42c8-a0db-aa857c66bc95.png" width="600"/>
</p>

## 1. Tạo MongoDB repository

Để thêm kho lưu trữ MongoDB vào hệ thống, cần tập file `mongodb-org.repo` trong thư mục /etc/yum.repos.d/:

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

![image](https://user-images.githubusercontent.com/111716161/190556034-fdd9bf16-809a-425f-b35d-aac5a445442a.png)

## 2. Cài đặt MongoDB

Bước 1: Bây giờ kho lưu trữ đã được thêm, ta tiến hành cài đặt gói mongodb-org.

```
yum install mongodb-org -y
```

![image](https://user-images.githubusercontent.com/111716161/190556164-174cd14a-d94b-4b25-87ea-0253bd39a4da.png)

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

![image](https://user-images.githubusercontent.com/111716161/190556237-2920fb12-e5ab-4b56-9b75-cb5ee99e2c3f.png)

Bước 3: Xác minh cài đặt 

```
mongo
```

![image](https://user-images.githubusercontent.com/111716161/190556308-c11c883b-8885-4313-ad25-5cde99865f06.png)

Hiển thị phiên bản MongoDB

```
db.version()
```

![image](https://user-images.githubusercontent.com/111716161/190556338-89b587d4-31dd-4ca7-be2f-ccb3d1499275.png)

Như vậy ta đã cài đặt xong MongoDB trên CentOS 7.

## 3. Cấu hình MongoDB

Thiết lập cấu hình MongoDB bằng cách chỉnh sửa tệp cấu hình /etc/mongod.conf.

Các thiết lập cấu hình mặc định khá đầy đủ trong hầu hết các trường hợp. Để tìm thêm thông tin về các tùy chọn cấu hình có sẵn trong MongoDB, truy cập: https://www.mongodb.com/docs/manual/reference/configuration-options/

Sau khi thay đổi tệp cấu hình, khởi động lại dịch vụ mongod:

```
systemctl restart mongod
```

## 4. Tạo user Admin

Tạo một người dùng MongoDB sử dụng để truy cập và quản lý MongoDB của mình.

- Bắt đầu với mongodb

```
mongo
```

- Kết nối với cơ sở dữ liệu quản trị viên

```
use admin
```

![image](https://user-images.githubusercontent.com/111716161/190556436-e2048caf-b34f-4959-9224-5738363f9d43.png)

- Tạo người dùng mới với vai trò userAdminAnyDatabase

```
db.createUser( { user: "Username", pwd: "Mật-khẩu", roles: [{role: "userAdminAnyDatabase", db: "admin"}]})
```

![image](https://user-images.githubusercontent.com/111716161/190556877-93f3b402-8754-4b3e-84e3-d31886037b23.png)

- Thoát khỏi mongo

```
quit()
```

- Kiểm tra các thay đổi, truy cập shell mongo bằng người dùng quản trị đã tạo:

```
mongo -u username -p --authenticationDatabase admin
```

![image](https://user-images.githubusercontent.com/111716161/190556991-058eebb1-6c7f-4bd6-b1c9-002421117005.png)

- In người dùng bằng lệnh: 

```
use admin
show users
```

![image](https://user-images.githubusercontent.com/111716161/190557065-85fc43bf-ad6b-41bb-a7b0-d91287636816.png)



