IIS 10.0 trên Windows Server 2016  được thiết kế để trở thành một nền tảng Web và ứng dụng linh động và an toàn nhất cho Microsoft. Microsoft đã thiết kế lại IIS từ những nền tảng đã có trước đó và trong suốt quá trình phát triển, nhóm thiết kế IIS đã tập trung vào 5 lĩnh vực lớn:

- Bảo mật ( Có thể sử dụng SSL để tăng độ mã hóa và tin cậy cho website ) 
- Khả năng mở rộng 
- Cấu hình và triển khai 
- Quản trị và chuẩn đoán 
- Hiệu suất cao

# Cấu hình IIS Web Server trên Windows Server 2016

Bước 1: Trên màn hình làm việc của Server Manager nhấn "Add roles and features", hoặc vào Manage rồi nhấn chọn. 

![image](https://user-images.githubusercontent.com/111716161/189829055-8eb76e99-ce76-4611-9335-3a7ad6a3f66c.png)

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

