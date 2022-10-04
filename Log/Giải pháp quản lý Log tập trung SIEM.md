# SIEM

SIEM được viết tắt từ cụm từ Security Information and Event Management.  Đây là nơi tập trung event và log trong toàn thể hệ thống của doanh nghiệp, thay vì phải manual từng thiết bị một, từng thiết bị một, thì SIEM sẽ giúp chúng ta tập hợp chúng lại.

SIEM là một giải pháp cung cấp lại 1 cái nhìn toàn diện về cái gì đang diễn ra bên trong hệ thống của bạn một cách real-time và từ đó giúp IT Team chủ động hơn trong việc chống lại các mối đe dọa tiềm tàng trong hệ thống.

![image](https://user-images.githubusercontent.com/111716161/193769141-eeed977e-1c8b-4bbb-b23b-9fe86a426ef4.png)

## Vai trò của SIEM

SIEM quản lý log và sự kiện tập trung, cung cấp các chức năng chính như:

- Thu thập và lưu trữ tập trung dữ liệu log và các sự kiện từ tất cả các thiết bị dài hạn, bảo mật, an toàn và chuẩn hóa giúp cho người quản trị dễ dàng hiểu được các vấn đề đang xảy ra trong hệ thống.
- Hỗ trợ phân tích và kết hợp các thông tin khác về ứng dụng, người dùng, máy chủ, … giúp phát hiện nhanh các vấn đề về bảo mật, hoạt động xâm nhập trên toàn bộ thiết bị trong hệ thống một cách nhanh chóng.
- Đưa ra các cảnh báo các sự cố bảo mật kịp thời và chính xác cao.
- Xây dựng sẵn các chuẩn báo cáo như PCI-DSS, HIPAA, NERC-CIP, FISMA, GLBA, SOX, ISO27001 hay có thể tùy biến theo nhu cầu của khách hàng.

### So sánh giữa 2 hệ thống đó: 1 bên có SIEM và 1 bên không có SIEM

| Hệ thống có giải pháp SIEM | Hệ thống không có giải pháp SIEM |
|---|---|
| Quản lý event log một cách tập trung và việc truy xuất đến log ở 1 thời điểm nhất định rát dễ dàng | Việc lưu trữ log bạn phải thực hiện trên local, và việc truy xuất logo bạn phải truy xuất đến từng thiết bị một cách thủ công. | 
| Dựa trên các event log bạn có thể đưa ra các phân tích cho toàn hệ thống một cách tự động hóa một cách dễ dàng. | Việc bạn phân tích log cho toàn thể hệ thống để đưa ra 1 đánh giá tổng thể là một việc làm khá khó, thậm chí sẽ tốn của bạn rất nhiều thời gian. |
| Tiết kiệm về chi phí phần cứng phục vụ cho việc lưu trữ log trong 1 thời gian dài: bạn cứ tưởng tượng 1 server xxx bạn đầu tư HDD cho việc lưu trữ log trong 10 năm thì liệu việc nầy có khả thi hay chăng, chưa kể nếu doanh nghiệp bạn có 100 server như vậy bạn phải đầu tư trang bị HDD lưu trữ log cho 100 server, việc đưa log tập trung lại ở 1 mối không chỉ tiết kiệm hơn về chi phí đầu tư mà còn cải thiện performance cho thiết bị vì không phải ghi log lên HDD của server đang vận hành. | Việc lưu trữ log trên từng thiết bị một cách dài hạn đòi hỏi bạn phải trang bị HDD với dung lượng lớn cho từng thiết bị, đó là chưa kể các thiết bị firewall, network device thì internal storage của các thiết bị nầy cực kỳ nhỏ nên thậm chí việc lưu trữ log trên local từng thiết bị nầy hầu như là việc cực kỳ khó khăn và tốn kém. Việc lưu trữ log xuống HDD local đối với nhiều thiết bị vận hành phức tạp thì việc nầy có thể dẫn đến việc ảnh hưởng tới performance của thiết bị đang vận hành khá nhiều.| 

# Một số tính năng chính của SIEM

Giải pháp SIEM Thế Hệ Mới đem đến cho khách hàng một hệ thống lưu trữ và phần tích tập trung về log và các sự kiện bảo mật với sự hiển thị chuyên sâu, tương quan về mặt ngữ cảnh chưa từng có trên thị trường.

1. Hệ thống quản lý log và sự kiện tập trung đảm bảo:
- Hỗ trợ thu thập thông tin từ nhiều nguồn.
- Bảo mật về mặt dữ liệu.
- Toàn vẹn dữ liệu.
- Khả năng sẵn sàng cao.
2. Khả năng phân tích chuyên sâu theo “thời gian thực” đưa ra cảnh báo kịp thời và chính xác, rút ngắn thời gian phát hiện và xử lý sự cố.
3. Kết hợp khả năng phản ứng nhanh với các loại hình tấn công hay vi phạm chính sách hoặc các tuân thủ.
4. Xây dựng sẵn các bộ báo cáo theo chuẩn hoặc tùy biến theo nhu cầu của khách hàng.

## Các khó khăn gặp phải khi triển khai và vận hành SIEM?
Để có được giải pháp SIEM phù hợp đã là vấn đề  rất nan giải rồi. Có 5 khó khăn mà doanh nghiệp hay gặp phải:

### Thiếu security analysts được đào tạo chuyên sâu
Doanh nghiệp đã sở hữu một giải pháp SIEM xịn chưa chắc sẽ khai thác hết điểm mạnh của nó.  Một hệ thống SIEM để hoạt động trơn tru nó cần có những con người xịn tương ứng. Nên việc tìm được chuyên gia vận hành SIEM có am hiểu sâu về Cyber Security là vấn đề rất nan giải với rất nhiều doanh nghiệp. Thậm chí có nhiều doanh nghiệp đầu từ SIEM đơn giản là chỉ để đối phó.

### Không được training đầy đủ để vận hành hệ thống SIEM
Đây là vấn đề doanh nghiệp thường gặp phải khi triển khai giải pháp SIEM. Việc không được training đầy đủ sẽ dẫn đến doanh nghiệp không khác thác hết sức mạnh mà giải pháp.

### Security Team không đủ nhân lực để cover 24/7
Security Team không đủ nhân lực để cover 24/7. Hacker thường tấn công vào những thời điểm mà đội ngũ security không túc trực. Vì vậy để hệ thống vận hành một cách an toàn việc có một đội ngủ túc trực 24/7.

### Những cảnh báo được thiết lập chưa hợp lý
Những cảnh báo mà bạn thiết lập chưa hợp lý hoặc quá nhiều đến nỗi bạn bị lụt thông tin. Và điều đó làm cho thật sự bị rối trong 1 đống thông tin.

### Các thông báo riêng lẻ không chính xác
Các thông báo riêng lẻ không được tương quan chính xác bởi  vậy hệ thống SIEM sẽ không notify.

