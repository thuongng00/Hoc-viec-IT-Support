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



