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

### Bước 3: Cài đặt Zimbra

- Cài đặt các gói cần thiết

```
yum install unzip net-tools sysstat openssh-clients perl-core libaio nmap-ncat libstdc++.so.6 wget -y
```

![image](https://user-images.githubusercontent.com/111716161/192749345-2ed257d0-f93d-443a-bd83-6a9482e91f68.png)

- Cài đặt wget

```
yum install wget -y
```

- Tải và giải nén Zimbra

```
mkdir zimbra && cd zimbra

wget https://files.zimbra.com/downloads/8.8.10_GA/zcs-8.8.10_GA_3039.RHEL7_64.20180928094617.tgz --no-check-certificate
```

![image](https://user-images.githubusercontent.com/111716161/192749568-3310635b-74b0-43af-8db2-fc13e6f10d1a.png)

- Cài đặt Zimbra

```
tar zxpvf zcs-8.8.10_GA_3039.RHEL7_64.20180928094617.tgz

cd zcs-8.8.10_GA_3039.RHEL7_64.20180928094617 

./install.sh
```

![image](https://user-images.githubusercontent.com/111716161/192752119-9d189922-6cd0-42dc-8e66-bd6effeaf8d0.png)

![image](https://user-images.githubusercontent.com/111716161/192752289-c09423ce-633c-4424-9548-6451c852af03.png)

![image](https://user-images.githubusercontent.com/111716161/192752724-7320cc5a-0783-4b0c-91e5-b79a4d77bc44.png)

Nhấn Y, create lại tên domain.

![image](https://user-images.githubusercontent.com/111716161/192973864-177ce397-5c82-411d-93be-4aa8ac54a503.png)

Chọn 7 sau đó chọn 4 để thiết lập tài khoản admin.

Q2CtYKjX1

![image](https://user-images.githubusercontent.com/111716161/192974369-ecbf4fd1-ed60-4670-a7fe-23388e30c50b.png)

Chọn `r` để xem lại cài đặt, chọn `a` để áp dụng thay đổi. 

![image](https://user-images.githubusercontent.com/111716161/192979678-074e9b98-f37b-4330-97e8-7aea5c660089.png)

- Mở firewalld

```
firewall-cmd --permanent --add-port={25,80,110,143,443,465,587,993,995,5222,5223,9071,7071}/tcp

firewall-cmd --reload
```

### Bước 4: Thiết lập các bản ghi DKIM, DMARC.

- Trên VPS sử dụng user zimbra thực hiện lệnh sau 

https://mail.xn--thng-mgb3g.vn:7071/zimbraAdmin/
