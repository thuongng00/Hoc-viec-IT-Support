### Bước 1: Lấy link tải

Đăng nhập Checkmk Server -> Vào Setup -> Agent -> Linux.

![image](https://user-images.githubusercontent.com/111716161/194269084-a4d51230-33e8-4672-b7e8-50f2ef3a3f07.png)

Ở đây có 2 link:

- `*.deb` dùng cho các host sử dụng debian.
- `*.rpm` dùng cho các host sử dụng RHEL.

Với client chạy hệ điều hành CentOS7 ta chọn `*.rpm`, copy đường link cài đặt. 

![image](https://user-images.githubusercontent.com/111716161/194271131-81f37228-1a9b-461a-8612-d8e153f1ce07.png)

### Bước 2: Tải file cài đặt về máy client

```
yum install wget -y
wget http://192.168.30.138/nganthuong/check_mk/agents/check-mk-agent-2.1.0p13-1.noarch.rpm
```

![image](https://user-images.githubusercontent.com/111716161/194449112-e61205a6-728e-4c2b-b020-b6d3f767c250.png)

![image](https://user-images.githubusercontent.com/111716161/194449070-3ec30edd-5872-43d4-a0ad-97c6af44b6cf.png)


### Bước 3: Cài đặt xinetd

```
yum install xinetd -y
```

![image](https://user-images.githubusercontent.com/111716161/194449166-6f385a51-f5cd-4823-8e1a-735b93f48539.png)

Khởi động lại dịch vụ xinetd và cho phép khởi động cùng hệ thống:

```
systemctl start xinetd
systemctl enable xinetd
```

![image](https://user-images.githubusercontent.com/111716161/194449270-25d36cab-2469-4881-a8a0-a43fb13e3368.png)

### Bước 4: Cài đặt agent

```
rpm -ivh check-mk-agent-2.1.0p13-1.noarch.rpm
```

![image](https://user-images.githubusercontent.com/111716161/194449434-700a3c5c-15a2-4292-84bb-d079cd718897.png)

### Bước 5: Cấu hình xinetd của checkmk

```
nano /etc/xinetd.d/check-mk-agent
```

`port`: 6556

`only_from`: Thêm địa chỉ IP server OMD của bạn

`disable`: no (Có nghĩa cho phép dịch vụ chạy)

![image](https://user-images.githubusercontent.com/111716161/194449933-418320de-7ded-4c74-ac85-1cae0d586937.png)

![image](https://user-images.githubusercontent.com/111716161/194450070-57dc9739-3559-4a82-8b68-8e4887b5917f.png)

### Bước 6: Khởi động lại xinetd

```
systemctl restart xinetd
```

![image](https://user-images.githubusercontent.com/111716161/194450295-5a24bae7-96c6-4fd8-bb75-85001280e565.png)

### Bước 7: Cấu hình firewalld

```
firewall-cmd --add-port=6556/tcp --permanent
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/194450478-b626351b-2953-4ad5-b057-d4eda0da1e97.png)

### Bước 8: Thêm host trên Checkmk Server

Vào Setup ->  Host -> Add host -> Nhập thông tin: Hostname, IP, các cấu hình phù hợp -> Save & go to service configuration. 

![image](https://user-images.githubusercontent.com/111716161/194451050-444e0c4c-535b-44d1-8a8a-7f173a0a0545.png)

![image](https://user-images.githubusercontent.com/111716161/194451092-bf2f0a0a-453d-4264-a2e2-b2c591b29b75.png)

![image](https://user-images.githubusercontent.com/111716161/194451216-a61a8d71-f64b-4929-98f1-8f771b539cc7.png)

Kết quả:

![image](https://user-images.githubusercontent.com/111716161/194451345-f7eb352d-d07f-4ffc-9d1b-631105fc0b8b.png)

![image](https://user-images.githubusercontent.com/111716161/194451874-d14e4d3b-28c1-4927-ac3e-deb60ca97ac0.png)
