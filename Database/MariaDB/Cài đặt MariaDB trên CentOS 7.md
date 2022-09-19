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

- Sau khi tạo file repo các bạn tiến hành cài đặt MariaDB bằng lệnh sau

```
yum install MariaDB-server MariaDB-client
```

![image](https://user-images.githubusercontent.com/111716161/190968959-225e5c28-6ee3-46ab-9f05-52bea45d2bcc.png)

- Kiểm tra các gói cài đặt MariaDB

```
yum list installed | grep mariadb
```

![image](https://user-images.githubusercontent.com/111716161/190969835-626c9d46-e758-48f9-bbed-11b313ea67ef.png)

## 3. Khởi động MariaDB

- MariaDB chưa được khởi động sau khi cài đặt nên cần gõ lệnh sau:

```
systemctl start mariadb
systemctl enable mariadb
```
![image](https://user-images.githubusercontent.com/111716161/190969562-2ae26324-a79d-4936-bf95-d98e96a61a81.png)

- Kiểm tra tình trạng MariaDB sau khi khởi động:

```
systemctl status mariadb
```

![image](https://user-images.githubusercontent.com/111716161/190969675-4972eef8-8e06-46a1-90fc-b3eba1ee7e71.png)



