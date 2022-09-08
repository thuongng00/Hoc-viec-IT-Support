# Một process hoạt động thế nào?
Khi hệ thống khởi động, kernel sẽ khởi tạo một vài hành vi của riêng nó dưới một process và khởi động một chương trình gọi là init. init theo đó sẽ khởi chạy một loạt các shell script (nằm ở /etc) được gọi là init script, sẽ khởi động tất cả các service hệ thống.

Rất nhiều service này được implement dưới dạng daemon program, chương trình chạy background mà không can thiệp tới giao diện người dùng. Vì thế kể cả khi chúng ta không đăng nhập thì hệ thống cũng ở trạng thái busy một lúc để khởi chạy.

Chương trình có thể khởi chạy một chương trình khác được diễn giải trong cơ chế process gọi là process cha sinh ra process con.

Kernel sẽ duy trì thông tin về mỗi một process. Ví dụ: mỗi process được gán cho một giá trị là PID (process ID). PID được gán theo thứ tự tăng dần và init luôn có PID là 1. Kernel cũng theo dõi thông tin bộ nhớ gán cho mỗi process, cũng như tính sẵn sàng của process để có thể tiếp tục thực thi.

Cũng như file thì process cũng có owner và user ID, ...
