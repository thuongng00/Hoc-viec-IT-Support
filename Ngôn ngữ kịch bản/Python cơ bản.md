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
yum -y install yum-utils  (Cài đặt yum utils)
(Cài đặt công cụ phát triển CentOs giúp xây dựng và biên dịch phần mềm từ mã nguồn)
yum -y groupinstall development 
yum -y install zlib zlib-devel
```

![image](https://user-images.githubusercontent.com/111716161/189559855-b21e0c64-a55d-45a7-a817-8ea0b0e2da3c.png)

![image](https://user-images.githubusercontent.com/111716161/189559892-0e0adf66-7c3d-4446-8b77-760d51e3bbcd.png)

![image](https://user-images.githubusercontent.com/111716161/189560673-3b956a49-142d-41a6-a4d3-0f3000e198fc.png)

Bước 3: Cài đặt tiện ích và tải phiên bản Python 3

- Cài đặt tiện ích wget

```
yum -y install wget
```

![image](https://user-images.githubusercontent.com/111716161/189560803-d1bb0ac0-c73d-406d-9b94-347c11b0f2c4.png)

- Di chuyển vào đường dẫn tmp

```
cd /tmp/
```

- Tải file nén Python 3:

```
wget https://www.python.org/ftp/python/3.8.2/Python-3.8.2.tgz
```

![image](https://user-images.githubusercontent.com/111716161/189560983-120997fe-a54e-41ff-a98a-4124ac65783d.png)

- Giải nén file vừa tải về

```
tar xvf Python-3.8.2.tgz
```

![image](https://user-images.githubusercontent.com/111716161/189561075-3d65b08b-0b12-445f-ac8a-ff07b905f69c.png)

Bước 4: Cài đặt Python 3

- Di chuyển vào thư mục vừa giải nén

```
cd Python-3.8.2/
```

- Thiết lập cài đặt

```
./configure --enable-optimizations
```

![image](https://user-images.githubusercontent.com/111716161/189561335-ef1149b0-d17a-4532-a9ff-4ebb520cc9d6.png)

- Bắt đầu biên dịch Python 3.8 trên CentOS 7 

```
make altinstall
```

![image](https://user-images.githubusercontent.com/111716161/189561353-cfb46f32-678c-4ca2-8b38-f4aa135a96b2.png)

![image](https://user-images.githubusercontent.com/111716161/189561592-3a9f3e76-45b9-4f35-9479-f2856dfe45e3.png)

Bước 5: Thiết lập Python 3 làm mặc định

Hiện tại tuy đã cài đặt thành công Python 3 nhưng hệ thống vẫn sử dụng Python 2.7 làm mặc định. Để thay đổi phiên bản mặc định thực hiện các bước sau:

- Kiểm tra vị trí Python 3 vừa cài đặt:

```
which python3.8
```

![image](https://user-images.githubusercontent.com/111716161/189561623-ccde5728-babc-4fd6-a8a3-dbb31a73a47e.png)

- Thêm bí danh (alias) vào .bash_profile

```
nano ~/.bash_profile
```

![image](https://user-images.githubusercontent.com/111716161/189561754-d33680c0-16c2-4246-8555-1e4fcc33d700.png)

Thay thế /usr/local/bin/python3.8 thành đường dẫn trên hệ thống

```
alias python='/usr/local/bin/python3.8'
```

![image](https://user-images.githubusercontent.com/111716161/189562044-10912279-e2fc-4c48-8507-d13d4717b016.png)

- Tải lại file .bash_profile bằng lệnh:

```
source ~/.bash_profile
```

Bước 6: Kiểm tra kết quả

```
python --version
```

![image](https://user-images.githubusercontent.com/111716161/189562357-f27fc5c9-7c23-401b-a2cf-ac0b03934d5c.png)

Như vậy ta đã cài đặt xong Python 3 và đặt nó làm mặc định trên CentOS 7.

