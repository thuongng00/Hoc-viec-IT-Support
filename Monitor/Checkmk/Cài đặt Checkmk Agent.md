### Bước 1: Lấy link tải

Đăng nhập Checkmk Server -> Vào Setup -> Agent -> Linux.

![image](https://user-images.githubusercontent.com/111716161/194269084-a4d51230-33e8-4672-b7e8-50f2ef3a3f07.png)

Ở đây có 2 link:

- `*.deb` dùng cho các host sử dụng debian.
- `*.rpm` dùng cho các host sử dụng RHEL.

Với client chạy hệ điều hành CentOS7 ta chọn `*.rpm`, copy đường link cài đặt. 

![image](https://user-images.githubusercontent.com/111716161/194271131-81f37228-1a9b-461a-8612-d8e153f1ce07.png)

### Bước 2: Tải file cài đặt về máy client
```
yum install wget -y
wget http://192.168.30.138/nganthuong/check_mk/agents/check-mk-agent-2.1.0p13-1.noarch.rpm
```

### Bước 3: Cài đặt xinetd

```
yum install xinetd -y
```

Khởi động lại dịch vụ xinetd và cho phép khởi động cùng hệ thống:

```
systemctl start xinetd
systemctl enable xinetd
```

### Bước 4: Cài đặt agent

```
rpm -ivh check-mk-agent-2.1.0p13-1.noarch.rpm
```

### Bước 5: Cấu hình xinetd của checkmk

```
nano /etc/xinetd.d/check_mk
```

### Bước 6: Khởi động lại xinetd

```
systemctl restart xinetd
```

## Bước 7: Cấu hình firewalld

```
firewall-cmd --add-port=6556/tcp --permanent
firewall-cmd --reload
```

## Thêm host trên Checkmk Server

