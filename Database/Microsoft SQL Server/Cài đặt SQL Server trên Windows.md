# Cài đặt SQL Server

Bước 1: Tải SQL Server về máy.

Để cài đặt Microsoft SQL Server hệ thống cần những yêu cầu sau:

- Os : Windows 7 (32 bit hoặc 64 bit) trở lên.
- CPU :  Pentium IV trở lên.
- Ram : Ít nhất 1GB.
- Ổ đĩa trống: Ít nhất 10GB.
- .NET Framework: Phiên bản 3.5 SP1 .

Link tải SQL Server 2019: https://www.microsoft.com/en-us/sql-server/sql-server-downloads

![image](https://user-images.githubusercontent.com/111716161/191170247-4e5c958e-6ecf-41e6-9587-842a7c322112.png)

Bước 2: Mở ứng dụng đã tải về

![image](https://user-images.githubusercontent.com/111716161/191170299-4cb11f99-3258-4082-920a-9f231ea889ee.png)

Bước 3: Sau khi mở ứng dụng, ta có 3 tùy chọn tùy theo mục đích của người sử dụng.

- Basic: đây là tùy chọn đơn giản nhất cho người dùng, tại đây ứng dụng sẽ tự động cài đặt các chức năng cơ bản.
- Custom: đây là phần cài đặt cho người dùng muốn sử dụng chuyên sâu hơn, khi chọn sẽ được tự cài đặt các cấu hình của phần mềm.
- Download Media: khi chọn vào mục này, hệ thống sẽ tải về một file cài đặt offline nhằm mục đích cài được trên nhiều thiết bị khác nhau mà không cần load lại từ đầu.

![image](https://user-images.githubusercontent.com/111716161/191170404-10366e8d-eb7f-4785-9bf4-1992c71a12af.png)

Với người dùng thông thường nên chọn Basic.

Bước 4: Nhấn Accept để đồng ý với các điều khoản sử dụng. 

![image](https://user-images.githubusercontent.com/111716161/191170688-8efbb007-13e9-4639-8d09-23fef5806dc7.png)

Bước 5: Chọn vị trí cài đặt tại Install location. 

![image](https://user-images.githubusercontent.com/111716161/191170771-2936d38b-a9f9-4cd4-9b18-2cf7991b7248.png)

Bước 6: Nhấn Install để cài đặt.

![image](https://user-images.githubusercontent.com/111716161/191170895-691ce8e4-291e-4e54-a0b3-37363a0c2e04.png)

![image](https://user-images.githubusercontent.com/111716161/191170928-4c2a1d08-f884-4814-a6af-d6d57aba7827.png)

Bước 7: Sau khi quá trình cài đặt xog sẽ tới màn hình thiết lập cài đặt, nhấn Customize. 

![image](https://user-images.githubusercontent.com/111716161/191184205-4be138d0-1395-4c32-9821-9cfd2d48fc9e.png)

Bước 8: Chọn Next ở màn hình Microsoft Update

![image](https://user-images.githubusercontent.com/111716161/191185269-fc3b40ae-f688-4c41-bfc9-e9fe7b9b7721.png)

Bước 9: Hệ thống sẽ kiểm tra xem các mục đã đạt yêu cầu chưa

Dấu tích xanh là đã ổn và thường thì mục Firewall sẽ màu vàng cảnh báo là nó có thể ảnh hưởng đến quá trình cài đặt, riêng mục này có thể bỏ qua và tiếp tục bấm next.

![image](https://user-images.githubusercontent.com/111716161/191185479-8177a39f-e07f-4f65-8cad-4d295bc1defb.png)

Bước 10: Nhấn Next ở mục Installation Type.

![image](https://user-images.githubusercontent.com/111716161/191185733-c4816370-6164-4d2e-b2c3-a921a09dc101.png)

Bước 11: Tiếp tục nhấn Next

![image](https://user-images.githubusercontent.com/111716161/191185830-bcf13b6b-ebb2-43e2-b51a-9490fc9d400d.png)

Bước 12: Chọn "I accept the license terms and Privacy Statement".

![image](https://user-images.githubusercontent.com/111716161/191185896-02c73aa9-64bd-4696-a3db-22caee43063b.png)

Bước 13: Ở màn hình Feature Selection, bạn có thể chọn Select All hoặc chọn một số tính năng tối thiểu (có thể dùng trong việc học các môn CSDL) như:

- Database Engine Services
- Data Quality Client
- Client Tools Connectivity

![image](https://user-images.githubusercontent.com/111716161/191186181-de576b09-15f3-4cb5-870e-1a320da10935.png)

Chọn Next để chuyển đến màn hình Instance Congifuration

Bước 14: Chọn Default instance hoặc Named instance (trong một số trường hợp cài SQL Server từ lần thứ hai bắt buộc phải thiết đặt lại field Name instance này). Nhấn Next để tiếp tục. 

![image](https://user-images.githubusercontent.com/111716161/191186440-32c54457-0615-42bf-9a55-8bb7a27b5be8.png)

Bước 15: Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/191186569-541ca44f-0b27-4dd1-9678-5012e6d13e3f.png)

Bước 16:  Ở màn hình Database Engine Configuration, chọn Mixed Mode và thiết lập password cho tài khoản > Add Current User để thêm user quản lý SQL vào ô "Specify SQL Server administrators". Nhấn Next để tới màn hình tiếp theo

![image](https://user-images.githubusercontent.com/111716161/191186874-29cd44a3-93ff-49a2-baa9-8fa412c7353b.png)

Bước 17: Nhấn Install.

![image](https://user-images.githubusercontent.com/111716161/191187125-622bfc4d-1ffe-42fc-9a5a-7cfadc792ee5.png)

Bước 18: Đợi đến khi file cài đặt xong và bấm close để hoàn tất.
