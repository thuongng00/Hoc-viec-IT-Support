# IPtables

Iptables chính là một chương trình Firewall – Tường lửa miễn phí. Chương trình này được phát triển chủ yếu cho hệ điều hành Linux. Chương trình cho phép hệ điều hành thiết lập các quy tắc riêng để kiểm soát truy cập và tăng tính bảo mật cho hệ thống gồm: VPS/Hosting/Server.

![image](https://user-images.githubusercontent.com/111716161/194467691-b53fe1e2-249a-4862-af33-590306b2c111.png)

Trong hệ điều hành Linux, tường lửa được thực thi tốt nhất bằng cách sử dụng netfilter. Đây là một kernel module quyết định packet nào được phép đi vào (input) hoặc đi ra bên ngoài (output).

IPtables chỉ là interface cho netfilter và cả hai thường được coi là tương tự nhau. Một cách nhìn dễ hiểu hơn là nghĩ về nó như một backend và một frontend.

# Cấu trúc IPtables

IPtables bao gồm các thành phần khác nhau:

- Chain: Có 5 chain trong iptables và mỗi chain chịu trách nhiệm cho một nhiệm vụ cụ thể. Các chain này là: PREROUTING, INPUT, FORWARD, OUTPUT và POSTROUTING. Giống như tên gọi của chúng, chúng chịu trách nhiệm về các packet ngay khi nhận được, hoặc ngay trước khi định tuyến ra bên ngoài.
- Table: các table khác nhau chịu trách nhiệm cho các nhiệm vụ khác nhau. Danh sách table bao gồm:  filter, nat, mangle, raw và security. Hai table đầu được sử dụng nhiều nhất. Table filter chịu trách nhiệm lọc (filter) và hạn chế các packet đến máy chủ. Table nat chịu trách nhiệm về chuyển đổi địa chỉ mạng (NAT – Network Address Translation).
- target: Các target chỉ định nơi packet sẽ đi. Điều này được quyết định bằng cách sử dụng các target của chính iptables:
  - ACCEPT (chấp nhận)
  - DROP (gỡ bỏ)
  - RETURN (quay trở lại)
  - Hoặc target của các extension module, phổ biến nhất là DNAT, LOG, MASQUERADE, REJECT, SNAT, TRACE và TTL.
  - Các target được chia thành có kết thúc và không kết thúc. Các target có kết thúc chấm dứt rule và các packet sẽ bị ngừng ở đó. Nhưng các target không kết thúc sẽ xử lý packet theo một cách nào đó và rule sẽ  được thực hiện tiếp tục sau đó.
  
# Table IPtables

Hầu hết thao tác bạn sẽ sử dụng chính trên table filter. Nếu khi viết rule, bạn không chỉ định bất kỳ table nào, filter được sử dụng theo mặc định. Vì vậy, hãy ghi nhớ điều đó. Và tiếp tục dưới đây, tôi sẽ giải thích từng table:

- filter: là table được sử dụng nhiều nhất hàng ngày. Đó là lý do tại sao nó là table mặc định. Trong table này, bạn sẽ quyết định xem packet có được phép vào (input) hoặc ra (output) khỏi máy tính của bạn hay không. Nếu bạn muốn chặn một port để ngừng nhận bất cứ thứ gì, đây là điểm table bạn cần.
- nat: Table này là table phổ biến thứ hai và chịu trách nhiệm tạo kết nối mới. Đó là cách viết tắt của Network Address Translation.
- mangle: table này dùng để thay đổi dữ liệu bên trong các packet trước khi chúng đến hoặc ra khỏi máy tính.
- raw: table này xử lý packet raw chưa qua xử lý như tên gọi của nó. Chủ yếu là để theo dõi trạng thái kết nối. Chúng ta sẽ thấy các ví dụ về điều này bên dưới khi muốn cho các packet thành công từ kết nối SSH.
- security: có nhiệm vụ đánh dấu những gói tin có liên quan đến context của SELinux, nó giúp cho SELinux hoặc các thành phần khác hiểu được context SELinux và xử lý gói tin.

