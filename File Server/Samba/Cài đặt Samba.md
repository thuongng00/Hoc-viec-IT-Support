### Bước 1: Cài đặt các gói Samba:

```
yum install samba samba-client samba-common
```

![image](https://user-images.githubusercontent.com/111716161/193732397-fd6b1565-2d31-47c8-a505-9d94dd919f42.png)

### Bước 2: Cho phép Samba dùng tường lửa

```
firewall-cmd --permanent --zone=public --add-service=samba firewall-cmd --reload 
```

![image](https://user-images.githubusercontent.com/111716161/193732495-afd0a959-e286-4693-978e-f422445b6127.png)

### Bước 3: Lưu 1 bản config

```
cp /etc/samba/smb.conf /etc/samba/smb.conf.orig
```

Bước 4: Tạo thư mục cần share và phân quyền cho thư mục

```
mkdir -p /srv/samba/anonymous
chmod -R 0775 /srv/samba/anonymous
chown -R nobody:nobody /srv/samba/anonymous
```

![image](https://user-images.githubusercontent.com/111716161/193732573-aa030d25-cd32-4c86-a87f-11bc5e6e7efe.png)

Bước 5: Tắt SELinux

```

```

![image](https://user-images.githubusercontent.com/111716161/193732613-b6da16dd-5e51-4b9a-8e99-e8f882d09e73.png)

Bước 6: Chỉnh sửa file config

```
nano /etc/samba/smb.conf
```

Nội dung file: 

```
[global]
	workgroup = WORKGROUP
	netbios name = centos
	security = user
[Anonymous]
	comment = Anonymous File Server Share
	path = /srv/samba/anonymous
	browsable =yes
	writable = yes
	guest ok = yes
	read only = no
	force user = nobody
```

Bước 7: Kiểm tra samba setting

```
testparm
```

![image](https://user-images.githubusercontent.com/111716161/193732970-d8c8db2f-f7b1-4c7d-a46d-16a73f28c87a.png)

Bước 8: Bật và khởi động Samba

```
systemctl enable smb.service
systemctl enable nmb.service
systemctl start smb.service
systemctl start nmb.service
```

![image](https://user-images.githubusercontent.com/111716161/193733041-1e8e3761-bd70-4662-845b-ef5ed5d2309c.png)

Bước 9: Tạo người dùng và group

- Tạo tài khoản và đặt mật khẩu

```
groupadd smbgrp
usermod thuong -aG smbgrp
smbpasswd -a thuong
```

- Tạo và phân quyền thư mục cho file

```
mkdir -p /srv/samba/secure
chmod -R 0770 /srv/samba/secure
chown -R root:smbgrp /srv/samba/secure
chcon -t samba_share_t /srv/samba/secure
```

- Chỉnh sửa file config

```
nano /etc/samba/smb.conf
```

Nội dung file:

```
[Secure]
	comment = Secure File Server Share
	path =  /srv/samba/secure
	valid users = @smbgrp
	guest ok = no
	writable = yes
	browsable = yes
```

- Kiểm tra và khởi động lại dịch vụ

```
testparm
systemctl restart smb.service
systemctl restart nmb.service
```
