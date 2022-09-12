# Tổng quan ngôn ngữ Python

**Ngôn ngữ Python** được Guido van Rossum tạo ra cuối năm 1990. 

Python khá giống Perl, Ruby, Scheme, Smalltalk và Tcl. 

Python được phát triển trong một dự án mã mở do một tổ chức phi lợi nhuận Python Software Foundation quản lý. 

Python được phát triển để chạy trên nền Unix. Nhưng theo thời gian, nó đã "bành trướng" sang mọi hệ điều hành từ MS-DOS đến MACOS, OS/2, Windows, Linux và một số hệ điều hành khác thuộc họ Unix.

Python là ngôn ngữ bậc cao (high-level) có hình thức sáng sủa, cấu trúc rõ ràng, thuận tiện cho người mới học lập trình. Cho phép người sử dụng viết mã với số lần gõ phím tối thiểu. 

Python cũng là một trong những ngôn ngữ phổ biến nhất thế giới.

Sau đây là các đặc điểm của Python:
- Ngữ pháp đơn giản, dễ đọc.
- Vừa hướng thủ tục (procedural-oriented), vừa hướng đối tượng (object-oriented)
- Hỗ trợ module và hỗ trợ gói (package)
- Xử lý lỗi bằng ngoại lệ (Exception)
- Kiểu dữ liệu động ở mức cao.
- Có các bộ thư viện chuẩn và các module ngoài, đáp ứng tất cả các nhu cầu lập trình.
- Có khả năng tương tác với các module khác viết trên C/C++ (Hoặc Java cho Jython, hoặc .Net cho IronPython).
- Có thể nhúng vào ứng dụng như một giao tiếp kịch bản (scripting interface).

Những điều Python có thể làm được:
- Lập trình Web: Youtube, Google, Dropbox, Quora, Reddit, Instagram, Nasa, Firefox, Yahoo Maps...
- Lập trình robot.
- Lập trình game.
- Lập trình ứng dụng.
- Bảo mật mạng và máy tính. 

# Cài đặt Python 3

Bước 1: Kiểm tra phiên bản Python đang sử dụng

Mặc định Python được cài đặt trên CentOS 7 là phiên bản Python 2.7.x. 

Sử dụng lệnh sau để kiểm tra phiên bản:
```
python --version
```

![image](https://user-images.githubusercontent.com/111716161/189559414-664bc7fe-8b13-4429-8840-2211baea931c.png)

Phiên bản ở đây là 2.7.5, ta sẽ nâng cấp lên phiên bản Python 3.

Bước 2: Cập nhật công cụ quản lý Yum

```
yum -y update  (Cập nhật yum)
yum -y install yum-utils  (Cài đặt ym utils)
yum -y groupinstall development (Cài đặt công cụ phát triển CentOs giúp xây dựng và biên dịch phần mềm từ mã nguồn)
```

![image](https://user-images.githubusercontent.com/111716161/189559855-b21e0c64-a55d-45a7-a817-8ea0b0e2da3c.png)

![image](https://user-images.githubusercontent.com/111716161/189559892-0e0adf66-7c3d-4446-8b77-760d51e3bbcd.png)








