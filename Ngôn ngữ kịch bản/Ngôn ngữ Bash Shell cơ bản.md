# Biến trong bash shell
Tạo các biến trong bash cũng tương tự như trong các ngôn ngữ lập trình. Nó không có kiểu dữ liệu. Biến trong bash có thể chưa số, ký tự, chuỗi ký tự, … Bạn cũng không cần phải khai báo biến, chỉ cần gán giá trị cho biến và tham chiếu của nó sẽ được tạo ra.

![image](https://user-images.githubusercontent.com/111716161/188346882-ae36090f-606a-4856-8651-ce8bb1f99cc4.png)

Dòng lệnh trên tạo một biến tên str và gán giá trị “hello world” cho nó. Để lấy giá trị của biến, bạn chỉ cần thêm $ vào trước tên biến:

![image](https://user-images.githubusercontent.com/111716161/188347038-6f6a3d03-ae76-4841-ba0a-abf93ca98c41.png)

# Mảng trong bash shell
Tương tự các ngôn ngữ lập trình, bash cũng có mảng. Một mảng là một tập hợp chứa nhiều giá trị. Không có kích thước giới hạn cho mảng. Mảng trong bash có chỉ số bắt đầu từ 0. Có một vài cách khác nhau để tạo ra biến mảng trong bash:

![image](https://user-images.githubusercontent.com/111716161/188347166-400798fd-7eac-4cd4-a4e2-13846abba4fd.png)

Để hiển thị một giá trị ở chỉ số nhất định, sử dụng cú pháp sau:

![image](https://user-images.githubusercontent.com/111716161/188347314-c89d0abb-a497-4923-8e16-260e48784184.png)

Nếu không chỉ định chỉ số mảng, chỉ số 0 sẽ được ngầm định. Để xem có bao nhiêu phần từ trong mảng, sử dụng cú pháp sau:

![image](https://user-images.githubusercontent.com/111716161/188347612-f9fb8e7d-babf-4c8c-bd98-0abce1902821.png)


# String trong Bash shell
Xem một số cú pháp dưới đây để biết các thao tác thay thế chuỗi trong bash script:

![image](https://user-images.githubusercontent.com/111716161/188348044-3a670a61-630d-4a9e-b53e-38741e1afe27.png)

# Hàm trong bash script
Như hầu hết các ngôn ngữ lập trình, bạn có thể sử dụng hàm để nhóm các đoạn code vào thành tức chức năng riêng nhằm mục đích cấu trúc và tái sử dụng. Trong Bash, khai báo một hàm nó như thế này function my_func { my_code }. Còn việc gọi hàm chỉ đơn giản là viết tên hàm ra thôi.

![image](https://user-images.githubusercontent.com/111716161/188348194-a171847c-99c3-4e40-8181-193232a5c847.png)

# Cấu trúc điều khiển
Cấu trúc điều khiển trong Bash tương tự như các ngôn ngữ lập trình khác. Có nhiều dạng cấu trúc điều khiển nhưng cơ bản nhất là câu lệnh if điều kiện then khối lệnh và khối lệnh chỉ được thực thi khi điều kiện là đúng (true).

![image](https://user-images.githubusercontent.com/111716161/188348241-2c5e4795-8006-4c31-a651-8f7ceae4405b.png)

Đôi khi việc sử dụng case statements sẽ làm code bạn rõ ràng hơn so với sử dụng if.

![image](https://user-images.githubusercontent.com/111716161/188348270-8e97517c-779a-4898-9584-3dc415f47cf2.png)

# Vòng lặp trong bash
Có 3 loại vòng lặp trong Bash: for, while và until.

Các cú pháp for khác nhau:

![image](https://user-images.githubusercontent.com/111716161/188348329-3d713344-705b-48b1-afe5-09768c3e0960.png)

Cú pháp while:

![image](https://user-images.githubusercontent.com/111716161/188348357-fd919ac3-b7f6-432d-b1df-b85ca7902aac.png)

Cú pháp until:

![image](https://user-images.githubusercontent.com/111716161/188348420-432569f1-63df-4dd7-a739-da29775a1ae9.png)

# Các mẹo dùng Bash

### Tạo alias (viết tắt)
Việc này giúp bạn tiết kiệm thời gian bằng cách gõ alias để chạy một command dài nào đó thường xuyên. Ví dụ:

Chạy nano ~/.bash_profile và thêm dòng dưới đây vào:

![image](https://user-images.githubusercontent.com/111716161/188350265-2cf55971-8648-4a5f-8984-8e8a9add8c8a.png)

Sau khi sửa bạn cần cập nhật lại:

![image](https://user-images.githubusercontent.com/111716161/188350311-e83699d1-3b8a-42b1-8432-38727addc05d.png)

### Di chuyển nhanh chóng
Chạy nano ~/.bashrc và thêm vào dòng dưới đây:

![image](https://user-images.githubusercontent.com/111716161/188350411-2e955d48-c07d-44a8-9a8d-f12637316bac.png)

Bây giờ, bạn cần cập nhật lại bashrc và việc di chuyển tới một đường dẫn dài trở nên rất đơn giản:

![image](https://user-images.githubusercontent.com/111716161/188350473-3a99e84f-4f57-4451-9a19-538c7b46eb6f.png)

### Chạy lại command trước đó
Cái này giúp bạn thực thi lại lệnh ngay trước đó. Bạn có thể sử dụng phím mũi tên UP cũng được. Nhưng có thể đôi khi nó vẫn hữu ích.

Để thực thi command ngay trước đó, chạy:

![image](https://user-images.githubusercontent.com/111716161/188350508-a22b89d5-e335-4537-bb03-ec2b8f007b81.png)

### Exit traps
Làm cho các tập lệnh bash của bạn hoàn hảo hơn bằng cách thực hiện dọn dẹp một cách đáng tin cậy.

![image](https://user-images.githubusercontent.com/111716161/188350598-4615ece0-3e78-4453-9ebe-8e1a62739fea.png)

### Lưu lại các biến môi trường
Khi bạn thực thi export FOO = BAR, biến của bạn chỉ được lưu trong shell làm việc hiện tại. Để có thể lưu và tiếp tục sử dụng trong tương lai, bạn hãy thêm nó vào tệp ~/.bash_profile như sau:

![image](https://user-images.githubusercontent.com/111716161/188350658-4a321a94-b880-41c4-8bc3-e1fbe52db799.png)

### Truy cập các script của bạn
Bạn có thể dễ dàng sử dụng các script bằng cách tạo một thư mục bin trong thư mục HOME của bạn với mkdir ~/bin. Bây giờ tất cả các script bạn để trong đó có thể sử dụng chỉ bằng cách gọi tên ở bất kỳ nơi đâu.

Nếu trong trường hợp có lỗi, hãy thử thêm code dưới đây vào cuối ~/.bash_profile và chạy source ~/.bash_profile để thử lại xem sao nhé.

![image](https://user-images.githubusercontent.com/111716161/188350697-1ebeaab7-9db6-47f4-b95c-35810610f50d.png)

### Debug trong Bash shell
Bạn có thể dễ dàng debug trong khi học bash shell (bash script) hoặc trong khi làm bằng cách thêm các option vào command. Ví dụ, -n để chỉ kiểm tra cú pháp mà không chạy command đó. -v để in ra command đó trước khi chạy. -x để in ra command đó sau khi chạy xong.

![image](https://user-images.githubusercontent.com/111716161/188350752-e612139f-a8b1-46c8-90f8-b3ae7ad08a12.png)

