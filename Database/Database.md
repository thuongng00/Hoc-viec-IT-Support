# Database
Database (cơ sở dữ liệu) là một tập hợp có tổ chức các thông tin có cấu trúc hoặc dữ liệu, thường được lưu trữ trực tuyến trong một hệ thống máy tính. Một cơ sở dữ liệu thường được kiểm soát bởi hẹ thống quản lý cơ sở dữu liệu (DBMS). Cùng với nhau, dữ liệu và DBMS, cùng với các ứng dụng được liên kết với chúng, được gọi là một hệ thống cơ sở dữ liệu, thường được rút ngắn thành cơ sở dữ liệu. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/190381406-e85e06d8-2182-4854-a79e-cf2a0eb64120.png" width="500"/>
</p>

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

# Hệ quản trị cơ sở dữ liệu

![image](https://user-images.githubusercontent.com/111716161/189632326-ca1d7a34-d3bd-4213-a84c-8ac0b8b24d17.png)

## Cấu trúc của hệ quản trị cơ sở dữ liệu

Cấu trúc của hệ quản trị cơ sở dữ liệu gồm có những yếu tố như sau:
- Các thao tác đối với hệ quản trị cơ sở dữ liệu với các thao tác chính bao gồm: Truy vấn, thay đổi sơ đồ dữ liệu, cập nhật dữ liệu.
- Bộ xử lý câu hỏi. 
- Bộ quản lý lưu trữ.
- Bộ quản trị giao dịch. 
- Dữ liệu, siêu dữ liệu.

## Các hệ quản trị cơ sở dữ liệu phổ biến

### Hệ quản trị cơ sở dữ liệu MySQL

![image](https://user-images.githubusercontent.com/111716161/189621715-1faf503b-65e2-421c-8c3b-8f8c3c636e31.png)

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

![image](https://user-images.githubusercontent.com/111716161/189621754-46ecb73f-0f33-4854-abd8-eb2d85673294.png)

Oracle có phiên bản đầu tiên được phát minh vào cuối những năm 70. Ở phiên bản mới nhất, Oracle được thiết kế sử dụng cho cloud và có thể thực hiện lưu trữ ở trên một hoặc nhiều server. Ngoài ra, Oracle còn cho phép quản lý các cơ sở dữ liệu có chứa hàng tỷ những bản record. Những tính năng của phiên bản này gồm có framework, sử dụng cấu trúc logic lẫn physical. 

Ưu điểm:

- Có những cải tiến và cả tính năng mới. Bởi lẽ, Oracle có xu hướng thiết lập các thanh bar cho công cụ quản lý cơ sở dữ liệu khác. 
- Công cụ quản lý cực kỳ mạnh mẽ, người dùng có thể tìm thấy được một công cụ có thể làm được những điều mà bạn muốn. 

Nhược điểm:

- Chi phí khá cao, nhất là với những tổ chức nhỏ. 
- Có khá nhiều yêu cầu về tài nguyên sau khi tiến hành cài đặt. Chính vì vậy, bạn cần phải nâng cấp những phần cứng. 
- Đây là một sự lựa chọn khá lý tưởng dành cho những tổ chức lớn. Hệ thống cần phải xử lý những cơ sở dữ liệu khổng lồ và cần thêm nhiều tính năng. 

### Hệ quản trị csdl SQL Server

![image](https://user-images.githubusercontent.com/111716161/189621818-ddf28961-78c1-4367-a21a-f44594bd6df6.png)

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

### Hệ quản trị csdl DB2

![image](https://user-images.githubusercontent.com/111716161/189621889-cc5ec379-ab63-4159-bbbb-5c3abeb776f2.png)

DB2 là một loại công cụ có khả năng NoSQL và có thể đọc được các file định dạng JSON và cả XML. Phiên bản mới nhất của DB2 chính là LUW và được cải tiến nhiều hơn. Đặc biệt nhất chính là sự thay đổi trong thiết kế để hỗ trợ công cụ hoạt động một cách nhanh chóng hơn thông qua một công nghệ có tên là bỏ qua dữ liệu. Ngoài ra, công cụ cũng được bổ sung thêm chức năng khôi phục, tương thích và cả phân tích. 

Ưu điểm:
- Có thể tận dụng một cách tối đa nguồn tài nguyên sẵn có cho những cơ sở dữ liệu lớn.
- Có thể lưu trữ từ cloud, physical server hoặc cũng có thể là cả hai. 
- Có thể chạy được nhiều việc cùng một lúc thông qua Task Scheduler.
- Error Code và cả Exit Code có thể xác định được công việc nào có thể chạy qua Task Scheduler.

Nhược điểm:
- Có chi phí tương đối cao. 
- Cần thêm một công cụ của bên thứ ba hoặc một phần mềm bổ sung để làm cho các cluster hoặc các nút phụ khác hoạt động. 
- Hỗ trợ mức độ cơ bản chỉ có sẵn trong thời gian ba năm, thời gian sau đó cần phải chi trả để sử dụng. 

### Hệ quản trị cơ sở dữ liệu MongoDB

![image](https://user-images.githubusercontent.com/111716161/189622402-71504f0e-06b4-449e-b392-d9e32fd81eaf.png)

Chúng được thiết kế để dành cho các ứng dụng dữ liệu có và không cấu trúc. Công cụ MongoDB này cực kỳ linh hoạt, chúng hoạt động thông qua việc kết nối cơ sở dữ liệu đến những ứng dụng thông qua trình điều khiển có tên là MongoDB.

Ưu điểm:
- Nhanh chóng và sử dụng cực kỳ đơn giản. 
- Có công cụ hỗ trợ JSON cùng với các tài liệu NoSQL khác. 
- Có thể lưu trữ và truy cập vào tất cả các loại cấu trúc một cách nhanh chóng. 
- Lược đồ có thể được viết mà không cần đến bộ đếm thời gian. 

Nhược điểm:
- SQL sẽ không được sử dụng tương tự như một loại ngôn ngữ truy vấn.
- Những công cụ dịch các truy vấn SQL chuyển sang thành MongoDB có sẵn. Tuy nhiên cần phải bổ sung một bước khác để có thể sử dụng. 
- Quá trình thiết lập sẽ tốn thời gian hơn và việc cài mặc định sẽ không đảm bảo an toàn. 

### Hệ quản trị cơ sở dữ liệu PostgreSQL

![image](https://user-images.githubusercontent.com/111716161/189623001-844badb9-61c3-443a-8e30-62d6e5ba6cf8.png)

PostgreSQL cực kì phổ biến và được sử dụng miễn phí, được sử dụng cho CSDL web. Chúng cho phép người dùng có thể quản lý cả dữ liệu có cấu trúc lẫn không có cấu trúc. 

Ưu điểm: 
- Có khả năng mở rộng và xử lý terabyte dữ liệu.
- Hỗ trợ JSON.
- Nhiều chức năng đã được xác định từ trước. 
- Một số giao diện đã có sẵn.

Nhược điểm:
- Tài liệu trong một số trường hợp không rõ ràng. 
- Cấu hình có thể gây nên sự nhầm lẫn. 
- Tốc độ cũng bị ảnh hưởng đối với những hoạt động lớn hoặc các truy vấn khác.
- Phù hợp cho những tổ chức có ngân sách còn hạn chế và muốn có khả năng chọn giao diện cũng như sử dụng JSON.

### Hệ quản trị cơ sở dữ liệu Redis

![image](https://user-images.githubusercontent.com/111716161/189625385-623da7ae-0f09-4953-938d-bfe484f28c3a.png)

Một sự kết hợp của công nghệ cơ sở dữ liệu và cả sự đổi mới của cộng đồng nguồn mở. Redis có tính khả dung tương đối cao ở dưới dạng Active-Active và cả Active-Passive có hiệu suất cao cùng khả năng tìm kiếm những tích hợp hàng đầu. Mở rộng các cơ sở dữ liệu Redis sang SSD Flash nhằm tiết kiệm tối đa chi phí cơ sở hạ tầng. Ngoài ra, chúng cũng sẽ sử dụng phần cứng ở mức tối đa cùng với Redis Enterprise.

Ưu điểm:
- Có hiệu suất cao cùng với khả năng mở rộng tuyến tính lên đến 1000 nút. 
- Có mức độ an toàn khá ổn định. 

Nhược điểm:
- Yêu cầu ít nhất là 3 master và 2 slave cho việc thiết lập cấu trúc. 
- Dữ liệu sẽ được phân đoạn dựa trên hash-slot và được chỉ định cho mỗi Master. Trong trường hợp Master đang giữ một số slot gặp vấn đề thì dữ liệu được ghi trong slot đó sẽ mất. 
- Các Client kết nối đến Redis Cluster cần biết cấu trúc liên kết Cluster. Việc này sẽ gây nên chi phí cấu hình trên máy của họ.
- Failover sẽ không xảy ra trong tình trạng không có ít nhất một slave.
- Quá trình thăng cấp cho slave trong tư cách là master với ít nhất 30-50 giây, vì vậy dữ liệu được ghi ở trong cluster trong thời gian đó sẽ mất đi.

### Hệ quản trị cơ sở dữ liệu SQLite

![image](https://user-images.githubusercontent.com/111716161/189627104-d093a9ef-222e-4597-8836-516a982d41c0.png)

Hệ quản trị cơ sở dữ liệu SQLite cực kỳ phổ biến và được sử dụng rất thành công ở định dạng file trên disk. Nó cực kỳ phù hợp đối với những ứng dụng máy tính để bàn ví dụ như Control System, Financial Analysis Tool hay Media Cataloging,...

Ưu điểm:
- Có dung lượng nhẹ và rất dễ sử dụng. 
- Thao tác đọc và ghi tương đối nhanh, hơn gần 35% so với File System.
- Dễ tìm hiểu và không cần phải cài đặt hoặc cấu hình, chỉ cần tải xuống thư viện SQLite trong máy tính và chúng sẽ sẵn sàng để tạo ra cơ sở dữ liệu. 

Nhược điểm:
- Sử dụng nhằm xử lý những yêu cầu HTTP với lưu lượng truy cập từ thấp đến trung bình.
- Kích thước giới hạn ở 2GB ở đa số trường hợp.
- Nội dung có khả năng phục hồi cao nếu bị mất, các dữ liệu sẽ tồn tại lâu hơn so với mã.
- Làm giảm chi phí ứng dụng bởi lẽ nội dung có thể sẽ được truy cập và cập nhật. Quá trình thực hiện thông qua việc sử dụng SQL Query ngắn gọn thay vì sự dài dòng và rất dễ xảy ra lỗi. 

### Hệ quản trị cơ sở dữ liệu Access

![image](https://user-images.githubusercontent.com/111716161/189628650-59b5ddf0-6cd5-4d50-b426-2f8e770151b5.png)

Hệ quản trị cơ sở dữ liệu Access sẽ cho phép những cá nhân và doanh nghiệp có thể nắm bắt cũng như quản lý dữ liệu. Đồng thời, chũng cũng tạo ra báo cáo một cách nhanh chóng, hiệu quả. 

Ưu điểm:
- Dễ dàng cài đặt và sử dụng.
- Có nhiều ứng dụng ở trên Windows và đều có khả năng tích hợp với Access. 
- Dễ bảo trì và cung cấp những ứng dụng lớn hơn những hệ thống khác. 
- Có thể đặt được ở trên một trang web để cho người dùng có thể truy cập từ xa.
- Chi phí khá hợp lý. 

Nhược điểm:
- Đối với những dữ liệu lớn sẽ có một số hạn chế vì file bị giới hạn về kích thước. 
- Với những file kích thước tối đa hệ quản trị sẽ cho phép và định dạng file, làm chậm hiệu suất của chương trình.
- Những dữ liệu đa phương tiện chiếm nhiều dung lượng và làm chậm hiệu suất của CSDL.

