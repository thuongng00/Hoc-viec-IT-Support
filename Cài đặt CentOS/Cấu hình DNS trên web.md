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


