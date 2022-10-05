# Lợi ích của quản trị tập trung Log

- Để có thể đánh giá khái quát về tình trạng an toàn, an ninh thông tin của một cơ quan, tổ chức, thì việc thu thập, phân tích và lưu trữ các sự kiện an toàn thông tin (ATTT) từ các thiết bị, dịch vụ và ứng dụng như: Router, Switch, Firewall, IDS/IPS, Mail Security, Web Security, Anti-Virus, ứng dụng Mail, Web, cơ sở dữ liệu, hệ điều hành… là hết sức cần thiết.
- Chính vì thế, hệ thống quản lý Log tập trung hay cao hơn là SIEM được ra đời với mục tiêu thu thập và liên kết tất cả các sự kiện trên cả hệ thống mạng giúp các quản trị viên có cái nhìn tổng quan và thống nhất về các vấn đề trên cả hệ thống.
- Quản trị tập trung Log giúp quản lý và phân tích các sự kiện an toàn thông tin, thực hiện thu thập, chuẩn hóa, lưu trữ và phân tích tương quan toàn bộ các sự kiện an toàn thông tin được sinh ra từ các thành phần trong hạ tầng công nghệ thông tin của cơ quan, tổ chức.
- Quản trị tập trung Log có thể thực hiện được các nhiệm vụ sau:
  + Phát hiện kịp thời các tấn công mạng xuất phát từ Internet cũng như các tấn công xuất phát trong nội bộ.
  + Phát hiện kịp thời các điểm yếu, lỗ hổng bảo mật của các thiết bị, ứng dụng và dịch vụ trong hệ thống.
  + Phát hiện kịp thời sự lây nhiễm mã độc trong hệ thống mạng, các máy tính bị nhiễm mã độc, các máy tính bị tình nghi là thành viên của mạng máy tính (botnet).
  + Giám sát việc tuân thủ chính sách an ninh trong hệ thống
  + Cung cấp bằng chứng số phục vụ công tác điều tra sau sự cố
- Tóm lại, việc xây dựng một giải pháp quản lý tập trung Log hợp lý sẽ giúp cải thiện hiệu quả cho hệ thống giám sát an ninh trong việc phân tích và xử lý các biến cố. Các phân tích viên sẽ tốn ít thời gian cho việc đánh giá chính xác được các biến cố nếu khả năng tự động của hệ thống gặp trục trặc.
- Một giải pháp tốt sẽ cho phép tất cả các biến cố an ninh quan trọng được thu thập và lưu trữ vào cơ sở dữ liệu nhằm cung cấp thông tin cho các phân tích viên an ninh, các đội ứng phó sự cố, và các bộ phận khác của tổ chức.

# Hệ thống thu thập Log tập trung ELK

**Elastic Stack (ELK Stack)** là một nhóm phần mềm nguồn mở, dựa trên Elastic nó cho phép tìm kiếm, phân tích, thể hiện trực quan các log thu thập được từ các nguồn, các log này là bất kỳ định dạng nào, ELK là trung tâm phân tích log. 

Trung tâm log này hữu ích khi trợ giúp xác định các vấn đề phát sinh trên các server, các ứng dụng mà bạn không cần truy cập trực tiếp vào log của từng server, từng ứng dụng. 

## Các thành phần chính

![image](https://user-images.githubusercontent.com/111716161/193982192-b896305e-ccb2-4a4d-98c9-667c8a878d99.png)

- Elasticsearch - máy chủ lưu trữ và tìm kiếm dữ liệu
- Logstash - thành phần xử lý dữ liệu, sau đó nó gửi dữ liệu nhận được cho Elasticsearch để lưu trữ
- Kibana - ứng dụng nền web để tìm kiếm và xem trực quan các logs
- Beats - gửi dữ liệu thu thập từ log của máy đến Logstash

## Cơ chế hoạt động

![image](https://user-images.githubusercontent.com/111716161/193982313-0849d596-d221-4d09-a5f1-d17aa713d4c4.png)

Đầu tiên, log sẽ được đưa đến Logstash. (Thông qua nhiều con đường, ví dụ như server gửi UDP request chứa log tới URL của Logstash, hoặc Beat đọc file log và gửi lên Logstash)

Logstash sẽ đọc những log này, thêm những thông tin như thời gian, IP, parse dữ liệu từ log (server nào, độ nghiêm trọng, nội dung log) ra, sau đó ghi xuống database là Elasticsearch.

Khi muốn xem log, người dùng vào URL của Kibana. Kibana sẽ đọc thông tin log trong Elasticsearch, hiển thị lên giao diện cho người dùng query và xử lý.

## Triển khai hệ thống ELK cơ bản

Một trong những ưu điểm của ELK là các bạn có thể bắt đầu rất nhỏ, chỉ với một server (physical hoặc virtual), và có thể mở rộng tùy theo nhu cầu (scale up và scale out). Tuy nhiên, vì đây là phần mềm miễn phí (về cơ bản) và bản chất của Elasticsearch là search engine, không phải là SIEM, nên để xây dựng được hệ thống theo dõi log cho Production thì người quản trị cần phải đầu tư thời gian (đồng nghĩa với tiền bạc).

- Nhân lực: thường thì chỉ cần 1 người là gánh đủ ELK. Ban đầu thì sẽ mất thời gian tìm hiểu để triển khai và tinh chỉnh, sau khi ổn định thì chỉ cần phân tích thông tin và xử lý.
- Tài nguyên hệ thống: ở mức nhở nhất, các bạn có thể bắt đầu triển khai ELK chỉ với 1 server gồm từ 2–4 CPU, 8 GB RAM, 30 GB free HDD. 

Yêu cầu tài nguyên tỷ lệ với nhiều yếu tố như sau:
  - Lưu lượng log được thu thập
    + Yêu cầu về tốc độ truy xuất dữ liệu từ Elasticsearch
    + Yêu cầu về mức độ tìm kiếm (keyword vs. full text search vs. custom full text search)
    +Yêu cầu về redundancy (number of replicas)

  - Nhìn chung là không có công thức nào để tính trước về mặt tài nguyên. Mỗi nhu cầu sử dụng sẽ yêu cầu tài nguyên khác nhau.
