[Giới thiệu về Let's Encrypt](#gioithieu)

[Cài đặt Let's Encrypt](#caidat)

<a name="gioithieu"></a>
# Giới thiệu về Let’s Encrypt

## 1. Giới thiệu về SSL

Chứng chỉ SSL là một loại chứng chỉ giúp mã hóa thông tin trên các thiết bị hoặc ứng dụng có hỗ trợ mã hóa bằng chứng chỉ SSL. Chứng chỉ SSL sẽ có hai phần gồm Private Key và Public Key, trong đó Public Key sẽ được cài ở ứng dụng đầu cuối mà trình duyệt hay các ứng dụng khác có thể truy cập đọc được, còn Private Key sẽ được cài đặt ở ứng dụng xử lý tiếp nhận dữ liệu, mục đích hoạt động giống như chìa khóa để giải mã các dữ liệu gửi đi từ thiết bị đầu cuối đã được mã hóa thông qua Public Key.

Muốn có chứng chỉ SSL bạn phải đăng ký với các tổ chức xác thực như Comodo, GeoTrust, Symantec,…với chi phí nhất định, chứng chỉ SSL cũng chia thành 3 loại như DV, OV hay EV tùy theo từng loại hình website của bạn.

HTTPS (Hyper Text Transfer Protocol Secure) là sự kết hợp của giao thức SSL và HTTP. Để tạo được một kết nối HTTPS thì phải có 3 thành phần tham gia Client, Web Server, CA. Trong đó:
- Client là các trình duyệt web như Chrome, Firefox…
- Web Server là máy chủ chạy Website bạn muốn truy cập, nó thường là Nginx, Apache…
- CA hiểu là đơn vị cung cấp chứng chỉ SSL

## 2. Giới thiệu về Let’s Encrypt

Let’s Encrypt là một tổ chức xác thực SSL giống như Comodo, GeoTrust, Symantec nhưng cái khác là họ là tổ chức phi lợi nhuận được thành lập với sự bảo trợ của những tổ chức lớn trên thế giới Cisco, Akamai, Mozilla, Facebook,…với mục đích là cung cấp chứng chỉ SSL miễn phí cho mọi người giúp mọi website đều được mã hóa, tạo nên một môi trường internet an toàn hơn.

Chứng chỉ SSL tại Let’s Encrypt sẽ không khác gì với các loại chứng chỉ SSL khác mà chỉ khác ở chỗ bạn phải gia hạn mỗi 90 ngày một lần.

<a name="caidat"></a>
# Cài đặt Let’ Encrypt cho Zimbra

- Truy cập vào server zimbra và stop hết các service.

```
su zimbra
zmcontrol stop
```

![image](https://user-images.githubusercontent.com/111716161/193246984-3d058d66-9fba-42d3-bad9-8b6546d038a7.png)

- Cài đặt Git cho Server

```
yum install epel-release -y

yum groupinstall "Development Tools" -y

yum install gettext-devel openssl-devel perl-CPAN perl-devel zlib-devel -y

yum update

yum install git -y
```

- Tiến hành clone project letsencrypt vào thư mục bất kì 

```
cd /mnt
git clone https://github.com/certbot/certbot
cd certbot
```

- Chạy Let’s Encrypt trong chế độ auto và sử dụng tùy chọn certonly

```
./letsencrypt-auto certonly --standalone
```

Sau khi chạy lệnh trên hệ thống sẽ hiển thị thông tin cần nhập là domain bạn đang sử dụng cài đặt SSL.


Nhấn Enter.

Người dùng có thể kiểm tra lại key đã được tạo ra trong đường dẫn /etc/letsencrypt/live/$domain với $domain là tên domain bạn vừa nhập ở bước trên. 

- Cần sửa lại file chain.pem trong thư mục trên để trust root CA.

Mở file /etc/letsencrypt/live/$domain/chain.pem và chèn thêm đoạn mã sau vào cuối file (Thay thế $domain bằng tên miền bạn sử dụng ở bước trên)

```
-----BEGIN CERTIFICATE-----
MIIDSjCCAjKgAwIBAgIQRK+wgNajJ7qJMDmGLvhAazANBgkqhkiG9w0BAQUFADA/
MSQwIgYDVQQKExtEaWdpdGFsIFNpZ25hdHVyZSBUcnVzdCBDby4xFzAVBgNVBAMT
DkRTVCBSb290IENBIFgzMB4XDTAwMDkzMDIxMTIxOVoXDTIxMDkzMDE0MDExNVow
PzEkMCIGA1UEChMbRGlnaXRhbCBTaWduYXR1cmUgVHJ1c3QgQ28uMRcwFQYDVQQD
Ew5EU1QgUm9vdCBDQSBYMzCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEB
AN+v6ZdQCINXtMxiZfaQguzH0yxrMMpb7NnDfcdAwRgUi+DoM3ZJKuM/IUmTrE4O
rz5Iy2Xu/NMhD2XSKtkyj4zl93ewEnu1lcCJo6m67XMuegwGMoOifooUMM0RoOEq
OLl5CjH9UL2AZd+3UWODyOKIYepLYYHsUmu5ouJLGiifSKOeDNoJjj4XLh7dIN9b
xiqKqy69cK3FCxolkHRyxXtqqzTWMIn/5WgTe1QLyNau7Fqckh49ZLOMxt+/yUFw
7BZy1SbsOFU5Q9D8/RhcQPGX69Wam40dutolucbY38EVAjqr2m7xPi71XAicPNaD
aeQQmxkqtilX4+U9m5/wAl0CAwEAAaNCMEAwDwYDVR0TAQH/BAUwAwEB/zAOBgNV
HQ8BAf8EBAMCAQYwHQYDVR0OBBYEFMSnsaR7LHH62+FLkHX/xBVghYkQMA0GCSqG
SIb3DQEBBQUAA4IBAQCjGiybFwBcqR7uKGY3Or+Dxz9LwwmglSBd49lZRNI+DT69
ikugdB/OEIKcdBodfpga3csTS7MgROSR6cz8faXbauX+5v3gTt23ADq1cEmv8uXr
AvHRAosZy5Q6XkjEGB5YGV8eAlrwDPGxrancWYaLbumR9YbK+rlmM6pZW87ipxZz
R8srzJmwN0jP41ZL9c8PDHIyh8bwRLtTcm1D9SZImlJnt1ir/md2cXjbDaJWFBM5
JDGFoqgCWjBH4d1QB7wCCZAA62RjYJsWvIjJEubSfZGL+T0yjWW06XyxV3bqxbYo
Ob8VZRzI9neWagqNdwvYkQsEjgfbKbYK7p2CNTUQ
-----END CERTIFICATE-----
```

- Tiếp theo tiến hành verify certificate

Copy Let’s Encrypt folder trong /etc/letsencrypt/live/$domain tới thư mục /opt/zimbra/ssl/letsencrypt với các lệnh bên dưới

```
mkdir /opt/zimbra/ssl/letsencrypt
cp /etc/letsencrypt/live/$domain/* /opt/zimbra/ssl/letsencrypt/
chown zimbra:zimbra /opt/zimbra/ssl/letsencrypt/*
```

- Tiếp tục chạy lệnh sau với phiên bản zimbra 8.7 trở lên:

```
su zimbra
cd /opt/zimbra/ssl/letsencrypt
/opt/zimbra/bin/zmcertmgr verifycrt comm privkey.pem cert.pem chain.pem
```

- Deploy Let’s Encrypt SSL certificate mới, lệnh bên dưới sử dụng với quyền user root

Backup thư mục SSL của zimbra

```
cp -a /opt/zimbra/ssl/zimbra /opt/zimbra/ssl/zimbra.$(date "+%Y%m%d")
```

Copy private key tới đường dẫn Zimbra SSL commercial:

```
cp /opt/zimbra/ssl/letsencrypt/privkey.pem /opt/zimbra/ssl/zimbra/commercial/commercial.key
chown zimbra:zimbra /opt/zimbra/ssl/zimbra/commercial/commercial.key
```

Deploy SSL

```
su zimbra
cd /opt/zimbra/ssl/letsencrypt
/opt/zimbra/bin/zmcertmgr deploycrt comm cert.pem chain.pem
```

Restart lại service Zimbra

```
zmcontrol restart 
```
