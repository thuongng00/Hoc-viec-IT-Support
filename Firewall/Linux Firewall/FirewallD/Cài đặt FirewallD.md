[Cài đặt FirewallD](#caidat)

[Cấu hình FirewallD](#cauhinh)

[Lệnh cơ bản](#lenh)

<a name="caidat"></a>
# Cài đặt FirewallD

FirewallD được cài đặt mặc định trên CentOS 7. 

- Cài đặt nếu chưa có:

```
yum install firewalld -y
```

![image](https://user-images.githubusercontent.com/111716161/194522458-2f046342-abfb-40d6-afa5-f7d7d65b7e48.png)

- Khởi động firewalld :

```
systemctl start firewalld
```

- Thiết lập firewalld khởi động cùng hệ thống:

```
systemctl enable firewalld
```

- Khởi động lại firewalld :

```
systemctl restart firewalld

hoặc 

firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/194522627-6a4e4b8e-de5d-4be5-b9dc-cc42602410ab.png)

- Tạm dừng và vô hiệu hóa firewalld :

```
systemctl stop firewalld

systemctl disable firewalld
```

![image](https://user-images.githubusercontent.com/111716161/194522721-24ddc805-dcdd-4f6e-8c57-fde550d2d536.png)

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

![image](https://user-images.githubusercontent.com/111716161/194522824-f365ff79-c50e-4f88-8956-0977b12e6952.png)

![image](https://user-images.githubusercontent.com/111716161/194523197-fff559d8-6919-4d29-87a4-1b151b3d9759.png)

<a name="cauhinh"></a>
# Cấu hình FirewallD

### Thiết lập các zone

- Liệt kê tất cả các zone trong hệ thống :

```
firewall-cmd --get-zones
```

![image](https://user-images.githubusercontent.com/111716161/194523298-bf8dbfac-10da-44c5-8e56-23a98b8964cd.png)

- Kiểm tra zone mặc định :

```
firewall-cmd --get-default-zone
```

![image](https://user-images.githubusercontent.com/111716161/194523377-d2e6d1cf-822b-4cc1-989c-0d8273e71e19.png)

- Kiểm tra zone active (được sử dụng bởi card mạng )

Vì FirewallD chưa được thiết lập bất kỳ quy tắc nào nên zone mặc định cũng đồng thời là zone duy nhất được kích hoạt, điều khiển mọi luồng dữ liệu .

```
firewall-cmd --get-active-zones
```

![image](https://user-images.githubusercontent.com/111716161/194523461-5961349f-729e-40c6-b8f3-43f9fe45eb75.png)

- Thay đổi default zone ( vd thành home ) :

```
firewall-cmd --set-default-zone=home
```

### Thiết lập các rule

Liệt kê toàn bộ các rule của các zones :

```
firewall-cmd --list-all-zones
```

![image](https://user-images.githubusercontent.com/111716161/194523584-9954a23f-ceac-4620-8e62-5fe990b400a6.png)

- Liệt kê toàn bộ các rule trong default zone và active zone:

```
firewall-cmd --list-all
```

Liệt kê toàn bộ các quy tắc trong một zone cụ thể, ví dụ home:

```
firewall-cmd --zone=home --list-all
```

![image](https://user-images.githubusercontent.com/111716161/194523671-c7c96c2a-395c-42db-b1d4-48b6b6dd2383.png)

- Liệt kê danh sách services/port được cho phép trong zone cụ thể:

```
firewall-cmd --zone=public --list-services

firewall-cmd --zone=public --list-ports
```

![image](https://user-images.githubusercontent.com/111716161/194523760-ccabf834-f6e8-46b0-8f12-7da89b23ee6b.png)

### Thiết lập cho services

- Xác định các services trên hệ thống :

```
firewall-cmd --get-services
```

![image](https://user-images.githubusercontent.com/111716161/194523813-67aa2d05-c4fb-468f-9649-cdf147be6fc4.png)

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

![image](https://user-images.githubusercontent.com/111716161/194524024-34241dd0-5897-4147-b3e4-f74c602bf1dd.png)

- Vô hiệu hóa services trên firewalld, sử dụng --remove-service:

```
firewall-cmd --zone=public --remove-service=http
firewall-cmd --zone=public --remove-service=http --permanent
```

![image](https://user-images.githubusercontent.com/111716161/194524174-c8dc0492-5488-4e5d-a868-3c7577ba20d3.png)

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

![image](https://user-images.githubusercontent.com/111716161/194524367-f3c18137-d68b-44a7-860f-a6fa56521004.png)

- Đóng port với tham số --remove-port :

```
firewall-cmd --zone=public --remove-port=9999/tcp
firewall-cmd --zone=public --remove-port=9999/tcp --permanent
```

![image](https://user-images.githubusercontent.com/111716161/194524482-0929872e-96f7-4c3c-aa4c-b050f5d5bc2c.png)

<a name="lenh"></a>
# Lệnh cơ bản của FirewallD

- Lưu cấu hình mặc định để tránh sửa đổi chúng:

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

- Hiển thị tất cả các lệnh tường lửa có sẵn:

```
firewall-cmd –help 

firewall-cmd –version

firewall-cmd –state
```

- Xem khu vực được sử dụng bởi giao diện mạng.

```
firewall-cmd –get-active-zones 
```

- Liệt kê tất cả các cấu hình vùng:

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
