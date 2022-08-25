# Mục lục

[Vlan là gì?](#vlan)

[Mục đích của một VLAN](#mucdich)

[Phân loại VLAN](#phanloai)

[Ứng dụng của VLAN](#ungdung)

[Cách hoạt động của VLAN](#hoatdong)

[Cách thiết lập VLAN](#thietlap)


# VLAN

<a name="vlan"/>

## VLAN là gì?
LAN là một mạng cục bộ, đây là từ viết tắt của Local Area Network. Từ này được định nghĩa là tất cả các máy tính trong cùng một miền quảng bá (Broadcast domain). Các router ( bộ định tuyến) dùng để chặn tin quảng bá, trong khi switch (bộ chuyển mạch) chỉ định tiếp chúng. 

VLAN được định nghĩa là một mạng LAN ảo và VLAN là từ viết tắt của Virut local area network hay còn gọi là Virut LAN ( mạng LAN ảo). VLAN là một kỹ thuật cho phép tạo lập các mạng LAN một cách độc lập và logic trên cùng một kiến trúc hạ tầng vật lý. Hiểu theo một cách đơn giản thì VLAN dùng để chia một con switch thành nhiều con switch nhỏ hơn và chúng hoàn toàn độc lập với nhau.

Một VLAN được định nghĩa là một nhóm logic bao gồm các thiết bị mạng và được thiết lập dựa trên các yếu tố đó là: chức năng, bộ phận, ứng dụng,… của công ty. Về mặt kỹ thuật thì VLAN là một miền quảng bá được tạo bởi các switch. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/111716161/186563319-513e2d11-15f5-45af-8bce-538ed3886187.png"/>
<p/>

Việc tạo lập ra nhiều mạng LAN ảo trong cùng một mạng cục bộ (giữa các khoa trong một trường học hay giữa các cục trong một công ty,…) giúp giảm thiểu được miền quảng bá, tạo thuận lợi cho việc quản lý một mạng cục bộ rộng lớn. Còn VLAN sẽ tương đương như một mạng con (subnet).

Tất cả các cổng trong một mạng VLAN đơn sẽ thuộc một miền quảng bá duy nhất.

Đối với Network thì: VLAN = Broadcast domain= Logical Network , còn với switch thì sẽ là: VLAN = Logical switch.

<a name="mucdich"/>

## Mục đích của một VLAN
Trong công nghệ mạng LAN, VLAN giữ vị trí rất quan trọng. Những kỹ sư mạng dùng VLAN với nhiều mục đích khác nhau. Dưới đây là một số lợi ích mà mạng LAN ảo mang lại cho người dùng:

**Cải thiện hiệu quả làm việc**

VLAN có thể cải thiện hiệu suất làm việc cho các thiết bị nhờ vào khả năng chia LAN thành các đoạn nhỏ, mỗi đoạn là một vùng quảng bá riêng (broadcast domain). Ví dụ như khi điện thoại, desktop nằm trên một VLAN còn các máy trạm lại nằm một VLAN khác thì điện thoại, desktop sẽ không thấy bất cứ lưu lượng phát sóng nào do máy trạm tạo ra và ngược lại.

Các kỹ sư mạng cũng có thể cài đặt một số quy tắc để xử lý lưu lượng khác nhau trên mỗi VLAN. Chẳng hạn như họ có thể ưu tiên cho phòng hội nghị nơi thường xuyên họp hành lưu lượng lớn hơn để các thiết bị kết nối mạng êm mượt, nhanh chóng.

**Thắt chặt an ninh**

Phân vùng VLAN là một cách để bảo mật khi các thiết bị ở những VLAN khác nhau không thể truy cập vào nhau. Quay trở lại với ví dụ trên, có thể thấy nếu nhóm VLAN của điện thoại và desktop cài đặt quyền truy cập thì máy trạm sẽ không thể kết nối được với những thiết bị này.

**Quản lý dễ dàng**

Sử dụng VLAN để nhóm các thiết bị có điểm chung lại với nhau giúp quản trị viên quản lý dễ dàng. Chẳng hạn như họ có thể cài các máy tính kế toán trên một VLAN, máy tính nguồn nhân lực ở một VLAN khác…

<a name="phanloai"/>

## Phân loại VLAN

Thông thường mạng VLAN được chia làm 3 loại chính đó là:
- Port – based VLAN (VLAN dựa trên cổng)

Đây là được cho là cách cấu hình VLAN đơn giản và phổ biến nhất. Mỗi cổng của Switch sẽ được gắn với một VLAN xác định (mặc định là VLAN 1), do vậy bất cứ thiết bị host nào gắn vào cổng đó cũng đều thuộc một VLAN nào đó.

- MAC address based VLAN (VLAN dựa trên địa chỉ vật lý):

Đây là cách cấu hình ít được sử dụng dó có rất nhiều bất tiện trong việc quản lý. Mỗi địa chỉ MAC sẽ được đánh dấu với một VLAN xác định.

- Protocol – based VLAN (VLAN dựa trên giao thức):

Cách cấu hình này cũng tương tự với VLAN dựa trên địa chỉ MAC nhưng nó lại sử dụng địa chỉ IP thay cho địa chỉ MAC. Và cách cấu hình này không được thông dụng cho lắm.

<a name="ungdung"/>

## Ứng dụng của VLAN

Trước khi tạo ra VLAN bạn cần cân nhắc việc sử dụng VLAN trong các trường hợp sau:
- Bạn đang có hơn 200 máy tính trong mạng LAN.
- Lưu lượng quảng bá (broadcast traffic) nằm trong mạng LAN của bạn quá lớn.
- Các nhóm làm việc cần phải gia tăng bảo mật hoặc bị làm chậm vì có quá nhiều bản tin quảng bá.
- Các nhóm làm việc cần phải nằm trên cùng một miền quảng bá, bởi họ đang dùng chung các ứng dụng này.

Ví dụ như: một công ty sử dụng điện thoại VoIP và một số người muốn sử dụng điện thoại sẽ có thể thuộc một mạng VLAN khác và  không cùng với người dùng thường xuyên.

Hoặc trường hợp chỉ để chuyển đổi một switch đơn thành nhiều switch ảo khác.

<a name="hoatdong"/>

## Cách hoạt động của VLAN

<p align = "center">
  <img src="https://user-images.githubusercontent.com/111716161/186308512-4704a942-78b9-49cd-b6a3-3cb5ef89246a.png"/>
</p>
 
- Các Virtual LAN ở trong mạng được xác định bằng một con số cụ thể.
- Phạm vi giá trị hợp lệ là 1- 4094. Trên một switch VLAN, ta có thể chỉ định các cổng với số VLAN thích hợp.
- Tiếp đến, switch sẽ cho phép dữ liệu cần được gửi giữa các port khác nhau có cùng một Virtual LAN.
- Vì hầu hết các mạng đều có nhiều hơn là chỉ một switch duy nhất. Vì vậy, cần có một cách nào đó để có thể gửi lưu lượng giữa hai switch trong mạng. Cách đơn giản nhất chính là gán một port trên mỗi switch của Virtual LAN và chạy một cable giữa chúng.

<a name="thietlap"/>

## Cách thiết lập VLAN
Trong phần cuối cùng, hãy cùng tìm hiểu xem cách thiết lập VLAN:

- Chọn một số VLAN hợp lệ.
- Chọn dải địa chỉ IP riêng cho để các thiết bị trên VLAN sử dụng.
- Cấu hình thiết bị switch – động (dynamic) hoặc tĩnh (static). Đối với cấu hình tĩnh, admin mạng cần gán một số VLAN cho từng switch. Còn trong cấu hình động, admin cần gán một danh sách các địa chỉ MAC hoặc username đến số VLAN.
- Cấu hình định tuyến giữa các Virtual LAN khi cần. Việc cấu hình hai hay nhiều Virtual LAN giao tiếp với nhau yêu cầu sử dụng một router nhận biết VLAN, hoặc một switch Layer 3.

### Cấu hình VLAN trên Switch Cisco

Cấu hình VLAN có thể khác nhau ngay cả giữa các mô hình chuyển mạch Switch Cisco khác nhau.
- Tạo VLAN mới.
- Đặt mỗi cổng trong VLAN thích hợp.

**Bước 1:** Khởi tạo 1 VLAN.

Switch#conf t

Enter configuration commands, one per line. End with CNTL/Z.

Switch(config)#int vlan 2

**Bước 2:** Đặt mô tả cho VLAN.

Switch(config-if)#description marketing

**Bước 3:** Đặt IP cho VLAN.

Switch(config-if)#ip add 192.168.2.1 255.255.255.0

**Bước 4:** Gán Port vào VLAN đã tạo.

Switch(config)#interface fastEthernet 0/1

Switch(config-if)#switchport access vlan 2
