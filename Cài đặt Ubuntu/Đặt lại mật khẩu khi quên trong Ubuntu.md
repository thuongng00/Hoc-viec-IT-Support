Bước 1: Khởi động lại Hệ điều hành Ubuntu của bạn và vào menu GRUB bằng cách giữ phím Shift trên bàn phím.

Bước đầu tiên là khởi động máy tính của bạn và tiếp tục nhấn nút shift trên bàn phím của bạn cho đến khi menu GRUB xuất hiện, như thể hiện trong hình dưới đây:

![image](https://user-images.githubusercontent.com/111716161/187326680-5130e28f-9fdd-4373-9c61-cf786728b339.png)

Bước 2: Nhấn ‘e’ để vào nơi chỉnh sửa các lệnh

![image](https://user-images.githubusercontent.com/111716161/187326711-7a25a41a-8494-4270-8042-9edaddeec939.png)

Bước 3: Chỉnh sửa nội dung của dòng cuối cùng thứ hai từ “ ro quiet splash $vt_handoff ”thành ‘rw init = / bin / bash’

Trước khi chỉnh sửa

![image](https://user-images.githubusercontent.com/111716161/187326728-b79ca9df-6117-4756-a382-e570c3692983.png)

Sau khi chỉnh sửa

![image](https://user-images.githubusercontent.com/111716161/187326774-306c2207-a7a2-4dd8-8f91-d39549c0fb06.png)

Bước 4: Nhấn F10 hoặc Ctrl-x để lưu các chỉnh sửa và khởi động

Nhấn F10 hoặc CTRL + X để lưu và khởi động hệ thống. Sau khi khởi động lại, màn hình nhắc lệnh shell của root sẽ xuất hiện, như trong hình bên dưới:

![image](https://user-images.githubusercontent.com/111716161/187326802-972de38d-98cb-4cba-9efa-3ed3ee2229b1.png)

Bước 5: Gõ lệnh ‘mount | grep -w / ’để xác nhận quyền truy cập đọc và ghi

![image](https://user-images.githubusercontent.com/111716161/187326823-87baa103-7aa4-454c-937f-af433432a0c0.png)

Bước 6:  Nhập lệnh ‘passwd’ và đặt mật khẩu mới cho thư mục gốc

![image](https://user-images.githubusercontent.com/111716161/187326842-3c81aad6-b01a-40eb-a914-3c80c5c043cc.png)

Bước 7: Gõ lệnh ‘execute / sbin / init’ để khởi động lại Hệ điều hành Ubuntu của bạn
