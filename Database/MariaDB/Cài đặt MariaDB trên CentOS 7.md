## 1. Tạo file repo

- Theo mặc định repo của CentOS chỉ có sẵn MariaDB 5. Để cài đặt MariaDB 10 các bạn cần tạo repo riêng.

```
nano /etc/yum.repos.d/mariadb.repo
```

Dán nội dung dưới đây vào

```
[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/10.10/rhel7-amd64/
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
```

![image](https://user-images.githubusercontent.com/111716161/190965075-01ae97ae-c522-471a-b38a-081490a8da11.png)

***Lưu ý:*** *Tại thời điểm này phiên bản MariaDB 10 mới nhất là 10.10. Trước khi tạo repo các bạn có thể truy cập http://yum.mariadb.org để kiểm tra phiên bản.*

- Xóa cache của yum:

```
yum clean all
```
![image](https://user-images.githubusercontent.com/111716161/190965601-17bb6d5e-c4eb-46f8-bc1f-7971e67b3482.png)

- Cập nhật các gói mới nhất

```
yum update
```

![image](https://user-images.githubusercontent.com/111716161/190965980-92c20400-15ef-4b4d-94aa-12076522ecc4.png)

![image](https://user-images.githubusercontent.com/111716161/190966283-5ed31d81-1dce-4739-aa22-ae9bf65b1bfb.png)

## 2. Cài đặt MariaDB

Sau khi tạo file repo các bạn tiến hành cài đặt MariaDB bằng lệnh sau

```
yum install MariaDB-server MariaDB-client -y
```

