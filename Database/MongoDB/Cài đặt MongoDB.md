![image](https://user-images.githubusercontent.com/111716161/190548475-104b22c9-e767-477b-8366-d811a2dc5bf2.png)

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

