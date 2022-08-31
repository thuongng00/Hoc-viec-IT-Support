### 1. pwd

Sử dụng lệnh pwd để tìm ra đường dẫn của thư mục (folder) làm việc hiện tại mà bạn đang đứng.

Lệnh này sẽ trả về một đường dẫn tuyệt đối (đầy đủ), về cơ bản là đường dẫn của tất cả các thư mục bắt đầu bằng dấu gạch chéo lên (/).

![image](https://user-images.githubusercontent.com/111716161/187575406-02cb4bcd-59d7-44bf-9204-1aa3902c2f7c.png)

### 2. cd

Để điều hướng qua các tệp và thư mục Linux, hãy sử dụng lệnh cd.

Nó yêu cầu đường dẫn đầy đủ hoặc tên của thư mục, tùy thuộc vào thư mục làm việc hiện tại mà bạn đang ở.

Có một số phím tắt giúp bạn điều hướng nhanh chóng hơn:
```
cd .. (2 dấu hai chấm) để di chuyển một cấp lên thư mục bên trên thư mục hiện tại
cd để chuyển thẳng đến thư mục chính
cd - (có dấu gạch ngang) để chuyển đến thư mục trước của bạn
cd / để chuyển đến thư mục gốc
```

![image](https://user-images.githubusercontent.com/111716161/187575608-da0260fd-8723-4d51-b7f9-f3b8b892ac11.png)

### 3. ls 

Lệnh ls được sử dụng để xem nội dung của một thư mục. Theo mặc định, lệnh này sẽ hiển thị nội dung của thư mục làm việc hiện tại của bạn.

Nếu bạn muốn xem nội dung của các thư mục khác, hãy nhập ls rồi đến đường dẫn của thư mục.

Có các biến thể bạn có thể sử dụng với lệnh ls:
```
ls -R cũng sẽ liệt kê tất cả các tệp trong các thư mục con
ls -a sẽ hiển thị các tệp ẩn
ls -al sẽ liệt kê các tệp và thư mục với thông tin chi tiết như quyền, kích thước, chủ sở hữu, v.v.
```

![image](https://user-images.githubusercontent.com/111716161/187575965-a3e9f1a6-55e9-4111-9cdc-617e7d6cebd8.png)

### 4. cat

cat (viết tắt của concatenate) là một trong những lệnh được sử dụng thường xuyên nhất trong Linux.

Nó được sử dụng để liệt kê nội dung của một tệp trên đầu ra chuẩn (sdout).

Để chạy lệnh này, hãy nhập cat, theo sau là tên tệp và phần mở rộng của nó.

Dưới đây là các cách khác để sử dụng lệnh cat:
```
cat > filename để tạo một tệp mới tên là filename
Cat filename1 filename2>filename3 kết hợp hai tệp (1 và 2) và lưu trữ kết quả đầu ra của chúng trong một tệp mới (3)
Để chuyển đổi một tệp sang sử dụng chữ hoa hoặc chữ thường, cat filename | tr a-z A-Z>output.txt
```
Ví dụ: Tệp bai1.txt nằm trong desktop có nội dung: 

hoc linux 

linux co ban

Khi gõ lệnh cat bait.txt ta được kết quả như hình: 

![image](https://user-images.githubusercontent.com/111716161/187577101-04f66a80-155e-4190-b6d7-0d07fb23017c.png)

### 5. cp

Sử dụng lệnh cp để sao chép tệp từ thư mục hiện tại sang một thư mục khác.

Ví dụ: Sao chép tệp bai1.txt nằm trong desktop sang thư mục folder1 nằm trong desktop:

![image](https://user-images.githubusercontent.com/111716161/187577359-0e334c66-7ca1-40a2-b539-2a6d018fbd04.png)

### 6. mv

Công dụng chính của lệnh mv là di chuyển tệp, mặc dù nó cũng có thể được sử dụng để đổi tên tệp.

Các đối số trong mv tương tự như lệnh cp. Bạn cần nhập mv, tên tệp và thư mục đich. 

Để đổi tên tệp, lệnh Linux là mv ten-cu.ext ten-moi.ext

### 7. mkdir

Sử dụng lệnh mkdir để tạo một thư mục mới - nếu bạn nhập mkdir Music, nó sẽ tạo một thư mục có tên là Music.

Ngoài ra còn có các lệnh mkdir bổ sung:
```
Để tạo một thư mục mới bên trong một thư mục khác, hãy sử dụng lệnh cơ bản của Linux này mkdir Music/Newfile
Sử dụng tùy chọn p (viết tắt của từ parents) để tạo một thư mục ở giữa hai thư mục hiện có. Ví dụ: mkdir -p Music/2021/Newfile sẽ tạo tệp “2021” mới.
```
### 8. rmdir

Nếu bạn cần xóa một thư mục, hãy sử dụng lệnh rmdir. Tuy nhiên, rmdir chỉ cho phép bạn xóa các thư mục trống.

### 9. rm

Lệnh rm được sử dụng để xóa các thư mục và nội dung bên trong chúng.

Nếu bạn chỉ muốn xóa thư mục, thay vì sử dụng rmdir, hãy sử dụng rm -r

Lưu ý: Hãy hết sức cẩn thận với lệnh này và kiểm tra kỹ xem bạn đang ở thư mục nào. Thao tác này sẽ xóa mọi thứ và KHÔNG THỂ HOÀN TÁC.

### 10. touch

Lệnh touch cho phép bạn tạo một tệp mới trống thông qua dòng lệnh Linux.

Ví dụ: nhập touch /home/username/Documents/index.html để tạo tệp HTML có tên index.html trong thư mục Documents

### 11. locate

Bạn có thể sử dụng lệnh locate để định vị tệp, giống như lệnh tìm kiếm trong Windows.

Hơn nữa, việc sử dụng đối số -i cùng với lệnh locate này sẽ làm cho nó không phân biệt chữ hoa chữ thường, vì vậy bạn có thể tìm kiếm một tệp ngay cả khi bạn không nhớ tên chính xác của nó.

Để tìm kiếm một tệp chứa hai từ trở lên, hãy sử dụng dấu *

Ví dụ: locate -i java*niit sẽ tìm kiếm bất kỳ tệp nào có chứa từ java và niit, cho dù đó là chữ hoa hay chữ thường.

### 12. find

Tương tự như lệnh locate, sử dụng lệnh find cũng giúp tìm kiếm các tệp và thư mục. Sự khác biệt là bạn sử dụng lệnh find để định vị các tệp trong một thư mục nhất định.

Ví dụ, lệnh find /home/ -name notes.txt sẽ tìm kiếm một tệp có tên là notes.txt trong thư mục home và các thư mục con của nó.

Các biến thể khác khi sử dụng tìm kiếm là:
```
Để tìm các tệp trong thư mục sử dụng hiện tại, hãy sử dụng find -name notes.txt
Để tìm kiếm thư mục sử dụng, / -type d -name notes.txt
```

### 13. grep

Một lệnh Linux cơ bản khác chắc chắn hữu ích cho việc sử dụng hàng ngày là grep. Nó cho phép bạn tìm kiếm qua tất cả văn bản trong một tệp nhất định.

Để minh họa, lệnh grep blue notepad.txt sẽ tìm kiếm từ "blue" trong tệp notepad.

Các dòng có chứa từ được tìm kiếm sẽ được hiển thị đầy đủ.

### 14. sudo

sudo viết tắt của “SuperUser Do”, lệnh này cho phép bạn thực hiện các tác vụ yêu cầu quyền quản trị hoặc quyền root.

Tuy nhiên, không nên sử dụng lệnh này hàng ngày vì có thể dễ xảy ra lỗi nếu bạn làm sai.

### 15. df

Sử dụng lệnh df để nhận báo cáo về việc sử dụng dung lượng ổ đĩa của hệ thống, được hiển thị bằng phần trăm và KBs.

Nếu bạn muốn xem báo cáo bằng megabyte, hãy nhập df -m

