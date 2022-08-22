# Git
## Định nghĩa
GIT là một hệ thống kiểm soát phiên bản phân tán (Distributed Version Control System – DVCS ) mà các developer triển sử dụng trên toàn thế giới. Nó giúp chúng ta theo dõi những thay đổi của mã nguồn theo dòng thời gian, và là một phần không thể thiếu khi làm việc theo nhóm.
![cafedev-git-vs-github](https://user-images.githubusercontent.com/111716161/185839706-6ca73def-b920-4786-819b-828a1972a315.png)
## Version Control System – VCS là gì?
VCS là viết tắt của Version Control System là hệ thống kiểm soát các phiên bản phân tán mã nguồn mở. Các VCS sẽ lưu trữ tất cả các file trong toàn bộ dự án và ghi lại toàn bộ lịch sử thay đổi của file. Mỗi sự thay đổi được lưu lại sẽ được và thành một version (phiên bản).
VCS nghĩa là hệ thống giúp lập trình viên có thể lưu trữ nhiều phiên bản khác nhau của một mã nguồn được nhân bản (clone) từ một kho chứa mã nguồn (repository), mỗi thay đổi vào mã nguồn trên local sẽ có thể ủy thác (commit) rồi đưa lên server nơi đặt kho chứa chính.
Và một máy tính khác nếu họ có quyền truy cập cũng có thể clone lại mã nguồn từ kho chứa hoặc clone lại một tập hợp các thay đổi mới nhất trên máy tính kia.
Lập trình viên có thể xem lại danh sách các sự thay đổi của file như xem một dòng thời gian của các phiên bản. Mỗi phiên bản bao gồm: nội dung file bị thay đổi, ngày giờ sửa đổi, người thay đổi là ai, lý do thay đổi hay tên phiên bản…
### VCS có tác dụng như thế nào?
- Lưu lại lịch sử các version của bất kỳ thay đổi nào của dự án. Giúp xem lại các sự thay đổi hoặc khôi phục (revert) lại sau này.
- Việc chia sẻ code trở nên dễ dàng hơn, lập trình viên có thể để public cho bất kỳ ai, hoặc private chỉ cho một số người có thẩm quyền có thể truy cập và lấy code về.
- Vốn là một VCS nên Git cũng ghi nhớ lại toàn bộ lịch sử thay đổi của source code trong dự án. Lập trình sửa file, thêm dòng code tại đâu, xóa dòng code ở hàng nào…đều được Git ghi nhận và lưu trữ lại.
## Git hoạt động như thế nào?
Sự khác biệt chính giữa Git và bất kỳ VCS nào khác (bao gồm Subversion…) là cách Git nghĩ về dữ liệu của nó.
Về mặt khái niệm, hầu hết các hệ thống khác đều lưu trữ thông tin dưới dạng danh sách các thay đổi dựa trên file. Các hệ thống này (CVS, Subversion, Perforce, Bazaar, v.v.) coi thông tin chúng lưu giữ dưới dạng một tập hợp các file và những thay đổi được thực hiện đối với mỗi file theo thời gian.
<img src="https://meta.vn/huong-dan/tong-hop/anh-dep-thien-nhien-13962"/>
# GitHub
## Định nghĩa
GitHub là một dịch vụ cung cấp kho lưu trữ mã nguồn Git cho các dự án phần mềm cho phép chúng ta lưu trữ và truy cập các dự án của mình một cách dễ dàng từ các máy chủ của họ.  Điều quan trọng chúng ta cần nhớ là GitHub không phải là Git. GitHub chỉ là một dịch vụ lưu trữ. Có những công ty khác cung cấp dịch vụ lưu trữ làm điều tương tự như GitHub, chẳng hạn như Bitbucket và GitLab.
