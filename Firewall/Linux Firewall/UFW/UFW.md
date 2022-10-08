Tường lửa được cấu hình đúng là một trong những khía cạnh quan trọng nhất của bảo mật hệ thống tổng thể. Theo mặc định, Ubuntu đi kèm với một công cụ cấu hình tường lửa được gọi là UFW (Tường lửa không biến đổi). 

UFW là một giao diện người dùng thân thiện để quản lý các quy tắc tường lửa iptables và mục tiêu chính của nó là làm cho việc quản lý iptables dễ dàng hơn hoặc như tên gọi không biến chứng.

# Cài đặt UFW

Tường lửa không biến chứng nên được cài đặt theo mặc định trong Ubuntu 18.04, nhưng nếu nó không được cài đặt trên hệ thống của bạn, bạn có thể cài đặt gói bằng cách gõ:

```
sudo apt install ufw
```

- UFW bị tắt theo mặc định. Nếu bạn chưa bao giờ kích hoạt UFW trước đó, đầu ra sẽ như thế này:

```
Status: inactive
```

- Nếu UFW được kích hoạt, đầu ra sẽ trông giống như sau:

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

- Tìm thêm thông tin về một hồ sơ cụ thể và các quy tắc bao gồm:

```
sudo ufw app info 'Nginx Full'
```

# Cho phép kết nối SSH

Trước khi bật tường lửa UFW, chúng ta cần thêm một quy tắc cho phép kết nối SSH đến. Nếu bạn đang kết nối với máy chủ của mình từ một địa điểm từ xa, điều này gần như luôn luôn như vậy và bạn kích hoạt tường lửa UFW trước khi cho phép rõ ràng các kết nối SSH đến, bạn sẽ không thể kết nối với máy chủ Ubuntu của mình nữa.

Để định cấu hình tường lửa UFW của bạn để cho phép các kết nối SSH đến, hãy nhập lệnh sau:

```
sudo ufw allow ssh
```

# Kích hoạt UFW

```
sudo ufw enable
```

Bạn sẽ được cảnh báo rằng việc bật tường lửa có thể phá vỡ các kết nối ssh hiện có, chỉ cần gõ y và nhấn Enter .

# Cho phép kết nối trên các cổng khác

## Mở cổng 80 - http

Kết nối HTTP có thể được cho phép bằng lệnh sau:

```
sudo ufw allow
```

thay vì http, bạn có thể sử dụng số cổng, 80:

```
sudo ufw allow 80/tcp
```


