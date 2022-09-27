# Giao diện quản trị Kerio Connect

### 1. Accounts

- Users

Tạo User theo tên miền và thiết lập cho user

![image](https://user-images.githubusercontent.com/111716161/192244122-221be043-b3c6-4c80-bf8e-3fe733813dc7.png)

- Groups

Tạo groups, xóa group và thiết lập cấu hình cho các group theo tên miền và gán group cho user

![image](https://user-images.githubusercontent.com/111716161/192245577-c01410e4-405c-4365-8a84-114b973eb352.png)

- Aliases

Tạo Alias (bí danh) theo tên miền cho user

![image](https://user-images.githubusercontent.com/111716161/192245685-ea1e47fb-b15b-4b25-8ebb-5ce978db6f31.png)

- Mailing list

Quản lý danh sách thư

![image](https://user-images.githubusercontent.com/111716161/192409210-e2880fa7-3cea-40af-8e3d-0341c847c6b2.png)

- Resources 

Quản lý tài nguyên

![image](https://user-images.githubusercontent.com/111716161/192409470-f30dac33-a2bd-4755-93db-629464adae5b.png)

### 2. Status

- Dashboard

Tại Dashboard hiển thị các thông tin: 

`Kerio News`: Giới thiệu về các chức năng mới trong phiên bản hiện tại.

`System`: Hiện thị thông tin phiên bản Kerio-connect, hệ điều hành và hostname.

`System status`: Hiển thị trạng thái của hệ thống.

`License Details`: Giấy phép.

`Kerio Antivirus`: Hiển thị trạng thái của Kerio Antivirus.

`System Health`: Hiển thị RAM, CPU, Disk của hệ thống dưới dạng biểu đồ (%, time).

`Disk Storage Info`: Hiển thị dung lượng Disk tổng và dung lượng Disk đang được sử dụng.

![image](https://user-images.githubusercontent.com/111716161/192411076-c45dff7d-5a7b-4fa6-9333-80ae884a4a1d.png)

- Message Queue

`Messages in Queue`: Hiển thị các thư đang được chờ trên hàng đợi để được gửi ra bên ngoài.

`Message Queue Processing`: Tiến trình xếp hàng thư.

![image](https://user-images.githubusercontent.com/111716161/192411109-c819027a-56ac-47bf-833c-b913bf7048f7.png)

- Traffic Chart

Tracffic Chart cho phép hiển thị các thông tin Connection hoặc các Message trong một khoảng thời gian (có thể tùy chỉnh tối đa 30 ngày).

![image](https://user-images.githubusercontent.com/111716161/192411208-c1e4a6ca-3d28-4dbc-ab67-218e4e1f5ebb.png)

- Statistics

Hiển thị các số liệu thống kê của hệ thống.

![image](https://user-images.githubusercontent.com/111716161/192411502-1c83d663-bee3-44a7-a77e-dcb5846483b3.png)

- Active Connections

Hiển thị các Connection và các Session đang hoạt động.

![image](https://user-images.githubusercontent.com/111716161/192411901-5e5779f4-f4f6-41d3-a138-be25da6df5da.png)

- Opened Folders

Hiển thị các thư mục đã mở.

![image](https://user-images.githubusercontent.com/111716161/192411951-055d6de0-8cd9-4fa1-bd74-a3910ba4cd5a.png)

-  System Health

Hiển thị mức độ sử dụng Ram, CPU của hệ thống, tổng dung lượng disk và dung lượng disk đã sử dụng.

![image](https://user-images.githubusercontent.com/111716161/192411991-5523123f-da91-4d51-8fff-9dfa7f331ef5.png)

### 3. Configuration

- Services

Hiển thị các dịch vụ, port và trạng thái các dịch vụ của mail server.

![image](https://user-images.githubusercontent.com/111716161/192412089-7e043dba-3f48-4cdd-8736-c704d913328d.png)

- Domains

Hiển thị các domain đã được tạo, tại đây có thể tạo, sửa, xóa domain và thiết lập các tùy chọn cho domain đó.

![image](https://user-images.githubusercontent.com/111716161/192412193-ebcd7172-e9a1-4392-9e21-baf12ab8f1f0.png)

-  SMTP server
   - Máy chủ SMTP xác định ai có thể gửi thư đi qua Kerio Connect và họ có thể thực hiện những hành động nào.
   - Để thiết lập gửi tin nhắn từ bên ngoài server Kerio Connect ta làm như sau: 
      - Trong giao diện Configuration chọn SMTP server -> Relay Control
      - Nhấp vào option Allow relay only for:
         - Để chỉ định một nhóm địa chỉ IP mà từ đó người dùng có thể gửi đi, chọn Users from IP address group và thiết lập như mong muốn.
         - Để cho phép người dùng đã xác thực gửi thư đi, chọn User authenticated through SMTP for outgoing mail.
         - Để cho phép người dùng đã xác thực trước đó qua POP3 gửi thư đi từ cùng một địa chỉ IP, chọn Users previously authenticated through POP3 from the same IP address.
         - Nhấp vào Apply để lưu thiết lập.

![image](https://user-images.githubusercontent.com/111716161/192413147-4f059937-a0e1-4bba-9ee7-4ae1f7c442fb.png)

- Instant Messaging

Dịch vụ trò chuyện tức thời trên Kerio Connect.

![image](https://user-images.githubusercontent.com/111716161/192413264-de3eb1df-3547-4dae-bc21-478f0dee3d16.png)

### 4. Log

- Config log

Lưu giữ lịch sử đầy đủ của các thay đổi điều chỉnh config. Nó cho ta biết người dùng nào đã thực hiện các tác vụ quản trị cá nhân và thời gian người đó thực hiện.

![image](https://user-images.githubusercontent.com/111716161/192415060-0e733edf-57cf-45dd-abf8-1f2be4de894f.png)

- Debug log

Giám sát nhiều loại thông tin khác nhau và được sử dụng để giải quyết vấn đề.

![image](https://user-images.githubusercontent.com/111716161/192415396-fae3ed25-21a5-4b9b-a12e-b4cfd1465b36.png)

- Error log

Hiển thị các lỗi có ý nghĩa quan trọng, thường ảnh hưởng đến hoạt động của mail server. Thông báo lỗi điển hình được hiển thị trong lần khởi tạo dịch vụ liên quan đến Error log, phân bổ dung lượng đĩa, khởi tạo kiểm tra chống virus, xác thực người dùng không đúng cách ...

![image](https://user-images.githubusercontent.com/111716161/192415419-1055b773-123b-4b90-b2d4-af07c8e294c5.png)

- Mail log

Chứa thông tin về các thư riêng lẻ được Kerio Connect xử lý.

- Operations log

Thu thập thông tin về các mục đã loại bỏ và di chuyển (thư mục, tin nhắn, danh bạ, sự kiện, tác vụ và ghi chú) trong hộp thư người dùng. Nó rất hữu ích, đặc biệt nếu người dùng không thể tìm thấy một thư cụ thể trong hộp của họ.

- Security log

Chứa thông tin liên quan đến bảo mật của Kerio Connect. Nó cũng chứa các bản ghi về tất cả các thư không gửi được.

- Spam log

Hiển thị thông tin về tất cả các email spam được lưu trữ (hoặc được đánh dấu) trong Kerio Connect.

- Warning log

Hiển thị các thông báo cảnh báo về các lỗi có ý nghĩa nhỏ. Các sự kiện hiển thị trong Security log không ảnh hưởng nhiều đến hoạt động của Kerio Connect.

- Audit log

Hiển thị thông tin về tất cả các lần xác thực thành công tài khoản Kerio Connect, bao gồm quản trị Kerio Connect, Kerio Connecy Client, Microsoft Outlook...
