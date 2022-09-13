# Mục lục

[Cấu hình IIS](#iis)

[Triển khai dịch vụ web với IIS trên Windows server](#web)

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

<a name="web"></a>
# Triển khai dịch vụ web với IIS trên Windows server 2016

Bước 1: Sau khi cài đặt xong IIS, để quản trị dịch vụ, vào Server manager chọn "Tools" chọn "Internet Infomation Services (IIS) Manager".

![image](https://user-images.githubusercontent.com/111716161/189846791-94d5833e-5ee9-40ff-9948-f605b72381fa.png)

Bước 2: Trong Default Web Site, chọn Default Document.

![image](https://user-images.githubusercontent.com/111716161/189831240-50051032-4618-4290-807d-a836d00cc485.png)

Bước 3: Default Document quy định tên trang chủ mà bạn sẽ sử dụng cho web site của mình.

![image](https://user-images.githubusercontent.com/111716161/189831654-2e4c5021-d072-4774-a037-029053feb1af.png)

Bước 4: Thư mục chứa web site mặc định khi cài dịch vụ là C:\inetpub\wwwroot. Nếu bạn không có các tùy chỉnh riêng, bạn chỉ cần bỏ trực tiếp web site mà bạn đã thiết kế vào đây.

![image](https://user-images.githubusercontent.com/111716161/189831974-b4de6a43-959c-44fd-a6d3-5a6a03af9e23.png)

Bước 5: Mặc định thư mục C:\inetpub\wwwroot chứa file iisstart. Khi đó, nếu bạn truy cập vào địa chỉ IP của máy chứa website bạn sẽ thấy nội dung của file này.

![image](https://user-images.githubusercontent.com/111716161/189832739-0c6d82e3-9043-4f0e-9898-2e033bfa4267.png)

Bạn tiến hành dùng notepad để tạo một file index.html trong C:\inetpub\wwwroot. Đây là dạng tên file đã được quy định ở phần Default Document.

![image](https://user-images.githubusercontent.com/111716161/189833525-250096f3-e369-4fe7-b577-741f74f2d694.png)

Bước 6: Để có thể truy cập web site bằng tên (DNS Name), bạn sẽ tiến hành tạo một record CNAME trong dịch vụ DNS của Domain Controller.

- Vào Tools, chọn DNS. Nhấn chuột phải vào tên dns, chọn New Alias (CNAME).

![image](https://user-images.githubusercontent.com/111716161/189847515-fc4b6815-e4c2-4287-b6d3-10837152d147.png)

- Tạo Record trên DNS

![image](https://user-images.githubusercontent.com/111716161/189848318-1cb625df-521e-4108-91ca-8584dcbbbf00.png)

- Sau khi tạo xong record trên DNS, bạn có thể truy cập bằng tên đến website. Bây giờ chúng ta sẽ thấy nội dung trang index.html mà ta đã tạo ra khi nảy trong thư mục C:\interpub\wwwroot, trang này đã thay thế trang iisstart ban đầu khi mới cài đặt dịch vụ IIS.

![image](https://user-images.githubusercontent.com/111716161/189848609-be964296-ca3b-4085-bd8f-dd55b1215b42.png)

Như vậy, chúng ta đã hoàn thành việc cài đặt dịch vụ IIS và triển khai web site một cách cơ bản.

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

![image](https://user-images.githubusercontent.com/111716161/189855070-b7f05de7-5d7c-40cd-a2f1-e6c1b77744ed.png)

Bước 5: Đặt tùy chọn ràng buộc.

Theo Binding, chọn nút Kiểu (HTTP hoặc HTTPS), Địa chỉ IP, Port và Tên máy chủ.

![image](https://user-images.githubusercontent.com/111716161/189855562-f84685b8-ec32-4814-a1aa-9038dbf9f77e.png)

Bước 6: Quyết định có bắt đầu trang web hay không.

Nếu bạn muốn bắt đầu trang web ngay lập tức, hãy chắc chắn rằng Bắt đầu trang web ngay lập tức được kiểm tra. Nếu không, bỏ chọn nó.

![image](https://user-images.githubusercontent.com/111716161/189855758-1cceb959-f71d-456c-80f0-a5baee2edbc3.png)

Bước 7: Kết thúc.

Nhấn vào OK nút để hoàn thành việc tạo trang web mới của bạn.

Sau Thêm trang web cửa sổ đóng lại, bạn sẽ có trang web mới của mình trong danh sách các trang web. Tại thời điểm này, bạn có thể sẽ muốn bảo vệ trang web mới của mình bằng SSL /TLS chứng chỉ.
