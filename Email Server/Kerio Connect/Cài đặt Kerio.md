# Cài đặt DNS

Bước 1: Cài đặt gói bind vào máy

```
yum install bind bind-utils –y
```

![image](https://user-images.githubusercontent.com/111716161/192222273-d5bc3350-71a5-4d54-9bfb-bbc736369a1c.png)

Bước 2: Chỉnh sửa file `/etc/named.conf`

```
nano /etc/named.conf
```

Thêm các dòng như hình:

![image](https://user-images.githubusercontent.com/111716161/192223171-d555663a-237d-4282-b1e3-b1d058b4e160.png)

![image](https://user-images.githubusercontent.com/111716161/192223717-52d664be-3def-4d75-a952-1ead18b15f6e.png)

![image](https://user-images.githubusercontent.com/111716161/192224653-57453625-05d4-41c3-a12a-07a68c142aa3.png)

Bước 3: Tạo Zone file

- Tạo file forward

```
nano /var/named/forward.nganthuong
```

Thêm nội dung sau:

```
$TTL 86400

@   IN  SOA     masterdns.nganthuong.com. root.nganthuong.com. (

2011071001  ;Serial

3600        ;Refresh

1800        ;Retry

604800      ;Expire

86400       ;Minimum TTL

)

@       IN  NS          masterdns.nganthuong.com.

@       IN  A           192.168.30.144

masterdns       IN  A   192.168.30.144
```

![image](https://user-images.githubusercontent.com/111716161/192226335-724a482d-6a8d-402b-9790-f2a133d32c9c.png)

- Tạo file reverse:

```
nano /var/named/reverse.nganthuong
```

Thêm nội dung sau:

```
$TTL 86400

@   IN  SOA     masterdns.nganthuong.com. root.nganthuong.com. (

2011071001  ;Serial

3600        ;Refresh

1800        ;Retry

604800      ;Expire

86400       ;Minimum TTL

)

@       IN  NS          masterdns.nganthuong.com.

masterdns       IN  A   192.168.30.144

1     IN  PTR         masterdns.nganthuong.com.
```

![image](https://user-images.githubusercontent.com/111716161/192227370-e0765bb9-dd97-4afd-80a2-9486859cb9e2.png)

Bước 4: Khởi chạy dịch vụ DNS Server :

```
systemctl enable named

systemctl start named
```

![image](https://user-images.githubusercontent.com/111716161/192227571-f67dd542-9777-416d-99df-0fdf59a1f4f5.png)

Bước 5: Cấu hình Firewall :

- Mở Port 53 trên Firewall để dịch vụ DNS có thể được thông qua :

```
firewall-cmd --permanent --add-port=53/tcp

firewall-cmd --permanent --add-port=53/udp
```

![image](https://user-images.githubusercontent.com/111716161/192227855-dbf43b7c-9dad-4bf1-8cb8-7f1a6b3bf3ac.png)

- Restart lại Firewall để thay đổi có hiệu lực :

```
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/192227908-c2a5226d-1a39-4daa-b045-c95dc17e4084.png)

Bước 6: Cấu hình SELinux, Permissions, Ownership 

Chạy từng dòng lệnh dưới đây:

```
chgrp named -R /var/named

chown -v root:named /etc/named.conf

restorecon -rv /var/named

restorecon /etc/named.conf
```

Bước 7: Kiểm tra

- Chạy dòng lệnh để check DNS Server :

```
named-checkconf /etc/named.conf
```

Nếu dòng lệnh không có gì trả về, tức là bạn đã cấu hình đúng.

![image](https://user-images.githubusercontent.com/111716161/192228400-5a04b44a-bd79-4a5f-bbae-f70d484b1d74.png)








### Bước 1: 

Kiểm tra trạng thái Selinux và cập nhật hệ thống

- Tắt Selinux:

```
sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config && setenforce 0
```

![image](https://user-images.githubusercontent.com/111716161/192210104-75c1342c-bf3a-4822-8c5f-f02622f126dd.png)

- Cập nhật những thay đổi mới nhất:

```
yum -y update
```

![image](https://user-images.githubusercontent.com/111716161/192212508-bf607b8f-8f46-40bb-bb9d-d6c0e64b2c2d.png)

### Bước 2: 

Gỡ cài đặt postfix

Postfix là một phầm mềm nguồn mở được dùng để gửi mail (Mail Transfer Agent-MTA). Được phát hành bởi IBM với mục tiêu thay thế trình gửi mail phổ biến là sendmail.

- Kiểm tra trạng thái của postfix:

```
systemctl status postfix
```

![image](https://user-images.githubusercontent.com/111716161/192212568-5b76c5ff-78f6-4146-b67a-cb5dee27bb04.png)

- Dừng dịch vụ postfix:

```
systemctl stop postfix
```

![image](https://user-images.githubusercontent.com/111716161/192213133-13e0508c-a062-479d-adc2-789d0a3ddf1a.png)

- Gỡ cài đặt postfix:

```
yum remove postfix -y
```

![image](https://user-images.githubusercontent.com/111716161/192213076-500e9148-4fda-4fb6-b4fa-4b3b29ed7cd5.png)

- Reboot lại máy: 

```
reboot
```

### Bước 3: 

Cài đặt Kerio Connect

- Tải file rpm Kerio Connect:

```
wget http://cdn.kerio.com/dwn/connect/connect-9.2.9-4540/kerio-connect-9.2.9-4540-p1-linux-x86_64.rpm
```

![image](https://user-images.githubusercontent.com/111716161/192214081-7451b7f4-b873-41ea-abed-4615c3949573.png)

- Cài đặt Kerio:

```
rpm -i kerio-connect-9.2.9-4540-p1-linux-x86_64.rpm
```

![image](https://user-images.githubusercontent.com/111716161/192214226-ad1a97d4-c7cd-402d-902c-3cc58316fa61.png)

- Kiểm tra trạng thái của dịch vụ Kerio:

```
systemctl status kerio-connect
```

![image](https://user-images.githubusercontent.com/111716161/192214283-86932370-b913-4bd4-b68d-043ff819e9bb.png)

### Bước 4: Cấu hình firewalld

Nếu sử dụng Firewalld để có thể truy cập được website sẽ cần mở cổng (port) bằng các lệnh sau đây:

```
firewall-cmd --permanent --zone=public --add-service=http
firewall-cmd --permanent --zone=public --add-service=https
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/192214411-e0ba1746-1ab2-46d9-985e-e9bc2dc6940d.png)

### Bước 5: 

Đăng nhập Email Server trên trình duyệt:

- Truy cập: 

```
https://IP-VPS:4040
```

![image](https://user-images.githubusercontent.com/111716161/192214884-04fee67e-ccf4-4a69-abc1-4d5cdd999f51.png)

- Chọn Next, sau đó chọn I accept the terms in the License Agreement. Chọn Next. 

![image](https://user-images.githubusercontent.com/111716161/192215077-fcc2b0d5-2b12-4312-b2a3-0d1339ba6149.png)

- Nhập Internet hostname và Email domain.

![image](https://user-images.githubusercontent.com/111716161/192216678-43edaa08-c01f-4376-9071-78941a1ed786.png)


