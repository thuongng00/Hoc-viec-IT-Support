# Ảo hóa là gì?

Trong ngành công nghệ thông tin, ảo hóa là hành động tạo một phiên bản ảo của bất kỳ tài nguyên nào (ví dụ như máy chủ, hệ thống mạng, storage device, hệ điều hành) thành một hay nhiều môi trường thực thi. Trong đó, người dùng, thiết bị và ứng dụng đều dễ dàng tương tác với tài nguyên ảo tương tự như tài nguyên thực. 

Ảo hóa sử dụng phần mềm mô phỏng chức năng phần cứng để tạo ra một hệ thống ảo. Thực tiễn này cho phép các tổ chức CNTT vận hành nhiều hệ điều hành, nhiều hệ thống ảo và các ứng dụng khác nhau trên một máy chủ duy nhất. Các lợi ích của ảo hóa bao gồm hiệu quả cao hơn và tính kinh tế theo quy mô.

Ảo hóa hệ điều hành là việc sử dụng phần mềm để cho phép một phần cứng chạy nhiều hình ảnh hệ điều hành cùng một lúc. Công nghệ này đã bắt đầu xuất hiện trên các máy tính lớn từ nhiều thập kỷ trước, cho phép các quản trị viên tránh lãng phí sức mạnh xử lý đắt tiền.

# Cách thức hoạt động của ảo hóa

Ảo hóa mô tả một công nghệ trong đó ứng dụng, hệ điều hành khách (client OS) hoặc bộ lưu trữ dữ liệu được trừu tượng hóa khỏi phần cứng hoặc phần mềm cơ bản thực sự. Công dụng chính của công nghệ ảo hóa là ảo hóa máy chủ, sử dụng một lớp phần mềm – được gọi là siêu giám sát (hypervisor) – để mô phỏng phần cứng bên dưới.

Điều này thường bao gồm bộ nhớ của CPU, đầu vào/đầu ra (I/O) và lưu lượng mạng. Người giám sát lấy các tài nguyên vật lý và tách chúng ra để chúng có thể được sử dụng bởi môi trường ảo. Chúng có thể ngồi trên hệ điều hành hoặc được cài đặt trực tiếp vào phần cứng. Phần phía sau là cách hầu hết các doanh nghiệp ảo hóa hệ thống của họ.

Xen hypervisor là một chương trình phần mềm mã nguồn mở chịu trách nhiệm quản lý các tương tác cấp thấp xảy ra giữa các máy ảo (VM – Virtual machine) và phần cứng vật lý. Nói cách khác, Xen hypervisor cho phép tạo, thực thi và quản lý đồng thời các máy ảo khác nhau trong một môi trường vật lý.

Với sự trợ giúp của hypervisor, hệ điều hành khách – bình thường tương tác với phần cứng thực – giờ đang làm như vậy với một mô phỏng phần mềm của phần cứng đó. Thông thường, hệ điều hành khách không biết nó ở trên phần cứng ảo hóa.

Mặc dù hiệu suất của hệ thống ảo này không bằng hiệu suất của hệ điều hành chạy trên phần cứng thực, nhưng khái niệm ảo hóa hoạt động vì hầu hết các hệ điều hành khách và ứng dụng không cần sử dụng toàn bộ phần cứng bên dưới.

Điều này cho phép linh hoạt hơn, kiểm soát và cách ly bằng cách loại bỏ sự phụ thuộc vào một nền tảng phần cứng nhất định. Mặc dù ban đầu có nghĩa là ảo hóa máy chủ, nhưng khái niệm ảo hóa đã lan rộng đến các ứng dụng, mạng, dữ liệu và máy tính để bàn.

