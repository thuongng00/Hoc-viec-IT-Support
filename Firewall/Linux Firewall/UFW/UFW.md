Tường lửa được cấu hình đúng là một trong những khía cạnh quan trọng nhất của bảo mật hệ thống tổng thể. Theo mặc định, Ubuntu đi kèm với một công cụ cấu hình tường lửa được gọi là UFW (Tường lửa không biến đổi). 

UFW là một giao diện người dùng thân thiện để quản lý các quy tắc tường lửa iptables và mục tiêu chính của nó là làm cho việc quản lý iptables dễ dàng hơn hoặc như tên gọi không biến chứng.

# Cài đặt UFW

Tường lửa không biến chứng nên được cài đặt theo mặc định trong Ubuntu 18.04, nhưng nếu nó không được cài đặt trên hệ thống của bạn, bạn có thể cài đặt gói bằng cách gõ:

```
sudo apt install ufw
```

![image](https://user-images.githubusercontent.com/111716161/194789242-443fbff4-78f7-4cf1-b3fb-f11525106c45.png)

- Sau khi cài đặt hoàn tất, kiểm tra trạng thái của UFW:

```
sudo ufw status verbose
```

- UFW bị tắt theo mặc định. Nếu bạn chưa bao giờ kích hoạt UFW trước đó, đầu ra sẽ như thế này:

![image](https://user-images.githubusercontent.com/111716161/194789300-5786c86a-0221-496b-837f-ab27a65c51d5.png)

- Khi đó bạn phải kích hoạt thủ công:

```
sudo ufw enable
```

![image](https://user-images.githubusercontent.com/111716161/194789404-c248e4f9-6811-4a3a-a81b-a450d68b4bf3.png)

- Nếu UFW được kích hoạt, đầu ra sẽ trông giống như sau:

![image](https://user-images.githubusercontent.com/111716161/194789422-9fb76ac9-be4c-41cd-836f-928b5be049a4.png)

- Để khôi phục ufw về mặc định:

Vì một lý do nào đó bạn cần phục hồi, xóa tất cả các rule hiện có để đưa về mặc định ban đầu, hãy sử dụng tùy chọn reset để thực hiện.

```
sudo ufw reset
```

- Để vô hiệu hóa kích hoạt ufw:

```
sudo ufw disable
```

# Chính sách mặc định của UFW

Theo mặc định, UFW sẽ chặn tất cả các kết nối đến và cho phép tất cả các kết nối ra ngoài. Điều này có nghĩa là bất kỳ ai đang cố gắng truy cập máy chủ của bạn sẽ không thể kết nối trừ khi bạn mở cổng cụ thể, trong khi tất cả các ứng dụng và dịch vụ đang chạy trên máy chủ của bạn sẽ có thể truy cập vào thế giới bên ngoài.

Các chính sách mặc định được xác định trong tệp `/etc/default/ufw` và có thể được thay đổi bằng cách sử dụng:

```
sudo ufw default
```

Chính sách tường lửa là nền tảng để xây dựng các quy tắc chi tiết hơn và do người dùng xác định. Trong hầu hết các trường hợp, Chính sách mặc định UFW ban đầu là điểm khởi đầu tốt.

# Hồ sơ ứng dụng

Khi cài đặt một gói với apt nó sẽ thêm một hồ sơ ứng dụng vào thư mục `/etc/ufw/applications.d`. Hồ sơ mô tả dịch vụ và chứa các cài đặt UFW.

- Liệt kê các hồ sơ ứng dụng có sẵn trên máy chủ:

```
sudo ufw app list
```

![image](https://user-images.githubusercontent.com/111716161/194792302-be81ba5f-1a4e-49c0-b5fd-def9797a81ce.png)

- Tìm thêm thông tin về một hồ sơ cụ thể và các quy tắc bao gồm:

```
sudo ufw app info 'CUPS'
```

![image](https://user-images.githubusercontent.com/111716161/194792285-7574aa5a-e7bb-4980-9e74-8e0febd353ed.png)

# Cho phép kết nối SSH

Trước khi bật tường lửa UFW, chúng ta cần thêm một quy tắc cho phép kết nối SSH đến. Nếu bạn đang kết nối với máy chủ của mình từ một địa điểm từ xa, điều này gần như luôn luôn như vậy và bạn kích hoạt tường lửa UFW trước khi cho phép rõ ràng các kết nối SSH đến, bạn sẽ không thể kết nối với máy chủ Ubuntu của mình nữa.

Để định cấu hình tường lửa UFW của bạn để cho phép các kết nối SSH đến, hãy nhập lệnh sau:

```
sudo ufw allow ssh
```

![image](https://user-images.githubusercontent.com/111716161/194792322-bd8037ba-098e-478a-b6c3-dcfced79eda7.png)

# Sử dụng ufw để quản lý quy tắc

## Cho phép mở port kết nối

```
sudo ufw allow <port>/<optional: protocol>
```

Ví dụ: Sử dụng ufw để mở cổng 80, 443, 8080:

```
sudo ufw allow 80/tcp

sudo ufw allow https

sudo ufw allow 8080/tcp
```

![image](https://user-images.githubusercontent.com/111716161/194791241-ec672523-a928-49c6-987d-c1a4243c1388.png)

## Từ chối, đóng port kết nối

```
sudo ufw deny <port>/<optional: protocol> 
```

Ví dụ: đóng cổng kết nối là 3306 và 8080

```
sudo ufw deny 3306
sudo ufw deny 8080
```

Ngoài ra ufw còn hỗ trợ cú pháp đơn giản như sau. Nếu bạn xác định được cổng thuộc dịch vụ nào bạn có thể deny dịch vụ thay vì cổng thuộc dịch vụ đó.

```
sudo ufw deny mysql
```

## Cho phép IP truy cập đến cổng nhất định

Với cú pháp này sẽ cho phép một IP cụ thể được quyền truy cập vào cổng đã được chỉ định. 

```
sudo ufw allow from 192.168.0.1 to any port 22
sudo ufw allow from 192.168.0.1 to any port 3306
```

## Xóa bỏ các quy tắc

Để quản lý các quy tắc trên UFW của bạn, bạn có thể liệt kê chúng ra theo dạng menu danh sách. Để thực hiện được bạn sử dụng lệnh sau, màn hình hiển thị các quy tắc kèm số thứ tự và bạn sẽ chọn các số thứ tự hoặc tên quy tắc để xoá bỏ.

```
sudo ufw status numbered
```

![image](https://user-images.githubusercontent.com/111716161/194791865-d8256ca0-77ea-4311-87e8-701588f54732.png)

- Dùng lệnh sau để xóa:

```
sudo ufw delete [number]
```

![image](https://user-images.githubusercontent.com/111716161/194791926-d5939de4-844f-4a5c-aaec-ae75b3544bc8.png)

## Cho phép phạm vi cổng

UFW cho phép bạn truy cập vào phạm vi cổng kết nối thay vì bạn mở cho từng cổng riêng biệt. Và khi bạn cho phép phạm vi cổng bạn cần xác định phạm vi cổng thuộc giao thức TCP hay là UDP để mở.

```
sudo ufw allow 35000:35999/tcp
sudo ufw allow 35000:35999/udp
```

![image](https://user-images.githubusercontent.com/111716161/194792091-5ca159ea-f97c-472b-8df0-a6dadbee6c9f.png)

## Đóng phạm vi cổng

```
sudo ufw deny 35000:35999/tcp
sudo ufw deny 35000:35999/udp
```

![image](https://user-images.githubusercontent.com/111716161/194792138-2a081296-b9f2-4b1a-a044-b0c08cf2ddba.png)

## Cho phép và từ chối IP

- Để cho phép, mở IP bạn sử dụng lệnh:

```
sudo ufw allow from $Your_IP
```

- Để từ chối IP truy cập bạn sử dụng lệnh:

```
sudo ufw deny from $Your_IP
```

