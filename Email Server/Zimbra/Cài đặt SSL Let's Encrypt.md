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

- Cài đặt Snap

```
yum install epel-release.noarch -y
yum install snapd -y
sudo systemctl enable --now snapd.socket
ln -s /var/lib/snapd/snap /snap
snap install core
snap refresh core
```

- Cài đặt Certbot

```
snap install --classic certbot
ln -s /snap/bin/certbot /usr/bin/certbot
```

- Đứng ở user root bạn chạy lệnh sau để yêu cầu cấp phát chứng chỉ SSL

```
certbot certonly --standalone 
```

- Tạo một thư mục sau đó di chuyển các chứng chỉ vào để tiện quản lý. Và tải chứng chỉ trung gian về để xác minh

```
mkdir -p /opt/zimbra/ssl/letsencrypt
cp /etc/letsencrypt/live/mail.xn--thng-mgb3g.vn/* /opt/zimbra/ssl/letsencrypt/
wget -P /opt/zimbra/ssl/letsencrypt https://tool.xn--thng-mgb3g.vn/share/ssl/CA.pem
chown -R zimbra:zimbra /opt/zimbra/ssl/letsencrypt/
```

- Deploy SSL

```
mv /opt/zimbra/ssl/zimbra/commercial/commercial.key /opt/zimbra/ssl/zimbra/commercial/commercial.key.bak
cp /opt/zimbra/ssl/letsencrypt/privkey.pem /opt/zimbra/ssl/zimbra/commercial/commercial.key
cd /opt/zimbra/ssl/letsencrypt/
/opt/zimbra/bin/zmcertmgr deploycrt comm cert.pem CA.pem
```

Restart lại service Zimbra

```
zmcontrol restart 
```
