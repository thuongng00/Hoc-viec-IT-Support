[Cài đặt FirewallD](#caidat)

[Cấu hình FirewallD](#cauhinh)

[Lệnh cơ bản](#lenh)

<a name="caidat"></a>
# Cài đặt FirewallD

FirewallD được cài đặt mặc định trên CentOS 7. 

- Cài đặt nếu chưa có:

```
yum install firewalld
```

- Khởi động firewalld :

```
systemctl start firewalld
```

- Thiết lập firewalld khởi động cùng hệ thống :

```
systemctl enable firewalld
```

- Khởi động lại firewalld :

```
systemctl restart firewalld

hoặc 

firewall-cmd --reload
```

- Tạm dừng và vô hiệu hóa firewalld :

```
systemctl stop firewalld

systemctl disable firewalld
```

- Kiểm tra tình trạng firewalld :

```
Cách 1 
systemctl status firewalld

Cách 2
firewall-cmd --state

Cách 3 
systemctl is-active firewalld
systemctl is-enabled firewalld
```

<a name="cauhinh"></a>
# Cấu hình FirewallD

### Thiết lập các zone

- Liệt kê tất cả các zone trong hệ thống :

```
firewall-cmd --get-zones
```

- Kiểm tra zone mặc định :

```
firewall-cmd --get-default-zone
```

- Kiểm tra zone active (được sử dụng bởi card mạng )

Vì FirewallD chưa được thiết lập bất kỳ quy tắc nào nên zone mặc định cũng đồng thời là zone duy nhất được kích hoạt , điều khiển mọi luồng dữ liệu .

```
firewall-cmd --get-active-zones
```

- Thay đổi default zone ( vd thành home ) :

```
firewall-cmd --set-default-zone=home
```

### Thiết lập các rule

Liệt kê toàn bộ các rule của các zones :

```
firewall-cmd --list-all-zones
```

Liệt kê toàn bộ các rule trong default zone và active zone:

```
firewall-cmd --list-all
```

Liệt kê toàn bộ các quy tắc trong một zone cụ thể, ví dụ home:

```
firewall-cmd --zone=home --list-all
```

Liệt kê danh sách services/port được cho phép trong zone cụ thể:

```
firewall-cmd --zone=public --list-services

firewall-cmd --zone=public --list-ports
```

### Thiết lập cho services

- Xác định các services trên hệ thống :

```
firewall-cmd --get-services
```

Thông tin về services được lưu trữ tại `/usr/lib/firewalld/services`

- Thiết lập cho phép services trên firewalld , sử dụng --add-service:

```
firewall-cmd --zone=public --add-service=http

firewall-cmd --zone=public --add-service=http --permanent
```

- Thực hiện kiểm tra xem service đã được cho phép chưa :

```
firewall-cmd --zone=public --list-services
```

- Vô hiệu hóa services trên firewalld, sử dụng --remove-service:

```
firewall-cmd --zone=public --remove-service=http

firewall-cmd --zone=public --remove-service=http --permanent
```

### Thiết lập cho port

Mở port với tham số --add-port:

```
firewall-cmd --zone=public --add-port=9999/tcp

firewall-cmd --zone=public --add-port=9999/tcp --permanent
```

- Mở 1 dải port :

```
firewall-cmd --zone=public --add-port=4990-5000/tcp

firewall-cmd --zone=public --add-port=4990-5000/tcp --permanent
```

- Kiểm tra lại các port đã mở :

```
firewall-cmd --zone=public --list-ports
```

Đóng port với tham số --remove-port :

```
firewall-cmd --zone=public --remove-port=9999/tcp

firewall-cmd --zone=public --remove-port=9999/tcp --permanent
```

<a name="lenh"></a>
# Lệnh cơ bản của FirewallD

- Khởi động dịch vụ:

```
systemctl start firewalld         
```

- Khởi động lại dịch vụ:

```
systemctl restart firewalld  
```

- Khởi động dịch vụ cùng hệ thống:

```
systemctl enable firewalld 
```

- Tắt firewall

```
systemctl stop firewalld  
```

- Vô hiệu hóa firewall

```
systemctl disable firewalld   
```

- Xem trạng thái hoạt động:

```
firewall-cmd --state  
```

- Xem các danh sách cổng tương ứng với dịch vụ zone cụ thể:

```
firewall-cmd --zone=public --list-ports 
```

- Lưu cấu hình mặc định để tránh sửa đổi chúng

```
/usr/lib/firewalld
```

- Lưu tệp cấu hình hệ thống, bạn sẽ ghi đè cấu hình mặc định:

```
/etc/firewall
```

- Firewalld cung cấp các tệp cấu hình chín vùng theo mặc định: block.xml, dmz.xml, drop.xml, external.xml, home.xml, internal.xml, public.xml, trust.xml, work.xml

```
/usr/lib/firewalld/zone/ 
```

- Hiển thị tất cả các lệnh tường lửa có sẵn

```
firewall-cmd –help 

firewall-cmd –version

firewall-cmd –state
```

- Xem khu vực được sử dụng bởi giao diện mạng.

```
firewall-cmd –get-active-zones 
```

- Liệt kê tất cả các cấu hình vùng

```
firewall-cmd –list-all-zones 
```

- Xem khu vực mặc định:

```
firewall-cmd –get-default-zone
```

- Đặt vùng mặc định:

```
firewall-cmd –set-default-zone=internal
```

- Xem khu vực mà giao diện được chỉ định thuộc về:

```
firewall-cmd –get-zone-of-interface=ens33
```

- Thêm giao diện vào vùng, tất cả các giao diện mặc định đều là công khai, có giá trị vĩnh viễn cộng thêm -permanent sau đó reload. 

```
firewall-cmd –zone=public –add-interface=ens33
```

- Mở tất cả các gói:

```
firewall-cmd –panic-on|off 
```

- Xem các dịch vụ có sẵn mặc định

```
firewall-cmd –get-services
```
