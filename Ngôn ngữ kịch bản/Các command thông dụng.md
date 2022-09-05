Các command cơ bản là nền tảng để bạn có thể làm các công việc đơn giản trên môi trường Bash shell và hỗ trợ bạn trong việc tạo ra các bash script để làm các công việc phức tạp hơn. Dưới đây là liệt kê chức năng và cách sử dụng các command đó.

## 1. Nhóm command cơ bản
### export
Hiển thị danh sách tất cả các biến môi trường. Nếu bạn muốn xem chi tiết một biến cụ thể, sử dụng echo $VARIABLE_NAME.

![image](https://user-images.githubusercontent.com/111716161/188342922-503a9604-b267-480a-b103-e8de8b942608.png)

### whatis
Whatis hiển thị mô tả các command của người dùng, command hệ thống, các hàm thư viện, và các command khác có trong manual page.

![image](https://user-images.githubusercontent.com/111716161/188342999-f96d04ed-eb10-46ea-9f71-80eb93deaa31.png)

### whereis
Whereis giúp bạn tìm kiếm các file thực thi, file nguồn và các manual page sử dụng cơ sở dữ liệu được xây dựng tự động bởi hệ thống.

![image](https://user-images.githubusercontent.com/111716161/188343032-8e0a0ab5-7b97-4556-8a60-4a5308365dd4.png)

### Which
Which giúp bạn tìm kiếm các file thực thi từ các đường dẫn thư mục mà bạn đã đặt trong biến môi trường PATH. Command này sẽ in ra [các] đường dẫn tuyệt đối của file thực thi.

![image](https://user-images.githubusercontent.com/111716161/188343076-5e3d1b9d-588e-4444-aca6-3675810a68bf.png)

### clear
Xóa nội dung trên cửa sổ làm việc.

![image](https://user-images.githubusercontent.com/111716161/188343119-04360feb-c552-4fa3-9a3c-122b91211bc2.png)

## 2. Nhóm command thao tác tệp

### cat

Hiển thị nội dung tệp tin văn bản lên màn hình
- Copy các tệp tin văn bản
- Gộp các tệp tin văn bản
- Tạo các tệp tin văn bản mới

![image](https://user-images.githubusercontent.com/111716161/188343264-175efed4-a592-4848-986a-66cf0d482360.png)

### chmod
Command chmod là viết gọn của “change mode”. Nó cho phép bạn thay đổi các quyền đọc (read), ghi (write) và thực thi (excute) của các tệp và thư mục. 

![image](https://user-images.githubusercontent.com/111716161/188343423-b1db68fb-b281-46ea-90eb-1343943fecb6.png)

### cp
Copy một tệp tin từ vị trí này tới vị trí khác.

![image](https://user-images.githubusercontent.com/111716161/188343470-e175864b-06c8-4536-8360-702ab8accfa7.png)

### diff
So sánh các tệp tin và hiển thị ra các sự khác biệt.

![image](https://user-images.githubusercontent.com/111716161/188343506-292a98f6-1067-40bb-ad91-8a2d8c24bc53.png)

### file
Xác định loại tệp tin và hiển thị thông tin encoding.

![image](https://user-images.githubusercontent.com/111716161/188343644-f3c1ccbd-8fe3-4d40-8e97-bb2d25cf1afe.png)

### find
Tìm kiếm các tệp tin trong một thư mục.

![image](https://user-images.githubusercontent.com/111716161/188343782-43be8876-5593-4988-94d4-0154ca193389.png)

### gunzip
Giải nén các tệp tin nén bởi gzip.

![image](https://user-images.githubusercontent.com/111716161/188343870-19f9d616-548a-4f9c-9cc2-6171b9265fac.png)

### gzcat
Cho phép bạn xem nội dung các tệp tin nén gzip mà không cần phải gunzip chúng.

![image](https://user-images.githubusercontent.com/111716161/188343902-d8dc8b77-6cfe-4410-9554-5b193752e449.png)

### gzip
Dùng để nén các tệp tin.

![image](https://user-images.githubusercontent.com/111716161/188343961-14bdb0a6-5d48-42f3-9258-d8c8cfb35930.png)

### head
Hiển thị n=10 (mặc định) dòng đầu tiên của một tệp tin. Nếu muốn thay đổi n, sử dụng 
```
head -n <number> filename.
```
![image](https://user-images.githubusercontent.com/111716161/188344006-723c0f1c-6cb5-4f37-a387-cd227f93f3f4.png)

### lpq
Kiểm tra hàng đợi máy in.

![image](https://user-images.githubusercontent.com/111716161/188344155-8de68a86-ce5f-4588-9f77-3a42e90c2f66.png)

### lpr
Thực hiện in 1 tệp tin.

![image](https://user-images.githubusercontent.com/111716161/188344185-eb0c9266-ba99-4117-8d5c-44310a3578a6.png)

### lprm
Xóa lệnh in đang có trong hàng đợi máy in.

![image](https://user-images.githubusercontent.com/111716161/188344225-c2199506-291e-414f-b9b8-32de4c338638.png)

### ls
Liệt kê các tệp tin và thư mục. ls có rất nhiều tham số: -l để hiển thị dạng danh sách với các thông tin kích thước, chủ sở hữu, ai có quyền thao tác và thời gian thay đổi lần cuối của các tệp tin. -a sẽ hiển thị tất cả các tệp tin (bao gồm các tệp tin bị ẩn).

![image](https://user-images.githubusercontent.com/111716161/188344300-a7b1923b-d41c-4381-96b8-1ea3c95ba747.png)

### more
Hiển thị một phần đầu nội dung của tệp tin (xem thêm bằng phím cách, gõ q để thoát).
![image](https://user-images.githubusercontent.com/111716161/188344343-b1cbd447-ee45-4dd2-8614-c0ab1550e8fb.png)

### mv
Di chuyển một tệp tin từ vị trí này tới vị trí khác.

![image](https://user-images.githubusercontent.com/111716161/188344399-bab083cd-3f3a-4bc9-b891-b82dc081d343.png)

Trong đó filename1 là đường dẫn ban đầu của tệp tin và filename2 là đường dẫn nơi bạn muốn chuyển tệp tin tới.

Và command này cũng dùng để đổi tên tệp tin hoặc thư mục.

![image](https://user-images.githubusercontent.com/111716161/188344425-6bc96d23-51ed-4c4b-859f-45a18310c27a.png)

### rm
Xóa một tệp tin. Sử dụng command này với thư mục bạn sẽ gặp báo lỗi.
rm: directory: is a directory
Để xóa một thư mục, bạn cần truyền tham số -r để nó xóa thư mục đó và toàn bộ nội dung bên trong. Bạn có thể bổ sung tham số -f để yêu cầu xóa và bỏ qua xác nhận của hệ thống.

### tail

Giống head command, nhưng là hiển thị nội dung ở cuối tệp tin. Sử dụng tham số -n nếu muốn thay đổi số lượng dòng hiển thị.

![image](https://user-images.githubusercontent.com/111716161/188344496-dc55005c-5e40-470c-80af-94db794e1010.png)

### touch
Cập nhật thời gian truy cập và sửa đổi của tệp tin tới thời gian hiện tại. Nếu tệp tin đó không tồn tại, nó sẽ được tạo ra.

![image](https://user-images.githubusercontent.com/111716161/188344538-c860864c-0747-42ee-bfae-544b25ff1785.png)

## 3. Nhóm command thao tác văn bản

## awk
awk là một trong những command rất hữu ích để làm việc với các tệp tin văn bản. Nó tác động tới từng dòng nội dung của văn bản. Mặc định awk sẽ dùng khoảng trắng để phân tách các trường. Cú pháp thông dụng nhất của awk là

![image](https://user-images.githubusercontent.com/111716161/188344778-9ee59bed-e154-4bff-9c55-7e882df299c2.png)

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
cd là viết tắt của “change directory”. Nó giúp bạn di chuyển vị trí làm việc. Chạy command dưới đây

![image](https://user-images.githubusercontent.com/111716161/188345371-f7a5adab-9eb0-4ecb-916f-0190de922a0a.png)

### mkdir
Tạo một thư mục mới.

![image](https://user-images.githubusercontent.com/111716161/188345440-6680816f-21f2-47cb-8bc2-21fd8997cdba.png)

### pwd
Cho bạn biết đường dẫn tuyệt đối của thư mục nơi bạn đang làm việc. Viết tắt của print working directory:

![image](https://user-images.githubusercontent.com/111716161/188345496-f1d58c56-9d15-48ba-b675-c164de6b0af9.png)

## 5. Nhóm command SSH, thông tin hệ thống & mạng
### bg
Hiển thị danh sách các backgroud job (công việc chạy trong nền).

### cal
Hiển thị lịch của tháng hiện tại.

### date
Hiển thị ngày và giờ của thời điểm hiện tại.

### df
Hiển thị mức dùng ổ đĩa: đã dùng bao nhiêu, còn trống bao nhiêu

### dig
Kiểm tra thông tin bản ghi DNS của một tên miền.

![image](https://user-images.githubusercontent.com/111716161/188345666-3cdc7a4c-de6d-4f12-a426-bac7c87c1f82.png)

### du
Hiển thị mức sử dụng ổ đĩa của các tệp tin hoặc thư mục.

![image](https://user-images.githubusercontent.com/111716161/188345750-12484ca1-e1d8-4b9f-954e-fb2317e3c0e5.png)

Các option:

-h (Dễ đọc hơn) Hiển thị mức dùng ở đơn vị (KB), (MB) và (GB).

-s (Tóm tắt) Hiển thị mức dùng ổ đĩa của thư mục một cách tóm tắt.

### fg
Di chuyển các job lên foreground (chuyển từ chạy trong nền ra chạy trên màn hình console)

### finger

Hiển thị thông tin về một user.

![image](https://user-images.githubusercontent.com/111716161/188345810-f1f80a7f-64e7-40c7-8b6e-09521d5d8b8d.png)

### jobs
Liệt kê các job đang chạy trong backgroud, cung cấp cho bạn chỉ số job (job number).

### last
Liệt kê các thông tin đăng nhập cuối cùng của bạn về người dùng được chỉ định.

![image](https://user-images.githubusercontent.com/111716161/188345904-fdfb3b22-04d8-4ff2-8662-13ed7eaea229.png)

### man
Hiển thị tài liệu hướng dẫn (manual page) của command cụ thể.

![image](https://user-images.githubusercontent.com/111716161/188345964-d7714e70-e6ed-42f7-8bf8-46ec2e191900.png)

### passwd
Cho phép user đang đăng nhập thay đổi mật khẩu đăng nhập.

### ping
PING tới 1 host nào đó kèm theo kết quả. Được dùng để kiểm tra xem máy của bạn có kết nối tới host đó hay không.

![image](https://user-images.githubusercontent.com/111716161/188345987-37299870-40a4-49ed-9204-52dee3390ea0.png)

### ps
Liệt kê các tiến trình hiện có của bạn.

![image](https://user-images.githubusercontent.com/111716161/188346027-7f67133f-6134-460d-8068-d8e33384e08a.png)

### quota
Cho biết mức dùng ổ đĩa của bạn là bao nhiêu.

### scp
Truyền dữ liệu từ máy localhost tới máy remote hoặc ngược lại.

### ssh
ssh (SSH client) là một chương trình cho phép bạn đăng nhập và thực thi các command trên 1 máy remote từ máy tính của bạn.

###top
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

![image](https://user-images.githubusercontent.com/111716161/188346339-a893b72f-75c4-4ff6-8165-058558372531.png)

### killall
Bắt buộc dừng (kết thúc) tất cả các tiến trình theo tên tiến trình.

![image](https://user-images.githubusercontent.com/111716161/188346361-c112524c-b282-4216-9f3a-97462b6ed406.png)

### &
Ký tự & chỉ định cho một command phải chạy ở chế độ background.

![image](https://user-images.githubusercontent.com/111716161/188346415-318bb29e-fc4f-4b34-8853-7d9345f53c2a.png)

### nohup
nohup là viết tắt của “No Hang Up”. Nó cho phép bạn chạy các command hoặc tiến trình trong backgroud ngay cả khi bạn đăng xuất (logout, không đồng nghĩa với tắt máy) khỏi terminal.

![image](https://user-images.githubusercontent.com/111716161/188346447-62b47394-92f8-4764-9f22-e0b4f3384b9f.png)
