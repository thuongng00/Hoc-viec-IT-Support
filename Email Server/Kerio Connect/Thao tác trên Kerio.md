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

# Các thao tác cơ bản trên Kerio Connect

### 1. Thêm domain mới

Vào Configuration -> Domain -> Add -> Local Domain...

![image](https://user-images.githubusercontent.com/111716161/192424386-362fa569-f972-494e-93f1-72fa808f9cf4.png)

- Tab General
   - Domain: tên domain của bạn.
   - Description: mô tả về domain.
   - Limit maximum number of users in the domain: Giới hạn số user trong domain.

![image](https://user-images.githubusercontent.com/111716161/192425152-59254203-973c-48a6-8304-8772c254dadd.png)

- Tab Sercurity

![image](https://user-images.githubusercontent.com/111716161/192425267-32d65c8d-6dc5-4bcf-9627-26a9884f87a6.png)

- Tab Message

![image](https://user-images.githubusercontent.com/111716161/192425348-1aba4cef-7d68-4392-9fce-d13d43415ba7.png)

- Tab Custom Logo

![image](https://user-images.githubusercontent.com/111716161/192425467-677164ba-928c-443d-b2b9-d0c1ada895eb.png)

Muốn set domain nào thành domain chính thì nhấn chuột phải vào domain, chọn Set as Primary.

![image](https://user-images.githubusercontent.com/111716161/192425717-0ef6b962-95fe-4b08-b723-7087f6a7650f.png)

### 2. Thêm User mới

Vào Account -> User -> Chọn domain -> Add

![image](https://user-images.githubusercontent.com/111716161/192428040-9595d08b-e1c5-4968-ba5b-f6ced9b55cee.png)

- Tab General

![image](https://user-images.githubusercontent.com/111716161/192428275-a4d7aee4-11b2-4397-b0d8-06931e2883f0.png)

- Tab Contact

![image](https://user-images.githubusercontent.com/111716161/192428418-63b5d7a4-5715-48b7-8016-591189d5e2bc.png)

- Tab Groups

![image](https://user-images.githubusercontent.com/111716161/192428784-0d3a420b-48d1-48ad-aaa1-aa7ab32760cd.png)

- Tab Right

![image](https://user-images.githubusercontent.com/111716161/192428849-5faa17e6-35bd-425c-a7d6-7d922d80b5fe.png)

- Tab Quota

![image](https://user-images.githubusercontent.com/111716161/192429034-e7aba9cc-72ef-44ab-8c0d-dc116d913d4b.png)

- Tab Message

![image](https://user-images.githubusercontent.com/111716161/192428958-d7e30579-68ca-4738-915e-f9ee5436123e.png)

Đăng nhập trang quản trị bằng user vừa tạo.

![image](https://user-images.githubusercontent.com/111716161/192429654-e85c2e0c-9eb1-4284-a07c-31e6caded410.png)

Đăng nhập thành công.

![image](https://user-images.githubusercontent.com/111716161/192429716-42815708-62fa-4c0c-9657-7251cd1153ab.png)

### 3. Gửi mail 

Gửi mail từ user vừa tạo đến admin.

- Đăng nhập vào user vừa tạo, soạn mail. 

![image](https://user-images.githubusercontent.com/111716161/192434193-84e50eb3-7b3d-42ed-b7d4-43cb10ae0e95.png)

- Gửi mail

![image](https://user-images.githubusercontent.com/111716161/192434309-eb4bf887-a9cd-4ec8-a7ee-97db078fe94f.png)

- Đăng nhập tài khoản admin để kiểm tra. 

