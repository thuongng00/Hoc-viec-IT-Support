### Chuẩn bị

Trước tiên bạn muốn tạo một email server yêu cầu bạn cần có một VPS có IP public và một domain name. Các bạn có thể đăng kí các dịch vụ tại <a href="https://nhanhoa.com/">Nhân Hòa</a> 

Domain name: XN--THNG-MGB3G.VN

### Bước 1: Thiết lập bản ghi DNS

Truy cập vào trang <a href="https://zonedns.vn/">ZoneDNS</a> để thiết lập các bản ghi:

![image](https://user-images.githubusercontent.com/111716161/193174454-2a8073cb-ea4c-4470-b5c9-4c27febe0e23.png)

### Bước 2: Chuẩn bị môi trường trên máy chủ mail

- Tắt SELinux

```
sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config && setenforce 0
```

- Update

```
yum update -y

```

- Postfix là một phầm mềm nguồn mở được dùng để gửi mail (Mail Transfer Agent-MTA). Được phát hành bởi IBM với mục tiêu thay thế trình gửi mail phổ biến là sendmail.

Kiểm tra trạng thái của postfix:

```
systemctl status postfix
```

Dừng dịch vụ postfix:

```
systemctl stop postfix
```

Gỡ cài đặt postfix:

```
yum remove postfix -y
```

![image](https://user-images.githubusercontent.com/111716161/192213076-500e9148-4fda-4fb6-b4fa-4b3b29ed7cd5.png)

- Reboot lại máy: 

```
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

![image](https://user-images.githubusercontent.com/111716161/193174747-3cd6660a-bc33-40ac-902f-841a8953da84.png)

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

![image](https://user-images.githubusercontent.com/111716161/193174564-4d3bc0ec-37cd-4fe0-ac6c-11f0b852c929.png)

![image](https://user-images.githubusercontent.com/111716161/193174612-fb31e623-d892-4cb6-abbd-62794c02d09d.png)

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

![image](https://user-images.githubusercontent.com/111716161/193173986-cfbfd5e6-1fba-45ec-a60d-b77e9ae8b663.png)

![image](https://user-images.githubusercontent.com/111716161/193174017-e476cc71-e476-45ab-a648-55bbac69c731.png)

Nhấn Y để tải xuống các gói liên quan đến Zimbra.

![image](https://user-images.githubusercontent.com/111716161/193174115-199fa180-e187-4ce1-9949-25ff56ba088e.png)

Nhấn Y, create lại tên domain.

![image](https://user-images.githubusercontent.com/111716161/193174242-d00747bd-24dd-4c50-aba2-b90ee38b35bb.png)

Chọn 7 sau đó chọn 4 để thiết lập tài khoản admin. (Nso01_8HMj)

![image](https://user-images.githubusercontent.com/111716161/193174295-4fe3ca9b-20d7-4f8a-8b98-e4352c080ef2.png)

![image](https://user-images.githubusercontent.com/111716161/193174323-6d427f62-45f4-4745-91a3-6b9243847356.png)

Chọn `r` để xem lại cài đặt, chọn `a` để áp dụng thay đổi. 

![image](https://user-images.githubusercontent.com/111716161/193174362-f8198c54-16cf-44ec-8b46-cb75ef8f5dc6.png)

![image](https://user-images.githubusercontent.com/111716161/193174399-eb1a1fb8-7820-4e55-bff0-2f800b21d5c2.png)

![image](https://user-images.githubusercontent.com/111716161/193176261-782bd3dc-fa45-42b9-bcf8-15dfe2a0eaaf.png)

- Sau khi cài đặt xong khởi động lại dịch vụ zimbar bằng lệnh:

```
su zimbra

zmcontrol restart
```

- Mở firewalld

```
firewall-cmd --permanent --add-port={25,80,110,143,443,465,587,993,995,5222,5223,9071,7071}/tcp

firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/193176371-f8a624a0-0c7f-4651-89a5-3e47878b8bcc.png)

### Bước 4: Thay đổi mật khẩu cho tài khoản admin

- Kiểm tra những quyền admin sử dụng

```
zmprov gaaa
```

![image](https://user-images.githubusercontent.com/111716161/193182481-2f706339-e2b6-4366-bfb3-02f81078d96b.png)

- Thay đổi mật khẩu:

```
zmprov sp <admin email address> <new password>
```

![image](https://user-images.githubusercontent.com/111716161/193182820-c7e43fe9-94de-45dd-bc38-c0457f73b6dc.png)

Truy cập đường link sau để vào Zimbra: 

```
https://mail.xn--thng-mgb3g.vn:7071/zimbraAdmin/
```

![image](https://user-images.githubusercontent.com/111716161/193181528-3dfdd2db-44db-42b7-b944-0211708951f1.png)

Đăng nhập bằng tài khoản admin vào trang quản trị. 

![image](https://user-images.githubusercontent.com/111716161/193181865-c032b4e0-6627-47e7-a125-03858eaf9cf5.png)

![image](https://user-images.githubusercontent.com/111716161/193181804-a608a6d3-3897-4a27-9020-e0a11a11aeb8.png)

Đăng nhập tài khoản admin vào trang user

```
https://mail.thương.vn/
```

![image](https://user-images.githubusercontent.com/111716161/193190990-5184cc55-4d03-4363-bac5-78bd38259f6f.png)

