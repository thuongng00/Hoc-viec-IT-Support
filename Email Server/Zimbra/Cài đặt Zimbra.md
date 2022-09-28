### Chuẩn bị

Trước tiên bạn muốn tạo một email server yêu cầu bạn cần có một VPS có IP public và một domain name. Các bạn có thể đăng kí các dịch vụ tại <a href="https://nhanhoa.com/">Nhân Hòa</a> 

Domain name: XN--THNG-MGB3G.VN

### Bước 1: Thiết lập bản ghi DNS

Truy cập vào trang <a href="https://zonedns.vn/">ZoneDNS</a> để thiết lập các bản ghi:

![image](https://user-images.githubusercontent.com/111716161/192745259-e2221a6e-130c-4092-8857-171bb4d8978d.png)

### Bước 2: Chuẩn bị môi trường trên máy chủ mail

- Update

```
yum update -y

reboot
```

- Sửa hostname

```
hostnamectl set-hostname "mail.xn--thng-mgb3g.vn"
exec bash
```

![image](https://user-images.githubusercontent.com/111716161/192747392-9f914b4b-2c5a-42a3-9c7c-9c217e2357c6.png)

- Sửa file /etc/hosts

```
nano /etc/hosts
```

![image](https://user-images.githubusercontent.com/111716161/192747768-a9d62a3d-bb51-4bff-bb63-81c26e87581f.png)

- Kiểm tra xem có dịch vụ nào đang sử dụng port mà Zimbra sử dụng hay không. 

Cài đặt `netstat`.

```
yum -y install net-tools
netstat -tulpn | grep -E -w '25|80|110|143|443|465|587|993|995|5222|5223|9071|7071'
```

![image](https://user-images.githubusercontent.com/111716161/192748310-b9a76a60-ebf0-45c2-8204-6ff3cf2d0936.png)

Nếu có service nào đang chạy trên các port trên thì tìm cách tắt đi hoặc thay thế, nếu chưa có thì thực hiện cài đặt.

```
yum install bind-utils
```

- Kiểm tra lại bản ghi

```
dig -t A mail.xn--thng-mgb3g.vn
dig -t MX xn--thng-mgb3g.vn
```

![image](https://user-images.githubusercontent.com/111716161/192748741-9a3f965b-80ba-4fd1-9d15-be184235d442.png)

![image](https://user-images.githubusercontent.com/111716161/192748806-0652eb33-1f9a-4023-8580-9154cfec4a5d.png)

