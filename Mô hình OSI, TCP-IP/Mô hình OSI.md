# Mục lục
[Mô hình OSI](#mohinhosi)

  [*Định nghĩa*](#dinhnghia)
  
  [*Cách thức hoạt động*](#cachthuchoatdong)
  
  [*Các giao thức*](#cacgiaothuc)
  
  [*Ưu, nhược điểm*](#uunhuocdiem)
  
 [Bảy tầng trong mô hình OSI](#baytang)
  
   [*1. Tầng vật lý*](#tang1)
   
   [*2. Tầng liên kết dữ liệu*](#tang2)
   
   [*3. Tầng mạng*](#tang3)
   
   [*4. Tầng giao vận*](#tang4)

   [*5. Tầng phiên*](#tang5)
                  
   [*6. Tầng trình diễn*](#tang6)
        
   [*7. Tầng ứng dụng*](#tang7)
 
 [Quá trình hoạt động của mô hình OSI](#quatrinhhoatdong)
 
   [*Xử lý dữ liệu từ máy gửi*](#maygui)
   
   [*Xử lý dữ liệu ở máy nhận*](#maynhan)
   
<a name="mohinhosi"></a>
# Mô hình OSI
<a name="dinhnghia"></a>
## Định nghĩa
Mô hình OSI (Open Systems Interconnection Reference Model, viết ngắn là OSI Model hoặc OSI Reference Model) - tạm dịch là Mô hình tham chiếu kết nối các hệ thống mở - là một thiết kế dựa vào nguyên lý tầng cấp, lý giải một cách trừu tượng kỹ thuật kết nối truyền thông giữa các máy tính và thiết kế giao thức mạng giữa chúng. Mô hình này được phát triển thành một phần trong kế hoạch Kết nối các hệ thống mở (Open Systems Interconnection) do ISO và IUT-T khởi xướng. Nó còn được gọi là Mô hình bảy tầng của OSI.

Mô hình OSI được tạo ra với mục đích là cho phép sự tương giao (interoperability) giữa các hệ máy (platform) đa dạng được cung cấp bởi các nhà sản xuất khác nhau. Mô hình cho phép tất cả các thành phần của mạng hoạt động hòa đồng, bất kể thành phần ấy do ai tạo dựng. Vào những năm cuối thập niên 1980, ISO đã tiến cử việc thực thi mô hình OSI như một tiêu chuẩn mạng.
<a name="cachthuchoatdong"></a>
## Cách thức hoạt động
OSI cho phép các chuyên gia triển khai mô hình hoá quá trình nhận và gửi dữ liệu trên mạng. Đây là một phần của các chứng chỉ mạng CNTT gồm CCNA và CompTIA Network+.

Mô hình OSI giúp phân chia các tiêu chuẩn, quy trình và giao thức truyền dữ liệu thành các gói nhỏ khác nhau thông qua một chuỗi gồm 7 lớp khác nhau. Trong đó, mỗi lớp chịu trách nhiệm thực hiện các tác vụ liên quan đến việc gửi và nhận dữ liệu trên mạng giữa các thiết bị kết nối.

Bảy lớp này được triển khai dựa trên các tính năng của ứng dụng, OS, trình điều khiển thiết bị thẻ mạng, phần cứng mạng và các giao thức hỗ trợ vật lý khác như đồng xoắn đôi, cáp quang, Wifi hay LTE 5G.
<a name="cacgiaothuc"></a>
## Các giao thức
Các giao thức trong OSI là yếu tố vô cùng quan trọng, 2 loại giao thức sử dụng trong mô hình đó là: Giao thức hướng liên kết và giao thức không liên kết

- Giao thức hướng liên kết – Connection Oriented

Trước khi bắt đầu quá trình truyền dữ liệu, các thực thể trong cùng một tầng của hai hệ thống khác nhau cần phải thiết lập một liên kết logic chung. Chúng tiến hành trao đổi, thương lượng với nhau về tập các tham số sẽ sử dụng trong quá trình truyền dữ liệu, có thể là cắt bớt hoặc hợp nhất dữ liệu, liên kết sẽ được hủy bỏ.

Việc thiết lập liên kết logic này sẽ giúp nâng cao độ tin cậy, an toàn.

- Giao thức không liên kết – Connectionless

Với các giao thức không liên kết chỉ có giai đoạn duy nhất truyền dữ liệu và dữ liệu khi này được truyền độc lập trên các tuyến khác nhau.

<a name="uunhuocdiem"></a>
## Ưu, nhược điểm
**Ưu điểm**
- Là một mô hình mạng tiêu chuẩn dành cho thiết bị máy tính.
- Hỗ trợ các dịch vụ không kết nối và định hướng kết nối.
- Hoạt động linh hoạt với nhiều giao thức khác nhau.
- Khả năng thích ứng và độ an toàn cao.

**Nhược điểm**
- Không hỗ trợ xác định bất kỳ giao thức cụ thể nào.
- Chỉ phù hợp với lớp 5 giúp quản lý phiên, lớp trình bày và xử lý các tương tác.
- Lớp 2 và lớp 4 có các cách sao chép dịch vụ khác nhau.
- Các lớp chỉ có thể hoạt động logic lần lượt từ lớp này đến lớp khác.

<a name="baytang"></a>
# Bảy tầng trong mô hình OSI
- Trong mô hình OSI, khả năng kiểm soát sẽ được luân chuyển từ tầng này tới tầng khác, quá trình bắt đầu từ tầng 7, sau đó dần dần được chuyển đến tầng dưới cùng thông qua các kênh tới các station rồi sau đó sao lưu hierarchy.
- Mô hình OSI 7 tầng tiếp nhận nhiệm vụ liên mạng, tiến hành chia thành các tầng tương ứng được xếp trồng lên nhau.
- Chủ yếu các chức năng của nó được tồn tại ở tất cả các hệ thống giao tiếp, ngoài tên mô hình 7 tầng, 7 lớp thì nó còn hay được gọi là Mô hình Tham chiếu OSI hoặc chỉ là Mô hình OSI.
- Mô hình gồm 7 tầng OSI là một hệ thống mở, nó có khả năng kết nối thông tin với các hệ thống khác nhau, tương thích với các chuẩn OSI.
  - Tầng 1-4: là các tầng thực hiện chức năng di chuyển dữ liệu, đây là các tầng cấp thấp.
  - Tầng 5-7: tầng cấp cao chứa các dữ liệu ứng dụng. Cách thức vận hành của hệ thống network nằm trong một quy tắc chung đó là chuyển dữ liệu đi. Mỗi tầng sẽ thực hiện các chức năng chuyên biệt riêng sau đó mới chuyển các dữ liệu đi tới các tầng tiếp theo.
<p align="center">
    <img src ="https://user-images.githubusercontent.com/111716161/186052056-67b648f7-ec58-4e7b-b0a4-efdf0462caa4.png"/>
 </p>
 
 <a name="tang1"></a>
 ## 1. Tầng vật lý (Physical Layer)
Physical Layer trong cấu trúc mô hình OSI thì là tầng thấp nhất. Tại đây thì các đối tượng thực hiện giao tiếp với nhau thông qua một đường truyền vật lý.

Chức năng: thực hiện xác định các chức năng, thủ tục về điện, cơ, quang giúp kích hoạt, duy trì và giải phóng các kết nối vật lý giữa hệ thống mạng. Dịch vụ các cơ chế về điện, hàm, thủ tục, … nhằm thực hiện việc kết nối các phần tử của mạng thành một hệ thống bằng các phương pháp vật lý.

Chức năng của tầng vật lý giúp đảm bảo cho các yêu cầu chuyển mạch hoạt động, tạo ra các đường truyền cho chuỗi bit thông tin. Các chuẩn trong tầng vật lý là các chuẩn xác định giao diện người sử dụng và môi trường mạng.

Giao thức ở tầng vật lý chia ra làm 2 đó là: truyền dị bộ (Asynchronous) và truyền đồng bộ (Synchronous).

Ví dụ ứng dụng ở tầng: V.35, V.24, FDDI, RJ45, Ethernet.

  <a name="tang2"></a>
 ## 2. Tầng liên kết dữ liệu (Data-Link Layer)
 <p align="center">
    <img src ="https://user-images.githubusercontent.com/111716161/186054336-e1c6aa84-dd63-4294-87d5-074244cecc09.png"/>
 </p>
Trong tầng hai có 2 tầng con nhỏ hơn:
- Tầng MAC: Media Access Control (Địa chỉ kiểm soát truy cập phương tiện).
- Tầng LLC: Logical Link Control (Điều khiển Liên kết Logic)
Chức năng: Nhiệm vụ của nó là xây dựng nên các mối liên kết, duy trì, hủy bỏ các liên kết dữ liệu đồng thời tiến hành việc kiểm soát lỗi, kiểm soát lưu lượng. Để thực hiện được chức năng này thì nó cần phải phân chia thông tin ra các khung thông tin, truyền các khung theo đúng thứ tự, xử lý các thông tin xác nhận từ máy nhận gửi về. Sắp xếp, tháo gỡ các khung thành chuỗi bit không cấu trúc để chuyển xuống tầng vật lý. Tầng 2 bên thu thì thực hiện tái tạo chuỗi bit về lại các khung thông tin.

Trong quá trình xử lý, đường truyền vật lý có thể bị lỗi, vì thế mà tầng liên kết phải giải kiểm soát lỗi, kiểm soát luồng, kiểm soát lưu lượng, ngăn không để nút nguồn gây “nghẽn” làm giảm tốc độ xử lý dữ liệu.

Trong các mạng quảng bá, tầng con MAC – Medium Access Sublayer điều khiển việc duy trì nhập đường truyền.

Ví dụ ứng dụng ở tầng Data Link: ATM, FDDI, IEEE 802.3/802.2, PPP, HDLC, IEEE 802.5/802.2.
  <a name="tang3"></a>
 ## 3. Tầng mạng (Network Layer)
Chức năng: thực hiện việc chọn routing để các gói tin nguồn tới đích trong cùng một mạng hoặc khác mạng. Routing này có thể là cố định, cũng có thể thể được định nghĩa khi bắt đầu trao đổi, hay cũng có thể đường đi là động cho phép thay đổi theo từng tập tin tùy vào trạng thái của mạng.

Không chỉ có vây, một chức năng cực kì quan trọng khác của tầng Network đó là kiểm soát việc tắc nghẽn. Với trường hợp có quá nhiều gói tin đến đi cùng một lúc, trên cùng 1 đường sẽ bị nghẽn thì Network sẽ giao tiếp các mạng để đưa gói tin từ mạng này qua mạng khác chuyển tới đích cuối cùng.

Ví dụ ứng dụng ở tầng Network: IP, IPX.

   <a name="tang4"></a>
 ## 4. Tầng giao vận (Transport Layer)
Đây là tầng cao nhất có liên quan đến các giao thức trao đổi dữ liệu trong các hệ thống mở, tham gia vào việc kiểm soát truyền dữ liệu End-to-End. Còn chức năng chủ yếu của 3 tầng dưới tầng vật lý, tầng liên kết dữ liệu và tầng mạng là để phục vụ việc truyền dữ liệu giữa các tầng liền nhau.

Chức năng: chia gói tin lớn thành các gói nhỏ trước khi gửi đi, đánh số gói tin để đảm bảo thông tin truyền đi theo thứ tự mong muốn. Đây là lớp cuối phải chịu trách nhiệm về độ an toàn của việc truyền dữ liệu đi. Chính vì thế mà giao thức tầng vận chuyển phụ thuộc rất nhiều vào tầng mạng.

Tầng này còn có thể thực hiện việc ghép kênh một vài liên kết vào chung một liên kết nối giúp giảm giá thành.

Ví dụ ứng dụng ở tầng Transport: TCP, UDP, SPX.
<p align="center">
    <img src ="https://user-images.githubusercontent.com/111716161/186054418-3bbe2dc7-71b1-4831-817e-edf90e1affdd.png"/>
 </p>

   <a name="tang5"></a>
 ## 5. Tầng phiên (Session Layer)
Ngay từ các tầng đầu, bạn đã thấy từ session được lặp lại nhiều lần. Ở tầng Session này nó cho phép người dùng có thể sử dụng các máy khác nhau thiết lập, đồng bộ và duy trì phiên truyền thông giữa họ. Hiểu theo cách đơn giản hơn thì Tầng phiên thiết lập “các giao dịch” giữa các thực thể đầu cuối.

Ứng dụng phiên cung cấp liên kết giữa 2 đầu cuối sử dụng dịch vụ phiên, sao cho đồng bộ được việc trao đổi dữ liệu đến khi kết thúc thì giải phóng liên kết. Sử dụng thẻ Token để tiến hành việc truyền dữ liệu, đồng bộ hóa, hủy bỏ liên kết trong cả truyền đồng thời hay luân phiên. Thiết lập các điểm đồng bộ hóa trong hội thoại. Khi xảy ra sự cố có thể khôi phục hội thoại bắt đầu từ một điểm đồng bộ hóa đã thỏa thuận.

Ví dụ ứng dụng ở tầng Session: NFS, SQL, RPC, NetBios Names.
   <a name="tang6"></a>
 ## 6. Tầng trình diễn (Presentation Layer)
Tầng thứ hai kế tiếp tầng ứng dụng là tầng trình bày, tầng này nhận lấy các dữ liệu từ tầng ứng dụng.

Chức năng: thực hiện một số công việc phức tạp như định dạng dữ liệu cho lớp 7 thông qua môi trường ứng dụng. Đồng thời lớp 6 cũng giúp xử lý mã hóa và giải mã theo yêu cầu của các lớp.

Trên thực tế, thông tin biểu diễn các ứng dụng nguồn và ứng dụng đích có thể khác nhau bởi các ứng dụng được chạy trên các hệ thống khác nhau.

Tầng Presentation cũng giống như với tầng ứng dụng, chúng chuyển hóa các dữ liệu nhận được thành các dữ liệu. Chúng cũng định đạng, mã hóa rồi gửi các dữ liệu qua mạng, độc lập với các vấn đề. Lớp này rất quan trọng vì dữ liệu cần phải được cấu trúc chuẩn thì mới đối tượng khác mới có thể hiểu được.
   <a name="tang7"></a>
 ## 7. Tầng ứng dụng (Application Layer)
 Chức năng tầng Ứng dụng: là lớp ứng dụng hay lớp 7 cho phép người dùng tương tác với ứng dụng hoặc mạng các tác vụ như đọc tin nhắn hay chuyển tệp. Đồng thời hỗ trợ trình duyệt web và các ứng dụng được kết nối internet khác như Outlook và Skype.

Khi các đối tượng ứng dụng AE (Application Entity) được thiết lập, nó sẽ kết nối với đến các phần tử dịch vụ ứng dụng ASE (Application Service Element). Trong mỗi đối tượng ứng dụng có thể gồm một hoặc nhiều các phần tử dịch vụ ứng dụng. Các phần tử dịch vụ này được kết hợp trong môi trường của thực thể ứng dụng bằng việc sử dụng các liên kết gọi là đối tượng liên kết đơn SAO (Single Association Object). Đối tượng liên kết SAO điều khiển việc truyền thông, cho phép tuần tự hóa các sự kiện truyền thông.

Tầng Application có các dịch vụ ứng dụng cho các tác vụ email, chuyển tệp, cho các phần mềm. Telnet, FTP là 2 ứng dụng tồn tại ở tầng này.

Ví dụ ứng dụng ở tầng Application: WWW, Telnet, HTTP, FTP, NFS, SNMP.

<a name="quatrinhhoatdong"></a>
# Quá trình hoạt động của mô hình OSI

<a name="maygui"></a>
## Xử lý dữ liệu từ máy gửi
- Tại tầng 7 Application, bạn gửi dữ liệu vào máy tính dưới các dạng văn bản, hình ảnh,…
- Tầng 6 Presentation tiếp nhận thông tin được chuyển xuống từ tầng 7, lúc này thông tin được tiến hành mã hóa và nén dữ liệu.
- Sau khi đã được mã hóa và nén, dữ liệu được chuyển xuống tầng 5 Session. Các dữ liệu sẽ được xử lý sau đó bổ sung thêm các thông tin cần thiết (thông tin gửi/nhận). Đơn giản hơn bạn có thể hiểu đây là bước xác nhận các thông tin.
- Khi xác nhận xong, dữ liệu được đẩy xuống tầng 4 Transport. Ở bước này các dữ liệu được chia thành nhiều phần nhỏ, đồng thời nó cũng được bổ sung thêm các thông tin như phương thức vận chuyển để đảm báo tính bảo mật.
- Tầng 3 Network, khi xuống tới tầng này, các phần dữ liệu vừa được chia nhỏ lại tiếp tục được chia ra thành nhiều gói thông tin khác nhau. Sau đó các gói thông tin sẽ được vận chuyển theo đúng tuyến đường đi đã được định sẵn.
- Tiếp nối quá trình, dữ liệu được chuyển tới Tầng 2 Data Link. Các gói thông tin nhỏ từ tầng 3 xuống tiếp tục được cắt nhỏ thành những Frame, đồng thời được bổ sung thông tin kiểm tra các gói tin chứa dữ liệu này, mục đích để có thể kiểm tra ở đầu máy nhận khi thông tin tới.
- Tầng cuối cùng trong mô hình, tầng 1 Physical. Các Frame khi được chuyển xuống đây sẽ được chuyển thành các chuỗi bit nhị phân, sau đó được đưa lên, phá tin hiệu trên các công cụ truyền dẫn (dây cáp quang) để chuyển tới được máy nhận.
- Các gói tin dữ liệu khi được chuyển xuống các tầng dưới sẽ được gắn thêm các header của tầng đó, chỉ riêng ở tầng 2 gói tin được gắn thêm FCS.

<a name="maynhan"></a>
## Xử lý dữ liệu ở máy nhận
- Dữ liệu từ máy đến tiếp xúc đầu tiên với tầng 1 của máy nhận. Ở đây, các dữ liệu sẽ được kiểm tra đồng bộ và đưa các chuỗi bit nhị phân vào vùng đệm, sau đó là gửi thông báo cho Tầng 2 “dữ liệu đã được nhận).
- Tầng 2 Data Link, nơi kiểm tra xem có lỗi nào đối với các Frame dữ liệu vừa gửi không. Phương thức kiểm tra đó là kiểm tra xem FCS có trong các Frame đó hay không. Khi phát hiện Frame bị lỗi thì sẽ hủy bỏ Frame đó. Tiếp đến là quá trình kiểm tra địa chỉ Data Link (địa chỉ MAC Address) có khớp với địa chỉ máy nhận hay không. Kiểm tra thấy đúng, các lớp Data Link sẽ gỡ bỏ Header để chuyển dữ liệu lên tầng 3 Network.
- Tầng 3 Network tiếp nhận và kiểm tra địa chỉ gói tin dư liệu có phải là địa chỉ máy nhận không (địa chỉ ở tầng này là địa chỉ IP). Nếu đúng các gói tin dữ liệu tiếp tục được gỡ bở Header của tầng Network rồi được chuyển tới tầng 4 Transport.
- Khi thông tin lên tới tầng 4 sẽ được hỗ trợ phục hồi và xử lý lỗi bằng cách gửi các gói tin ACK, NAK. Đây là những gói tin dùng để phản hồi xem các gói chứa dữ liệu đã được gửi đến máy nhận hay chưa. Khi các gói tin đã được phục hồi xong sẽ được chuyển tiếp lên tầng 5 Session của mô hình 7 tầng OSI.
- Tầng 5 Session sẽ kiểm tra để chắc chắn rằng các gói tin nguyên vẹn từ máy gửi tới máy nhận. Tiếp tục gỡ bỏ các Header của tầng 5 và chuyển tiếp thông tin đi.
- Tầng 6 Presentation tiếp nhận, tiến hành chuyển đổi định dạng dữ liệu để xử lý gói tin và đưa lên tầng 7.
- Tầng cuối cùng, Application nhận dữ liệu, gỡ bỏ nốt Header, kết thúc quá trình nhận dữ liệu đến.
