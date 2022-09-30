# File Server

File server (máy chủ tệp tin), là một máy tính chính có trách nhiệm lưu trữ và quản lý tệp dữ liệu để các máy tính khác trong cùng một mạng có thể truy cập tệp. Nó cho phép người dùng chia sẻ thông tin qua mạng mà không cần phải chuyển tệp hay sử dụng đĩa ngoài hoặc các thiết bị lưu trữ khác.

![image](https://user-images.githubusercontent.com/111716161/193169990-1ce34b21-e9dd-47ef-bd35-66a70985b728.png)

Máy chủ đảm nhận vai trò máy tính hoặc máy chủ để lưu trữ và cung cấp các dữ liệu có sẵn cho máy khách, trở thành 1 vị trí trung tâm để lưu trữ và chia sẻ tệp cho một mạng, có thể được giới hạn trong một mạng cục bộ (LAN) hoặc được mở với Internet.

## Hoạt động của File Server

File server làm cho máy khách có thể truy cập hệ thống tệp từ xa. Chúng có thể lưu trữ bất kì loại dữ liệu nào ví dụ: tài liệu, ảnh video…

File server thường được lưu trữ dữ liệu dưới dạng các đốm màu của dữ liệu hoặc tệp nhị phân. Như vậy có nghĩa là chúng không thực hiện lập chỉ mục bổ sung hoặc xử lý các tệp được lưu trữ trên chúng. File server không cung cấp các cách tích hợp để tương tác với dữ liệu và dựa vào máy khách để sử dụng nó.

![image](https://user-images.githubusercontent.com/111716161/193170102-98815caa-a3a2-456a-8e41-4485d9de90ed.png)

File server thường bao gồm các tính năng bổ sung để cho phép nhiều người dùng cùng truy cập:

- Phân quyền sử dụng.
- Khóa tệp sẽ ngăn nhiều người dùng chỉnh sửa một tệp cùng lúc.
- Giải quyết xung đột duy trì được tính toàn vẹn của dữ liệu trong trường hợp tệp bị ghi đè.
- Tệp phân tán cho phép người dùng của hệ thống phân tán vật lý chia sẻ dữ liệu và tài nguyên của chúng bằng cách sử dụng hệ thống tệp chung.

## Giao thức của File Server

Điểm nổi trội của file server là hỗ trợ đa giao thức AFP, FTP, NFS, SMB, WebDAV, HTTP. Nhờ như vậy mà các dữ liệu lưu trữ trên Synology được truy cập mọi lúc, mọi nơi từ các hệ điều hành Windows, Mac, Linux.

Các giao thức được sử dụng trong File server, chúng cung cấp các tính năng khác nhau và khả năng tiếp cận khách hàng khác nhau:

- SMB là giao thức phổ biến nhất cho các máy chủ tệp mạng LAN. SMB vốn được hỗ trợ cho các hệ điều hành Windows và macOS. Linux và Unix có thể truy cập hoặc phục vụ SMB bằng Samba hoặc CIFSD, một phiên bản mã nguồn mở của Hệ thống tệp Internet chung.
- NFS chủ yếu được sử dụng bởi hệ điều hành Linux và Unix. Vì thế, nó không phổ biến đối với máy chủ tệp người dùng cuối nhưng có thể được sử dụng để truy cập tệp máy chủ.
- FTP và SFTP (FTP security) được thiết kế để cung cấp tệp qua Internet. FTP thường được sử dụng để tải xuống và tải lên các tệp; nó không được thiết kế để máy khách thực thi dữ liệu từ hệ thống tệp từ xa một cách trực tiếp.

## Bảo mật

File server lưu trữ giữ liệu quan trọng nhất trong một tổ chức. Việc mất dữ liệu sẽ làm ảnh hưởng cũng như để lại hậu quả vô cùng nghiêm trọng đến bất kì hoạt động kinh doanh nào. Do đó file server cần được bảo vệ khỏi sự cố thảm họa hay tấn công.

Sao lưu là cơ bản để vạn hành file server. Một bản sao lưu tốt sẽ luôn đảm bảo được dữ liệu vẫn có sẵn hoặc có thể phục hồi trong trường hợp phần cứng bị lỗi hoặc tấn công từ bên ngoài.

Phương pháp tốt nhất là giữ một số bản sao lưu dữ liệu quan trọng ở một ví trí thực tế khác và phải ở chế độ ngoại tuyến hoặc không được kết nối với mạng. Bằng cách này ngay cả khi bị phá hủy dữ liệu trung tâm hoặc nếu ransomware mã hóa máy chủ tệp, các tệp vẫn có thể được khôi phục. Quan trọng là phải kểm tra các bản sao lưu tệp thường xuyên.

File server là mục tiêu có giá trị cao đối với những kẻ tấn công vì vậy cần phải cách ly khỏi internet. Quyền với tệp cần được kiểm tra, cập nhật thường xuyên để đảm bảo luôn được hoạt động tốt và không bị khai thác. Cảnh bảo, kiểm tra thông báo về các hoạt động lạ để dừng các chương trình mã hóa hoặc đào thải tệp.

## Ưu, nhược điểm

### Ưu điểm
- Chi phí phù hợp với lợi ích mang lại.
- Dễ dàng mở rộng và tùy biến.
- Khả năng sao lưu và phục hồi dễ dàng khi cần.
- Dễ dàng quản lý từ xa.
- Công suất và hiệu suất cao.

### Nhược điểm
- Yêu cầu quyền quản lý cần có trình độ chuyên môn nhất định.
- Cần được bảo mật.
- Siêu dữ liệu tích hợp bị hạn chế và thao tác tệp khá phức tạp.
- Cần được lên kế hoạch cho công xuất bổ sung.

