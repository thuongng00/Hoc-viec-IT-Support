### 1. Truy cập Teminal CenOS 7 với quyền root với câu lệnh
```
sudo -i
```
![image](https://user-images.githubusercontent.com/111716161/188358270-ca6f7bc9-2a10-4148-916b-8bbfc22feac3.png)

### 2. Do Apache đã có sẵn trong kho lưu trữ CentOS mặc định nên việc cài đặt khá đơn giản. Để cài đặt Apache hãy chạy lệnh sau:

```
yum install httpd -y
```

![image](https://user-images.githubusercontent.com/111716161/188358417-d00f34e4-f0c2-4e86-b340-94c4373a7411.png)

### 3. Sau khi cài đặt hoàn tất, tiến hành khởi động Apache bằng cách khởi động lại nó bằng các lệnh sau :
```
systemctl enable httpd
systemctl start httpd
```

![image](https://user-images.githubusercontent.com/111716161/188358524-4ebccdd3-ea77-40d7-a566-6772c2d55139.png)

*Để kiểm tra trạng thái apache chúng ta sử dụng câu lệnh ``systemctl status httpd``*

![image](https://user-images.githubusercontent.com/111716161/188358612-daaa8c7f-f825-4da5-ac68-0aaa89a925b5.png)

### 4. Cấu hình firewall (nếu có)

Nếu các bạn sử dụng Firewalld để có thể truy cập được website các bạn sẽ cần mở port bằng các lệnh sau đây:
```
firewall-cmd --permanent --zone=public --add-service=http
firewall-cmd --permanent --zone=public --add-service=https
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/111716161/188358800-d3531ad8-f707-4311-8354-d7032b2fff0e.png)
