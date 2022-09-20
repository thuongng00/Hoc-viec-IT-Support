# PHPMyAdmin

PhpMyAdmin là phần mềm mã nguồn mở được viết bằng ngôn ngữ PHP giúp quản trị cở sở dữ liệu MySQL thông qua giao diện web. 

![image](https://user-images.githubusercontent.com/111716161/191202445-bb134896-fa77-4a3c-b67e-c2c7a55ad08a.png)

## Tính năng

- Quản lý user(người dùng): thêm, xóa, sửa(phân quyền).
- Quản lý cơ sở dữ liệu: tạo mới, xóa, sửa, thêm bảng, hàng, trường, tìm kiếm đối tượng.
- Nhập xuất dữ liệu(Import/Export): hỗ trợ các định dạng SQL, XML và CSV.
- Thực hiện các truy vấn MySQL, giám sát quá trình và theo dõi.
- Sao lưu và khôi phục(Backup/Restore): Thao tác thủ công.

## Ưu, nhược điểm 

### Ưu điểm

PHPMyAdmin có thể xem như công cụ lý tưởng để thiết lập, quản lý hệ cơ sở dữ liệu. Phần mềm lời theo nhiều đặc quyền cho người dùng, cho phép thực hiện truy vấn SQL, tích hợp đầy đủ chức năng quản trị.

Với PHPMyAdmin, bạn có thể đồng thời làm việc với đối tượng và xử lý tình huống bất ngờ. Ví dụ như với SQL injection, lỗi từ phía người dùng và tình huống database dễ dàng xử lý cùng lúc.

### Nhược điểm

Hạn chế lớn nhất của phần mềm PHPMyAdmin làm ở khả năng sao lưu tự động cài đặt trước và phương thức lưu trữ phương tiện truyền thông. Cụ thể, chức năng sao lưu tự động cài đặt trước hoạt động chưa thực sự ổn định.

Phần mềm PHPMyAdmin hiện vẫn chỉ hỗ trợ sao lưu vào Local Drive tích hợp sẵn trong hệ thống. Lưu trữ của hội thoại Save as hoạt động chưa được mượt.

## Điểm yếu trong việc sao lưu dữ liệu của phpMyAdmin

Trong quá trình sử dụng các chức năng trong phần mềm phpMyAdmin, người dùng vẫn phải phải đối mặt với vấn đề bảo mật và sao lưu.

Cho đến nay, hạn chế lớn nhất của phpMyAdmin vẫn nằm ở khả năng bảo mật. Bởi đây là phần mềm xây dựng trên mã nguồn mở. Quá trình truy cập đến URL của phpMyAdmin xuất phát từ IP cố định chưa thực sự được mượt.

Ngoài ra khi tiến hành sao lưu, khôi phục dữ liệu thủ công thông qua phpMyAdmin vẫn tồn tại một vài yếu điểm. Chẳng hạn như:

- Chưa thể tự động xuất database.
- Chỉ hỗ trợ kết nối qua trình duyệt có nghĩa chúng chỉ có thể sao lưu vào Local Drive tích hợp sẵn trên hệ thống.
- File xuất thông qua phpMyAdmin chưa thể xuất mã an toàn, tiêu tốn tài nguyên đĩa cứng 
