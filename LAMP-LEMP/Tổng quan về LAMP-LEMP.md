# LAMP stack

**LAMP** là viết tắt của Linux, Apache, MySQL và PHP (cũng có thể là Python, Perl nhưng bài này chỉ nói về Php), mỗi trong số đó là các gói phần mềm riêng lẻ được kết hợp để tạo thành một giải pháp máy chủ web linh hoạt. Các thành phần này, được sắp xếp theo các lớp hỗ trợ lẫn nhau, tạo thành các stack phần mềm.

<img src = "https://user-images.githubusercontent.com/111716161/190982341-210e87ad-c896-4f76-92f6-b4b38f7c38f5.png" width=700/>

## Stack của LAMP
- Linux: là lớp đầu tiên trong stack. Hệ điều hành này là cơ sở nền tảng cho các lớp phần mềm khác.
- Apache đóng vai trò một HTTP server dùng để xử lý các yêu cầu gửi tới máy chủ.
- Mysql là cơ sở dữ liệu để lưu trữ mọi thông tin trên website.
- PHP sau đó sẽ xử lý các nhiệm vụ cần thiết hoặc kết nối với CSDL MySQL để lấy thông tin cần thiết sau đó trả về cho Apache. Apache cuối cùng sẽ trả kết quả nhận được về cho máy khách đã gửi yêu cầu tới.

## Cơ chế hoạt động

- Hoạt động của Linux trong LAMP
Linux đóng vai trò là một hệ điều hành. Trên nguyên tắc thì một hệ điều hành cũng được coi là một chương trình phần mềm Software tuy nhiên Linux lại là một dạng Software đặc biệt phục vụ cho mục đích quản lý những nguồn nhân lực bên trong một hệ thống, bao gồm toàn bộ các Hardware và Software. Trong LAMP, Linux có vai trò là một hệ điều hành mã nguồn mở, được cung cấp hoàn toàn miễn phí. Khi bạn tìm thấy một vài chương trình trong LAMP mà không thấy Linux như Suse, Redhat, Ubuntu,... thì khoan hãy lo lắng, Linux của bạn không hề thiếu vì những chương trình này chính là phiên bản khác của Linux.

- Hoạt động của Apache trong LAMP
Apache có thế mạnh về độ nhanh chóng khi truy cập và cực kỳ an toàn. Người dùng có thể tùy chỉnh nó để phục vụ cho mục đích hỗ trợ ngôn ngữ Web như CGI, PHP, SSL, ASP. Apache đã mang đến cho doanh nghiệp rất nhiều dự án là những phần mềm hoạt động theo tính năng tự do. Điều này đã thu hút được đông đảo sự quan tâm của cộng đồng người dùng vì ai cũng có thể dễ dàng hiểu về Apache để sử dụng nó, kể cả là các đối tượng đến từ hoạt động thương mại hay các cá nhân.

![image](https://user-images.githubusercontent.com/111716161/190981734-9e43f3f8-b930-4a3c-b9df-ae662a184dc0.png)

- Hoạt động của MySQL trong LAMP
Vốn là hệ quản trị cơ sở dữ liệu có khả năng truy cập nhanh hàng đầu trên thế giới, MySQL được chọn ứng dụng hoạt động trong LAMP. Đây là một mã nguồn mở và vô cùng phổ biến, có lợi thế lớn từ độ hiệu suất cũng như mức độ uy tín cao, đem đến cho người dùng có thể dễ dàng sử dụng. MySQL đặc biệt tốt khi ứng dụng trên Web, đây là một lý do quan trọng khiến cho nó trở nên đặc biệt hiệu quả trong LAMP.

Khi các công cụ hỗ trợ LAMP người dùng có thể thực hiện bất cứ điều gì mong muốn. Sự linh hoạt của nó có thể chạy được trên hơn 20 nền tảng giúp kiểm soát tốt hệ thống, chinh phục rất nhiều tổ chức lơn trên thế giới từ Google, Fcaebook đến Zappos vì nó giúp chúng ta tiết kiệm tiền bạc, thời gian.

- Hoạt động của PHP trong LAMP
PHP là ngôn ngữ kịch bản trong máy chủ và cũng được cập nhật một cách thường xuyên những kỹ thuật mới thông qua cơ chế vay mượn những tính năng tốt nhất từ các ngôn ngữ lập trình.

## Ưu điểm

- Sử dụng miễn phí
Đây là tin tốt đối với người dùng bởi trong bối cảnh mà thế độc quyền về phần mềm của Microsoft đã khiến giá bản quyền của hệ thống phần mềm này khá cao, thì với việc miễn phí tiền bản quyền, LAMP có thể là một trong những sự lựa chọn rất đáng cân nhắc với người sử dụng nếu muốn có những trải nghiệm tuyệt vời tương tự Microsoft mà không phải tốn chi phí.

- Hỗ trợ hiệu quả
Việc ngày càng có nhiều người sử dụng LAMP, cộng đồng hỗ trợ của LAMP hiện đang khá đông đảo như vậy, người dùng có thể yên tâm hơn trong quá trình sử dụng phần mềm nếu như có gặp bất kỳ một sự cố nào dù là nhỏ nhất. Hay nói cách khác, việc có cộng đồng người sử dụng đông đảo khiến cho LAMP là hệ thống an toàn về mặt hỗ trợ cho người dùng.

- Tạo cơ hội tìm Host
Với các máy tính có máy chủ cài đặt Linux, chi phí để duy trì là không quá cao. Nếu bạn lập trình trên các phần mềm thành phần của LAMP, việc bạn có thể tìm Host miễn phí cho ứng dụng của mình là điều hoàn toàn trong tầm tay của bạn. Cơ hội sẽ luôn luôn rộng mở cho bạn khi sử dụng LAMP để lập trình.

# LEMP stack 

Các thành phần cấu thành LEMP stack cũng gần tương tự với LAMP, chỉ khác là Apache sẽ được thay thế bởi Nginx. Nginx được đọc là “engine-x”, giải thích cho chữ E trong “LEPM”. Nginx có ưu điểm là cho phép xử lý tốc độ tải cao hơn đối với các HTTP request.

![image](https://user-images.githubusercontent.com/111716161/191681253-64172ba2-193e-40bd-b5dc-686fea337a8a.png)

Hiện tại, Nginx đã đạt được thành tựu đáng kể khi nó bắt đầu được nhiều người sử dụng từ năm 2008 và hiện trở thành ứng dụng web server tiếng tăm thứ 2 sau Apache.

## Sự khác nhau giữa LEMP và LAMP Stack

![image](https://user-images.githubusercontent.com/111716161/190982001-7f58b39f-78ee-4e02-afd5-3f661e8d8470.png)

Sự khác biệt giữa LEMP và LAMP Stack đến từ 2 thành phần là Apache và Nginx. Do đó việc sử dụng Nginx và Apache sẽ tạo ra những khác biệt nhất định.

- Đối với Apache
  - Apache đã được sử dụng từ lâu (từ những năm 1995), có rất nhiều các module được viết và cả người dùng tham gia vào mở rộng hệ chức năng cho Apache.
  - Phương pháp process/thread-oriented – sẽ bắt đầu chậm lại khi xuất hiện tải nặng, cần tạo ra các quy trình mới dẫn đến tiêu thụ nhiều RAM hơn, bên cạnh đó, cũng tạo ra các thread mới cạnh tranh các tài nguyên CPU và RAM.
  - Giới hạn phải được thiết lập để đảm bảo rằng tài nguyên không bị quá tải, khi đạt đến giới hạn, các kết nối bổ sung sẽ bị từ chối.
  - Yếu tố hạn chế trong điều chỉnh Apache: bộ nhớ và thế vị cho các deadlocked threads cạnh tranh cho cùng một CPU và bộ nhớ. 

- Đối với Nginx
  - Ứng dụng web server mã nguồn mở được viết để giải quyết các vấn đề về hiệu suất và khả năng mở rộng có liên quan đến Apache.
  - Phương pháp Event-driven, không đồng bộ và không bị chặn, không tạo các process mới cho mỗi request từ web.
  - Đặt số lượng cho các worker process và mỗi worker có thể xử lý hàng nghìn kết nối đồng thời.
  - Các module sẽ được chèn vào trong thời gian biên dịch, có trình biên dịch mã PHP bên trong (không cần đến module PHP).

Để kết luận thì Nginx nhanh hơn và có khả năng xử lý tải cao hơn nhiều so với Apache khi sử dụng cùng một bộ phần cứng. Tuy nhiên, Apache vẫn là tốt hơn nhiều khi nói đến chức năng và tính sẵn sàng của các module cần thiết để làm việc với các ứng dụng máy chủ back-end và chạy các ngôn ngữ kịch bản lệnh.

Vậy nên việc lựa chọn sẽ phụ thuộc phần lớn vào những gì bạn muốn chạy trên web server của mình. Việc chạy cả Apache và nginx trên cùng một máy chủ vẫn có khả năng thực hiện được, và nó sẽ giúp người dùng có được lợi ích tốt nhất từ cả 2 phương pháp.

# Kiến thức cơ bản
## 1. Phân quyền tệp và thư mục
Sử dụng máy chủ Linux việc phân quyền tệp và thư mục rất quan trọng. Ví dụ trong trường hợp người dùng upload files lên hệ thống mà bạn chưa phân quyền thư mục thì lúc này việc đọc và ghi file lên máy chủ sẽ xảy ra lỗi. Và máy chủ web sẽ trả về lỗi 500.

Phân quyền trong Linux có 3 quyền hạn cơ bản của một user/group nào đó trên một file/folder nào đó bao gồm:

- r (read) – quyền đọc file/folder.
- w (write) – quyền ghi/sửa nội dung file/folder.
- x (execute) – quyền thực thi (truy cập) thư mục. Đối với thư mục thì bạn cần phải có quyền execute thì mới dùng lệnh cd để truy cập vào được.

## 2. Log và xem log error
Tùy thuộc vào config hệ thống mà các file log sẽ nằm ở vị trí tương ứng. Ví dụ webite của bạn hiển thị một màn hình trắng tinh và không có bất cứ thông báo nào từ màn hình debug. Lúc này bạn cần xem log hệ thống xem sao nhé.

## 3. Cấu hình cơ sở dữ liệu (Database)
Để mở rộng hay backup một hệ thống cũng như để đảm bảo một cơ sở dữ liệu toàn vẹn, không bị mất mát trước những sự cố. Việc hiểu biết nơi, cách cấu hình cơ sở dữ liệu cũng khá quan trọng bạn có thể tìm hiểu thêm về cấu hình Mysql Replication.

## 4. Cài đặt package
Linux không cung cấp đầy đủ các package cho anh em developer, nó chỉ làm môi trường thôi, còn lại bạn cần package nào thì tải cái đó. Để tải package cần thiết ta có thể dùng lệnh apt hoặc là yum.

## 5. Chỉnh sửa file trực tiếp trên máy chủ
Nhiều lúc bạn sẽ gặp phải lỗi và phải hot fix trực tiếp trên server, hoặc config web server. Việc này đòi hỏi bạn phải biết cách sử dụng trình soạn thảo của Linux thông qua câu lệnh vi ít nhất bạn có thể mở file và chỉnh sửa file. Lúc này bạn sẽ cần một list các câu lệnh Linux thông dụng để làm việc cho tiện, search thêm Google mỗi khi cần dùng nhé.
