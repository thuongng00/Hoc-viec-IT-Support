# Web Server
**Web server** hay còn gọi là máy chủ web, trong đó được kết nối và liên kết mạng máy tính mở rộng. Máy chủ web được cài đặt các chương trình để phục vụ ứng dụng web, chứa toàn bộ dữ liệu và nắm quyền quản lý. Web server có thể lấy thông tin requess từ phía trình duyệt web và gửi phần hồi tới máy khách thông qua HTTP hoặc giao thức khác.

Những web server được sử dụng nhiều nhất hiện nay: Apache, Nginx, IIs...

*Về mặt phần cứng*

Web server là một máy tính lưu trữ các file thành phần tạo nên một website (ví dụ: HTML, images, CSS, và file javacript...) và truyền chúng tới người dùng cuối. 

Web server được kết nối đến internet và truy cập thông qua một domain giống như mozilla.org. 

*Về mặt phần mềm*

Web server bao gồm một số phần kiểm soát người dùng web truy cập đến file host tại tối thiểu một HTTP server. Một HTTP server là một phần của phần mềm nó hiểu là URLs(web address) và HTTP (là phương thức để trình duyệt của bạn hiển thị trang web) Ở mức cơ bản nhất, bất cứ một trình duyệt nào cần một file host trên một web server, trình duyệt đó sẽ request file đó thông qua HTTP. Khi một yêu cầu được gửi đến địa chỉ web server đúng thì HTTP server gửi trở lại một yêu cầu thông qua HTTP. 

*Để công khai một trang web*

Chúng ta cần một web server tĩnh hoặc một web server động. 

- Một web server tĩnh hay bao gồm một máy tính với một HTTP server. Chúng ta gọi đó là web server tĩnh vì web server gửi cái file không hề thay đổi của nó đến trình duyệt của người dùng. 
- Một web server động bao gồm một web server tĩnh cùng với các phần mềm mở rộng của chúng, nhìn chung nhất đó là các application server và databases. Chúng ta gọi nó là web động vì application server update các host file trước khi gửi nó về trình duyệt của người dùng thông qua HTTP server. 

## Cách trả lại response của web server
Để truy nhập vào một trang web, trình duyệt của bạn gửi một yêu cầu đến server. Web server sẽ xử lý và tìm kiếm file được yêu cầu đó trong bộ nhớ của web server. Trong việc tìm file, Server sẽ đọc file đó xử lý nó nếu cần rồi gửi nó về cho trình duyệt.

## Hosting files (Web server lưu trữ các file)
Thứ nhất, web server phải lưu trữ các file của website nó là tất cả các file HTML và các file liên quan đến nó nó như css và javascript, fonts và các video ...

Về mặt kỹ thuật thì bạn có thể lưu trữ tất cả các file đó trên máy tính của mình, nhưng để thuận tiện hơn thì chúng ta nên lưu trữ dữ liệu đó trên các web server riêng rẽ có các đặc tính sau:

- Luôn chạy và hoạt động liên tục.
- Luôn luôn kết nối với internet.
- Luôn có trung một địa chỉ IP. 
- Được bảo trì bởi một bên cung cấp thứ 3. 

Vì tất cả các lý do trên việc tìm một nhà cung cấp host tốt là một phần quan trọng trong việc phát triên websites. Hiện có rất nhiều công ty cung cấp các giải pháp hosting cho việc phát triển web bạn chỉ cần chọn một trang web tốt phù hợp với ngân sách của bạn. 

## Giao tiếp thông qua HTTP

Thứ hai, một web server cung cấp các dịch vụ hỗi trợ HTTP (Hypertext Transfer Protocol). Cũng như cái tên của nó, HTTP chỉ ra cách truyền siêu văn bản giữa hai máy tính. Giao thức là tập hợp các quy tắc để truyền thông giữa hai máy tính. HTTP là một giao thức nguyên bản, vô cấp.

- Textual: tất cả các lệnh là văn bản thuần túy mà còn con người có thể đọc.
- Stateless: Cả máy chủ và khách đều không nhớ rõ các thao tác trước đó.

HTTP cung cấp một luật rất rõ ràng cho người dùng và server giao tiếp trao đổi với nhau. Bạn cần lưu ý những điều sau:

- Chỉ có khách được phép gửi request tới server và chỉ có server mới có quyền trả lời các request của khách.
- Khi yêu cầu một file thông qua HTTP, khách phải cung cấp url của file.
- Wed server phải trả lời mọi yêu cầu HTTP, ít nhất với thông báo lỗi.
- Trên web server, máy chủ HTTP có trách nhiệm xử lý và trả lời các yêu cầu đến:

Khi nhận yêu cầu, máy chủ HTTP đầu tiên sẽ kiểm tra xem URL yêu cầu có khớp với tệp hiện có hay không.  

Nếu vậy, máy chủ web gửi nội dung tệp tin về trình duyệt. 

Nếu không, máy chủ ứng dụng sẽ tạo tệp cần thiết. Nếu không thể xử lý được, máy chủ web trả lại thông báo lỗi cho trình duyệt, thông thường là "404 Not Found" NGINX

# Hoạt động của Web Server

![image](https://user-images.githubusercontent.com/111716161/189258022-f477db52-3693-4231-a8f8-b948c92105bc.png)

1. Trình duyệt phân giải tên miền thành địa chỉ IP

Trình duyệt web của bạn trước tiên cần phải xác định địa chỉ IP nào mà tên miền tech.vccloud.vn trỏ về. Nếu thông tin này không được lưu trữ sẵn trong bộ nhớ cache, trình duyệt sẽ yêu cầu thông tin từ một hoặc nhiều máy chủ DNS (thông qua internet). Máy chủ DNS sẽ cho trình duyệt biết địa chỉ IP nào tên miền sẽ trỏ đến (cũng là nới đặt trang web).

Lưu ý rằng địa chỉ IP sẽ được chỉ định khi trang web được tạo lần đầu trên máy chủ web.

2. Trình duyệt yêu cầu URL đầy đủ

Bây giờ trình duyệt web đã biết địa chỉ IP của trang web, nó có thể yêu cầu URL đầy đủ từ web server.

3. Web server gửi Trang được yêu cầu

Web server phản hồi bằng cách gửi lại trang được yêu cầu. Nếu trang không tồn tại (hoặc có lỗi khác xảy ra), nó sẽ gửi lại thông báo lỗi thích hợp.

4. Trình duyệt hiển thị trang web

Trình duyệt web của bạn nhận được trang và hiển thị trang theo yêu cầu.

Khi nói đến các trình duyệt web và web server theo cách này, ta cũng co thể hiểu theo các khái niệm máy khách (trình duyệt web) và máy chủ (web server).

# Giới thiệu về các loại web server thông dụng
1. Nginx

Loại web server được dùng khá là phổ biến hiện nay đó là Nginx, đây là 1 máy chủ reverse proxy mã nguồn mở cho các giao thức HTTP, HTTPS, SMTP, POP3 và IMAP, cũng như là 1 máy chủ cân bằng tải (load balancer), HTTP cache và web. 

Dự án Nginx được bắt đầu với việc tập trung vào tính đồng thời cao, hiệu năng cao và sử dụng tài nguyên thấp và được phát triển bởi Igor Sysoev vào nằm 2002, được phân phối ra công chúng lần đầu vào nằm 2004.

2. Internet Information Services (IIS)

IIS do Microsoft phát triển, sản phẩm này được tích hợp cùng với hệ điều hành Windows. Server. Trong IIS bao gồm nhiều dịch vụ như: dịch vụ Web Server, dịch vụ FTP Server. 

Tất cả các tính năng của web server được quản lí độc lập do đó chúng ta có thể dễ dàng thêm, loại bỏ hoặc thay thế các tính năng của web server.  

IIS đảm bảo an toàn cho máy chủ bằng cách giảm diện tích bề mặt tấn công. Giảm diện tích bề mặt tấn công là một trong những cách mạnh mẽ nhất để đảm bảo hệ thống máy chủ. Với IIS, chúng ta có thể loại bỏ những tính năng máy chủ không cần thiết để máy chủ đạt diện tích bề mặt nhỏ nhất mà vẫn giữ những tính năng cần thiết. Bằng cách loại bỏ một số tính năng máy chủ không sử dụng, chúng ta có thể làm giảm số lượng bộ nhớ mà máy chủ sử dụng, cải thiện hiệu suất bằng cách làm giảm số lượng đoạn code cần thực hiện. Bằng cách lựa chọn tập hợp các tính năng máy chủ chúng ta có thể xây dựng một máy chủ để tối ưu hóa một chức năng trong liên kết ứng dụng, chẵn hạn như bộ nhớ đệm hoặc cân bằng tải.  

Chúng ta có thể thêm các tính năng hoặc thay thế bất kì tính năng hiện có nào bằng cách sử dụng các thành phần máy chủ của bên thứ ba hoặc các thành phần chúng ta tự xây dựng trên phần mở rộng API. Cấu trúc từng phần cung cấp lợi ích lâu dài cho cộng động IIS: nó tạo điều kiện phát triển những tính năng mới khi cần thiết cho các nhà phát triển của Microsoft và cả của bên thứ ba. 

Nhờ được tích hợp ASP.NET IIS có thể sử dụng toàn bộ sức mạnh của ASP.NET. Module ASP.NET làm cho máy chủ phát triển nhanh chóng nhờ vào giao diện quen thuộc và các dịch vụ ứng dụng của ASP.NET. 

IIS hỗ trợ chứng thực người dùng, virtual hosting, CGI, FCGI, ISAPI, php, hỗ trợ Ipv6,…

3. Apache HTTP server  

Apache HTTP server hay còn được gọi là Apache là phần mềm web server được sử dụng rộng rãi nhất thế giới. Apache được phát triển và duy trì bởi một cộng đồng mã nguồn mở dưới sự bảo trợ của Apache Software Foundation. Apache được phát hành với giấy phép Apache License, là một phần mềm tự do, miễn phí.  

Apache có các tính năng như chứng thực người dùng, virtual hosting, hỗ trợ CGI, FCGI, SCGI, WCGI, SSI, ISAPI, HTTPS, Ipv6,…  

4. Apache Tomcat

Apache Tomcat là một Java Servlet được phát triển bởi Apache Software Foundation. Tomcat thi hành các ứng dụng Java Servlet và JavaServer Pages (JSP). Tomcat cung cấp một máy chủ HTTP cho ngôn ngữ Java thuần túy. Apache Tomcat là một phần mềm mã nguồn mở để chạy các ứng dụng web có nền tảng là ngôn ngữ Java. Tomcat được hỗ trợ và tăng cường bởi một nhóm tình nguyện viên từ cộng đồng mã nguồn mở của Java. 

Apache Tomcat rất ổn định và có tất cả các tính năng của một ứng dụng web thương mại nhưng đi kèm theo giấy phép mã nguồn mở của Apache. Tomcat cũng cung cấp một số chức năng bổ sung như tomcat manager application, speciallized realm imlementation và tomcat valves. Các phiên bản của apache tomcat trùng với phiên bản và đặc điểm kỹ thuật của servlet java hoặc java servlet API. Tomcat 5.5X hỗ trợ Servlet API 2.3, tomcat 6.0X hỗ trợ servlet API 2.4 và tomcat 7.0 hỗ trợ servlet API 3.0. Ngoài Servlet versions API, phiên bản tomcat hỗ trợ phiên bản JSP API tương ứng.

Apache Tomcat có các tính năng như chứng thực người dùng, virtual hosting, CGI, Java Servlet, SSI, hỗ trợ Ipv6, … 

Apache Tomcat hỗ trợ các hệ điều hành như windows, linux, OS, BSD, solaris,… 

5. Lighttpd    

Lighttpd là một phần mềm mã nguồn mở, an toàn và linh hoạt, đặc biệt miễn phí và được phân phối theo giấy phép BSD.. Lighttpd được viết bởi Jan Kneschke. Lighttpd chiếm ít tài nguyên, memory thấp, CPU nhỏ. Lighttpd được phát triển bằng ngôn ngữ C. chạy trên hệ điều hành Linux, Windows, Mac OS,…  

Lighttpd hỗ trợ FastCGI, SCGI, CGI cho phép nó chạy được các ứng dụng web được viết bằng bất cứ ngôn ngữ nào. Lighttpd còn có các tính năng như chứng thực, hỗ trợ HTTPS, virtual hosting, hỗ trợ Ipv6,… Lighttpd không hỗ trợ ISAPI (Internet Service Application Programming Interface).  
