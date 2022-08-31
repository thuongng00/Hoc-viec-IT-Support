## 1. Các lệnh kiểm tra thông tin hệ thống trong Linux
| Lệnh Linux	| Mô tả |
|-------------------|-------|
| cat /proc/cpuinfo	| Kiểm tra thông tin CPU (số core) |
| cat /proc/meminfo	| Kiểm tra thông tin về RAM đang sử dụng |
| cat /proc/version	| Kiểm tra phiên bản của Kernel Linux |
| cat /proc/ioports	| Xem thông tin port I/O |
| cat /etc/redhat-release	| Kiểm tra phiên bản Centos |
| uname -a	| Kiểm tra các thông tin về Kernel |
| free -m	| Kiểm tra dung lượng RAM còn trống |
| init 0	| Tắt máy (tương đương lệnh shutdown -h now hoặc telinit 0) |
| df -h	| Hiển thị thông tin những file hệ thống, nơi file được lưu hoặc tất cả những file mặc định. Lệnh này có thể xem được dung lượng ổ cứng đã sử dụng và còn trống. |
| du -sh	| Kiểm tra dung lượng thư mục hiện tại |
| du  -ah	 | Hiển thị dung lượng của thư mục con và các file trong thư mục hiện tại |
| du -h –max-depth=1	| Hiển thị dung lượng các thư mục con ở cấp 1 (ngay trong thư mục hiện tại) |
| df	| Kiểm tra dung lượng đĩa cứng, các phân vùng đĩa |
| lspci	| Xem thông tin mainboard   
| /sbin/ifconfig | Xem các địa chỉ IP của máy |
| hostname	| Xem tên máy (hostname) |
| finger user@server	| Thu thập thông tin chi tiết về người dùng hiện đang dùng hệ thống |
| arch	| Kiểm tra kiến trúc của máy (architech) |
| cat /proc/swaps	| Kiểm tra thông tin SWAP của máy (tương tự như virtual RAM của Windows) |
| last reboot	| Xem lịch sử reboot máy |

## 2. Các lệnh shutdown, restart… trong Linux
| Lệnh Linux	| Mô tả |
|-------------|-------|
| logout	| Kết thúc session (phiên làm việc) hiện tại |
| reboot	| Khởi động lại máy |
| shutdown -r now	| Khởi động lại máy (tương đương với lệnh reboot) |
| shutdown -h now	| Tắt máy (ngay lập tức) |
| shutdown -h 9:30	| Hẹn giờ tắt máy (schedule) vào lúc 9h30 (tính theo khung 24h) |
| shutdown -c	| Hủy bỏ tất cả các lệnh tắt máy trước đó (các lệnh tắt máy theo schedule) |
| telinit 0	| Tắt máy (tương đương lệnh shutdown -h now) |
| init 0	| Tắt máy (tương đương lệnh shutdown -h now hoặc telinit 0) |
| exit	| Thoát khỏi terminal |
| halt	| Tắt máy (tương tự shutdown) |
| sleep	| Cho hệ thống ngừng hoạt động trong một thời gian (ngủ – tương tự Windows) |

## 3. Các lệnh về quản lý user trong Linux
| Lệnh Linux	| Mô tả |
|-------------|-------|
| passwd	| Đổi mật khẩu (standard user có thể đổi pass của họ còn user root thì thay đổi được password của mọi user) |
| pwck	| Kiểm tra syntax và định dạng của dữ liệu user/password (/etc/passwd) |
| useradd	| Tạo user mới, ví dụ: useradd -c “test user 1” -g group1 |
| userdel	| Xóa User |
| usermod	| Thay đổi thông tin user (group, name…) |
| groupadd	| Tạo một nhóm user mới |
| groupdel	| Xóa nhóm user | 
| groupmod	| Thay đổi thông tin group, ví dụ, groupmod -n “old group name”  “new name” |
| who /w	| Hiển thị những user đang đăng nhập hệ thống |
| uname	| Hiển thị tên của hệ thống (host) |
| id	| Hiển thị user ID (Chỉ danh của user) |
| logname	| Hiển thị tên user đang login |
| su	| Cho phép đăng nhập với tên user khác (tương tự secondary logon của Windows) |
| groups	| Hiển thị nhóm của user hiện tại |
| #vi /etc/passwd	| Xem danh sách user |
| #vi /etc/group	| Xem danh sách nhóm (group) |
| chmod [tên file=””][/tên]	| Thay đổi quyền cho file/thư mục (chỉ user sở hữu file mới thực hiện được) |
| chown user [tên file=””][/tên]	| Thay đổi chủ sở hữu file/thư mục |
| chgrp group [file][/file]	| Thay đổi group sở hữu file/thư mục |
