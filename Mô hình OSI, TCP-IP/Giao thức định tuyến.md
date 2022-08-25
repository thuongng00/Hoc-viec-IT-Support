# Mục lục
[Giao thức định tuyến](#gtdt)

- [Khái niệm về định tuyến](#khainiem)

- [Những khái niệm cơ bản liên quan đến định tuyến](#khainiemcoban)

- [Giao thức định tuyến](#giaothucdinhtuyen)

- [Yêu cầu về giao thức định tuyến](#yeucau)

[Giao thức định tuyến động](#dynamic)
- [Mục đích của giao thức định tuyến động](#mucdich)
- [Phân loại giao thức định tuyến động](#phanloai)

[Giao thức định tuyến tĩnh](#static)
- [Ứng dụng của giao thức định tuyến tĩnh](#ungdung)
- [Ưu, nhược điểm](#uunhuoc)
- [Những trường hợp sử dụng giao thức định tuyến tĩnh](#sudung)

<a name="gtdt"/>
# Giao thức định tuyến

<a name="khainiem"a/>
## Khái niệm về định tuyến
Định tuyến (Routing) là quá trình tìm kiếm và xác định đường đi tốt nhất trên một mạng máy tính để gói tin tới được đích thông qua các thiết bị định tuyến.

Để làm được điều đó thì các thiết bị định tuyến cần phải dựa vào thông tin bẳng định tuyến (Routing Table) và giao thức định tuyến ( Routing Protocol).
  
<a name="khainiemcoban"/>
## Những khái niệm cơ bản liên quan đến định tuyến
### Bảng định tuyến (routing tables)
<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186311501-8bbfc28f-f1aa-4e25-9f11-12a0c47234d9.png"/>
 </p>
 
 - Router sử dụng các giao thức định tuyến để xây dựng, cập nhật và duy trì thông tin trong bảng định tuyến.
 - Các thông tin thông thường gồm:
     - **Protocol type** - đặc tả giao thức định tuyến sử dụng để xây dựng mỗi phần tử trong bảng định tuyến.
     - **Next-hop associations** - thông tin về router kế tiếp khi sử dụng chức năng chuyển tiếp gói tin. 
     - **Routing metric** được sử dụng làm đơn vị cho tiêu chí định tuyến. Ví dụ RIP sử dụng hop count làm đơn vị định tuyến duy nhất; IGRP sử dụng băng thông, tải, trễ, và đơn vị tin cậy để tạo ra một đơn vị định tuyến riêng.
### Đơn vị tiêu chí định tuyến
- Bandwidth (Băng thông).
- Delay (Trễ): Thời gian tối đa để gửi một gói tin trên một đường dẫn giữa 2 thiết bị đầu cuối.
- Load (Tải): Tần suất hoạt động của tài nguyên mạng nào đó, ví dụ router hay đường dẫn mạng.
- Reliability (độ tin cậy): Thường được đánh giá bằng khả năng chịu lỗi trên một đường dẫn mạng.
- Hop count: số lượng bước trung chuyển từ nguồn tới đích.
- Ticks: độ trễ của gói tin sử dụng IBM PC clock ticks. Một tick xấp xỉ 1/18 giây.
- Cost: chi phí, thông thường dựa trên dung lượng/ lưu lượng dữ liệu gửi qua routers. 

<a name="giaothucdinhtuyen"/>
## Giao thức định tuyến

<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186310370-4efd3cd5-97be-458b-80d2-9125d6166e36.png"/>
 </p>
 
- Giao thức định tuyến được dùng trong khi thực hiện giải thuật/ thuật toán định tuyến để trao đổi thông tin giữa các mạng, cho phép các router xây dựng bảng định tuyến một cách linh hoạt. 
    - Thu thập thông tin mạng: topo, tài nguyên. 
    - Trao đổi dữ liệu giữa các nút trong quá trình tính toán đường đi. 
    - Thiết lập bản định tuyến. 
- Các giao thức/ giải thuật định tuyến thường được thực thi bởi các router.
- Một số ví dụ về các giao thức định tuyến trên mạng Internet là RIP, IGRP, OSPF, BGP, và EIGRP.
- Một số ví dụ về các giao thức định tuyến trên mạng Mobile wireless ad hoc Networks là AODV, DSR, OLSR.

<a name="yeucau"/>
## Yêu cầu về giao thức định tuyến
Cơ sở thiết kế các giao thức định tuyến: 
- Optimization (Tối ưu): Đường đi của gói tin phải được tối ưu hóa dựa trên các đơn vị định tuyến được lựa chọn. 
- Simplicity & low overhead (Đơn giản và chi phí điều khiển thấp): Các giao thức đinh tuyến được thiết kế đơn giản, hiệu quả sẽ mang lại chi phí tính toán thấp, tối ưu hóa bộ nhớ sử dụng sẽ rất hiệu quả khi mạng vận hành có quy mô lớn. 
- Robustness & stability: các giao thức định tuyến phải được thiết kế với sự ổn định cao.
- Flexibility (mềm dẻo): các giao thức định tuyến phải được thiết kế một cách mềm dẻo, linh hoạt để thích ứng nhanh với sự thay đổi topology hay các đặc tính riêng của mạng (băng thông, trễ, link-state, etc).
- Rapid convergence: các giao thức định tuyến phải được thiết kế để quá trình tìm đường nhanh chóng hội tụ.

***Phân loại theo cách xây dựng gồm 2 loại: Định tuyến động (Dynamic Route) và định tuyến tĩnh (Static route).***

<a name="dynamic"/>  
# Giao thức định tuyến động
Định tuyến động là phương thức tự động chia sẻ, trao đổi thông tin giữa các thiết bị định tuyến dựa trên các giao thức định tuyến động.
Tự động cập nhật thông tin bảng định tuyến nếu hệ thống có sự thay đổi.
Tính toán và đưa ra tuyến đường chuyển thông tin tốt nhất.

<a name="mucdich"/>  
## Mục đích của giao thức định tuyến động

Trong một mạng rất lớn có rất nhiều bộ định tuyến như mạng Internet, việc cập nhật bảng định tuyến bằng tay là không thể, vì vậy cần phải có giao thức định tuyến, giao thức định tuyến cho phép các Router xây dựng bảng định tuyến một cách linh hoạt đó là:

- Khám phá mạng từ xa.
- Duy trì việc cập nhật thông tin định tuyến.
- Tính toán và chọn tuyến đường đi tốt nhất đến đích.
- Nếu tuyến đường chuyển thông tin chính bị lỗi, tự tính toán và đưa ra tuyến đường chuyển thông tin backup.
  
<a name="phanloai"/>
## Phân loại giao thức định tuyến động

- Exterior Gateway Protocols: có giao thức BGP
- Interior Gateway Protocols: Distance Vector Protocols và Link- State Protocols.
- Giao thức Distance Vector: có giao thức RIPv1, RIPv2 và IGRP, EIGRP.
- Giao thức Link- State: có giao thức OSPF và IS-IS

<a name="static"/>  
# Giao thức định tuyến tĩnh
Định tuyến tĩnh là phương pháp định tuyến theo phương thức người quản trị khai báo thông tin định tuyến cho thiết bị định tuyến theo phương thức thủ công.
<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186322685-99416298-9785-4ac4-9e17-a6d45c176c3f.png"/>
 </p>
 
Có thể hiểu đơn giản là router định tuyến dựa trên bảng định tuyến (routing table) và khi ban đầu cấu hình cơ bản cho một  router thì nó sẽ chỉ hiểu được những đường kết nối trực tiếp với nó. Khi một gói tin gửi đến router, nó sẽ xét xem trong bảng định tuyến có thông tin đích nơi gói tin cần đến hay không ? nếu có thông tin đích đến (tức là trong bảng định tuyến có tuyến đường – đích mà gói tin đi đến) thì router sẽ đẩy gói tin theo thông tin đã có trong bảng định tuyến đó và tiếp tục gửi gói tin đi đến đích. Vì vậy nên điều rất quan trọng trong việc định tuyến chính là thông tin trong bảng định tuyến.

Trong nhiều trường hợp, nhân viên quản trị mạng sẽ Định Tuyến Tĩnh, tức là “khai báo” bằng tay cho router biết các tuyến đường có – cần có trong một hệ thống mạng và đưa vào bảng định tuyến của router. Không giống như Định Tuyến Động (Dynamic Routing), Định Tuyến Tĩnh (Static Routing) là cố định và không thay đổi mặc dù trong mạng có những sự thay đổi, trừ khi là do chính người quản trị phải khai báo lại cho router sự thay đổi đó.

<a name="ungdung"/>
  
## Ứng dụng của giao thức định tuyến tĩnh 
1. Định Tuyến Tĩnh có thể được sử dụng để xác định cổng ra từ một con router khi không có đường khác có sẵn thông tin trong bảng định tuyến. Điều này được gọi là Default Route.
2. Định Tuyến Tĩnh có thể được sử dụng cho các mạng nhỏ chỉ có một hoặc hai con đường, điều này hiệu quả hơn vì một liên kết sẽ không bị quá lãng phí so với việc trao đổi thông tin trong Định Tuyến Động.
3. Định Tuyến Tĩnh thường được sử dụng giúp chuyển thông tin định tuyến từ một giao thức định tuyến khác (routing redistribution).

<a name="uunhuoc"/>
## Ưu, nhược điểm
### Ưu điểm
- Sử dụng ít băng thông hơn so với các phương thức định tuyến khác.
- Không tiêu tốn tài nguyên để tính toàn và phân tích gói tin định tuyến.
- Dễ dàng triển khai, cấu hình.
- Có tính bảo mật tốt hơn.
### Nhược điểm
- Không có khả năng tự động cập nhật đường đi.
- Phải cấu hình thủ công khi mạng có sự thay đổi.
- Khả năng mở rộng kém, phù hợp với mô hình mạng nhỏ.

<a name="sudung"/>
## Những trường hợp sử dụng giao thức định tuyến tĩnh
- Đường truyền có băng thông thấp.
- Người quản trị cần kiểm soát các kết nối trong hệ thống.
- Hệ thống co các tuyến kết nối ít.
- Kết nối dùng định tuyến tĩnh là đường dự phòng cho đường kết nối dùng giao thức định tuyến động.
- Phương thức triển khai định tuyến tĩnh: Next hop hoặc Exit Interface.
   - Next hop: thông tin sẽ chuyển đến Router kế tiếp nào trước khi đến đích.
   - Exit Interface: thông tin sẽ được đưa ra cổng nào trước khi đến đích.
