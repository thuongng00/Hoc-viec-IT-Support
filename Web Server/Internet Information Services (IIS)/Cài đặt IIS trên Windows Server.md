# Mục lục

[Cấu hình IIS](#iis)

[Tạo một trang web mới trong Windows IIS 10](#taoweb)

IIS 10.0 trên Windows Server 2016  được thiết kế để trở thành một nền tảng Web và ứng dụng linh động và an toàn nhất cho Microsoft. Microsoft đã thiết kế lại IIS từ những nền tảng đã có trước đó và trong suốt quá trình phát triển, nhóm thiết kế IIS đã tập trung vào 5 lĩnh vực lớn:

- Bảo mật ( Có thể sử dụng SSL để tăng độ mã hóa và tin cậy cho website ) 
- Khả năng mở rộng 
- Cấu hình và triển khai 
- Quản trị và chuẩn đoán 
- Hiệu suất cao

<a name="iis"></a>

# Cấu hình IIS Web Server trên Windows Server 2016

Bước 1: Trên màn hình làm việc của Server Manager nhấn "Add roles and features", hoặc vào Manage rồi nhấn chọn. 

![image](https://user-images.githubusercontent.com/111716161/189834895-2d3d7f8b-7277-4be7-b5c9-11a121724a76.png)

Bước 2: Chọn Server Roles, bật tùy chọn Web Server. 

![image](https://user-images.githubusercontent.com/111716161/189829464-20a363b8-e5c1-41b1-a834-e9009b7e9ac2.png)

Bước 3: Nhấn Add features, sau đó nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189829716-180e5271-2c4e-4082-a9b1-729938dc9429.png)

Bước 4: Tiếp theo, chọn Next đến phần Role Service. Tùy theo nhu cầu triển khai dịch vụ mà bạn có thể chọn các roles cho phù hợp. Nhấn Next. 

![image](https://user-images.githubusercontent.com/111716161/189830102-53e7b574-3896-4b3e-8998-7465469d069c.png)

Bước 5: Nhấn Install để cài đặt.

![image](https://user-images.githubusercontent.com/111716161/189830250-d34df63a-2a6c-4b65-9e88-98566ead9c2c.png)

Chờ cho quá trình cài đặt hoàn tất. 

![image](https://user-images.githubusercontent.com/111716161/189830470-2e351736-f2e1-4ec2-9b46-d97f79471824.png)

Bước 6: Nhấn Close. Như vậy ta đã cài đặt xong IIS.

![image](https://user-images.githubusercontent.com/111716161/189830629-bb1756fe-a33f-458e-b3ac-16d3dfdf813a.png)

<a name="taoweb"></a>

# Tạo một trang web mới trong Windows IIS 10

Bước 1: Mở Trình quản lý IIS.

Vào Server manager chọn "Tools" chọn "Internet Infomation Services (IIS) Manager".

![image](https://user-images.githubusercontent.com/111716161/189846791-94d5833e-5ee9-40ff-9948-f605b72381fa.png)

Bước 2: Thêm trang Web

Mở rộng thư mục máy tính của bạn bằng cách nhấp vào > ở bên trái của biểu tượng trong khung bên trái. Sau đó, nhấp chuột phải Các trang web và chọn Thêm trang web...

![image](https://user-images.githubusercontent.com/111716161/189852767-08fc89e6-9a10-443a-987d-5908df3df7a0.png)

Bước 3: Tạo tên trang web.

Mô hình Thêm trang web cửa sổ sẽ mở ra. Đầu tiên, thêm một tên dễ nhớ cho trang web trong Tên trang web trường.

![image](https://user-images.githubusercontent.com/111716161/189853914-8e0a66e3-bf1e-40d6-a4aa-e8c2783a32a2.png)

Bước 4: Thêm đường dẫn vật lý.

Điều hướng đến thư mục chứa các tệp trên trang web của bạn để nó xuất hiện trong Con đường vật lý trường.

![image](https://user-images.githubusercontent.com/111716161/190038672-c4130dd7-8ff3-48c0-83b2-797ec8e36011.png)

Bước 5: Đặt tùy chọn ràng buộc.

Theo Binding, chọn nút Kiểu (HTTP hoặc HTTPS), Địa chỉ IP, Port và Tên máy chủ.

![image](https://user-images.githubusercontent.com/111716161/190038893-dc880898-f471-4a1f-84b3-510977f109a1.png)

Bước 6: Quyết định có bắt đầu trang web hay không.

Nếu bạn muốn bắt đầu trang web ngay lập tức, hãy chắc chắn rằng Bắt đầu trang web ngay lập tức được kiểm tra. Nếu không, bỏ chọn nó.

![image](https://user-images.githubusercontent.com/111716161/190038959-11cf4db6-e824-4c6c-b8c6-86badd63e488.png)

Bước 7: Kết thúc.

Nhấn vào OK nút để hoàn thành việc tạo trang web mới của bạn.

![image](https://user-images.githubusercontent.com/111716161/190039043-f3f2923b-196c-4172-afa5-2d8a89798208.png)

Sau Thêm trang web cửa sổ đóng lại, bạn sẽ có trang web mới của mình trong danh sách các trang web. Tại thời điểm này, bạn có thể sẽ muốn bảo vệ trang web mới của mình bằng SSL /TLS chứng chỉ và triển khai các dịch vụ web.
