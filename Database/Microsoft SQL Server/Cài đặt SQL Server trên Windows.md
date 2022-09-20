[Cài đặt SQL Server 2019](#sql)

[Cài đặt SQL Server Management Studio (SSMS)](#ssms)

[Gỡ cài đặt SQL Server và SSMS](#go)

<a name="sql"></a>
# Cài đặt SQL Server 2019 trên Windows Server 2019.

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

![image](https://user-images.githubusercontent.com/111716161/191203873-2950b4b7-512a-4f94-b098-df4f8119e0cf.png)

Bước 17: Nhấn Install.

![image](https://user-images.githubusercontent.com/111716161/191187125-622bfc4d-1ffe-42fc-9a5a-7cfadc792ee5.png)

Bước 18: Đợi đến khi file cài đặt xong và bấm close để hoàn tất.

![image](https://user-images.githubusercontent.com/111716161/191187277-7423336e-3e16-4738-9ac8-a7f62f4756c9.png)

![image](https://user-images.githubusercontent.com/111716161/191187521-b74f31b7-0ae8-4761-9b03-e4a5bc57b0a8.png)

Như vậy ta đã cài đặt thành công SQL Server 2019.

<a name="ssms"></a>
# Cài đặt SQL Server Management Studio (SSMS)

Bước 1: Tại màn hình Developer Edition, chọn Install SSMS để mở link tải. 

![image](https://user-images.githubusercontent.com/111716161/191188004-bfd36b7d-fd6d-4247-985d-77b65418d89d.png)

Bước 2: Tải SSMS 18.12.1.

![image](https://user-images.githubusercontent.com/111716161/191188286-72f45eeb-98b8-4c2f-8967-cf36fd87a773.png)

Bước 3: Sau khi tải xong, mở file vừa tải về. 

![image](https://user-images.githubusercontent.com/111716161/191188774-41f0c585-f110-47e3-8f50-b4d656c3b4a5.png)

Bước 4: Chọn nơi lưu trữ, sau đó nhấn Install để cài đặt.

![image](https://user-images.githubusercontent.com/111716161/191188995-286f3f67-672b-4d87-812c-d3baf584b15e.png)

Bước 5: Chờ quá trình cài đặt hoàn tất, sau đó nhấn Close. 

![image](https://user-images.githubusercontent.com/111716161/191190455-201565d4-69cf-4343-970a-c7f945b0b667.png)

Bước 6: Khởi động lại máy và đăng nhập vào SSMS.

![image](https://user-images.githubusercontent.com/111716161/191207746-b7d8e4d6-f78b-4caa-b074-abf89979f175.png)

![image](https://user-images.githubusercontent.com/111716161/191207828-03b98f50-1174-4b87-987d-9313a5edf434.png)

<a name="go"></a>
# Gỡ cài đặt MS SQL Server và SSMS

## Gỡ cài đặt SQL Server

Bước 1: Vào Setting, chọn App tìm kiếm Microsoft SQL Server

![image](https://user-images.githubusercontent.com/111716161/191193408-5d49ebc0-77d2-404e-b2e1-d56fdd893b99.png)

Bước 2: Nhấn Uninstall

![image](https://user-images.githubusercontent.com/111716161/191193579-4b9eb9af-8151-45d2-979a-9ed1ebc67e0b.png)

Bước 3: Chọn Remove.

![image](https://user-images.githubusercontent.com/111716161/191193694-fd840b73-37b1-4fee-89a7-fda989d2f50e.png)

Bước 4: Ở mục "Instance to remove features from" chọn MSSQLSERVER rồi nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/191196265-c06c888b-ae44-4417-ac74-98e6107fbdc7.png)

Bước 5: Chọn Select All, nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/191196399-1c5838f2-1794-461e-b7ff-75e8e18585f4.png)

Bước 6: Nhấn Remove

![image](https://user-images.githubusercontent.com/111716161/191196487-4bd84676-6e0e-473a-ad6a-90e61a53e444.png)

Bước 7: Chờ quá trình gỡ cài đặt hoàn tất, sau đó Close. 

![image](https://user-images.githubusercontent.com/111716161/191196553-725eb37b-8304-42fc-9e85-152fd5e59150.png)

![image](https://user-images.githubusercontent.com/111716161/191196867-e66165ad-08c3-440b-a6f0-198713e6a809.png)

Bước 8: Quay lại bước 1 và thao tác tương tự. Tại màn hình Select Instance, nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/191198155-886e3b95-2885-493d-9f2f-303dcb66cd75.png)

Nhấn Select All -> Next.

![image](https://user-images.githubusercontent.com/111716161/191198236-5421c9d8-6426-4cd8-90e7-3f49a098385a.png)

Nhấn Remove.

![image](https://user-images.githubusercontent.com/111716161/191198347-ef4ae754-2a6c-4268-b4c5-dc40409fb9d8.png)

Nhấn Close.
![image](https://user-images.githubusercontent.com/111716161/191198823-3989ee73-cfd7-4223-8b43-86f2907c88ba.png)

Bước 9: Quay lại bước 1, chọn MSSQL Server 2019 T-SQL Language Service, nhấn Uninstall.

![image](https://user-images.githubusercontent.com/111716161/191199034-b3a0c750-1c48-4bec-ba23-e83a99883e34.png)

Như vậy ta đã gỡ cài đặt SQL Server thành công. 

## Gỡ cài đặt SSMS

Bước 1: Vào Setting, chọn App tìm kiếm Microsoft SQL Server Management Studio

![image](https://user-images.githubusercontent.com/111716161/191199946-b99097a6-2f27-442d-9c60-ad5991d67ee1.png)

Bước 2: Sau khi cửa sổ hiện lên, chọn Uninstall. 

![image](https://user-images.githubusercontent.com/111716161/191200094-6e70ff09-8ac9-4f01-b317-7e015b205d85.png)

Bước 3: Chờ quá trình gỡ cài đặt hoàn tất, sau đó nhấn Close

![image](https://user-images.githubusercontent.com/111716161/191200164-ac972c94-406b-43ea-82be-c5d88dad05dd.png)

![image](https://user-images.githubusercontent.com/111716161/191200280-9eb4c145-5e0b-4cd6-bd32-84ca427cdb29.png)


