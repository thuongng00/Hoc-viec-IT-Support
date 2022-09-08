# Database
Database (cơ sở dữ liệu) là một tập hợp có tổ chức các thông tin có cấu trúc hoặc dữ liệu, thường được lưu trữ trực tuyến trong một hệ thống máy tính. Một cơ sở dữ liệu thường được kiểm soát bởi hẹ thống quản lý cơ sở dữu liệu (DBMS). Cùng với nhau, dữ liệu và DBMS, cùng với các ứng dụng được liên kết với chúng, được gọi là một hệ thống cơ sở dữ liệu, thường được rút ngắn thành cơ sở dữ liệu. 

Dữ liệu trong các loại cơ sở dữ liệu phổ biến nhất đang hoạt động hiện nay thường được mô hình hóa theo hàng và cột trong một loạt các bảng để giúp xử lý và truy vấn dữ liệu hiệu quả. Dữ liệu sau đó có thể dễ dàng truy cập, quản lý, sửa đổi, cập nhật, kiểm soát và tổ chức. Hầu hết các cơ sở dữ liệu sử dụng ngôn ngữ truy vấn có cấu trúc (SQL) để viết và truy vấn dữ liệu. 

## Phân loại database

Theo mục đích sử dụng:
- Database dạng file: Đây là dữ liệu được lưu trữ dưới dạng các file. Loại database dạng file hay được sử dụng nhất *.mdb, ngoài ra còn có *.dbf,...
- Database quan hệ: Chúng là các dữ liệu khác nhau được lưu trữ trong các bảng dữ liệu nhưng giữa chúng lại có mối liên hệ với nhau. Một số hệ quản trị hỗ trợ database quan hệ hiện nay rất được ưa chuộng bao gồm MySQL, MS SQL Server, Oracle...
- Database hướng đối tượng: Điểm giống nhau giữa database hướng đối tượng và database quan hệ chính là chúng đều được lưu trữ trong bảng dữ liệu, còn điểm khác biệt là các bảng của database hướng đối tượng có thêm các tính năng hướng đối tượng, ví dụ như lưu trữ thêm một số hành vi để thể hiện rõ hơn hành vi của đối tượng. Các hệ quản trị hỗ trợ database hướng đối tượng nổi bật: MS SQL Server, Postgres SQL, Oracle...
- Database bán cấu trúc: Loại database này được lưu với định dạng XML, nó có thông tin mô tả dữ liệu và đối tượng được trình bày trong các thẻ tag. Ưu điểm vượt trội của nó là lưu trữ được nhiều loại dữ liệu khác nhau.

Theo hệ điều hành:
- Database dùng hệ điều hành Windows: SQL Server, MSSQL,...
- Database dùng hệ điều hành Linux: MySQL, Mariadb...

## Vai trò và tầm quan trọng của database

Trong thời đại công nghệ 4.0 hiện nay, database và quá trình xây dựng cơ sở dữ liệu đóng vai trò quan trọng với mỗi tổ chức/doanh nghiệp.

- Lưu trữ thông tin có hệ thống.

Xây dựng cơ sở dữ liệu giúp dữ liệu được lưu trữ một cách có hệ thống và có tính nhất quán cao. Từ đó người dùng dễ dàng quản lý, tạo lập, lưu trữ, tìm kiếm và sử dụng một cách chính xác, nhanh chóng. 

- Nâng cao tính bảo mật dữ liệu

Database được quản lý qua các hệ thống quản trị dữ liệu giúp nâng cao tính bảo mật và toàn vẹn của dữ liệu. 

- Cho phép truy xuất dữ liệu từ nhiều user.

Khi xây dựng database việc truy xuất dữ liệu từ nhiều người cùng một lúc trở nên dễ dàng và đơn giản hơn, nhờ đó quá trình truy cập database nhanh và hiệu quả hơn.

- Quản lý dữ liệu dễ dàng hơn

Database được xây dựng để việc tạo lập, cập nhật và khai thác thông tin dễ dàng hơn, trong đó quá trình cập nhật dữ liệu diễn ra thường xuyên và không trùng lặp. Ứng dụng database giúp tối ưu hệ thống, tạo ra các sản phẩm chuyên nghiệp hơn, dữ liệu được lưu trữ một cách hệ thống và hoạt động quản lý trở nên đơn giản.

## Các hệ quản trị cơ sở dữ liệu phổ biến

### Hệ quản trị cơ sở dữ liệu MySQL
Đây là một cơ sở dữ liệu cực kỳ phổ biến dành cho các ứng dụng web (miễn phí). MySQL thường được cập nhật một cách nhanh chóng và các tính năng và những cải tiến về sự bảo mật. 

Công cụ này sẽ cho phép bạn lựa chọn được nhiều công cụ lưu trữ. Như vậy, bạn có thể thay đổi được các chức năng của công cụ cũng như việc xử lý dữ liệu đến từ những loại bảng khác nhau. Giao diện đơn giản, dễ dùng với các lệnh hàng loạt. hệ thống nhìn chung khá tin cậy và không bị hao hụt nguồn tài nguyên, đồng thời chúng cũng cho phép bạn có thể xử lý được một lượng dữ liệu lớn. 

Ưu điểm:

- Có phiên bản miễn phí
- Cung cấp cho người dùng nhiều chức năng
- Đa dạng giao diện
- Hoạt động được ở trên nhiều cơ sở dữ liệu khác nhau ví dụ như DB2 và Oracle

Nhược điểm:

- Cần phải dành nhiều thời gian hơn để làm việc với hệ quản trị MySQL
- Không có sự hỗ trợ tích hợp cho XML hoặc cho OLAP
- Các hỗ trợ sẽ có sẵn ở trong phiên bản miễn phí, tuy nhiên bạn cần phải trả phí để sử dụng
- Là một hệ quản trị CSDL khá lý tưởng dành cho một tổ chức cần đến công cụ quản lý mạnh mẽ nhưng vẫn tiết kiệm. 

### Hệ quản trị cơ sở dữ liệu Oracle
Oracle có phiên bản đầu tiên được phát minh vào cuối những năm 70. Ở phiên bản mới nhất, Oracle được thiết kế sử dụng cho cloud và có thể thực hiện lưu trữ ở trên một hoặc nhiều server. Ngoài ra, Oracle còn cho phép quản lý các cơ sở dữ liệu có chứa hàng tỷ những bản record. Những tính năng của phiên bản này gồm có framework, sử dụng cấu trúc logic lẫn physical. 

Ưu điểm:

- Có những cải tiến và cả tính năng mới. Bởi lẽ, Oracle có xu hướng thiết lập các thanh bar cho công cụ quản lý cơ sở dữ liệu khác. 
- Công cụ quản lý cực kỳ mạnh mẽ, người dùng có thể tìm thấy được một công cụ có thể làm được những điều mà bạn muốn. 

Nhược điểm:

- Chi phí khá cao, nhất là với những tổ chức nhỏ. 
- Có khá nhiều yêu cầu về tài nguyên sau khi tiến hành cài đặt. Chính vì vậy, bạn cần phải nâng cấp những phần cứng. 
- Đây là một sự lựa chọn khá lý tưởng dành cho những tổ chức lớn. Hệ thống cần phải xử lý những cơ sở dữ liệu khổng lồ và cần thêm nhiều tính năng. 

### Hệ quản trị csdl SQL Server
Hệ quản trị này hoạt động dựa trên những server cloud tương tự như server cục bộ. Chúng có thể được thiết lập nhằm mục đích hoạt động cả hai đồng thời. Phiên bản mới nhất hiện tại của Microsoft Sever cũng sẽ cho phép Dynamic Data Masking. Điều này đảm bảo rằng, chỉ có những người được ủy quyền thì mới có thể nhìn thấy những dữ liệu mật. 

Ưu điểm:

- Tốc độ nhanh và ổn định.
- Cung cấp cho người dùng khả năng điều chỉnh lẫn theo dõi hiệu suất. Đồng thời, chúng cũng làm giảm việc phải sử dụng các tài nguyên.
- Người dùng có thể truy cập được các hình ảnh trực quan ở trên các thiết bị di động. 
- Hoạt động khá tốt đối với những sản phẩm của nhà Microsoft.

Nhược điểm:

- Ngay cả khi đã điều chỉnh hiệu suất thì vẫn có thể tiêu tốn tài nguyên.
- Có khá nhiều cá nhân gặp phải sự cố khi sử dụng các dịch vụ tích hợp SQL Server cho việc nhập file. 
- SQL Server rất lý tưởng cho những tổ chức lớn khi sử dụng một số các sản phẩm của nhà Microsoft. 
