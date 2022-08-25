# Mục lục

[Container là gì?](#container)

[Đặc điểm kỹ thuật của container](#dacdiem)

[Lợi ích của container trong khi lưu trữ các ứng dụng đám mây Cloud](#loiich)

[Sự khác biệt giữa container và ảo hóa](#khacbiet)

# Container

## Container là gì?
Container là một giải pháp cho vấn đề làm thế nào để phần mềm chạy một cách đáng tin cậy khi được chuyển từ môi trường máy tính này sang môi trường máy tính khác. Điều này có thể là từ máy tính xách tay của nhà phát triển đến môi trường thử nghiệm, từ môi trường tiền sản xuất đến môi trường sản xuất và có thể từ máy vật lý trong trung tâm dữ liệu đến máy ảo trên cloud.

<p align="center">
  <img height="300" src="https://user-images.githubusercontent.com/111716161/186553198-083fe82c-1d0a-43c9-8398-5a6b15d2f035.png"/>
<p/>

Container giải quyết vấn đề trên bằng cách tạo ra một môi trường bị cô lập (isolated) chứa mọi thứ mà phần mềm cần để có thể chạy được bao gồm mã nguồn, các thư viện runtime, các thư viện hệ thống, các công cụ hệ thống,… (gọi là sự phụ thuộc hoặc các phụ thuộc) mà không bị các yếu tố liên quan đến môi trường hệ thống làm ảnh hưởng tới cũng như không làm ảnh hưởng tới các phần còn lại của hệ thống.
## Đặc điểm kỹ thuật của Container
Mô hình kiến trúc của container bao gồm các thành phần chính là Server (máy chủ vật lý hoặc máy ảo), host OS (hệ điều hành cài đặt trên server) và các container.

Mỗi một ứng dụng (App A và App B) sẽ có những sự phụ thuộc riêng của nó bao gồm cả về phần mềm (các dịch vụ hay thư viện) lẫn cả về phần cứng (CPU, bộ nhớ, lưu trữ).

Các ứng dụng này sẽ được Container Engine, một công cụ ảo hóa tinh gọn, được cài đặt trên host OS, nó sẽ cô lập sự phụ thuộc của các ứng dụng khác nhau bằng cách đóng gói chúng thành các container. Các tiến trình (process) trong một container bị cô lập với các tiến trình của các container khác trong cùng hệ thống tuy nhiên tất cả các container này đều chia sẻ kernel của host OS (dùng chung host OS).

Với mô hình trên, sự phụ thuộc của ứng dụng vào tầng OS cũng như cơ sở hạ tầng được loại bỏ giúp việc triển khai phương pháp “deploy anywhere” (triển khai ở bất kỳ nơi đâu) của container được hiệu quả hơn. Thêm vào đó, do chia sẻ host OS nên container có thể được tạo gần như một cách tức thì, giúp việc scale-up & scale-down theo nhu cầu được thực hiện một cách nhanh chóng.

## Lợi ích của container trong khi lưu trữ các ứng dụng đám mây Cloud
### 1. Container có thể được nhân rộng
Hệ thống container là các gói có thể được triển khai cách xa hệ hệ thống. Đó là lý do tại sao các container có thể được di chuyển không chỉ trong đám mây một cách dễ dàng mà còn đến các nền tảng và môi trường lưu trữ khác.

Thuộc tính linh hoạt này cho phép các ứng dụng được thu nhỏ trên các môi trường lưu trữ đám mây khác nhau, làm cho các hệ thống container trở thành một công cụ đáng tin cậy cho các doanh nghiệp trên các phân khúc khác nhau.

### 2. Các container đảm bảo an ninh đám mây
Vì các container được phân tách giữa các môi trường CNTT hoặc đám mây, chúng không tương tác với nhau nên nó vẫn đảm bảo các hoạt động của riêng mình và bảo vệ ứng dụng khỏi các cuộc tấn công của virus.

Nếu một container bị tấn công, các ứng dụng trong các container khác sẽ không bị ảnh hưởng mà sé tiếp tục hoạt động với tốc độ đã định. Đây là một lợi ích rất lớn được cung cấp bởi các hệ thống container.

### 3. Cải thiện năng suất các hệ thống
Các container cho phép các ứng dụng hoạt động cục bộ riêng lẻ giúp đơn giản hóa việc kiểm tra và gỡ lỗi do có một số khác biệt về các ứng dụng đang chạy trên máy trạm, máy chủ thử nghiệm hoặc bất kỳ môi trường sản xuất nào.

### 4. Tăng tính linh hoạt trên môi trường đám mây Cloud 
- Sự cô lập của Container cho phép một ứng dụng trong một container chạy ở tốc độ chậm hơn hoặc nhanh hơn ứng dụng trong một container khác. Việc tách rời các hệ thống container này mang lại lợi ích cho người dùng và có thể triển khai theo nhiều cách.
- Do tốc độ của một ứng dụng trong một hệ thống là độc lập với nhau, nên các ứng dụng có thể chạy trơn tru, tăng tốc độ chung của môi trường đám mây.
- Các container tạo điều kiện độc lập nền tảng, hiệu quả tài nguyên và đơn giản hóa hoạt động khi một môi trường lưu trữ đám mây tốt được hỗ trợ bởi một hệ điều hành tự cập nhật một cách nhất quán.

## Sự khác biệt giữa container và ảo hóa
Với công nghệ ảo hóa, các gói là một máy ảo và nó bao gồm toàn bộ hệ điều hành cũng như ứng dụng. Một máy chủ vật lý chạy ba máy ảo sẽ có một trình ảo hóa và ba hệ điều hành riêng biệt chạy trên nó.

Ngược lại, một máy chủ chạy ba ứng dụng được đóng gói với Docker chạy một hệ điều hành và mỗi container chia sẻ nhân hệ điều hành với các container khác. Các phần được chia sẻ của hệ điều hành có chức năng chỉ cho phép được đọc, trong khi mỗi container có các phân vùng riêng (nghĩa là cách truy cập vào bộ chứa) cho quá trình ghi. Điều đó có nghĩa là các container nhẹ hơn nhiều và sử dụng ít tài nguyên hơn nhiều so với máy ảo.

Container thường nhẹ và linh hoạt hơn, mức yêu cầu tài nguyên cũng thấp hơn so với phương pháp ảo hóa máy chủ thông thường bởi vì chúng không chứa image hệ điều hành mà dùng chung kernel của máy chủ host. Container cũng có thể triển khai thành 1 hoặc nhiều cụm container khi muốn chạy những ứng dụng lớn hơn.

