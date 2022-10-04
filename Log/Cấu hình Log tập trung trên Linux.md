# Cấu hình Rsyslog Server

### Bước 1: Chỉnh sửa trong file cấu hình.
- Chỉnh sửa file máy chủ Syslog-server để nó có thể nhận các bản tin log từ các client gửi về.

```
nano /etc/rsyslog.conf
```

- Bỏ comment 2 dòng dưới giao thức, có thể chọn sử dụng UDP hoặc TCP, mặc định `syslog` sử dụng port 514 để gửi và nhận thông tin log.

Ở đây sử dụng giao thức UDP.

- Để máy chủ log tạo thành các thư mục lưu riêng log đối với từng máy Client gửi về, thêm dòng sau vào cuối file cấu hình. 

Cách 1: Thư mục lưu log client trả về sẽ là IP - client.

```
$template RemoteServer, "/var/log/%fromhost-ip%/%SYSLOGFACILITY-TEXT%.log"
*.* ?RemoteServer
```

![image](https://user-images.githubusercontent.com/111716161/193760933-3b1c8741-1147-434d-abd6-a9414d91879c.png)

Cách 2: Thư mục lưu log client trả vê sẽ là tên máy client.

```
$template RemoteServer, "/var/log/%HOSTNAME%/%SYSLOGFACILITY-TEXT%.log"
*.* ?RemoteServer
```

Ngoài ra có thể sử dụng cấu hình sau để lưu các file log với tên các chương trình: 

```
$template TmplAuth,"/var/log/%HOSTNAME%/%PROGRAMNAME%.log" #hostname
*.*     ?TmplAuth
$template TmplAuth,"/var/log/%fromhost-ip%/%PROGRAMNAME%.log" #ip-server
*.*     ?TmplAuth
```

### Bước 2: Mở port 514

```
firewall-cmd --permanent --add-port=514/udp
firewall-cmd --permanent --add-port=514/tcp
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/193760725-ceab06bf-6fc0-4d5d-aaf8-bf816c3848d6.png)

### Bước 3: Khởi động lại Rsyslog

```
systemctl restart rsyslog
```

### Bước 4: Cấu hình Rsyslog Client

```
nano /etc/rsyslog.conf
```

Thêm dòng:

- *.* @IPserver:514 : Đối với giao thức UDP
- *.* @@IPserver:514 : Đối với giao thức TCP

![image](https://user-images.githubusercontent.com/111716161/193761087-6ca6dae8-3f49-47ac-8907-93f7b8d2b61f.png)

Khởi động lại Rsyslog. 

### Bước 5: Sau khi restart rsyslog

- Bắt và kiểm chứng các gói tin từ client gửi về:

```
tcpdump -nni ens33 port 514
```

- Kiểm tra thư mục đẩy về trên `/var/log`

```
cd /var/log/ | ls -al
```

![image](https://user-images.githubusercontent.com/111716161/193761337-8d72c37e-541f-4844-a695-d9c8882e81c8.png)
