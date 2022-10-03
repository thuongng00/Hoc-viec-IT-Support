# Giới thiệu về Samba

Samba là một ứng ụng chạy trên Unix và nó mô phỏng một hệ thống Windows. Samba cho phép một hệ thống Unix gia nhập vào “Network neighborhood” và người dùng Windows có thể truy cập tài nguyên trên Unix.

Samba thực hiện được nhờ vào sự mô phỏng giao thức CIFS hay” Common Internet File System” và giao thức truyền tin SMB hay “Server Message Block”

Nói gọn lại samba là một phần mệ miễn phí chủ yếu sử dụng để chia sẻ file giữa các nền tảng khác nhau như Windows và Linux bằng cách sử dụng giao thức SMB/CIFS.

Samba bao gồm 2 chương trính chính và một số công cụ hỗ trợ. Hai chương trình chính là.

- smbd : dịch vụ tệp và máy in, xác thực phân quyền truy cập tài nguyên.
- nmdb : Phân giải tên và thông báo cá dịch vụ ra bên ngoài

Một sô công cụ hỗ trợ samba là:

- smbclient: có chức năng tương tự NFS, kết nối từ hệ thống unix tới smb share của một hệ thống windows để truyền tệp, gửi tệp.
- nmblookup: Phân giải tên NetBIOS. để tìm địa chỉ IP tương ứng và các thông tin của máy chạy Windows
- swat : cho phép cấu hình samba qua giao diện web.

# Cách thức hoạt động sơ bộ của giao thức SMB

Đối với giao thức SMB (tên gọi sơ khai của CIFS), nó hoạt động trong mạng Internet dựa trên giao thức TCP/IP. Và đem đến cho người dùng toàn quyền trong việc tạo một tập tin với các quyền hạn như Chỉ đọc (Read Only), Đọc và ghi (Read-Write), đặt mật khẩu, khóa một tập tin, …. Ngoài ra, SMB còn hỗ trợ các tính năng khác như:

- Đàm phán, dàn xếp để tương thích giữa các hình thái SMB
- Phát hiện các máy chủ sử dụng SMB trên mạng (browse network)
- Xác thực truy cập file, thư mục chia sẻ
- Thông báo sự thay đổi file và thư mục
- Xử lý các thuộc tính mở rộng của file
- Hỗ trợ Unicode

![image](https://user-images.githubusercontent.com/111716161/193536053-12fa697a-7363-46ca-be76-3d2b3c1f92e9.png)

