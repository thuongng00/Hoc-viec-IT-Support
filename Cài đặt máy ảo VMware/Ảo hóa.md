# Ảo hóa là gì?

Trong ngành công nghệ thông tin, ảo hóa là hành động tạo một phiên bản ảo của bất kỳ tài nguyên nào (ví dụ như máy chủ, hệ thống mạng, storage device, hệ điều hành) thành một hay nhiều môi trường thực thi. Trong đó, người dùng, thiết bị và ứng dụng đều dễ dàng tương tác với tài nguyên ảo tương tự như tài nguyên thực. 

Ảo hóa sử dụng phần mềm mô phỏng chức năng phần cứng để tạo ra một hệ thống ảo. Thực tiễn này cho phép các tổ chức CNTT vận hành nhiều hệ điều hành, nhiều hệ thống ảo và các ứng dụng khác nhau trên một máy chủ duy nhất. Các lợi ích của ảo hóa bao gồm hiệu quả cao hơn và tính kinh tế theo quy mô.

Ảo hóa hệ điều hành là việc sử dụng phần mềm để cho phép một phần cứng chạy nhiều hình ảnh hệ điều hành cùng một lúc. Công nghệ này đã bắt đầu xuất hiện trên các máy tính lớn từ nhiều thập kỷ trước, cho phép các quản trị viên tránh lãng phí sức mạnh xử lý đắt tiền.

# Cách thức hoạt động của ảo hóa

Ảo hóa mô tả một công nghệ trong đó ứng dụng, hệ điều hành khách (client OS) hoặc bộ lưu trữ dữ liệu được trừu tượng hóa khỏi phần cứng hoặc phần mềm cơ bản thực sự. Công dụng chính của công nghệ ảo hóa là ảo hóa máy chủ, sử dụng một lớp phần mềm – được gọi là siêu giám sát (hypervisor) – để mô phỏng phần cứng bên dưới.

Điều này thường bao gồm bộ nhớ của CPU, đầu vào/đầu ra (I/O) và lưu lượng mạng. Người giám sát lấy các tài nguyên vật lý và tách chúng ra để chúng có thể được sử dụng bởi môi trường ảo. Chúng có thể ngồi trên hệ điều hành hoặc được cài đặt trực tiếp vào phần cứng. Phần phía sau là cách hầu hết các doanh nghiệp ảo hóa hệ thống của họ.

Xen hypervisor là một chương trình phần mềm mã nguồn mở chịu trách nhiệm quản lý các tương tác cấp thấp xảy ra giữa các máy ảo (VM – Virtual machine) và phần cứng vật lý. Nói cách khác, Xen hypervisor cho phép tạo, thực thi và quản lý đồng thời các máy ảo khác nhau trong một môi trường vật lý.

Với sự trợ giúp của hypervisor, hệ điều hành khách – bình thường tương tác với phần cứng thực – giờ đang làm như vậy với một mô phỏng phần mềm của phần cứng đó. Thông thường, hệ điều hành khách không biết nó ở trên phần cứng ảo hóa.

Mặc dù hiệu suất của hệ thống ảo này không bằng hiệu suất của hệ điều hành chạy trên phần cứng thực, nhưng khái niệm ảo hóa hoạt động vì hầu hết các hệ điều hành khách và ứng dụng không cần sử dụng toàn bộ phần cứng bên dưới.

Điều này cho phép linh hoạt hơn, kiểm soát và cách ly bằng cách loại bỏ sự phụ thuộc vào một nền tảng phần cứng nhất định. Mặc dù ban đầu có nghĩa là ảo hóa máy chủ, nhưng khái niệm ảo hóa đã lan rộng đến các ứng dụng, mạng, dữ liệu và máy tính để bàn.

**Quá trình ảo hóa**

Quá trình ảo hóa thực hiện theo các bước được liệt kê bên dưới:

- Người giám sát tách các tài nguyên vật lý ra khỏi môi trường vật lý của chúng.
- Các tài nguyên được lấy và phân chia, khi cần, từ môi trường vật lý đến các môi trường ảo khác nhau.
- Người dùng hệ thống làm việc với và thực hiện các phép tính trong môi trường ảo.
- Khi môi trường ảo đang chạy, người dùng hoặc chương trình có thể gửi một lệnh yêu cầu tài nguyên bổ sung tạo thành môi trường vật lý. Đáp lại, hypervisor chuyển tiếp thông báo tới hệ thống vật lý và lưu trữ các thay đổi. Quá trình này sẽ diễn ra với tốc độ gần như nguyên bản.
- Môi trường ảo thường được gọi là máy khách hoặc máy ảo. Máy ảo – VM – hoạt động giống như một tệp dữ liệu duy nhất có thể được chuyển từ máy tính này sang máy tính khác và được mở trên cả hai; nó được mong đợi sẽ thực hiện theo cùng một cách trên mọi máy tính.

# Các loại ảo hóa
## Ảo hóa mạng
Ảo hóa mạng là phương pháp kết hợp các tài nguyên có sẵn trong mạng bằng cách chia băng thông khả dụng thành các kênh, mỗi kênh độc lập với các kênh khác và có thể được gán – hoặc chỉ định lại – cho một máy chủ hoặc thiết bị cụ thể trong thời gian thực.

Ý tưởng là ảo hóa che giấu sự phức tạp thực sự của mạng bằng cách tách nó thành các phần có thể quản lý được, giống như ổ cứng được phân vùng giúp bạn dễ dàng quản lý các tệp của mình hơn.

## Ảo hóa bộ nhớ
Ảo hóa bộ nhớ là tập hợp bộ nhớ vật lý từ nhiều thiết bị lưu trữ mạng thành một thiết bị lưu trữ duy nhất được quản lý từ bảng điều khiển trung tâm. Ảo hóa lưu trữ thường được sử dụng trong các mạng khu vực lưu trữ.

## Ảo hóa máy chủ
Ảo hóa máy chủ (ảo hóa server) là việc che giấu tài nguyên máy chủ – bao gồm số lượng và danh tính của từng máy chủ vật lý, bộ xử lý và hệ điều hành – khỏi người dùng máy chủ. Mục đích là giúp người dùng không phải hiểu và quản lý các chi tiết phức tạp của tài nguyên máy chủ trong khi tăng cường chia sẻ và sử dụng tài nguyên cũng như duy trì khả năng mở rộng sau này.

Lớp phần mềm cho phép trừu tượng hóa này thường được gọi là siêu giám sát. Hypervisor phổ biến nhất – Loại 1 – được thiết kế để đặt trực tiếp trên kim loại trần và cung cấp khả năng ảo hóa nền tảng phần cứng để các máy ảo sử dụng. 

Ảo hóa KVM là một siêu giám sát ảo hóa dựa trên nhân Linux cung cấp các lợi ích ảo hóa Loại 1 tương tự như các siêu giám sát khác. KVM được cấp phép theo mã nguồn mở. Một siêu giám sát loại 2 yêu cầu một hệ điều hành chủ và thường được sử dụng cho các thử nghiệm và phòng thí nghiệm.

## Ảo hóa dữ liệu
Ảo hóa dữ liệu là trừu tượng hóa các chi tiết kỹ thuật truyền thống của dữ liệu và quản lý dữ liệu, chẳng hạn như vị trí, hiệu suất hoặc định dạng, có lợi cho quyền truy cập rộng hơn và khả năng phục hồi cao hơn gắn liền với nhu cầu kinh doanh.

## Ảo hóa máy tính để bàn
Ảo hóa máy tính để bàn là ảo hóa tải máy trạm thay vì máy chủ. Điều này cho phép người dùng truy cập máy tính để bàn từ xa, thường sử dụng một thin client tại bàn làm việc. Vì máy trạm về cơ bản đang chạy trong một máy chủ trung tâm dữ liệu, nên việc truy cập vào nó có thể an toàn hơn và di động hơn. Giấy phép hệ điều hành vẫn cần được tính đến như cơ sở hạ tầng.

## Ảo hóa ứng dụng
Ảo hóa ứng dụng là trừu tượng hóa lớp ứng dụng khỏi hệ điều hành. Bằng cách này, ứng dụng có thể chạy ở dạng đóng gói mà không bị phụ thuộc vào hệ điều hành bên dưới. Điều này có thể cho phép một ứng dụng Windows chạy trên Linux và ngược lại, ngoài việc tăng thêm mức độ cô lập.

Ảo hóa có thể được xem là một phần của xu hướng tổng thể trong doanh nghiệp CNTT bao gồm tính toán tự động, một kịch bản trong đó môi trường CNTT sẽ có thể tự quản lý dựa trên hoạt động được nhận thức và tính toán tiện ích, trong đó sức mạnh xử lý của máy tính được coi là tiện ích mà khách hàng chỉ có thể trả tiền khi cần thiết. Mục tiêu thông thường của ảo hóa là tập trung các tác vụ quản trị trong khi cải thiện khả năng mở rộng và khối lượng công việc.

# Ưu điểm của việc sử dụng ảo hóa
Những lợi thế của việc sử dụng môi trường ảo hóa bao gồm:

### Giá rẻ
Ảo hóa làm giảm số lượng máy chủ phần cứng cần thiết trong một công ty và trung tâm dữ liệu. Điều này làm giảm tổng chi phí mua và bảo trì số lượng lớn phần cứng.
### Khôi phục thảm họa dễ dàng hơn 
Khôi phục thảm họa rất đơn giản trong môi trường ảo hóa. Snapshots thường xuyên cung cấp dữ liệu cập nhật, cho phép các máy ảo được sao lưu và phục hồi một cách khả thi. Ngay cả trong trường hợp khẩn cấp, máy ảo có thể được di chuyển đến vị trí mới trong vòng vài phút.
### Kiểm tra dễ dàng hơn 
Kiểm tra ít phức tạp hơn trong môi trường ảo. Ngay cả khi gây ra sai lầm lớn, việc kiểm tra cũng không cần phải dừng lại và quay lại từ đầu. Nó có thể chỉ cần quay lại snapshots trước đó và tiến hành kiểm tra.
### Sao lưu nhanh hơn 
Các bản sao lưu có thể được thực hiện trên cả máy chủ ảo và máy ảo. Snapshots tự động được thực hiện suốt cả ngày để đảm bảo rằng tất cả dữ liệu đều được cập nhật. Hơn nữa, các máy ảo có thể dễ dàng di chuyển giữa nhau và được triển khai lại một cách hiệu quả.
### Cải thiện năng suất
Ít tài nguyên vật lý hơn dẫn đến việc dành ít thời gian hơn cho việc quản lý và bảo trì máy chủ. Các nhiệm vụ có thể mất vài ngày hoặc vài tuần trong môi trường vật chất có thể được thực hiện trong vài phút ở môi trường ảo. Điều này cho phép các nhân viên dành phần lớn thời gian của họ cho các nhiệm vụ hiệu quả hơn, chẳng hạn như tăng doanh thu và thúc đẩy các sáng kiến kinh doanh.

Bên cạnh đó Ảo hóa còn có những nhược điểm sau:
– Dữ liệu có thể gặp rủi ro: Làm việc trên các phiên bản ảo trên tài nguyên được chia sẻ có nghĩa là dữ liệu được lưu trữ trên tài nguyên của bên thứ ba khiến dữ liệu ở trong tình trạng dễ bị tấn công. 
– Chi phí đầu tư ban đầu cao.

 # Lợi ích khi sử dụng ảo hóa
- **Máy chủ chuyên dụng:** Ảo hóa cung cấp một cách hiệu quả về chi phí để tách email, cơ sở dữ liệu và máy chủ web, tạo ra một hệ thống toàn diện và đáng tin cậy hơn.
Nhanh chóng triển khai và tái triển khai: Khi máy chủ vật lý gặp sự cố, máy chủ sao lưu có thể không phải lúc nào cũng sẵn sàng hoặc đã được cập nhật. Cũng có thể không có sẵn hình ảnh hoặc bản sao của máy chủ. Nếu đúng như vậy, thì quá trình triển khai lại có thể tốn nhiều thời gian. Tuy nhiên, nếu trung tâm dữ liệu được ảo hóa, thì quá trình này diễn ra nhanh chóng và khá đơn giản. Các công cụ sao lưu ảo, chẳng hạn như Veeam, có sẵn để đẩy nhanh quá trình này chỉ mất vài phút.
- **Giảm nhiệt và cải thiện tiết kiệm năng lượng:** Các công ty sử dụng nhiều máy chủ phần cứng có nguy cơ quá nóng tài nguyên vật lý của họ. Cách tốt nhất để ngăn điều này xảy ra là giảm số lượng máy chủ được sử dụng để quản lý dữ liệu và cách tốt nhất để làm điều này là thông qua ảo hóa.
- **Tốt hơn cho môi trường:** Các công ty và trung tâm dữ liệu sử dụng nhiều phần cứng để lại lượng lớn khí thải carbon; họ phải chịu trách nhiệm về ô nhiễm mà họ đang tạo ra. Ảo hóa có thể giúp giảm những ảnh hưởng này bằng cách giảm đáng kể lượng điện năng và làm mát cần thiết, do đó giúp làm sạch không khí và bầu không khí. Kết quả là, các công ty và trung tâm dữ liệu ảo hóa sẽ nâng cao danh tiếng của họ đồng thời nâng cao chất lượng mối quan hệ của họ với khách hàng cũng như giữa con người với môi trường.
- **Di chuyển sang đám mây dễ dàng hơn:** Ảo hóa đưa các công ty đến gần hơn với việc trải nghiệm một môi trường hoàn toàn dựa trên đám mây. Máy ảo thậm chí có thể được triển khai từ trung tâm dữ liệu để xây dựng cơ sở hạ tầng dựa trên đám mây. Khả năng nắm bắt tư duy dựa trên đám mây với ảo hóa giúp việc di chuyển sang đám mây thậm chí còn dễ dàng hơn.
- **Không cần phụ thuộc nhiều vào nhà cung cấp:** Máy ảo là bất khả tri trong cấu hình phần cứng. Do đó, ảo hóa phần cứng và phần mềm có nghĩa là một công ty không cần phụ thuộc vào nhà cung cấp cho các tài nguyên vật lý này.
