# IPtables

Iptables chính là một chương trình Firewall – Tường lửa miễn phí. Chương trình này được phát triển chủ yếu cho hệ điều hành Linux. 

Chương trình cho phép hệ điều hành thiết lập các quy tắc riêng để kiểm soát truy cập và tăng tính bảo mật cho hệ thống gồm: VPS/Hosting/Server.

![image](https://user-images.githubusercontent.com/111716161/194467691-b53fe1e2-249a-4862-af33-590306b2c111.png)

Trong hệ điều hành Linux, tường lửa được thực thi tốt nhất bằng cách sử dụng netfilter. Đây là một kernel module quyết định packet nào được phép đi vào (input) hoặc đi ra bên ngoài (output).

IPtables chỉ là interface cho netfilter và cả hai thường được coi là tương tự nhau. Một cách nhìn dễ hiểu hơn là nghĩ về nó như một backend và một frontend.

# Cấu trúc IPtables

IPtables bao gồm 3 thành phần cơ bản:

- Chain: Có 5 chain trong iptables và mỗi chain chịu trách nhiệm cho một nhiệm vụ cụ thể. Các chain này là: PREROUTING, INPUT, FORWARD, OUTPUT và POSTROUTING. Giống như tên gọi của chúng, chúng chịu trách nhiệm về các packet ngay khi nhận được, hoặc ngay trước khi định tuyến ra bên ngoài.
- Table: các table khác nhau chịu trách nhiệm cho các nhiệm vụ khác nhau. Danh sách table bao gồm:  filter, nat, mangle, raw và security. Hai table đầu được sử dụng nhiều nhất. Table filter chịu trách nhiệm lọc (filter) và hạn chế các packet đến máy chủ. Table nat chịu trách nhiệm về chuyển đổi địa chỉ mạng (NAT – Network Address Translation).
- Target: Các target chỉ định nơi packet sẽ đi. Điều này được quyết định bằng cách sử dụng các target của chính iptables:
  - ACCEPT (chấp nhận)
  - DROP (gỡ bỏ)
  - RETURN (quay trở lại)
  - Hoặc target của các extension module, phổ biến nhất là DNAT, LOG, MASQUERADE, REJECT, SNAT, TRACE và TTL.
  - Các target được chia thành có kết thúc và không kết thúc. Các target có kết thúc chấm dứt rule và các packet sẽ bị ngừng ở đó. Nhưng các target không kết thúc sẽ xử lý packet theo một cách nào đó và rule sẽ  được thực hiện tiếp tục sau đó.

## 1. Table IPtables

Tables – Các bảng trong Iptables là một trong những thành phần xử lý các gói tin theo những cách cụ thể khác nhau. Đặc biệt nếu không được chỉ định công việc cụ thể thì các bảng tính sẽ được mặc định làm việc với filter table, ngoài ra còn có các bản khác. 

### 1.1. Filter Table
Đối với thành phần Tables – Các bảng trong Iptables thì bảng Filter Table là một trong những bảng được Iptables sử dụng nhiều nhất trong suốt quá trình hoạt động. Bảng này được tích hợp với nhiệm vụ chính là quyết định việc một gói tin có được đi đến đích dự kiến hay không. Hay quyết định từ chối yêu cầu của gói tin một cách chắc chắn, nhanh chóng.

### 1.2. NAT Table
Như đã đề cập ở trên, mỗi bảng trong Iptables sẽ có một nhiệm vụ khác nhau trong hệ thống. Vì vậy đối với bản NAT Table sẽ dùng các rules về NAT. Nhiệm vụ chính của NAT Table chính là chịu trách nhiệm chỉnh sửa các Source hay còn gọi là IP nguồn. Hoặc chỉnh sửa các destination (IP đích) của các gói tin. Với sự hiện diện của bảng NAT Table thì việc chỉnh sửa thông tin gói tín khi thực hiện cơ chế NAT trở nên đơn giản, dễ dàng hơn.

### 1.3. Mangle Table
Mangle Table là một trong những bảng quan trọng trong Iptables. Bảng này có nhiệm vụ chỉnh sửa header của gói tín. Ngoài ra, sự hiện diện của Mangle Table còn cho phép chỉnh sửa giá trị của các trường: TTL, MTL, Type of Service.

### 1.4. RAM Table
Dựa theo bản chất của Iptables thì Iptables là một stateful firewall với các gói tin. Các gói tin này được kiểm tra liên quan đến trạng thái State. RAM Tablet sẽ là bảng giúp người dùng dễ dàng làm việc với các gói tin trước khi kernel bắt đầu kiểm tra trạng thái. Bảng RAM cũng chức năng loại bỏ một số gói tin khỏi việc tracking vì vấn đề hiệu năng của hệ thống. Vì thế tâm quan trọng của bảng RAM trong Iptables cũng vô cùng quan trọng và cần thiết.

### 1.5. Security Table
Bảng tiếp theo có trong Iptables chính là Security Table. Một số Kernel có thể hỗ trợ thêm cho Security Table, được dùng bởi Selinux từ đó giúp thiết lập các chính sách bảo mật hiệu quả. Vậy nên Security Table luôn là một trong những bảng quan trọng trong các bảng của Iptables.

## 2. Chains
Chains chính là thành phần cơ bản tiếp theo trong Iptables. Thành phần này được tạo ra với một số lượng nhất định ứng với mỗi bảng trong Iptables. Công dụng chính của thành phần này chính là giúp lọc gói tin tại điểm khác nhau.

![image](https://user-images.githubusercontent.com/111716161/194498191-a635cc75-c9b3-4340-afc1-96022679e120.png)

- Chain Prerouting: Chain tồn tại trong Nat Table, Mangle Table và Raw Table. Các rules trong Chain sẽ được thực thi ngay khi gói tin vào đến giao diện Network Interface.
- Chain Input: Chain chỉ có ở Mangle Table và Nat Table. Các rules trong Chain này được cung cấp nhiệm vụ thực thi trước khi gói tin vào tiến trình.
- Chain Output: Chain này tồn tại ở các bảng quen thuộc như Raw Table, Mangle Table và Filter. Các rules tại đây được cung cấp nhiệm vụ thực thi sau khi gói tin được tiến trình tạo ra.
- Chain Forward: Chain này tồn tại ở các bảng Mangle Table và Filter Table. Các rules được cung cấp nhiệm vụ thực thi cho các gói tin được định tuyến qua host hiện đại.
- Chain Postrouting: Chain này chỉ tồn tại ở các bảng Mangle Table và Nat Table. Các rules trong Chain được thực thi khi gói tin rời giao diện Internet.

## 3. Target
Bộ phận thứ 3 trong Iptables chính là Target. Target – hành động sử dụng dành cho các gói tin khi các gói tin thỏa mãn các rules đặt ra. 

- ACCEPT: Hành động chấp nhận và cho phép gói tin đi vào hệ thống
- DROP: Hành động loại gói tin, không có gói tin trả lời.
- REJECT: Hành động loại gói tin nhưng vẫn cho phép gói tin trả lời Table gói tin khác. 
- LOG: Hành động chấp thuận gói tin nhưng có ghi lại log
Target là hành động dành cho gói tin được phép đi qua tất cả các rules đặt ra mà không dừng lại ở bất kỳ rules nào. Trong trường hợp gói tin không khớp với yêu cầu của reles thì mặc định sẽ được chấp thuận.

# Cấu hình của Iptables
Iptables – tường lửa có cấu hình yêu cầu cao về độ bảo mật. Trong đó tất cả các dữ liệu từ các gói tin được gửi đi sẽ được định dạng qua Internet. Linux Kernel sẽ thực hiện nhiệm vụ lọc các gói tin này bằng cách mang đến một giao diện sử dụng một bảng các bộ lọc khác nhau. Iptables của Linux cho phép người dùng thiết lập, duy trì và kiểm tra tất cả các bảng được sử dụng. 

Lúc này, người chơi sẽ thực hiện các thiết lập theo mong muốn với nhiều bảng khác nhau. Trong đó mỗi bảng được thiết lập sẽ chứa nhiều chuỗi. Mỗi chuối sẽ là một quy tắc. Mỗi quy tắc chính là đinh nghĩa cho việc phải làm với gói tin khi phù hợp với gói tin đó. Sau khi hoàn tất quá trình kiểm tra, thiết lập bảng thì một Target sẽ được đưa ra khi có một gói tin được xác lập.

Các Target có thể là một chuỗi khác để khớp với một trong các giá trị mà hệ thống đưa ra như sau:

- ACCEPT: Gói tin được phép đi qua
- DROP: Gói tín không được phép đi qua
- RETURN: Bỏ qua chuỗi hiện tại. Quy trở lại quy tắc tiếp theo từ chuỗi được gọi
