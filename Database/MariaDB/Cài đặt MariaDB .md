[Cài đặt MariaDB](#caidat)

[Cấu hình MariaDB](#cauhinh)

[Gỡ cài đặt MariaDB](#go)

<a name="caidat"></a>
# Cài đặt MariaDB trên CentOS 7

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

![image](https://user-images.githubusercontent.com/111716161/190969958-412d3f6a-2b1c-49b5-83c1-27e23b2509fe.png)

***Lưu ý:*** *Tại thời điểm này phiên bản MariaDB 10 mới nhất là 10.10. Trước khi tạo repo bạn có thể truy cập http://yum.mariadb.org để kiểm tra phiên bản.*

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

- Sau khi tạo file repo các bạn tiến hành cài đặt MariaDB bằng lệnh sau:

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

MariaDB active và chạy thành công, như vậy ta đã cài đặt và khởi động được MariaDB trên CentOS 7.

<a name="cauhinh"></a>
# Cấu hình MariaDB

## 1. Đặt mật khẩu root

- Chạy lệnh dưới đây:

```
mariadb-secure-installation
```

- Khi được nhắc nhập mật khẩu, ta có thể nhấn Enter để trống hoặc cập nhật mật khẩu mới.

![image](https://user-images.githubusercontent.com/111716161/190971327-a2fcc1b5-0203-4e0c-b712-6580835b81df.png)

Làm các bước để thiết lập mật khẩu. 

![image](https://user-images.githubusercontent.com/111716161/190971573-7f7a31fd-9f1d-4fa0-9f67-20005a5fa75a.png)

Cuối cùng, tập lệnh sẽ yêu cầu định cấu hình một số biện pháp bảo mật, bao gồm:
```
Xóa người dùng ẩn danh?
Không cho phép đăng nhập từ xa?
Xóa cơ sở dữ liệu thử nghiệm và truy cập vào nó?
Tải lại bảng đặc quyền ngay bây giờ
```

![image](https://user-images.githubusercontent.com/111716161/190971849-289288db-8bb8-4439-9916-89da753c023f.png)

![image](https://user-images.githubusercontent.com/111716161/190972187-f43282ce-ab50-46eb-8896-107c78270675.png)

## 2. Kiểm tra phiên bản MariaDB hiện hành

```
mariadb -u root -p
```

![image](https://user-images.githubusercontent.com/111716161/190972586-9083f972-2546-4fe2-9fcf-42c0e292827c.png)

## 3. Đặt lại mật khẩu MariaDB

- Dừng MariaDB

```
systemctl stop mariadb
```

- Cài đặt tùy chọn môi trường 

```
sudo systemctl set-environment MYSQLD_OPTS="--skip-grant-tables"
```

<a name="go"></a>
# Gỡ cài đặt MariaDB trên CentOS 7

