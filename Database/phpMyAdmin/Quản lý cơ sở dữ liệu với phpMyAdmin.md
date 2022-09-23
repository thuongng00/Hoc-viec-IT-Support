## 1. Thao tác với database

- Tạo database mới

Ở cột bên trái, click chọn “New” sau đó nhập vào tên CSDL của bạn rồi chọn “Create”

![image](https://user-images.githubusercontent.com/111716161/191885577-1e379391-abdd-410f-b651-9c86b1bdbca4.png)

- Chọn database để quản lý

 Ở trang chủ phpMyAdmin, bấm vào tab Database.
 
 ![image](https://user-images.githubusercontent.com/111716161/191885846-2d624ce0-e2ef-4e60-95bf-5273fa783130.png)

Sau đó chọn database để quản lý bằng cách nhấp vào tên của nó.

![image](https://user-images.githubusercontent.com/111716161/191885868-91831b0c-126d-4a9b-89e7-796eacb6da85.png)

Trong trang mở ra, bạn sẽ thấy một danh sách với các bảng cơ sở dữ liệu, các hành động được phép với chúng, số lượng bản ghi, công cụ lưu trữ, đối chiếu(Collation), kích thước của bảng và chi phí.

## 2.Thao tác với bảng

- Tạo bảng mới 

Chọn 1 CSDL, chọn “Create table” để tạo bảng mới. Chú ý đặt tên bảng và chọn số cột có trong bảng. Sau đó chọn “Go” để hoàn thành tạo bảng.

![image](https://user-images.githubusercontent.com/111716161/191885635-9a9999b7-cb7d-4e54-a74b-7d41e30ad175.png)

Tiếp theo bạn sẽ thực hiện cấu hình cấu trúc của bảng với các tùy chọn

![image](https://user-images.githubusercontent.com/111716161/191885648-9f004d89-2d1b-4f64-b688-e26ae293321c.png)

Cụ thể:

 `Name` – Tên của cột;

`Type` – Loại dữ liệu sẽ được lưu trong cột;

`Length/Values` – Độ dài của trường;

`Default` – tùy chọn giúp bạn đặt giá trị mặc định cho cột. Điều này sẽ hữu ích trong trường hợp bạn cần đặt dấu thời gian;

`Collation` – Đối chiếu dữ liệu cho từng trường;

`Attributes` – Gán bất kỳ thuộc tính đặc biệt nào cho trường;

`Null` – Xác định giá trị của trường có thể để tróng hay không;

`Index` – Đặt chỉ mục ho các hàng;

`A_I` – viết tắt của Auto Increment. Nếu tùy chọn này được bật thì các giá trị trong trường của cột sẽ tự động tăng lên;

`Comments` – Bạn có thể thêm nhận xét tại đây.

Sử dụng “Preview SQL” để xem xem các thao tác trên dưới dạng câu lệnh truy vấn, chọn “Save” để lưu cấu hình với bảng.

- Browse

Chỉ các bảng với các bản ghi hiện có có thể được browse. Khi bạn nhấp vào nút Browse, một trang mới với danh sách các bản ghi bên trong bảng sẽ được mở.

![image](https://user-images.githubusercontent.com/111716161/191886010-0a680c3d-0fa4-41b7-8445-f26056eb576e.png)

Click vào nút edit, bạn có thể chỉnh sửa các bản ghi đã chọn.

Bạn sẽ nhìn thấy cấu trúc bản ghi và bạn có thể thay đổi giá trị của bản ghi. Khi đã thực hiện xong các thay đổi, click vào “Go” để lưu.

![image](https://user-images.githubusercontent.com/111716161/191886029-04b183e5-4fbf-4772-b6a6-25c943df6794.png)

- Structure

Click vào nút Structure, một trang mới sẽ mở ra hiển thị cấu trúc của bảng cơ sở dữ liệu.

![image](https://user-images.githubusercontent.com/111716161/191886058-45231544-6582-4e2d-9050-6511f546e047.png)

Bạn sẽ thấy tên của các trường, loại, tập hợp, thuộc tính, thông tin bổ sung, giá trị mặc định và liệu các giá trị của trường có thể là NULL hay không. Bạn có thể duyệt các giá trị riêng biệt bằng cách nhấp vào biểu tượng action tương ứng. Ngoài ra, bạn có thể chỉnh sửa cấu trúc của một trường hoặc xóa một trường. Bạn có thể xác định các chỉ mục khác nhau: Primary, Unique, Index và Fulltext.

- Search

Với nút Tìm kiếm, bạn có thể tạo truy vấn tìm kiếm cho bảng đã chọn.

![image](https://user-images.githubusercontent.com/111716161/191886090-2ad42c6e-56c1-4654-9505-d8b85953b43c.png)

Bạn có thể sử dụng chức năng Query by example (truy vấn theo ví dụ) để thực hiện tìm kiếm. Chỉ cần sử dụng cho các trường khác nhau cho cấu trúc truy vấn tìm kiếm của bạn và nhấp vào nút Go để thực hiện nó.

- Insert

Sử dụng nút Insert, bạn có thể chèn bản ghi vào bảng cơ sở dữ liệu của mình.

![image](https://user-images.githubusercontent.com/111716161/191886137-240bcf04-0181-4fde-b086-e4087f001b35.png)

Chọn “Go” để hoàn tất chèn dữ liệu.

- Empty

Nút Empty cho phép bạn làm trống bảng cơ sở dữ liệu, xóa dữ liệu và giữ bảng trống.

![image](https://user-images.githubusercontent.com/111716161/191886164-dcc56fd1-01f4-4480-9679-275351d3dcae.png)

- Drop

Với nút Drop, bạn có thể xóa toàn bộ bảng và tất cả các bản ghi được lưu trong đó.

![image](https://user-images.githubusercontent.com/111716161/191886202-ef4b6814-18dd-42f1-8a32-26890b8ddcc9.png)

- Ngoài ra, phpMyAdmin cũng hỗ trợ bạn Export, Import dữ liệu và cấu hình Replication.
