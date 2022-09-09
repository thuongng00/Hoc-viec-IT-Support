Các command cơ bản là nền tảng để bạn có thể làm các công việc đơn giản trên môi trường Bash shell và hỗ trợ bạn trong việc tạo ra các bash script để làm các công việc phức tạp hơn. Dưới đây là liệt kê chức năng và cách sử dụng các command đó.

## 1. Nhóm command cơ bản
### export
Hiển thị danh sách tất cả các biến môi trường. Nếu bạn muốn xem chi tiết một biến cụ thể, sử dụng echo $VARIABLE_NAME.

![image](https://user-images.githubusercontent.com/111716161/189308263-da694de0-6d6b-4834-b8e4-651287ffa069.png)

### whatis
Whatis hiển thị mô tả các command của người dùng, command hệ thống, các hàm thư viện, và các command khác có trong manual page.

![image](https://user-images.githubusercontent.com/111716161/189308416-61a47b6f-5ede-440d-a3a0-b257a19cbfa6.png)

### whereis
Whereis giúp bạn tìm kiếm các file thực thi, file nguồn và các manual page sử dụng cơ sở dữ liệu được xây dựng tự động bởi hệ thống.

![image](https://user-images.githubusercontent.com/111716161/189308496-e6126ca9-9452-416f-a9f5-2493d240f9d6.png)

### Which
Which giúp bạn tìm kiếm các file thực thi từ các đường dẫn thư mục mà bạn đã đặt trong biến môi trường PATH. Command này sẽ in ra [các] đường dẫn tuyệt đối của file thực thi.

![image](https://user-images.githubusercontent.com/111716161/189308620-3e585b7a-9fd0-452f-aaf0-93101a65cedc.png)

### clear
Xóa nội dung trên cửa sổ làm việc.

![image](https://user-images.githubusercontent.com/111716161/189308718-18153798-4968-4121-a698-2f6ca0105ebb.png)

## 2. Nhóm command thao tác tệp

### cat

Hiển thị nội dung tệp tin văn bản lên màn hình
- Copy các tệp tin văn bản
- Gộp các tệp tin văn bản
- Tạo các tệp tin văn bản mới

```
cat filename
cat file1 file2
cat file1 file2 > newcombinedfile
cat < file1 > file2  #copy file1 sang file2
```

### chmod
Command chmod là viết gọn của “change mode”. Nó cho phép bạn thay đổi các quyền đọc (read), ghi (write) và thực thi (excute) của các tệp và thư mục. 

```
chmod -options filename
```

### cp
Copy một tệp tin từ vị trí này tới vị trí khác.

```
cp file1 file2
```

### diff
So sánh các tệp tin và hiển thị ra các sự khác biệt.

```
diff file1 file2
```

### file
Xác định loại tệp tin và hiển thị thông tin encoding.

```
file filename
```

### find
Tìm kiếm các tệp tin trong một thư mục.

### gunzip
Giải nén các tệp tin nén bởi gzip.

### gzcat
Cho phép bạn xem nội dung các tệp tin nén gzip mà không cần phải gunzip chúng.

### gzip
Dùng để nén các tệp tin.

### head
Hiển thị n=10 (mặc định) dòng đầu tiên của một tệp tin. Nếu muốn thay đổi n, sử dụng 

```
head -n <number> filename.
```

### lpq
Kiểm tra hàng đợi máy in.

### lpr
Thực hiện in 1 tệp tin.

### lprm
Xóa lệnh in đang có trong hàng đợi máy in.

### ls
Liệt kê các tệp tin và thư mục. ls có rất nhiều tham số: -l để hiển thị dạng danh sách với các thông tin kích thước, chủ sở hữu, ai có quyền thao tác và thời gian thay đổi lần cuối của các tệp tin. -a sẽ hiển thị tất cả các tệp tin (bao gồm các tệp tin bị ẩn).

### more
Hiển thị một phần đầu nội dung của tệp tin (xem thêm bằng phím cách, gõ q để thoát).

### mv
Di chuyển một tệp tin từ vị trí này tới vị trí khác.

```
mv filename1 filename2
```

Trong đó filename1 là đường dẫn ban đầu của tệp tin và filename2 là đường dẫn nơi bạn muốn chuyển tệp tin tới.

Và command này cũng dùng để đổi tên tệp tin hoặc thư mục.

```
mv oldname newname
```

### rm
Xóa một tệp tin. Sử dụng command này với thư mục bạn sẽ gặp báo lỗi.
rm: directory: is a directory
Để xóa một thư mục, bạn cần truyền tham số -r để nó xóa thư mục đó và toàn bộ nội dung bên trong. Bạn có thể bổ sung tham số -f để yêu cầu xóa và bỏ qua xác nhận của hệ thống.

### tail

Giống head command, nhưng là hiển thị nội dung ở cuối tệp tin. Sử dụng tham số -n nếu muốn thay đổi số lượng dòng hiển thị.

### touch
Cập nhật thời gian truy cập và sửa đổi của tệp tin tới thời gian hiện tại. Nếu tệp tin đó không tồn tại, nó sẽ được tạo ra.

## 3. Nhóm command thao tác văn bản

## awk
awk là một trong những command rất hữu ích để làm việc với các tệp tin văn bản. Nó tác động tới từng dòng nội dung của văn bản. Mặc định awk sẽ dùng khoảng trắng để phân tách các trường. Cú pháp thông dụng nhất của awk là

### cut
Xóa một phần nội dung ở mỗi dòng của các tệp tin văn bản.

### echo
Hiển thị một dòng văn bản lên màn hình.

### egrep
Tìm và xuất ra các dòng khớp với một pattern nào đó – Extended Expression (đại diện cho: grep -E).

### fgrep
Tìm và xuất ra các dòng khớp với một pattern nào đó – FIXED pattern matching (alias for: grep -F).

### fmt
Định dạng lại cách hiển thị văn bản.

### grep
Tìm kiếm văn bản trong các tệp tin. Bạn có thể sử dụng grep để tìm các dòng văn bản khớp với một hoặc nhiều biểu thức chính quy (regular expression). Command này sẽ chỉ xuất ra các dòng khớp với điều kiện của bạn.

### nl
Thêm số thứ tự dòng vào đầu các dòng trong tệp văn bản.

### sed
Trình chỉnh sửa phục vụ cho việc tạo bộ lọc (filter) và chuyển đổi (tranform) dữ liệu văn bản.

### sort
Sắp xếp các dòng văn bản trong một tệp tin. Sử dụng tham số -r để sắp xếp theo thứ tự đảo ngược.

### tr
Thay đổi hoặc xóa các ký tự.

### uniq
Xóa trùng lặp dữ liệu trong tệp tin văn bản

### wc
Cho chúng ta biết tệp tin có bao nhiêu dòng, bao nhiều từ và bao nhiêu ký tự trong đó.

## 4. Nhóm command thao tác thư mục

### cd
cd là viết tắt của “change directory”. Nó giúp bạn di chuyển vị trí làm việc. 

### mkdir
Tạo một thư mục mới.

### pwd
Cho bạn biết đường dẫn tuyệt đối của thư mục nơi bạn đang làm việc. Viết tắt của print working directory

## 5. Nhóm command SSH, thông tin hệ thống & mạng
### bg
Hiển thị danh sách các backgroud job (công việc chạy trong nền).

### cal
Hiển thị lịch của tháng hiện tại.

![image](https://user-images.githubusercontent.com/111716161/189310234-e8491daf-0d4d-45c1-88e8-3969f31bacd8.png)

### date
Hiển thị ngày và giờ của thời điểm hiện tại.

![image](https://user-images.githubusercontent.com/111716161/189310303-63840d7b-9046-4754-b38d-1024531a8599.png)

### df
Hiển thị mức dùng ổ đĩa: đã dùng bao nhiêu, còn trống bao nhiêu

![image](https://user-images.githubusercontent.com/111716161/189310367-4ddf78c0-d047-4f44-9281-9c7295359622.png)

### dig
Kiểm tra thông tin bản ghi DNS của một tên miền.

![image](https://user-images.githubusercontent.com/111716161/189310456-e673acd4-714a-4cb3-a183-6259b8d6309d.png)

### du
Hiển thị mức sử dụng ổ đĩa của các tệp tin hoặc thư mục.

![image](https://user-images.githubusercontent.com/111716161/189310549-34695404-44c8-4bad-a93c-5a34826348e9.png)

Các option:

-h (Dễ đọc hơn) Hiển thị mức dùng ở đơn vị (KB), (MB) và (GB).

-s (Tóm tắt) Hiển thị mức dùng ổ đĩa của thư mục một cách tóm tắt.

### fg
Di chuyển các job lên foreground (chuyển từ chạy trong nền ra chạy trên màn hình console)

### finger

Hiển thị thông tin về một user.

```
finger username
```

### jobs
Liệt kê các job đang chạy trong backgroud, cung cấp cho bạn chỉ số job (job number).

### last
Liệt kê các thông tin đăng nhập cuối cùng của bạn về người dùng được chỉ định.

```
last yourUsername
```

### man
Hiển thị tài liệu hướng dẫn (manual page) của command cụ thể.

```
man command
```

### passwd
Cho phép user đang đăng nhập thay đổi mật khẩu đăng nhập.

### ping
PING tới 1 host nào đó kèm theo kết quả. Được dùng để kiểm tra xem máy của bạn có kết nối tới host đó hay không.

### ps
Liệt kê các tiến trình hiện có của bạn.

### quota
Cho biết mức dùng ổ đĩa của bạn là bao nhiêu.

### scp
Truyền dữ liệu từ máy localhost tới máy remote hoặc ngược lại.

### ssh
ssh (SSH client) là một chương trình cho phép bạn đăng nhập và thực thi các command trên 1 máy remote từ máy tính của bạn.

### top
Hiển thị các tiến trình đang được kích hoạt.

### uname
Hiển thị thông tin nhân hệ điều hành.

### uptime
Hiển thị thời gian hoạt động (uptime).

### w
Displays who is online.
Hiển thị user nào đang online.

### wget
Download tệp tin từ internet.

### whoami
Trả về username của user đang đăng nhập.

### whois
Xem thông tin whois của một tên miền.

## 6. Nhóm command thác tác tiến trình

### kill
Bắt buộc dừng (kết thúc) một tiến trình có PID mà bạn cung cấp.

### killall
Bắt buộc dừng (kết thúc) tất cả các tiến trình theo tên tiến trình.

### &
Ký tự & chỉ định cho một command phải chạy ở chế độ background.

### nohup
nohup là viết tắt của “No Hang Up”. Nó cho phép bạn chạy các command hoặc tiến trình trong backgroud ngay cả khi bạn đăng xuất (logout, không đồng nghĩa với tắt máy) khỏi terminal.
