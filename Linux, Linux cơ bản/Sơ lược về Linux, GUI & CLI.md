# Kernel
Kernel là một chương trình máy tính, trái tim và cốt lõi của Hệ điều hành. Do Hệ điều hành có quyền kiểm soát hệ thống nên Kernel cũng có quyền kiểm soát mọi thứ trong hệ thống. Đây là phần quan trọng nhất của Hệ điều hành.

### Chức năng của Kernel

- Truy cập tài nguyên máy tính: Kernel có thể truy cập các tài nguyên máy tính khác nhau. Như CPU, thiết bị I/O và các tài nguyên khác. Nó hoạt động như một cầu nối giữa người dùng và tài nguyên của hệ thống.
- Quản lý tài nguyên: Nhiệm vụ của Kernel là chia sẻ tài nguyên giữa các process khác nhau.
- Quản lý bộ nhớ: Mỗi process cần một số không gian bộ nhớ. Vì vậy, bộ nhớ phải được phân bổ và truy cập để hoạt động. Tất cả những tác vụ quản lý bộ nhớ này được thực hiện bởi Kernel.
- Quản lý thiết bị: Các thiết bị ngoại vi được kết nối trong hệ thống được sử dụng bởi các process. Vì vậy, việc phân bổ các thiết bị này được quản lý bởi Kernel.

### Các loại Kernel
Có năm loại Kernel.

1. Monolithic Kernels

Monolithic Kernels là những Kernel mà các user service và kernel service được triển khai trong cùng một không gian bộ nhớ, tức là bộ nhớ khác nhau cho các user service, và kernel service không được sử dụng trong trường hợp này. Bằng cách đó, kích thước của Kernel được tăng lên và điều này sẽ làm tăng kích thước của Hệ điều hành. Vì không có User space và Kernel space riêng biệt, nên việc thực thi process sẽ nhanh hơn trong Monolithic Kernels.

![image](https://user-images.githubusercontent.com/111716161/187120927-aa9da6c0-89d1-486e-82d9-c874caba3f0f.png)

2. Microkernel

Một Microkernel khác với kernel Monolithic vì trong Microkernel, các dịch vụ người dùng và dịch vụ kernel được triển khai vào các không gian khác nhau. Vì sử dụng riêng User space và Kernel space, do đó, nó làm giảm kích thước của Kernel và do đó, làm giảm kích thước của Hệ điều hành.

![image](https://user-images.githubusercontent.com/111716161/187120982-df3249cd-d4cc-4ca3-9b79-36cc4301960b.png)

3. Hybrid Kernel

Hybrid Kernel là sự kết hợp của cả Microkernel và Monolithic Kernel. Nó sử dụng tốc độ của Monolithic Kernels và tính mô đun của Microkernel.

4. Nanokernel

Trong một Nanokrnel, như tên cho thấy, toàn bộ mã của kernel rất nhỏ, tức là mã thực thi trong chế độ đặc quyền của phần cứng là rất nhỏ.

5. Exokernel

Exokernel là một nhân hệ điều hành được phát triển bởi song song MIT và nhóm Hệ điều hành phân tán. Ở loại Kernel này, việc bảo vệ tài nguyên được tách ra khỏi quản lý và do đó, điều này dẫn đến việc cho phép chúng ta thực hiện các tùy chỉnh dành riêng cho ứng dụng.

# Operating System (hệ điều hành) GNU/Linux

GNU / Linux là sự kết hợp của các thành phần hệ điều hành và dịch vụ mà cùng nhau tạo ra hệ điều hành Linux. GNU / Linux được xem là phiên bản đầu tiên của Linux được xây dựng cùng với các thành phần và dịch vụ của GNU và hạt nhân Linux.

Hệ thống GNU/Linux làm theo hệ điều hành UNIX. Kể từ đầu, GNU/Linux đã được thiết kế như là hệ thống đa tác vụ, đa người dùng. Những sự thật này là đủ làm cho GNU/Linux khác với các hệ điều hành nổi tiếng khác. Tuy nhiên, GNU/Linux vẫn còn khác hơn. Trái ngược với hệ điều hành khác, không có ai sở hữu GNU/Linux. Phần lớn việc phát triển nó được làm bởi người tình nguyện không được tiền.

# Shell
Shell là một chương trình cung cấp giao diện giao tiếp giữa người dùng và hệ điều hành (OS). Hệ điều hành khởi động một shell cho mỗi người dùng khi người dùng đăng nhập hoặc mở một cửa sổ terminal hoặc console.

![image](https://user-images.githubusercontent.com/111716161/187121434-0b288d28-5961-47f2-b75b-a0c7d670d953.png)

### Các loại Shell

1. Bournce Shell

Bourne Shell (sh):

Là Shell được viết bởi Steve Bourne tại AT & T Bell Labs, là 1 UNIX shell đầu tiên. Shell này thích hợp sử dụng cho lập trình shell vì lợi thế về tính nhỏ gọn và tốc độ. Một nhược điểm của Bourne shell là nó thiếu các tính năng tương tác, ví dụ như tính năng gọi lại các lệnh đã sử dụng trước đó (lịch sử lệnh). Bourne Shell cũng không có các tính năng tích hợp số học và xử lý biểu thức logic.

Bourne Shell là shell mặc định của Solaris OS, là shell tiêu chuẩn cho các script quản trị hệ thống Solaris.

*Các lệnh trong Bourne shell:*

Lệnh gọi tên đường dẫn đầy đủ là / bin / sh và / sbin / sh.

Lời nhắc mặc định cho non-root user là $.

Lời nhắc mặc định cho root user là #.

2. C Shell

C shell (csh):

Là một phần cải tiến UNIX được viết bởi Bill Joy - Đại học California Berkeley.

Có các tính năng kết hợp để sử dụng tương tác, chẳng hạn như bí danh và lịch sử lệnh

Hỗ trợ các tính năng lập trình tiện lợi, chẳng hạn như số học tích hợp và cú pháp biểu thức C-like.

*Các lệnh trong C-shell:*

Lệnh tên đường dẫn đầy đủ là / bin / csh

Dấu nhắc mặc định cho non-root user là tên máy chủ %.

Dấu nhắc mặc định cho root user là tên máy chủ #.

3. Korn Shell

Korn Shell (ksh):

Được viết bởi David Korn tại AT & T Bell Labs

Là một superset của Bourne Shell

Có các tính năng tương tác tương đương với các tính năng trong C shell

Bao gồm các tính năng lập trình tiện lợi như các hàm số học và các hàm C-like, cùng các phương thức thao tác chuỗi.

Nhanh hơn C shell

Chạy các script được viết cho Bourne shell.

*Các lệnh trong Korn shell:*

Lệnh tên đường dẫn đầy đủ là / bin / ksh.

Dấu nhắc mặc định cho non-root user là $

Dấu nhắc mặc định cho root user là #.

4. GNU Bourne-Again Shell

GNU Bourne-Again shell (bash):

Tương thích với Bourne shell

Kết hợp các tính năng hữu ích từ Korn và C Shell.

Có các phím mũi tên cho phép tự động map để recall lệnh và chỉnh sửa.

*Các lệnh trong GNU Bourne-Again Shell:*

Lệnh tên đường dẫn đầy đủ là / bin / bash.

Dấu nhắc mặc định cho non-root user là bash-x.xx$. (Trong đó x.xx cho biết số phiên bản shell là gì. Ví dụ: bash-3.50 $)

Dấu nhắc mặc định cho root user bash-x.xx #. (Trong đó x.xx cho biết số phiên bản shell là gì. Ví dụ: bash-3.50 $ #).

# Distribution/Distro

Distribution là các bản phân phối linux hay còn gọi tắt là Distro giúp người dùng có thể tùy chỉnh và tự do phát triển và định hướng theo nhu cầu thực tế của mình cái mà hệ điều hành mã nguồn đóng bị hạn chế.

Như hình dưới đây ta có thể thấy có rất nhiều bản Distro Linux:

![image](https://user-images.githubusercontent.com/111716161/187122328-8fa25bba-a216-4cc5-86f0-6355273a2af3.png)
