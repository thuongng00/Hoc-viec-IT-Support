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

**Tăng hiệu quả của công việc quản lý cơ sở dữ liệu**

phpMyadmin giúp bạn có được giao diện xử lý các thao tác trên CSDL một cách trực quan nhất. Từ đó, tiết kiệm thời gian, thao tác so với việc thực hiện bằng dòng lệnh quen thuộc trên command line. Đặc biệt, công cụ này rất đa năng khi có thể vừa làm việc với một đối tượng mà vẫn đồng thời xử lý được những vấn đề bất ngờ.

**Có cộng đồng hỗ trợ rộng lớn**

Bản chất của phpMyadmin là có mã nguồn mở. Nó được phát triển, xây dựng bởi rất nhiều lập trình viên đến từ nhiều nước trên khắp thế giới. Nhờ đó, người dùng phpMyadmin có thể nhận được sự hỗ trợ rất lớn từ cộng đồng người dùng có cùng nhu cầu, mong muốn.

**phpMyadmin đa ngôn ngữ, rất dễ sử dụng**

Mã nguồn mở nổi tiếng này được duy trì bởi The phpMyAdmin Project. Hiện tại, nó được cung cấp cho người sử dụng với 64 ngôn ngữ khác nhau và có sẵn. Nhờ vậy việc làm quen và sử dụng với phpMyAdmin rất đơn giản.

**Tối ưu chi phí sử dụng**

Có rất nhiều ưu điểm cho người sử dụng, mang tới hàng loạt lợi ích nhưng phpMyAdmin lại là công cụ miễn phí 100%. Nhờ vậy, mọi người sẽ có được những trải nghiệm hoàn hảo với mức chi phí phải chăng bậc nhất khi sử dụng mã nguồn này.

### Nhược điểm

**Về tính bảo mật**

Hạn chế lớn nhất của phpMyAdmin cũng như các mã nguồn mở khác chính là khả năng bảo mật. Hạn chế truy cập vào URL của phpMyAdmin từ những địa chỉ IP cố định là điều người dùng cần ghi nhớ.

**Về mặt sao lưu dữ liệu**

Tính đến thời điểm hiện tại, phpMyAdmin vẫn còn một số nhược điểm chưa được khắc phục về vấn đề sao lưu dữ liệu. Cụ thể như sau:

- Không thể tự xuất được database.
- Chỉ có thể kết nối thông qua trình duyệt, có nghĩa là chỉ lưu được các bản sao lưu vào các local driver có sẵn ở trên hệ thống mà thôi.
- Định dạng file xuất phpMyAdmin không được mã hóa nên được đánh giá là thiếu an toàn về khả năng bảo mật.
- File xuất ra từ phpMyAdmin chiếm dung lượng ổ đĩa lớn nên khiến nhiều người gặp khó khăn.

# Điểm yếu trong việc sao lưu dữ liệu của phpMyAdmin

Trong quá trình sử dụng các chức năng trong phần mềm phpMyAdmin, người dùng vẫn phải phải đối mặt với vấn đề bảo mật và sao lưu.

Cho đến nay, hạn chế lớn nhất của phpMyAdmin vẫn nằm ở khả năng bảo mật. Bởi đây là phần mềm xây dựng trên mã nguồn mở. Quá trình truy cập đến URL của phpMyAdmin xuất phát từ IP cố định chưa thực sự được mượt.

Ngoài ra khi tiến hành sao lưu, khôi phục dữ liệu thủ công thông qua phpMyAdmin vẫn tồn tại một vài yếu điểm. Chẳng hạn như:

- Chưa thể tự động xuất database.
- Chỉ hỗ trợ kết nối qua trình duyệt có nghĩa chúng chỉ có thể sao lưu vào Local Drive tích hợp sẵn trên hệ thống.
- File xuất thông qua phpMyAdmin chưa thể xuất mã an toàn, tiêu tốn tài nguyên đĩa cứng 
