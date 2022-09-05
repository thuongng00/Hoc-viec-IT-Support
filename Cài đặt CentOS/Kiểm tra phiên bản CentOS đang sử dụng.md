## 1. Kiểm tra version CentOS bằng Command Line
Lệnh lsb_release sẽ hiển thị thông tin chuẩn cơ bản (Linux Standard Base) về bản phân phối của Linux đang chạy trên máy tính.

Đây là cách đơn giản nhất để kiểm tra version của CentOS , nó chạy trên mọi phiên bản của CentOS nên bạn cứ yên tâm mà sử dụng.

Hãy mở Terminal của bạn lên và nhập lệnh sau:
```
lsb_release -a
```

![image](https://user-images.githubusercontent.com/111716161/188342078-95214838-fe4f-4455-b208-5851cc8c1de3.png)

*Lưu ý: Nếu bạn nhận thông báo lỗi lsb_release: command not found thì tức là máy bạn chưa được cài đặt gói redhat-lsb-core nhé. Hãy chạy lệnh dưới đây để cài đặt nó:*
```
sudo yum install redhat-lsb-core
```

## 2. Kiểm tra version CentOS bằng lệnh rpm
rpm (Red Hat Package Manager) là một công cụ quản lý gói cho các hệ thống dựa trên Red Hat như RHEL, CentOS và Fedora.

Bạn có thể sử dụng công cụ rpm để hiển thị thông tin về gói centos-release, bao gồm phiên bản CentOS trong tên gọi của nó:
```
rpm --query centos-release
```
![image](https://user-images.githubusercontent.com/111716161/187610072-f37512e7-d584-41e4-95cc-5e97d94809bc.png)

## 3. Kiểm tra version CentOS bằng file /etc/centos-release
Package centos-release cung cấp file /etc/centos-release, vì vậy ta có thể kiểm tra thông tin bên trong file này.

Hãy chạy lệnh sau nhé:

```
cat /etc/centos-release
```
![image](https://user-images.githubusercontent.com/111716161/187610377-207304f1-72d2-4c57-b129-6a29a220a581.png)

## 4. Kiểm tra version CentOS bằng file /etc/os-release
File /etc/os-rease chạy trên tất cả các bản phối Linux sử dụng systemd nên nó chỉ hoạt động trên CentOS7.
```
cat /etc/os-release
```
![image](https://user-images.githubusercontent.com/111716161/187610514-cbf1f777-ba41-4b05-99d4-506bb417646e.png)

