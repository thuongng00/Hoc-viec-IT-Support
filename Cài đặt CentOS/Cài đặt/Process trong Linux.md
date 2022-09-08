# Tiến trình (process)

Tiến trình được hiểu đơn giản là một chương trình đang chạy trong hệ điều hành. Một tiến trình có thể phân thành một hay nhiều tiến trình con khác. 

Phân loại tiến trình:

### 1. Init process

Init process là tiến trình đầu tiên được khởi động sau khi lựa chọn hệ điều hành trong boot loader. Trong cây tiến trình, init process là tiến trình cha của các tiến trình khác.

Init process có đặc điểm sau:
- PID = 1.
- Không thể kill init process.

### 2. Parents process - Child process

Trong hệ điều hành Linux, các tiến trình được phân thành tiến trình cha (parents process) và tiến trình con (child process). Một tiến trình khi thực hiện lệnh fork() để tạo ra một tiến trình mới thì được gọi là parents process. Tiến trình mới tạo được gọi là child process.

![image](https://user-images.githubusercontent.com/111716161/189055536-0b1e0345-f046-436d-a080-43037d2fcc72.png)

Một parents process có thể có nhiều child process nhưng một child process chỉ có một parents process. Khi quan sát thông tin của một tiến trình, ngoài PID (Processes ID) ta cần để ý tới PPID (Parents Processes ID), nó sẽ cho ta thông tin về parents process của tiến trình đó. 

```
ps -ef
```

![image](https://user-images.githubusercontent.com/111716161/189056022-f3368b44-a2dc-415b-b2bf-dab603e2564d.png)

### 2.3. Orphan process - Zombie Process

Khi parents process – child process hoạt động sẽ xảy ra một số trường hợp đặc biệt. Lúc đó Orphan process – Zombie Process sẽ được hình thành.

Khi một parents process bị tắt trước khi child process được tắt, tiến trình con đó sẽ trở thành một orphan process. Lúc này init process sẽ trở thành cha của orphan processes và thực hiện tắt chúng.

Khi một child process được kết thúc, mọi trạng thái của child process sẽ được thông báo bởi lời gọi hàm wait() của parents process. Vì vậy, kernel sẽ đợi parents process trả về hàm wait() trước khi tắt child process. Tuy nhiên vì một vài lí do mà parents process không thể trả về hàm wait(), khi đó child process sẽ trở thành một zombie process. Khi ở trạng thái này, tiến trình sẽ gần như giải phóng bộ nhớ hoàn toàn, chỉ lưu giữ một số thông tin như PID, lượng tại nguyên sử dụng,… trên bảng danh sách tiến trình.

Tuy giải phóng bộ nhớ hoàn toàn nhưng các zombie process không bị kết thúc. Vì vậy nếu lượng zombie process lớn sẽ nắm giữ lượng lớn các PID. Nếu lượng PID đầy, sẽ không có tiến trình mới được tạo thêm. Các zombie process sẽ chỉ bị kết thúc nếu như parents process của chúng bị kill.

Để tìm các zombie process ta gõ kiểm tra trạng thái của tiến trình theo lệnh sau:

```
ps -lA | grep '^. Z'
```

### 4. Daemon Process

Một daemon process là một tiến trình chạy nền. Nó sẽ luôn trong trạng thái hoạt động và sẽ được kích hoạt bởi một điều kiện hoặc câu lệnh nào đó. Trong Unix, các daemon thường được kết thúc bằng "d" ví dụ như httpd, sshd, crond, mysqld...

# Một process hoạt động thế nào?
Khi hệ thống khởi động, kernel sẽ khởi tạo một vài hành vi của riêng nó dưới một process và khởi động một chương trình gọi là init. init theo đó sẽ khởi chạy một loạt các shell script (nằm ở /etc) được gọi là init script, sẽ khởi động tất cả các service hệ thống.

Rất nhiều service này được implement dưới dạng daemon program, chương trình chạy background mà không can thiệp tới giao diện người dùng. Vì thế kể cả khi chúng ta không đăng nhập thì hệ thống cũng ở trạng thái busy một lúc để khởi chạy.

Chương trình có thể khởi chạy một chương trình khác được diễn giải trong cơ chế process gọi là process cha sinh ra process con.

Kernel sẽ duy trì thông tin về mỗi một process. Ví dụ: mỗi process được gán cho một giá trị là PID (process ID). PID được gán theo thứ tự tăng dần và init luôn có PID là 1. Kernel cũng theo dõi thông tin bộ nhớ gán cho mỗi process, cũng như tính sẵn sàng của process để có thể tiếp tục thực thi.

Cũng như file thì process cũng có owner và user ID, ...

## Theo dõi process `ps`

Câu lệnh phổ biến để theo dõi các process là `ps`. `ps` có rất nhiều tùy chọn, cách dùng cơ bản nhất là 
```
ps
```

![image](https://user-images.githubusercontent.com/111716161/189034149-86ac2283-41a9-4135-91c6-d90138f74cd0.png)

- Kết quả list ra 2 process cùng với thông tin PID.
- `TTY` là viết tắt của teletype, để chỉ terminal đang chạy process đó. 
- `TIME` để chỉ thời gian chiếm CPU của process tương ứng.

Khi thêm option `x`: 
```
ps x
```
![image](https://user-images.githubusercontent.com/111716161/189034449-f3052ce2-d2d9-4a1c-9b63-ecd1c08550bf.png)

- `STAT` là viết tắt của State để chỉ trạng thái của process tương ứng.

Các dạng state: 

| Trạng thái | Ý nghĩa | 
|------------|---------|
| R |Running: process đang chạy hoặc sẵn sàng để chạy|
| S | Sleeping: process đang đợi một event để tiếp tục chạy |
| D | Process đang đợi I/O |
| T | Stopped: process đang trong quá trình dừng chạy |
| Z | Zombie process: đây là các tiến trình con đã bị chấm dứt nhưng chưa được tiến trình cha giải phóng |
| < | Process có độ ưu tiên cao, có thể có nhiều thời gian CPU hơn |
| N | Process có độ ưu tiên thấp, chỉ có thể chiếm CPU khi các process khác có độ ưu tiên cao hơn hết thời gian CPU |

Khi thêm option `aux`:

```
ps aux
```

![image](https://user-images.githubusercontent.com/111716161/189035106-e81ebb88-51ef-445e-ae9a-b2bc410cd39e.png)

- Hiển thị process thuộc về mọi user.

## Theo dõi process với `top`

`ps` cung cấp một bản snapshot của các tiến trình trong hệ thống tại thời điểm mà chúng ta chạy nó. Trong khi đó `top` cung cấp một hệ thống theo dõi động. 

![image](https://user-images.githubusercontent.com/111716161/189036528-33cff8b4-67ff-4858-b359-ae8844744ca8.png)

| Dòng | Trường | Ý nghĩa |
|----|----|---|
| 1 | top | Tên của chương trình |
| | 21:46:52| Thời gian hiện tại |
| | up 3:03 | uptime, thời gian hệ thống bắt đầu chạy |
| | 3 users | có 3 user đã log in |
| | load average: 0.08, 0.08, 0.09 | Chỉ ra con số ở trạng thái có thể chạy và đang share CPU. Giá trị < 0.1 chỉ ra là hệ thống đang không busy |
| 2 | Task | Tổng kết số lượng process và số lượng process theo trạng thái |
| 3 | Cpu(s) | Miêu tả đặc điểm của những tác vụ CPU đang thực thi |
| | us | CPU đang được dùng cho user process |
| | sy | CPU đang được dùng cho systeam process |
| | ni | CPU đang được dùng cho process có độ ưu tiên thấp |
| | id | Phần CPU đang nhàn rỗi | 
| | wa | Phần CPU đang chờ I/O |
| 4 | Mem | Chỉ ra có bao nhiêu RAM đang được dùng |
| 5 | Swap | Chỉ ra có bao nhiêu Swap Space đang được dùng |

## Kiểm soát process

Khi chúng ta gõ một lệnh và chạy nó, terminal sẽ ở trạng thái không dùng được cho đến khi chương trình chạy xong. Để một chương trình không chiếm terminal, ta thêm `&` vào cuối câu lệnh muốn chạy, ví dụ `xlogo &`

![image](https://user-images.githubusercontent.com/111716161/189052685-d0aef074-a66b-403a-a894-68cb8f4f3ffb.png)

- Để list các background job: 
```
jobs
```
- Để trả một process đang chạy background về foreground:
```
fg
```

## Signals

Signals là cách mà OS giao tiếp với chương trình. Để gửi signal đến một chương trình, sử dụng lệnh `kill`` kết hợp với số/tên của signal.

| Số hiệu | Tên | Ý nghĩa |
|---|---|---|
| 2 | INT | Giống với Ctrl - c, thường là terminate chương trình |
| 9 | KILL | Kernel ngay tập tức terminate chương trình mà không có một hành động clean up nào |
| 15 | TERM | Terminate, đây là tín hiệu mặc định mà lệnh kill gửi đến chương trình |
| 18 | CONT | continue, restore trạng thái của process sau khi nhận tín hiệu STOP |
| ... |...|...|

- `kill -l`: list ra các signal khả dụng của hệ thống. 
- `killall`: gửi kill signal đến nhiều tiến trình chạy cùng một chương trình. 
- `kill`: dừng process.
