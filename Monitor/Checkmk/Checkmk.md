# Checkmk

Khi càng nhiều công ty hoạt động dựa trên hệ thống mạng, việc giám sát hệ thống cũng trở nên quan trọng hơn. Các sự cố gián đoạn hệ thống mạng, máy chủ không hoạt động, các dịch vụ và ứng dụng gặp vấn đề… đều gây ảnh hưởng nghiêm trọng đến hoạt động doanh nghiệp. Tổn thất có thể lên đến hàng ngàn, thậm chí hàng triệu USD tùy theo doanh thu và lĩnh vực hoạt động. 

Để giảm thiểu thiệt hại đến mức tối thiểu hoặc ngăn chặn những sự cố đáng tiếc xả ra thì sẽ cần sự giúp đỡ rất nhiều từ các hệ thống giám sát. Bộ giải pháp OMD - Checkmk một giải pháp giám sát mã nguồn mở có khả năng giám sát, cảnh báo và hiển thị các biểu đồ khá tốt đối với những hệ thống tầm trung không sẵn sàng chi nhiều kinh phí cho việc giám sát hệ thống mạng.

## Khái niệm về Checkmk

Check_mk là một giải pháp giám sát dựa trên mã nguồn mở có lõi là nagios core.

Check_mk được tạo ra với mục đích giải bài toán hiệu năng cho nagios, giúp cho việc mở rộng hệ thống giám sát dễ dàng hơn.

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

## Các khái niệm trong check_mk

### Livestatus

Là một phần quan trọng trong check_mk. Nó giúp cho check_mk truy xuất dữ liệu một cách nhanh chóng.

Livestatus sẽ sử dụng socket để lấy dữ liệu để trả lời truy vấn dó đó tốc độ truy vấn của nó không còn phụ thuộc vào tốc độ I/O như là lưu dữ liệu trong file.

Khi truy xuất dữ liệu bằng command line thì livestatus sẽ phân biệt chữ hoa và chữ thường.
Livestatus sẽ sử dụng socket để check dữ liệu do đó công việc được phân đều cho các CPU.

### Multisite – Giao diện web
Multisite là một giao diện web được check_mk áp dụng để thay thế cho nagios web.

Nó được sử dụng để xem thông tin và kiểm soát hệ thống giám sát.

Kết hợp WATO để có thể hỗ trợ việc cấu hình bằng website
WATO là tập hợp nhiều modules được sử dụng để cấu hình cho check_mk server.

Mỗi khi có thay đổi cần chọn cập nhật thay đổi
Có sẵn các agent giám sát được lưu trữ và hiển thị sẵn trên web.

Nó có phiên bản tối ưu hóa cho điện thoại.

![image](https://user-images.githubusercontent.com/111716161/194236428-b6cc82b2-c4f4-4ae4-9a92-2b04de6820d5.png)

### Event console
Ngoài việc giám sát theo khoảng thời gian check bình thường còn có một loại giám sát theo sự kiện.

Event console là hệ thống tích hợp theo dõi sự kiên từ các nguồn như syslog; SNMP traps; Windows event logs …

Những sự kiện xảy ra không được xử lý bằng lõi của check_mk mà được xử lý bằng một dịch vụ riêng biệt.

### Round Robin Database(RRD).

Đây là dạng DB mặc định mà check_mk dùng để lưu trữ thông tin.

Thông tin của DB được lưu trữ dưới dạng bảng và cột để lưu trữ dữ liệu.

Có thể hợp nhất được dữ liệu của một khoảng thời gian lại vào làm một.

Có thể truy vấn được dữ liệu trong RRD bằng live status language.

Lưu ý ngôn ngữ truy vấn này phân biệt chữ hoa và chữ thường.

Có thể sử dụng các headers để lọc thông tin hiển thị từ các truy vấn được sử dụng.

Khi muốn truy vấn thống kê thì có các giá trị và các toán tử được định nghĩa sẵn để sử dụng.

Khi dữ liệu được lưu đầy thì nó sẽ ghi đè lên dữ liệu cũ.

![image](https://user-images.githubusercontent.com/111716161/194236609-edfa6129-999c-4658-8dd1-d50598b764b9.png)

### Site
Để có thể thực hiện việc giám sát thì cần tạo ra một site để có thể sử dụng.

Một server có thể tạo ra được nhiều site.

Để đăng nhập được vào site thì cần có user để đăng nhập và user được phân thành 3 loại user: Administrator; Guest; Normal monitoring.

Có 2 user mặc định có quyền Administrator là omdadmin và cmkadmin.

Site là cách gọi của sản phẩm được tạo ra từ Multisite.

## Cấu trúc của check_mk

![image](https://user-images.githubusercontent.com/111716161/194236748-3a676df1-0efc-4af6-afeb-e6fb60319e4d.png)

Các lõi sẽ gọi xuống check_mk để thực hiện chức năng kiểm tra của nó.

sau khi check thì livestatus sẽ hiển thị thông tin của mk lên website.

PNP4nagios: được sử dụng để xử lý dữ liệu để chuyển sang dạng biểu đồ.

Nagvis: được sử dụng để vẽ lại mô hình giám sát giúp người dùng có thể nhìn một cách dễ dàng hiểu hơn.

Dữ liệu sẽ được lưu vào trong RRD.
