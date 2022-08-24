# Mục lục 

[IPv4 là gì?](#ipv4)

[Cấu trúc của địa chỉ IPv4](#cautruc)

[Phân lớp địa chỉ IPv4](#phanlop)

[Phân loại địa chỉ IP](#phanloai)

[Địa chỉ Broadcast, Subnet mask, số prefix length](#diachi)

[Những điểm hạn chế của IPv4](#hanche)

[Cách chia địa chỉ IPv4](#cachchia)

# IPv4
<a name="ipv4"><a/>
## IPv4 là gì?
  
IPv4 là phiên bản IP thế hệ thứ 4, nó được sử dụng nhiều nhất hiện nay bên cạnh IPv6. Hai phiên bản IP này là yếu tố chủ chốt cho việc giao tiếp giữa các thiết bị trong mạng internet.

IPv4 được ra mắt vào năm 1981 trong phiên bản RFC 791 và đã được bộ quốc phòng Hoa Kỳ chuẩn hóa trong phiên bản MIL-STD-1777.

IPv4 được ứng dụng trong các hệ thống chuyển mạch gói. Vai trò của nó là định hướng dữ liệu truyền đi. Khi truyền đi các gói tin, giao thức này chỉ đảm bảo phần truyền tải mà không để ý đến thứ tự truyền gói tin hoặc vấn đề gói tin có đến đích hay không, có lặp lại ở máy đích hay không. Vấn đề này sẽ được giải quyết ở tầng cao hơn của hệ thống TCP/IP. Một điều mà IPv4 đảm bảo được đó là tính toàn vẹn dữ liệu bằng cách sử dụng kết quả của việc chạy thuật toán Checksum để kiểm tra.

  <a name="cautruc"><a/>
## Cấu trúc của địa chỉ IPv4
Về cấu tạo, địa chỉ IPv4 sẽ có 32 bit và được biểu diễn thành một dãy số nhị phân và chia thành 4 cụm. Mỗi cụm như vậy sẽ gọi là octet. Mỗi octet sẽ là 8 bit và chúng được ngăn cách bằng dấu chấm (.).

Về hình dáng, cấu trúc của một địa chỉ IPv4 sẽ gồm 4 con số ở dạng thập phân tượng trưng cho 4 cụm. Địa chỉ này gồm 2 phần là phần mạng và phần host.

<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186295779-485967af-bea7-497b-b9d9-02cc9f792d59.png"/>
 </p>
 
Việc đặt địa chỉ IP phải tuân theo các quy tắc sau:
- Không được đặt những bit ở phần network bằng 0 cùng một lúc. Khi đặt tất cả những bit ở phần network bằng không thì địa chỉ IP sẽ có 3 số đầu là 0.0.0. Đây là một địa chỉ sai.
- Nếu đặt tất cả các bit ở phần host bằng 0 thì số cuối cùng của địa chỉ IP sẽ bằng 0. Khi đó địa chỉ đó là một địa chỉ mạng, không thể dùng làm host. Ví dụ: 191.168.10.0 là một địa chỉ mạng.
- Nếu đặt tất cả các bit ở phần host là 1 thì số cuối cùng của địa chỉ IP là 255. Khi đó địa chỉ này sẽ là một địa chỉ broadcast của mạng đó. Ví dụ: 192.168.10.255 là một địa chỉ broadcast.

  <a name="phanlop"><a/>
## Phân lớp địa chỉ IPv4
    
Dựa vào cách chọn địa chỉ mạng mà địa chỉ IP được phân thành 5 lớp A, B, C, D, E. Đặc điểm của các lớp như sau:
### Lớp A

<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186295941-76e2f204-58e0-433f-bf9d-ad585a872fa9.png"/>
 </p>

- Địa chỉ lớp A sử dụng một octet đầu làm phần mạng, ba octet sau làm phần host.
- Bit đầu của một địa chỉ lớp A luôn được giữ là 0.
- Các địa chỉ mạng lớp A gồm: 1.0.0.0 -> 126.0.0.0.
- Mạng 127.0.0.0 được sử dụng làm mạng loopback.
- Phần host có 24 bit => mỗi mạng lớp A có (224 – 2) host.
### Lớp B

<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186296026-1276f5a8-385a-4c24-ac8a-8869df8d057f.png"/>
 </p>
 
- Địa chỉ lớp B sử dụng hai octet đầu làm phần mạng, hai octet sau làm phần host.
- Hai bit đầu của một địa chỉ lớp B luôn được giữ là 1 0.
- Các địa chỉ mạng lớp B gồm: 128.0.0.0 -> 191.255.0.0. Có tất cả 214 mạng trong lớp B.
- Phần host dài 16 bit do đó một mạng lớp B có (216 – 2) host.

### Lớp C

<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186296090-2b85eb64-7d03-403d-bbfa-532d011d71af.png"/>
 </p>
 
- Địa chỉ lớp C sử dụng ba octet đầu làm phần mạng, một octet sau làm phần host.
- Ba bit đầu của một địa chỉ lớp C luôn được giữ là 1 1 0.
- Các địa chỉ mạng lớp C gồm: 192.0.0.0 -> 223.255.255.0. Có tất cả 221 mạng trong lớp C.
- Phần host dài 8 bit do đó một mạng lớp C có (28 – 2) host.

### Lớp D
- Gồm các địa chỉ thuộc dải: 224.0.0.0 -> 239.255.255.255
- Được sử dụng làm địa chỉ multicast.
- Ví dụ: 224.0.0.5 dùng cho OSPF; 224.0.0.9 dùng cho RIPv2

### Lớp E
Các địa chỉ trong lớp E có vai trò dùng để dự phòng, bao gồm những địa chỉ từ 240.0.0.0 trở đi.

***Lưu ý:***
Các host chỉ có thể sử dụng địa chỉ IP trong 3 lớp A, B, C. Để biết địa chỉ nằm trong lớp nào, ta sẽ xem số đầu tiên trong địa chỉ IP để biết dựa vào các khoảng sau:
- Lớp A từ 1 đến 126.
- Lớp B từ 128 đến 191.
- Lớp C từ 192 đến 223.
- Lớp D từ 224 đến 239.
- Lớp E từ 240 đến 255.

<a name="phanloai"><a/>
## Phân loại địa chỉ IP
      
Địa chỉ IP được phân thành 2 loại: *private* và *public*.
- Private: chỉ được sử dụng trong mạng nội bộ (mạng LAN), không được định tuyến trên môi trường Internet. Có thể được sử dụng lặp lại trong các mạng LAN khác nhau.
- Public: là địa chỉ được sử dụng cho các gói tin đi trên môi trường Internet, được định tuyến trên môi trường Internet. Địa chỉ public phải là duy nhất cho mỗi host tham gia vào Internet.

Dải địa chỉ private (được quy định trong RFC 1918):
- Lớp A: 10.x.x.x
- Lớp B: 172.16.x.x -> 172.31.x.x
- Lớp C: 192.168.x.x
Kỹ thuật NAT (Network Address Translation) được sử dụng để chuyển đổi giữa IP private và IP public.

Ý nghĩa của địa chỉ private: được sử dụng để bảo tồn địa chỉ public.

<a name="diachi"><a/>
## Địa chỉ Broadcast, Subnet mask, số prefix length
  
### Địa chỉ Broadcast
Gồm 2 loại:
+ Direct broadcast: ví dụ như 192.168.1.255.
+ Local broadcast: 255.255.255.255.
  
Để phân biệt hai loại địa chỉ này, ta xét ví dụ sau:
```
Xét host có địa chỉ IP là 192.168.2.1. Khi host này gửi broadcast đến 255.255.255.255, tất cả các host thuộc mạng 192.168.2.0 sẽ nhận được gói broadcast này, còn nếu nó gửi broadcast đến địa chỉ 192.168.1.255 thì tất cả các host thuộc mạng 192.168.1.0 sẽ nhận được gói broadcast (các host thuộc mạng 192.168.2.0 sẽ không nhận được gói broadcast này).
```

### Subnet mask
Subnet mask là một dãy nhị phân dài 32 bit đi kèm với một địa chỉ IP để cho phép xác định được network mà IP này thuộc về. Điều này được thực hiện bằng phép toán AND địa chỉ IP với subnet-mask theo từng bit một.
```
Ví dụ: Xét địa chỉ IP 192.168.1.1 với subnet-mask là 255.255.255.0. Để xác định địa chỉ mạng của địa chỉ này, thực hiện AND 192.168.1.1 với 255.255.255.0
(Phép toán AND:    

0 AND 0 = 0

0 AND 1 = 0

1 AND 0 = 0

1 AND 1 = 1 )
```
|     | Dạng thập phân | Dạng nhị phân |
|-----|-----------------|---------------|
| Địa chỉ IP |	192.168.1.1 |	11000000.10100000.00000001.00000001 |
| Subnet mask	| 255.255.255.0 |	11111111.11111111.11111111.00000000 |
| Địa chỉ mạng	| 192.168.1.0	| 11000000.10100000.00000001.00000000 |

Để đơn giản, chỉ cần nhớ rằng: phần network của địa chỉ chạy đến đâu, các bit 1 của subnet-mask này chạy tới đó; ứng với các bit phần host của địa chỉ, các bit của subnet-mask nhận giá trị bằng 0.

Các subnet-mask chuẩn của các địa chỉ lớp A, B, C:
- Lớp A: 255.0.0.0

- Lớp B: 255.255.0.0

- Lớp C: 255.255.255.0

### Prefix length
Một cách khác để xác định địa chỉ IP là sử dụng số prefix – length. Số prefix – length là số bit mạng trong một địa chỉ IP. Giá trị này được viết ngay sau địa chỉ IP và ngăn cách bởi dấu “/”.
```
Ví dụ:    

192.168.1.1/24

172.168.2.1/16

10.0.0.8/8
```

  <a name="hanche"><a/>
## Những điểm hạn chế của IPv4
Vấn đề lớn nhất mà IPv4 không thể giải quyết được đó là tính bảo mật. Cấu trúc của IPv4 không có bất kỳ cách bảo mật nào và nó cũng không có công cụ nào để mã hóa dữ. Do đó khi liên lạc giữa các host sẽ không được bảo mật, nếu có thì chỉ ở mức tầng ứng dụng. Việc sử dụng IPSec để bảo mật cũng chỉ áp dụng được ở tầng 3 (Network layer) của mô hình OSI và chỉ có thể bảo mật lưu lượng truyền đi giữa các mạng.

Một hạn chế nữa của IPv4 đó là số lượng địa chỉ IP bị hạn chế. Vì giới hạn trong 32 bit nên số địa chỉ tạo ra được là 2^32 = 4.294.967.296 (hơn 4 tỉ) địa chỉ IP. Tuy nhiên hiện nay nhu cầu số lượng địa chỉ IP cần sử dụng ngày càng tăng nên giao thức IPv4 không còn đáp ứng đủ nhu cầu nữa. Vì lý do này mà IPv6 đã được cho ra đời. IPv6 có đến 128bit nên có thể tạo ra số lượng địa chỉ IP lớn hơn gấp nhiều lần so với IPv4. Hiện nay tổ chức IETF đang cố gắng để thay thế hoàn toàn IPv4 thành IPv6.

Bạn có thể lên một số web để kiểm tra địa chỉ IP ví dụ như https://whatismyipaddress.com/. Khi đó bạn sẽ thấy hiện ra địa chỉ cả phiên bản IPv4 lẫn IPv6. Đây là một hành động nhằm giảm bớt sự ảnh hưởng của IPv4 để có thể dễ dàng thay thế bằng IPv6.

<a name="cachchia"><a/>
## Cách chia địa chỉ IPv4
### 1. Đổi số nhị phân sang thập phân và ngược lại
Hệ thập phân (hệ đếm cơ số 10) là 1 số có thể được ráp nối lại bởi 10 chữ số khác nhau (0 -> 9). Vd: 192, 128,…

Hệ nhị phân (hay hệ đếm cơ số 2) là một hệ đếm chỉ dùng hai ký tự là 0 và 1 để biểu đạt một giá trị số. Vd: 100, 010,1000100,…

+ Cách đổi từ hệ nhị phân sang thập phân

Xếp các bit nhị phân vào bảng trên và xét vị trí nào có bit 1 thì ta lấy các số ở vị trí đó cộng lại với nhau sẽ ra số thập phân cần tìm.

Ví dụ như ta muốn đổi từ 192 và 168 sang hệ nhị phân, ta làm như sau

<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186297987-fc8a91db-d7c6-4412-94b2-1d9389bb9087.png"/>
 </p>

+ Đổi thập phân sang nhị phân
  
Cách đổi trên có thể tóm gọn như sau: Đầu tiên bắt đầu ta lấy 128 so sánh với số cần đổi (SCĐ), tiếp đó ta cứ cộng dồn 128 với các số sau theo nguyên tắc:

Nếu kết quả cộng dồn đó SCĐ thì bit tương ứng bên dưới sẽ là 0 và ta sẽ ta bỏ số cộng dồn đó ra (nhưở phép đổi 168 là ta bỏ 2 số 64 và 16).

Nếu kết quả cộng dồn đó = SCĐ thì bit tương ứng bên dưới sẽ là 1 và tất cà các bit theo sau là 0. Phép chuyển đổi dừng lại tại đây và ta có kết quả cuối cùng.

### 2. Subneting (chia mạng con)
Subneting (chia subnet) là tổ hợp những kỹ thuật phân chia không gian địa chỉ của một lớp mạng cho trước thành nhiều lớp mạng nhỏ hơn bằng cách lấy một số bit ở phần Host Address để làm địa chỉ mạng cho mạng con (Subnet).

**Công thức tính**

Gọi n là số bit 1 tăng thêm của Subnet Mask (hay còn gọi là số bit mượn). 

Gọi m là số bit 0 còn lại của Subnet Mask (m = 32 – n – SM hiên tại). Ta làm theo 5 bước sau:

Bước 1: Số Subnet: 2^n.

Bước 2: Số Host/Subnet : 2^m – 2 (vì phải trừ đi địa chỉ NetID và Broadcast).

Bước 3: Bước nhảy: 2^m.

Bước 4: Subnet mask mới: 256 – Bước nhảy.

Bước 5: Các Subnet ID gồm + Subnet ID đầu tiên = 0 + Subnet ID kế tiếp = Subnet hiện tại + Bước nhảy.

Bước 6: Trong Subnet ID.

+ Host đầu: Subnet ID + 1.
+ Host cuối: Subnet ID + Bước nhảy – 2.
+ Địa chỉ Broadcast: Host cuối + 1.

***Lưu ý:*** Tổng số subnet có 2 cách tính : 2^m-2 và 2^m.

