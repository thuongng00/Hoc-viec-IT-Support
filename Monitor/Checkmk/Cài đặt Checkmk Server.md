Truy cập link: https://checkmk.com/de/download để cập nhật phiên bản mới nhất.

## Bước 1: Tải và cài đặt các gói checkmk

```
yum install -y epel-release wget
```

![image](https://user-images.githubusercontent.com/111716161/194260012-d43b1c49-0b1a-43a3-9118-1a750642d88e.png)

- Tải file cài đặt:

```
wget https://download.checkmk.com/checkmk/2.1.0p13/check-mk-raw-2.1.0p13-el7-38.x86_64.rpm
```

![image](https://user-images.githubusercontent.com/111716161/194260315-4079d4a7-02ad-455a-a8ca-8d64d0f0f321.png)

### Bước 2: Cài đặt checkmk

```
yum install -y check-mk-raw-2.1.0p13-el7-38.x86_64.rpm
```

![image](https://user-images.githubusercontent.com/111716161/194261273-43c0ee64-b5c0-418e-9e02-b5e42bb01d11.png)

### Bước 3: Tạo mới site

```
omd create nganthuong
```

![image](https://user-images.githubusercontent.com/111716161/194261414-b4f1faa3-ff75-4eab-b4a6-b8ebe187949e.png)

- Cài mật khẩu cho site:

```
htpasswd -m /omd/sites/nganthuong/etc/htpasswd cmkadmin
```

![image](https://user-images.githubusercontent.com/111716161/194261783-9a95b8d4-b5d7-44ae-8182-637a1f8251f5.png)

- Khởi động site:

```
omd start nganthuong
```

![image](https://user-images.githubusercontent.com/111716161/194261870-115a7124-96e6-4c65-a9d8-7c5a1e05be28.png)

### Bước 4: Truy cập checkmk server

Truy cập đường dẫn:

```
IP-VPS/nganthuong
```

![image](https://user-images.githubusercontent.com/111716161/194262638-121d2f71-aa6e-4a17-805f-81a51258524c.png)

Đăng nhập với tài khoản đã tạo.

![image](https://user-images.githubusercontent.com/111716161/194262574-c8d9a33e-7ff8-4db8-9bac-2d7bf593f6b2.png)
