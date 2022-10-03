# Cài đặt máy chủ FTP với VSFTPD

### Bước 1: Cập nhật trình quản lý gói

```
yum update -y
```

### Bước 2: Cài đặt phần mềm VSFTPD

```
yum install vsftpd
```

![image](https://user-images.githubusercontent.com/111716161/193546082-166e3932-bc31-448c-8a00-63e0071ccee9.png)

### Bước 3: Bắt đầu dịch vụ, thiết lập cho khởi động cùng hệ thống. 

```
systemctl start vsftpd
```

```
systemctl enable vsftpd
```

### Bước 4: Cấu hình firewall

```
firewall-cmd --zone=public --permanent --add-port=21/tcp
firewall-cmd --zone=public --permanent --add-service=ftp
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/193546554-fbe31332-1047-478c-8c47-8219731ec900.png)

# Cấu hình VSFTPD

### Bước 1: Tạo một bản sao để cấu hình mặc định:

```
cp /etc/vsftpd/vsftpd.conf /etc/vsftpd/vsftpd.conf.default
```

### Bước 2: Mở tệp `vsftpd.conf`

```
nano /etc/vsftpd/vsftpd.conf
```

### Bước 3: Tìm và sửa các mục dưới đây

```
anonymous_enable=NO

local_enable=YES

write_enable=YES

chroot_local_user=YES

allow_writeable_chroot=YES

```

