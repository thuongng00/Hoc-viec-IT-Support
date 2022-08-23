# Mục lục

# IPv4
## IPv4 là gì?
IPv4 là phiên bản IP thế hệ thứ 4, nó được sử dụng nhiều nhất hiện nay bên cạnh IPv6. Hai phiên bản IP này là yếu tố chủ chốt cho việc giao tiếp giữa các thiết bị trong mạng internet.

IPv4 được ra mắt vào năm 1981 trong phiên bản RFC 791 và đã được bộ quốc phòng Hoa Kỳ chuẩn hóa trong phiên bản MIL-STD-1777.

IPv4 được ứng dụng trong các hệ thống chuyển mạch gói. Vai trò của nó là định hướng dữ liệu truyền đi. Khi truyền đi các gói tin, giao thức này chỉ đảm bảo phần truyền tải mà không để ý đến thứ tự truyền gói tin hoặc vấn đề gói tin có đến đích hay không, có lặp lại ở máy đích hay không. Vấn đề này sẽ được giải quyết ở tầng cao hơn của hệ thống TCP/IP. Một điều mà IPv4 đảm bảo được đó là tính toàn vẹn dữ liệu bằng cách sử dụng kết quả của việc chạy thuật toán Checksum để kiểm tra.

## Cấu trúc của địa chỉ IPv4
Về cấu tạo, địa chỉ IPv4 sẽ có 32 bit và được biểu diễn thành một dãy số nhị phân và chia thành 4 cụm. Mỗi cụm như vậy sẽ gọi là octet. Mỗi octet sẽ là 8 bit và chúng được ngăn cách bằng dấu chấm (.)

Về hình dáng, cấu trúc của một địa chỉ IPv4 sẽ gồm 4 con số ở dạng thập phân tượng trưng cho 4 cụm. Địa chỉ này gồm 2 phần là phần mạng và phần host.

Việc đặt địa chỉ IP phải tuân theo các quy tắc sau:
- Không được đặt những bit ở phần network bằng 0 cùng một lúc. Khi đặt tất cả những bit ở phần network bằng không thì địa chỉ IP sẽ có 3 số đầu là 0.0.0. Đây là một địa chỉ sai.
- Nếu đặt tất cả các bit ở phần host bằng 0 thì số cuối cùng của địa chỉ IP sẽ bằng 0. Khi đó địa chỉ đó là một địa chỉ mạng, không thể dùng làm host. Ví dụ: 191.168.10.0 là một địa chỉ mạng.
- Nếu đặt tất cả các bit ở phần host là 1 thì số cuối cùng của địa chỉ IP là 255. Khi đó địa chỉ này sẽ là một địa chỉ broadcast của mạng đó. Ví dụ: 192.168.10.255 là một địa chỉ broadcast.

## Phân lớp địa chỉ IPv4
Dựa vào cách chọn địa chỉ mạng mà địa chỉ IP được phân thành 5 lớp A, B, C, D, E. Đặc điểm của các lớp như sau:
### Lớp A
Địa chỉ lớp A có phần mạng là 8 bit đầu và phần host là 24 bit sau. Bit đầu tiên của phần mạng luôn là 0.

Lớp A sẽ có các địa chỉ mạng từ 1.0.0.0 đến 126.0.0.0 và mỗi mạng sẽ có 224 địa chỉ host (loại trừ địa chỉ mạng và địa chỉ broadcast).

Mạng loopback sẽ là 127.0.0.0.
### Lớp B
Địa chỉ lớp B có phần mạng là 16 bit đầu và phần host là 16 bit sau. 2 bit đầu tiên của phần mạng luôn là 1.0.

Lớp B sẽ có các địa chỉ mạng từ 128.0.0.0 đến 191.255.0.0 và mỗi mạng sẽ có 214 địa chỉ host (loại trừ địa chỉ mạng và địa chỉ broadcast).
