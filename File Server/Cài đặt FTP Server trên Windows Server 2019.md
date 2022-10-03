[Cài đặt FTP Server](#caidat)

[Các thao tác trên FTP Server](#thaotac)

<a name="caidat"></a>
# Cài đặt FTP Server trên Windows Server 2019

Bước 1: Mở “Windows Server Control Panel” và chọn “Add roles and features”.

![image](https://user-images.githubusercontent.com/111716161/193403314-24f109a7-bc92-425f-8da3-167817e2bcb0.png)

Bước 2: Lựa chọn “Role-based or feature-based installation”.

![image](https://user-images.githubusercontent.com/111716161/193403343-c417146e-90e2-4413-ada9-29a66d3f47b0.png)

Bước 3: Chọn máy chủ của bạn

![image](https://user-images.githubusercontent.com/111716161/193403366-dcda4e40-38e3-4fa4-b1c6-b05671f5e5db.png)

Bước 4: Tích vào “IIS” -> tích vào “FTP server”.

![image](https://user-images.githubusercontent.com/111716161/193403380-49a37de2-f3f9-44f1-a6fc-31d3e35e698b.png)

Bước 5: Nhấn Install

![image](https://user-images.githubusercontent.com/111716161/193403422-2e62e1bc-3746-4ad1-9814-3b73accec167.png)

<a name="thaotac"></a>
# Các thao tác trên FTP Server

## Tạo một trang FTP trên máy chủ Windows

Bước 1: Mở "IIS Manager". Nhấp chuột phải vào “Sites” và chọn "Add FTP Site...".

![image](https://user-images.githubusercontent.com/111716161/193487922-915541dc-f2a7-4423-8797-cf5826c9bfaf.png)

Bước 2: Nhập tên trang web và đường dẫn đến thư mục chứa trang web.

![image](https://user-images.githubusercontent.com/111716161/193488045-45ff8c92-c086-47a3-8d87-21a1c36a85bc.png)

Bước 3: Chọn địa chỉ IP trong danh sách thả xuống, tích vào "No SSL".

![image](https://user-images.githubusercontent.com/111716161/193488155-5154178e-9c1b-4e14-8bbc-da05c0ac87cf.png)

Bước 4: Chọn "Basic for authentication". Chọn "Authorization Specified roles or groups", nhập tên của nhóm người dùng FTP. Tích chọn cho phép đọc và ghi. Nhấn "finish".

![image](https://user-images.githubusercontent.com/111716161/193488274-2e359351-dfca-4665-9c9b-bdf631d0f0f3.png)

Như vậy ta đã tạo xong một FTP site. 

![image](https://user-images.githubusercontent.com/111716161/193488302-51ae2efd-0895-43f2-b1b6-95400a403bae.png)

## Tạo nhóm người dùng

Tạo một nhóm Windows là cần thiết để xác định người dùng có quyền truy cập vào máy chủ ftp. 

Bước 1: Mở Computer Management, chọn Groups. Chuột phải chọn tạo nhóm mới.

![image](https://user-images.githubusercontent.com/111716161/193496333-2fadb3cc-23fb-4d32-b602-cf5cd80e90c7.png)

Bước 2: Nhập tên nhóm và mô tả. Nhấn Add để thêm user.

![image](https://user-images.githubusercontent.com/111716161/193496396-d90564fd-6915-4b4b-93c6-0b48240f2499.png)

Bước 3: Nhập user, nhấn 
