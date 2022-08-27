# Máy ảo

Máy ảo là một chương trình đóng vai trò như một máy vi tính ảo. Nó chạy trên hệ điều hành hiện tại - hệ điều hành chủ và cung cấp phần cứng ảo tới hệ điều hành khách. Các hệ điều hành khách chạy trên các cửa sổ của hệ điều hành chủ, giống như bất kỳ chương trình nào khác của máy. Đối với những hệ điều hành khách, máy ảo lại hiện diện như một cỗ máy vật lý thực sự.

# Hoạt động của máy ảo

Công nghệ ảo hóa cho phép bạn chia sẻ một hệ thống với nhiều môi trường ảo. Hypervisor (phần mềm giám sát máy ảo) quản lý phần cứng và tách các tài nguyên vật lý khỏi môi trường ảo. Những tài nguyên này được phân vùng khi cần thiết từ môi trường vật lý đến các máy ảo.

Khi máy ảo đang chạy và người dùng hoặc chương trình đưa ra lệnh yêu cầu tài nguyên bổ sung từ môi trường vật lý, hypervisor sẽ lập lịch yêu cầu tới tài nguyên của hệ thống vật lý để hệ điều hành và ứng dụng của máy ảo có thể truy cập nhóm tài nguyên vật lý được chia sẻ.

# Tác dụng của máy ảo

1. Dùng thử hệ điều hành mới
2. Chạy phần mềm cũ hoặc không tương thích
3. Phát triển phần mềm cho các nền tảng khác
4. Xử lý phần mềm độc hại tiềm năng một cách an toàn
5. Khám phá thêm về hệ thống
6. Tận dụng lợi thế của "ảnh" chụp hệ thống trong máy ảo
7. Sao chép một hệ thống vào máy khác

# Lợi ích của việc sử dụng máy ảo

- Tiết kiệm chi phí: Chạy nhiều môi trường ảo từ một phần cơ sở hạ tầng có nghĩa là bạn có thể giảm đáng kể ảnh hưởng lên cơ sở hạ tầng vật lý của mình. Điều này thúc đẩy lợi nhuận, vì giảm nhu cầu duy trì nhiều máy chủ, tiết kiệm chi phí bảo trì và lượng điện tiêu thụ.
- Nhanh chóng và tốc độ: Việc quay vòng một máy ảo tương đối dễ dàng, nhanh chóng và đơn giản hơn nhiều so với việc cung cấp một môi trường hoàn toàn mới cho các nhà phát triển. Ảo hóa làm cho quá trình chạy các kịch bản thử nghiệm nhà phát triển nhanh hơn rất nhiều.
- Giảm thời gian ngừng hoạt động: VM rất dễ di chuyển và cũng dễ dàng chuyển từ hypervisor này sang hypervisor khác nằm trên một máy khác - điều này có nghĩa chúng là một giải pháp tuyệt vời để sao lưu, trong trường hợp máy chủ gặp sự cố đột ngột.
- Khả năng mở rộng: Máy ảo cho phép bạn dễ dàng mở rộng ứng dụng của mình bằng cách thêm nhiều máy chủ vật lý hoặc ảo hơn để phân phối khối lượng công việc trên nhiều máy ảo. Do đó, bạn có thể tăng tính khả dụng và hiệu suất của các ứng dụng của mình.
- Lợi ích bảo mật: Vì máy ảo chạy trong nhiều hệ điều hành, việc sử dụng hệ điều hành khách trên máy ảo cho phép bạn chạy các ứng dụng có vấn đề về bảo mật và bảo vệ hệ điều hành máy chủ của mình. Máy ảo cũng cho phép thực hiện các biện pháp bảo mật tốt hơn và thường được sử dụng để nghiên cứu virus máy tính một cách an toàn, cô lập virus để tránh gây rủi ro cho máy tính chủ.

# Phần mềm máy ảo phổ biến

### VirtualBox
VirtualBox là một ứng dụng máy ảo mã nguồn mở tuyệt vời chạy được trên Windows, Mac OS X và Linux. Một trong những điều tuyệt nhất về VirtualBox là không có bản thương mại. Bạn nhận được đầy đủ tính năng một cách miễn phí, gồm cả những tính năng nâng cao như “snapshots”, cho phép lưu trạng thái máy ảo.

![image](https://user-images.githubusercontent.com/111716161/187020686-c33b86ca-8f90-4591-8954-38e05059cbcd.png)

### VMware Workstation
VMware Workstation là phần mềm tạo máy ảo nổi tiếng, nó hỗ trợ những hệ điều hành mới phát hành như Windows 10, các phần cứng mới nhất, giao diện dễ sử dụng, xử lý đồ họa 3D tốt, kết nối tốt,... Phần mềm này có sẵn cho Windows và Linux và được rất nhiều người dùng ưa chuộng.

![image](https://user-images.githubusercontent.com/111716161/187020469-6170af35-e2b6-4368-89ed-93f183a2bc94.png)
