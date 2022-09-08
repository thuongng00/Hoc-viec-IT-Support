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

Khi chúng ta gõ một lệnh và chạy nó, terminal sẽ ở trạng thái không dùng được cho đến khi chương trình chạy xong. 
