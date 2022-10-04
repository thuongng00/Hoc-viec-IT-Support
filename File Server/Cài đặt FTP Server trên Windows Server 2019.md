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

Bước 1: Mở Computer Management, chọn Groups.

Trong trường hợp Computer Managemet không có Local User and Groups, ta nhấn tổ hợp Windows + R -> nhập `mmc` -> vào File chọn Add/Remove Snap-in... hoặc nhấn tổ hợp Ctrl + M.

![image](https://user-images.githubusercontent.com/111716161/193725768-232d315c-9998-45ae-abc6-83f0e81e4291.png)

Tìm mục Local Users and Groups -> Add.

![image](https://user-images.githubusercontent.com/111716161/193725936-7545441b-1c8e-47b6-ab4f-51be8dc39f25.png)

Nhấn Finish -> OK.

![image](https://user-images.githubusercontent.com/111716161/193726055-06725d6a-8a2f-48ea-a668-3dd4cd544561.png)

Chuột phải Groups -> New Group...

![image](https://user-images.githubusercontent.com/111716161/193726599-19fa1828-34bc-4269-a880-2052c3f53adc.png)

Bước 2: Nhập tên nhóm và mô tả. Nhấn Add để thêm user.

Bước 3: Nhập user, nhấn Check Names để kiểm tra người dùng có tồn tại hay không. 

![image](https://user-images.githubusercontent.com/111716161/193726917-e4397774-0922-4b65-9b5e-449afac3b23a.png)

Bước 4: Sau khi thêm user, nhấn Create để tạo nhóm. 

![image](https://user-images.githubusercontent.com/111716161/193726953-ee766c65-3954-48b3-9975-6684da4ece71.png)

## Phân vùng người dùng

Để mỗi user có được thư mục riêng của mình và không có quyền truy cập vào các tệp khác sau khi kết nối với máy chủ, cần phải thiết lập isolation. 

Bước 1: Mở IIS Manager -> vào trang web ftp -> FTP User Isolation -> Open Feature.

![image](https://user-images.githubusercontent.com/111716161/193722472-1c14e23e-37b9-4fdc-b0b3-7e9254379c14.png)

Bước 2: Tích chọn User name directory -> Apply. 

![image](https://user-images.githubusercontent.com/111716161/193722648-91f7fbe0-355b-423c-9a03-2df741c4ba4c.png)

Bước 3: Chuột phải vào tên ftp site, chọn Add Virtual Directory.

![image](https://user-images.githubusercontent.com/111716161/193722734-31fa7490-db5c-4bd7-a0f6-1f070f32b4c6.png)

Bước 4: Trong trường Alias, nhập tên hiệu hoặc tên, trường đường dẫn nhập đường dẫn đến thư mục người dùng. 

![image](https://user-images.githubusercontent.com/111716161/193722797-e4441900-f4ba-40e9-863d-1c5c1f857d37.png)

Bước 5: Cài đặt quyền truy cập cho folder ảo, chọn ftp site của bạn và chọn Edit Permission. 

![image](https://user-images.githubusercontent.com/111716161/193722877-f8c92d24-a380-4bea-ae43-44742132efcf.png)

Bước 6: Chọn Security tab, nhấn Advanced -> disalbe inheritance -> Convert inherited... để chuyển sang trạng thái Enable. Nhấn Apply -> OK để lưu thay đổi. 

![image](https://user-images.githubusercontent.com/111716161/193723081-c0ad64a2-3268-45bd-9ea6-8f15378ac76f.png)

![image](https://user-images.githubusercontent.com/111716161/193723225-db205e16-368c-4135-bdeb-e806b91a3c13.png)

Bước 7: Quay lại tab Security -> Edit.

![image](https://user-images.githubusercontent.com/111716161/193723477-92380857-6b65-4b6d-93ab-a4853f7dcebf.png)

Xóa các nhóm người dùng không cần thiết để đảm bảo chỉ chủ sở hữu thư mục mới được truy cập, chọn user/group -> nhấn Remove.

![image](https://user-images.githubusercontent.com/111716161/193723667-06bda564-0195-4717-852d-727aa8b33e93.png)

Trong trường hợp muốn thêm một người dùng để người dùng này có quyền truy cập vào thư mục với các quyền, nhấn Add. 

![image](https://user-images.githubusercontent.com/111716161/193724045-dcc987f0-da76-41cf-9ae1-ecaba117b37c.png)

Chỉnh sửa các quyền của user/group tại đây. 

![image](https://user-images.githubusercontent.com/111716161/193724183-f2394b86-8801-4f82-9443-4a2e011a52a7.png)

## Thiết lập rule Firewall

Bước 1: Mở Windows Firewall with Advanced Security -> Inbound rules -> New Rule.

![image](https://user-images.githubusercontent.com/111716161/193724414-8daced0f-d94e-41c9-98c9-7be299a645be.png)

Bước 2: Chọn Predefined -> Next.

![image](https://user-images.githubusercontent.com/111716161/193724577-0b130a3c-e717-4e15-8679-e0c59fa87220.png)

Bước 3: Tích chọn tất cả các dòng -> Next.

![image](https://user-images.githubusercontent.com/111716161/193724783-0d2c0f7a-605f-41bd-b055-906c60caca57.png)

Bước 4: Tích chọn Allow the connection -> finish. Khởi động lại máy. 

![image](https://user-images.githubusercontent.com/111716161/193724810-60be6941-e42d-4ae6-8752-164b1eebf258.png)

## Kết nối với máy chủ FTP

Kết nối thông qua Explorer. Trong thanh địa chỉ nhập:

```
ftp: // ip address
```

![image](https://user-images.githubusercontent.com/111716161/193727172-aaf6e48e-fbae-49b1-9fe2-3ec04b3e4e8b.png)

Cửa sổ đăng nhập mở ra, nhập tài khoản đã tạo để truy cập. 

![image](https://user-images.githubusercontent.com/111716161/193727216-fc88b13f-79d6-4981-a167-dfdd60eef9a7.png)
