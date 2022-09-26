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

### Bước 2: 

Kiểm tra và tắt postfix

Postfix là một phầm mềm nguồn mở được dùng để gửi mail (Mail Transfer Agent-MTA). Được phát hành bởi IBM với mục tiêu thay thế trình gửi mail phổ biến là sendmail.

- Kiểm tra trạng thái của postfix:

```
systemctl status postfix
```

- Tắt dịch vụ postfix:

```
systemctl disable postfix
```

- Dừng dịch vụ postfix:

```
systemctl stop postfix
```

### Bước 3: 

Cài đặt Kerio Connect

- Cài đặt bằng lệnh sau: 

```
sudo yum install kerio-connect-9.2.10-4692-linux-x86_64.rpm
```

- Kiểm tra trạng thái của dịch vụ Kerio:

```
systemctl status kerio-connect
```

### Bước 4: Cấu hình firewalld

Nếu sử dụng Firewalld để có thể truy cập được website sẽ cần mở cổng (port) bằng các lệnh sau đây:

```
firewall-cmd --permanent --zone=public --add-service=http
firewall-cmd --permanent --zone=public --add-service=https
firewall-cmd --reload
```

### Bước 5: 

Mở URL `https://your_CentOS_IP:4040/admin`
