# Giới thiệu về Samba

Samba là một ứng ụng chạy trên Unix và nó mô phỏng một hệ thống Windows. Samba cho phép một hệ thống Unix gia nhập vào “Network neighborhood” và người dùng Windows có thể truy cập tài nguyên trên Unix.

![image](https://user-images.githubusercontent.com/111716161/193727792-026a286c-1dfd-4cd0-a3d7-4f192d9b52e5.png)

Samba thực hiện được nhờ vào sự mô phỏng giao thức CIFS hay” Common Internet File System” và giao thức truyền tin SMB hay “Server Message Block”

Nói gọn lại samba là một phần mệ miễn phí chủ yếu sử dụng để chia sẻ file giữa các nền tảng khác nhau như Windows và Linux bằng cách sử dụng giao thức SMB/CIFS.

Samba bao gồm 2 chương trính chính và một số công cụ hỗ trợ. Hai chương trình chính là.

- smbd : dịch vụ tệp và máy in, xác thực phân quyền truy cập tài nguyên.
- nmdb : Phân giải tên và thông báo cá dịch vụ ra bên ngoài

Một sô công cụ hỗ trợ samba là:

- smbclient: có chức năng tương tự NFS, kết nối từ hệ thống unix tới smb share của một hệ thống windows để truyền tệp, gửi tệp.
- nmblookup: Phân giải tên NetBIOS. để tìm địa chỉ IP tương ứng và các thông tin của máy chạy Windows
- swat : cho phép cấu hình samba qua giao diện web.

# Giao thức SMB

SMB được viết tắt của từ Server Message Block, là một giao thức trong hệ điều hành Windows và DOS. SMB cung cấp cơ chế để các máy khách (client) có thể truy cập vào hệ thống file máy chủ (server), cũng như những thiết bị input/output (ví dụ như máy in). 

![image](https://user-images.githubusercontent.com/111716161/193727724-0dd1c5b6-458c-4f68-8428-a5daddff1d09.png)

## Cách thức hoạt động sơ bộ của giao thức SMB

Đối với giao thức SMB (tên gọi sơ khai của CIFS), nó hoạt động trong mạng Internet dựa trên giao thức TCP/IP. Và đem đến cho người dùng toàn quyền trong việc tạo một tập tin với các quyền hạn như Chỉ đọc (Read Only), Đọc và ghi (Read-Write), đặt mật khẩu, khóa một tập tin, …. 

Ngoài ra, SMB còn hỗ trợ các tính năng khác như:

- Đàm phán, dàn xếp để tương thích giữa các hình thái SMB
- Phát hiện các máy chủ sử dụng SMB trên mạng (browse network)
- Xác thực truy cập file, thư mục chia sẻ
- Thông báo sự thay đổi file và thư mục
- Xử lý các thuộc tính mở rộng của file
- Hỗ trợ Unicode

![image](https://user-images.githubusercontent.com/111716161/193536053-12fa697a-7363-46ca-be76-3d2b3c1f92e9.png)

## Chức năng của giao thức SMB

Một điểm mạnh của giao thức SMB mà nhiều công cụ khác không có được chính là hỗ trợ cả Unicode. Bên cạnh đó thì SMB còn có những chức năng quan trọng khác như:

- Hỗ trợ tìm kiếm máy chủ sử dụng giao thức SMB khác.
- Hỗ trợ in qua mạng.
- Cho phép xác thực các file và thư mục được chia sẻ.
- Thông báo những thay đổi của file và thư mục.
- Xử lý những thuộc tính mở rộng của file.
- Hỗ trợ dàn xếp, đàm phán để tương thích giữa các hình thái của SMB.
- Cho phép khóa file đang truy cập tùy theo yêu cầu.
- Khi sử dụng SMB kết hợp với giao thức xác thực NTLM người dùng sẽ được cung cấp trọn gói chia sẻ file, máy in ở mức user. Chỉ cần thực hiện đăng nhập kết nối với dữ liệu ở máy khác, Windows sẽ lập tức gửi dữ liệu thông tin đăng nhập của người dùng đó về SMB trước khi yêu cầu tên đăng nhập và mật khẩu.

## Làm thế nào để tắt được SMB?

Để ngăn chặn sự xâm nhập của virus vào máy tính của bạn và bảo mật thông tin các bạn có thể disable SMB. Tai sao SMB lại dễ bị tấn công bởi virus? Vì là giao thức chia sẻ các file nên nó phải có các port mạng để kết nối các hệ thống máy tính với nhau, hơn thế nữa SMB sử dụng port 139 và port 445. 

Để tắt được SMB trên máy tính của mình, các bạn có thể thực hiện như sau:
- Update Windows: nên thường xuyên cập nhật các bản mới của Windows để vá các lỗ hổng, đặc biệt là lỗ hổng ETERNALBLUE.
- Disable hỗ trợ SMBv1: để tắt được SMB bằng cách này, bạn mở cửa sổ Command Prompt và cho chạy lệnh: “dism/online/norestart/disable-feature/featurename:SMB1Protocol”.
- Chặn các port 135, 445: SMB sử dụng các port này và đây cũng là cách mà virus hay xâm nhập vào hệ thống. Do vậy nếu không cần sử dụng, các bạn nên đóng các port này bằng cách mở cửa sổ Command Prompt và chạy lệnh:
```
netsh advfirewall firewall add rule dir=in action=block protocol=TCP localport=135
name=”Block_TCP-135″
netsh advfirewall firewall add rule dir=in action=block protocol=TCP localport=445 name=”Block_TCP-445″.
```

## Cách phòng chống khi sử dụng giao thức SMB
Nếu bạn vẫn có nhu cầu sử dụng giao thức SMB nhưng vẫn muốn bảo vệ tốt nhất cho hệ thống máy tính của mình, các bạn có thể thực hiện một vài biện pháp sau:
- Khởi chạy tường lửa hoặc để chế độ Endpoint Protection để bảo vệ port SMB và cập nhật blacklist để ngăn chặn các kết nối từ địa chỉ IP đã tấn công trước đó.
- Thiết lập VPN để mã hóa và bảo vệ lưu lượng mạng.
- Sử dụng mạng VLAN riêng với lưu lượng nội bộ.
- Sử dụng bộ lọc địa chỉ MAC để phát hiện và ngăn chặn những địa chỉ không xác định đang muốn truy cập.
