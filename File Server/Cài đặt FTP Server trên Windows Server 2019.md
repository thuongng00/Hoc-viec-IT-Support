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

Bước 1: Mở “IIS Manager”. Nhấp chuột phải vào “Sites” và chọn "Add FTP Site".

Bước 2: Nhập tên trang web và đường dẫn đến thư mục chứa trang web.

Bước 3: Chọn địa chỉ IP trong danh sách thả xuống, tích vào "No SSL".

Bước 4: Chọn "Basic for authentication". Chọn "Authorization Specified roles or groups", nhập tên của nhóm người dùng FTP. Tích chọn cho phép đọc và ghi. Nhấn "finish".

Như vậy ta đã tạo xong một FTP site. 

## Tạo nhóm người dùng

