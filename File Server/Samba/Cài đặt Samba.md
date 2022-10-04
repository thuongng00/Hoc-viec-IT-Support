### Bước 1: Cài đặt các gói Samba:

```
yum install samba samba-client samba-common
```

### Bước 2: Cho phép Samba dùng tường lửa

```
firewall-cmd --permanent --zone=public --add-service=samba firewall-cmd --reload 
```

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

Bước 5: Tắt SELinux

```

```

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

Bước 8: Bật và khởi động Samba

```
systemctl enable smb.service
systemctl enable nmb.service
systemctl start smb.service
systemctl start nmb.service
```

