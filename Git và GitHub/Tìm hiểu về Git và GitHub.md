# Git
## Định nghĩa
GIT là một hệ thống kiểm soát phiên bản phân tán (Distributed Version Control System – DVCS ) mà các developer triển sử dụng trên toàn thế giới. Nó giúp chúng ta theo dõi những thay đổi của mã nguồn theo dòng thời gian, và là một phần không thể thiếu khi làm việc theo nhóm.
![cafedev-git-vs-github](https://user-images.githubusercontent.com/111716161/185839706-6ca73def-b920-4786-819b-828a1972a315.png)
## Version Control System – VCS là gì?
VCS là viết tắt của Version Control System là hệ thống kiểm soát các phiên bản phân tán mã nguồn mở. Các VCS sẽ lưu trữ tất cả các file trong toàn bộ dự án và ghi lại toàn bộ lịch sử thay đổi của file. Mỗi sự thay đổi được lưu lại sẽ được và thành một version (phiên bản).

VCS nghĩa là hệ thống giúp lập trình viên có thể lưu trữ nhiều phiên bản khác nhau của một mã nguồn được nhân bản (clone) từ một kho chứa mã nguồn (repository), mỗi thay đổi vào mã nguồn trên local sẽ có thể ủy thác (commit) rồi đưa lên server nơi đặt kho chứa chính và một máy tính khác nếu họ có quyền truy cập cũng có thể clone lại mã nguồn từ kho chứa hoặc clone lại một tập hợp các thay đổi mới nhất trên máy tính kia.

Lập trình viên có thể xem lại danh sách các sự thay đổi của file như xem một dòng thời gian của các phiên bản. Mỗi phiên bản bao gồm: nội dung file bị thay đổi, ngày giờ sửa đổi, người thay đổi là ai, lý do thay đổi hay tên phiên bản…
### VCS có tác dụng như thế nào?
- Lưu lại lịch sử các version của bất kỳ thay đổi nào của dự án. Giúp xem lại các sự thay đổi hoặc khôi phục (revert) lại sau này.
- Việc chia sẻ code trở nên dễ dàng hơn, lập trình viên có thể để public cho bất kỳ ai, hoặc private chỉ cho một số người có thẩm quyền có thể truy cập và lấy code về.
- Vốn là một VCS nên Git cũng ghi nhớ lại toàn bộ lịch sử thay đổi của source code trong dự án. Lập trình sửa file, thêm dòng code tại đâu, xóa dòng code ở hàng nào…đều được Git ghi nhận và lưu trữ lại.
## Git hoạt động như thế nào?
Sự khác biệt chính giữa Git và bất kỳ VCS nào khác (bao gồm Subversion…) là cách Git nghĩ về dữ liệu của nó.
- Về mặt khái niệm, hầu hết các hệ thống khác đều lưu trữ thông tin dưới dạng danh sách các thay đổi dựa trên file. Các hệ thống này (CVS, Subversion, Perforce, Bazaar, v.v.) coi thông tin chúng lưu giữ dưới dạng một tập hợp các file và những thay đổi được thực hiện đối với mỗi file theo thời gian.
 
![git1](https://user-images.githubusercontent.com/111716161/185839954-61059334-b80c-4064-8769-94e78aeb9759.png)
- Git không nghĩ đến hoặc lưu trữ dữ liệu của mình theo cách này. Thay vào đó, Git coi thông tin được lưu trữ là một tập hợp các snapshot – ảnh chụp toàn bộ nội dung tất cả các file tại thời điểm.
Mỗi khi bạn “commit”, Git sẽ “chụp” và tạo ra một snapshot cùng một tham chiếu tới snapshot đó. Để hiệu quả, nếu các tệp không thay đổi, Git sẽ không lưu trữ lại file — chỉ là một liên kết đến tệp giống file trước đó mà nó đã lưu trữ. Git nghĩ về dữ liệu của nó giống như dưới đây:

![git2](https://user-images.githubusercontent.com/111716161/185840151-ee23bb42-423d-4684-b742-e4143baeaea9.png)
## Lợi ích của Git
- Dễ sử dụng, thao tác nhanh, gọn, lẹ và rất an toàn.
- Sễ dàng kết hợp các phân nhánh (branch), có thể giúp quy trình làm việc code theo nhóm đơn giản hơn rất nhiều.
- Chỉ cần clone mã nguồn từ kho chứa hoặc clone một phiên bản thay đổi nào đó từ kho chứa, hoặc một nhánh nào đó từ kho chứa là bạn có thể làm việc ở mọi lúc mọi nơi.
- Deployment sản phẩm của bạn một cách không thể nào dễ dàng hơn.
# GitHub
## Định nghĩa
GitHub là một dịch vụ cung cấp kho lưu trữ mã nguồn Git cho các dự án phần mềm cho phép chúng ta lưu trữ và truy cập các dự án của mình một cách dễ dàng từ các máy chủ của họ.  Điều quan trọng chúng ta cần nhớ là GitHub không phải là Git. GitHub chỉ là một dịch vụ lưu trữ. Có những công ty khác cung cấp dịch vụ lưu trữ làm điều tương tự như GitHub, chẳng hạn như Bitbucket và GitLab.
## Lịch sử của GitHub
GitHub được viết bằng Ruby on Rails và Erlang do Tom Preston-Werner, Chris Wanstrath, và PJ Hyett phát triển trang web được đưa ra và chạy chính thức vào tháng 4 năm 2008.

Tính đến thời điểm tháng 3 năm 2018 Github đang là dịch vụ máy chủ lưu trữ các mã nguồn lập trình lớn nhất thế giới. Với hơn 25 triệu người dùng và hơn 80 triệu mã nguồn dự án, Github đã trở thành một phần không thể thiêu đối với cộng đồng phát triển mã nguồn mở và cộng đồng lập trình viên trên toàn thế giới.
## Tính năng của GitHub
GitHub được coi là một mạng xã hội dành cho lập trình viên lớn nhất và dễ dùng nhất với các tính năng cốt lõi như:
- Wiki, issue, thống kê, đổi tên project, project được đặt vào namespace là user.
- Watch project: theo dõi hoạt động của project của người khác. Xem quá trình người ta phát triển phầm mềm thế nào, project phát triển ra sao.
- Follow user: theo dõi hoạt động của người khác.

Có 2 cách tiếp cận GitHub: Tạo project của riêng mình Contribute cho project có sẵn: fork project có sẵn của người khác, sửa đổi, sau đó đề nghị họ cập nhật sửa đổi của mình (tạo pull request).
## Lợi ích của GitHub đối với lập trình viên
- Quản lý source code dễ dàng.
- Tracking sự thay đổi qua các version.
- Markdown.
- Github giúp chứng tỏ bạn là ai.
- Github giúp cải thiện kỹ năng code, thậm chí là tracking bug.
- Github là một kho tài nguyên tuyệt vời.
- Github Action.
- Github Package Registry.
- Mở rộng mối quan hệ.
