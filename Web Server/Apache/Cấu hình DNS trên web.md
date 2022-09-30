# Cấu hình IP tĩnh

Bước 1: Liệt kê thông tin card mạng

```
ip link show
```

![image](https://user-images.githubusercontent.com/111716161/191690206-f7b28c2a-b1b5-441c-af0c-d1c9d313ad54.png)

Hoặc

```
nmcli -p dev
```

![image](https://user-images.githubusercontent.com/111716161/191690272-c7e5035d-c7e9-43aa-a355-e40c49fa7b60.png)

Bước 2: Cấu hình IP tĩnh

- Cách 1: Cấu hình bằng tay

Mở file cấu hình card mạng:

```
nano /etc/sysconfig/network-scripts/ifcfg-ens33
```

![image](https://user-images.githubusercontent.com/111716161/191690481-c7e57861-efa4-4890-8250-972485a0691e.png)

Các option cần cấu hình:

`DEVICE`: tên card mạng, cần điền chính xác tên card mạng thì hệ thống mới nhận biết được card nào để cấu hình cho nó. 

`NAME`: như DEVICE

`ONBOOT`: phải để "yes" thì khi reboot hệ thống, network mới tự động được bật lên với cấu hình card mạng tương ứng. 

`BOOTPROTO`: Cấu hình IP tĩnh hay DHCP, nếu là DHCP thì để giá trị DHCP, nếu là IP tĩnh thì để STATIC

`IPV6INIT`: tắt chức năng hỗ trợ sử dụng IPv6.

`IPADDR`: địa chỉ IP tĩnh.

`PREFIX`: subnet mask của lớp mạng IP sử dụng.

`GATEWAY`: địa chỉ IP cổng gateway.

`DNS1`: thông tin DNS server.

![image](https://user-images.githubusercontent.com/111716161/193211148-c43abeef-2841-421b-8574-f48da8194228.png)

- Cách 2: Cấu hình IP tĩnh với chương trình dịch vụ Network Manager

Network Manager là một chương trình/dịch vụ hỗ trợ điều khiển quản lý mạng cũng như cấu hình hệ thống mạng trên CentOS 7. 

Mặc định khi sử dụng OS CentOS 7/RHEL 7 thì chương trình này đã được cài đặt từ ban đầu. Nhưng ta cần phải cài đặt chương trình "NetworkManager Text User Interface (TUI) -**nmtui**" nhằm cung cấp một giao diện text cấu hình linh động tương tác với NEtwork Manager ngay trên Terminal hoặc Console kết nối đến hệ thống thay vì phải dùng lệnh riêng của NetworkManager.

Từ chương trình **mntui**, ta có thể cấu hình IP tĩnh cho card mạng, tắt mở kết nối mạng, thiết lập hostname cho OS, tạo card bonding, cấu hình VLAN bằng NM,...

Để cài đặt chương trình **nmtui**, dùng lệnh sau:

```
yum install NetworkManager-tui -y
```

![image](https://user-images.githubusercontent.com/111716161/191697263-bd55b221-4f94-4fef-9273-7c55fa1a1acc.png)

Thêm dòng sau vào file cấu hình card mạng:

```
nano /etc/sysconfig/network-scripts/ifcfg-ens33
...
...
NM_CONTROLLERD="yes"
...
...
```

![image](https://user-images.githubusercontent.com/111716161/191697460-eaaa6d9a-a56a-4d16-8547-c67ebcdb5de7.png)

Khởi động dịch vụ Network Manager

```
systemctl start NetworkManager.service
```

![image](https://user-images.githubusercontent.com/111716161/191697344-61c9948b-42dd-45ee-a254-0697aa5793f5.png)

Cấu hình IP tĩnh cho card mạng

```
nmtui edit ens33
```

Cửa sổ giao diện trên terminal của Network Manager xuất hiện cho phép ta cấu hình địa chỉ IP của ens33. 

![image](https://user-images.githubusercontent.com/111716161/191697545-74bbc61b-4be7-44bb-a0e0-74f55dd2d9af.png)

Sử dụng các phím tab, space, phím di chuyển để thay đổi, chỉnh sửa các giá trị cấu hình. Sau khi xong ta bấm chọn nút OK.

![image](https://user-images.githubusercontent.com/111716161/191697848-5bc92fa7-28c9-41ac-87ed-531661a55ed6.png)

Bước 3: Khởi động network và kiểm tra cấu hình

- Khởi động lại dịch vụ network

```
systemctl restart network
```

![image](https://user-images.githubusercontent.com/111716161/191698039-ba0bcff1-302f-424e-8d5b-cf727ce4bc40.png)

- Kiểm tra thông tin IP tĩnh đã cấu hình cho card mạng

```
ip a s ens33
```

![image](https://user-images.githubusercontent.com/111716161/191698940-36b1f3b3-8248-4344-b369-2266a3100efc.png)

- Kiểm tra thông tin routing

```
ip r
```

![image](https://user-images.githubusercontent.com/111716161/191699021-8f43a81f-04e1-4744-8ac0-a36a89ed947a.png)

- Kiểm tra thông tin DNS

```
cat /etc/resolv.conf
```

- Ping gateway

```
ping IP-VPS
```

# Gắn miền cho IP

### 1. Sử dụng lệnh ip add để check IP của Centos 7

```
ip add
```

![image](https://user-images.githubusercontent.com/111716161/188354756-cff0102f-02b8-4bed-b307-bf57032cbbd6.png)

IP ở đây là 192.168.30.130

### 2. Gắn miền cho IP, sử dụng lệnh vi /etc/hosts để cài DNS cho địa chỉ IP

```
vi /etc/hosts
```

![image](https://user-images.githubusercontent.com/111716161/188356557-bbdcdfec-370b-4bdd-bd20-f20e9efa4cdd.png)

### 3. Sử dụng phím tắt Insert trên bàn phím để sửa tập tin và thêm DNS và miền

![image](https://user-images.githubusercontent.com/111716161/188356663-7fce0b58-99c6-48e9-8555-c59a884634c6.png)

### 4. Tiếp theo ấn phím tắt Esc trên bàn phím để thoát chế độ chỉnh sửa và sử dụng lệnh :wq để lưu lại và gõ Enter để lưu

![image](https://user-images.githubusercontent.com/111716161/188356750-78a91011-3851-4098-920a-3aaad34f9570.png)

# Tạo file trên DNS

### 1. Sử dụng cd /etc/httpd/ đây là thư mục cấu hình cho httpd

``` 
cd /etc/httpd/
```

![image](https://user-images.githubusercontent.com/111716161/188395218-a859ab2c-62a5-4ec6-a1d6-89756b6069b7.png)

### 2. Gõ ls để kiếm tra các file cấu hình:

```
ls
```

![image](https://user-images.githubusercontent.com/111716161/188395569-0d681ed4-ff60-4c47-978e-b4723cf14c42.png)

### 3. Gõ cd conf để vào file cấu hình web và gõ cd /var/www/html để truy cập vào file tạo web

```
cd conf
cd /var/www/html
```

![image](https://user-images.githubusercontent.com/111716161/188395791-7cf0502d-f507-4474-b5cd-c0d984dbc2a1.png)

### 4. Gõ vi index.html để tạo một trang web riêng, nhập nội dung hiển thị và lưu lại. 

```
vi index.html
```

![image](https://user-images.githubusercontent.com/111716161/188398599-4f2f1a74-4383-4a8d-b72a-839aaffb3fc1.png)

### 5. Truy cập "thuong.com.vn"
![image](https://user-images.githubusercontent.com/111716161/188398483-5b0d0c77-5a6e-4fe9-bab1-80b9b39e55e6.png)



