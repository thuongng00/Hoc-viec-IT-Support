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
