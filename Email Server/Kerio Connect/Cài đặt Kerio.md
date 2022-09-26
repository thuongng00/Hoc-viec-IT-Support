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

- Nhập mật khẩu

![image](https://user-images.githubusercontent.com/111716161/192238388-9d596c53-a210-42cd-80aa-57c763b6651c.png)

- Nhấn Next

![image](https://user-images.githubusercontent.com/111716161/192238547-da35b2b8-f1d3-4a92-9e58-7d794e38b9fb.png)

- Chọn thư mục lưu trữ mail

![image](https://user-images.githubusercontent.com/111716161/192238943-25aea7ba-eda6-4b7f-92dc-88c79790c33b.png)

- Chọn mua bản quyền hoặc dùng thử 30 ngày. 

![image](https://user-images.githubusercontent.com/111716161/192239012-5659fda3-506a-4969-84e1-6bc0e3952b6d.png)

KEY BẢN QUYỀN: 10512-1XWX7-44R91

![image](https://user-images.githubusercontent.com/111716161/192239300-d02299d6-b2a4-44e6-9580-f394d081fd8e.png)

![image](https://user-images.githubusercontent.com/111716161/192239372-63cd33d5-bb9f-41e9-a0b0-37b717dd9634.png)

- Nhấn Finish để hoàn tất.

![image](https://user-images.githubusercontent.com/111716161/192239454-e7712c5b-6dec-4363-a1dd-b963a9d25304.png)

Chờ hệ thống tự khởi động lại

![image](https://user-images.githubusercontent.com/111716161/192239578-0b4e383f-0dcc-40bb-8266-1138bebff5fd.png)

