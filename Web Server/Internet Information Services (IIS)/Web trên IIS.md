# Triển khai dịch vụ web cơ bản với IIS trên Windows server

<a name="html"></a>
## 1. Web html
Bước 1: Để quản trị dịch vụ, vào Server manager chọn "Tools" chọn "Internet Infomation Services (IIS) Manager".

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

## 2. Web ASP .NET

Bước 1: Vào Start / Control Panel / Chọn Turn Windows features on or off.

![image](https://user-images.githubusercontent.com/111716161/190044127-f8422e13-2d92-4aa4-9ac3-2dcefea40114.png)

Bước 2: Chọn các dịch vụ cần cài đặt. Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/190044322-770e2886-b96d-4f8e-8ee8-3fbafc1ed2d4.png)

Bước 3: Tiếp tục chọn. Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/190044490-d192f216-d8f2-4a94-9990-b9bca9c4e897.png)

Bước 4: Nhấn Install và chờ cho quá trình cài đặt hoàn tất.

![image](https://user-images.githubusercontent.com/111716161/190044549-4b087735-a5f5-4021-b4fb-f6ccb14cd414.png)

Bước 5: Mở Command Prompt với quyền Administrator, chuyển đến đường dẫn `C:/Windows/Microsoft.NET/Framework/v4.0.30319`, đăng ký asp.net vào hệ thống với mã lệnh `aspnet_regiis –i`

![image](https://user-images.githubusercontent.com/111716161/190047202-82abba21-6f25-4272-913f-0e2f93bb7038.png)

Bước 6: Mở IIS bằng cách vào Server Manager/ Tools / chọn Internet Information Services (IIS) Manager.

![image](https://user-images.githubusercontent.com/111716161/190047541-7a646adc-bae0-4300-9a3b-afd250944879.png)

Bước 7: Bạn tiến hành dùng notepad để tạo một file index.aspx trong C:\inetpub\wwwroot. Đây là dạng tên file đã được quy định ở phần Default Document.

![image](https://user-images.githubusercontent.com/111716161/190063102-319af005-8ada-42a2-81ad-ccd8736cf516.png)

Bước 8: Vào Default Document, chọn Add, thêm file vừa tạo. 

![image](https://user-images.githubusercontent.com/111716161/190063307-ab2b9b86-c3e4-4684-abdf-743a4b6d4205.png)

Bước 9: Truy cập website.

![image](https://user-images.githubusercontent.com/111716161/190062770-37b71b07-e6f7-4f47-bdc2-151c98dfcb2b.png)

## 3. Web PHP

Bước 1: Vào Server manager chọn "Tools" chọn "Internet Infomation Services (IIS) Manager". Chọn Get New Web Platform Components.

![image](https://user-images.githubusercontent.com/111716161/190083497-f649b200-09a3-46f7-90d5-32faffdfd78a.png)

Bước 2: 

![image](https://user-images.githubusercontent.com/111716161/190084511-aa625298-8060-405a-bdd6-21d553649d28.png)
