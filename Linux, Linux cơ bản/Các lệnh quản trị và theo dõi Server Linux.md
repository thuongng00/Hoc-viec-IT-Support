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
