# Checkmk

Khi càng nhiều công ty hoạt động dựa trên hệ thống mạng, việc giám sát hệ thống cũng trở nên quan trọng hơn. Các sự cố gián đoạn hệ thống mạng, máy chủ không hoạt động, các dịch vụ và ứng dụng gặp vấn đề… đều gây ảnh hưởng nghiêm trọng đến hoạt động doanh nghiệp. Tổn thất có thể lên đến hàng ngàn, thậm chí hàng triệu USD tùy theo doanh thu và lĩnh vực hoạt động. 

Để giảm thiểu thiệt hại đến mức tối thiểu hoặc ngăn chặn những sự cố đáng tiếc xả ra thì sẽ cần sự giúp đỡ rất nhiều từ các hệ thống giám sát. Bộ giải pháp OMD - Checkmk một giải pháp giám sát mã nguồn mở có khả năng giám sát, cảnh báo và hiển thị các biểu đồ khá tốt đối với những hệ thống tầm trung không sẵn sàng chi nhiều kinh phí cho việc giám sát hệ thống, mạng.

## Khái niệm về Checkmk

Check_mk là một giải pháp giám sát dựa trên mã nguồn mở. Có lõi là nagios core.

Check_mk được tạo ra với mục đích giải bài toán hiệu năng cho nagios. Giúp cho việc mở rộng hệ thống giám sát dễ dàng hơn.

Với tính năng được tích hợp với nhiều sản phẩm thì check_mk được cấu hình đơn giản hơn nhiều so với lõi nagios trước kia. Check_mk bổ sung thêm một số chức năng:

- Thời gian check tiêu chuẩn được giảm từ 5 phút xuống 1 phút
- Có thể cấu hình bằng giao diện WEB
- Có chức năng giám sát phân tán
- Có bảng điều khiển
- Có bảng thống kê số liệu
- Có biểu đồ hiển thị

## Lịch sử về Checkmk

Năm 2008 check_mk được ra mắt như là một plugins hỗ trợ và bổ sung thêm cho lõi nagios. Để có thể giúp cho giải pháp nagios hoàn thiện hơn các nhược điểm mà nagios còn mắc phải

Năm 2010 dự án OMD (Open Monitoring Distribution) được khởi động bởi Mathias Kettner. Đã kết hợp nhiều sản phẩm để có thể tạo ra sự linh hoạt trong giám sát hơn. Lúc đó có 2 phiên bản distro của OMD là OMD-LABS và CHECK_MK RAW ( OMD thường) . OMD sử dụng nhân là nagios kết hợp thêm nhiều sản phẩm mã nguồn mở để tạo ra một sản phẩm tối ưu cho nhu cầu giám sát, cảnh báo và hiển thị

Năm 2015 phiên bản đơn giản của OMD đã được ra mắt gọi là CHECK_MK vào lúc đó có 2 phiên bản của là: CHECK_MK RAW EDITION(CRE) và CHECK_MK ENTERPRISE EDITION(CEE). Hiện nay có thêm một phiên bản mới phiên bản này dựa trên phiên bản CEE được gọi là Checkmk Managed Services Edition.

## Phân biệt OMD-LABS và OMD(check_mk)

OMD là một phiên bản nhỏ của OMD-LABS nó tập chung chủ yếu vào việc phát triển check_mk.

OMD-LABS là phiên bản nâng cấp của OMD nên nó có thêm một số sản phẩm mã nguồn mở khác được tích hợp ví dụ như: Naemon; Icinga2; Grafana/Influxdb…

Trang web mặc định của OMD-LABS là Thruk.

Từ phiên bản OMD-LABS 3.0 trở đi đã remove một số phần mềm là: Nagios3; Icinga 2, Check_mk, Nagvis.

## Các phiên bản của Check_mk
Đến thời điểm hiện tại thì nagios có 3 phiên bản chính và có sẵn: 

- Check_MK Raw Edition (CRE)
- Check_MK Enterprise Edition (CEE)
- Checkmk Managed Services Edition (CME)

| Tính năng	| CRE	| CEE	| CME |
|---|---|---|---|
| Có sẵn hơn 1700 plugins tích hợp	| Có	| Có	| Có |
| Event console và hệ thống syslog	| Có	| Có	| Có |
| Chuyển dữ liệu sang dạng đô thị	 | Có |	Có |	Có |
| Báo cáo được chuyển sang dạng PDF |	Không |	Có |	Có |
| Thời gian kiểm tra tiêu chuẩn	| 60s	| 1s	| 1s |
| Hệ thống giám sát phân tán |	Không |	có |	có |
| Tự động update agent |	Không |	Có	| Có |
| Giao diện GUI bằng tiếng Đức |	Không |	Có | Có |
| Quản lý và phân chia dữ liệu một cách nghiêm ngặt	 | Không	| Không |	Có |

Phiên bản Check_MK Raw Edition (CRE) là phiên bản mã nguồn mở và hoàn toàn miễn phí còn 2 phiên bản còn lại chúng ta sẽ phải trả tiền nếu muốn sử dụng nó.

Chúng ta sẽ đi tìm hiểu và làm việc với phiên bản miễn phí là CRE. Và phiên bản stable là phiên bản 1.5 và phiên bản beta là phiên bản 1.6. Chu kỳ phát triển của check_mk là 6 tháng sẽ có một bản stable.


