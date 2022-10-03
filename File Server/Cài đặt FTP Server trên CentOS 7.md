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

![image](https://user-images.githubusercontent.com/111716161/193547395-4a4ca025-917e-4724-a7cb-4ee11aec4d34.png)

### Bước 3: Tìm và sửa các mục dưới đây

```
anonymous_enable=NO

local_enable=YES

write_enable=YES

```

![image](https://user-images.githubusercontent.com/111716161/193549721-53565898-ac5a-418f-8db6-9ef897aca38e.png)

```
chroot_local_user=YES
```

![image](https://user-images.githubusercontent.com/111716161/193550055-e1353f78-5bf7-45b7-b783-efcf24400c2e.png)

```
userlist_enable=YES
```

![image](https://user-images.githubusercontent.com/111716161/193550601-62910739-d8fb-4320-85d8-1a1617993b8f.png)

### bước 4: Lưu thay đổi và reset lại dịch vụ 

```
systemctl restart vsftpd
```

# Tạo người dùng FTP mới

- Tạo tài khoản user mới:

```
sudo adduser username

sudo passwd username
```

Sau khi tạo người dùng mới, hệ thống sẽ nhắc bạn nhập và xác nhận mật khẩu người dùng mới.

![image](https://user-images.githubusercontent.com/111716161/193551923-5ff9823c-462e-43ef-90fb-1457eb0f571b.png)

- Thêm người dùng vào userlist

```
echo "username" | sudo tee -a /etc/vsftpd/user_list
```

![image](https://user-images.githubusercontent.com/111716161/193552140-05172e72-3f36-4e4c-ac60-295d81e9919b.png)

- Tạo một thư mục cho người dùng mới, điều chỉnh các quyền:

```
sudo mkdir –p /home/username/ftp/upload
sudo chmod 550 /home/usename/ftp
sudo chmod 750 /home/username/ftp/upload
sudo chown –R username: /home/username/ftp
```

- Truy cập vào FTP

```
ftp localhost
```

![image](https://user-images.githubusercontent.com/111716161/193553475-6cc25e7b-1d5e-42f1-9d14-3046450596e7.png)
