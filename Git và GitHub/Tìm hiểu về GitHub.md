# GitHub
## Định nghĩa
GitHub là một dịch vụ cung cấp kho lưu trữ mã nguồn Git cho các dự án phần mềm cho phép chúng ta lưu trữ và truy cập các dự án của mình một cách dễ dàng từ các máy chủ của họ.  Điều quan trọng chúng ta cần nhớ là GitHub không phải là Git. GitHub chỉ là một dịch vụ lưu trữ. Có những công ty khác cung cấp dịch vụ lưu trữ làm điều tương tự như GitHub, chẳng hạn như Bitbucket và GitLab.

![github-la-gi](https://user-images.githubusercontent.com/111716161/185856800-8451f6f3-7e35-43a7-93d2-a66f87a7ade5.jpg)

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

Toàn bộ source code của repo đó được lưu trên GitHub khi bạn tạo một repo. Bạn hoàn toàn có thể thông qua các comment sau mỗi lần commit để kiểm tra lại quá trình mình đã làm việc. Hơn thế nữa, nhiều người có thể cùng làm một repo.

Source của bạn có thể phát triển theo nhiều nhánh. Bạn có thể rẽ nhiều nhánh để phát triển project. Nhưng cuối cùng, bạn phải merge lại vào nhánh MASTER để ra được project hoàn chỉnh.
- Tracking sự thay đổi qua các version.

Sẽ khá phức tạp để theo dõi revisons nếu có quá nhiều lập trình viên cùng tham gia một dự án. Những thiết lập cài đặt hay thay đổi các file được stored ở đâu. Khi dùng Github, bạn không cần quá lo lắng đến vấn để đó nữa, Github luôn lưu lại những thay đổi bạn đã push lên repository. Bạn sẽ có một lịch sử phiên bản để phòng trường hợp các phiên bản trước đó bị mất hay không được lưu.
- Markdown.

Bạn có thể hiểu đơn giản, Markdown là một cách định dạng text trên web. Vì vậy, với Markdown bạn dễ dàng chỉnh sửa cách hiển thị của document, format từ như định dạng in đậm hay in nghiêng, thêm hình và tạo list những thứ bạn có thể làm.

Khi hiểu rõ hơn về tính năng của Github là gì, bạn có thể sử dụng Mardown ở những nơi: Git, Comments tại Issues và Pull Requests, các file có đuôi .md hay .markdown extension.
- Github giúp cải thiện kỹ năng code, thậm chí là tracking bug.

Để cải thiện kỹ năng code của bản thân mình, bạn có thể thông qua hàng vạn open source projects, hàng trăm ngàn contributors, hàng tỉ commit mỗi ngày bằng việc xem. So sánh, học tập từ những thay đổi đó đã đem lại cho bạn những kiến thức vổ ích.

Cùng với đó, một tính năng được GitHub tích hợp vào để đơn giản hóa quá trình tìm và diệt virus đó chính là tracking bug.

Để hiểu được quy trình thì những gì bạn cần làm là mở dashboard của từng project lên và filter các thông tin. Sau đó, các câu hỏi sẽ được hệ thống, sắp xếp theo mức độ phổ biến, thời gian update hay tương tại.
- Github là một kho tài nguyên tuyệt vời.

Không chỉ với những lợi ích như trên, khi bạn hiểu rõ về Github là gì, bạn sẽ hiểu rằng chắc năng Explore của Github giúp bạn theo dõi, tìm kiếm những open source projects theo đúng technology pattern mà bạn ưa thích. Chúng còn hỗ trợ code search không kể nó ở dưới dạng một project riêng biệt hay là website.

Bạn cũng có thể sử dụng nền tảng này để thực hiện seo một cách dễ dàng vì người dùng có thể tìm kiếm bất kỳ code string nào được chia sẻ public.
- Github Action.

Trên server của Github có những workflow scripts chạy tự động. Dev có thể dùng chúng để phản hồi các events trên repositories hoặc thực hiện vài action. Ví dụ như tôi có viết một cái tiện ích nho nhỏ, Autotagger – GitHub Marketplace, sẽ tự động tạo git tafs khi mà số phiên bản của package.json thay đổi. 
- Github Package Registry.

Với tính năng này, cho phép lập trình viên duy trì distribution registries của họ, bao gồm npm, docker, maven, nuget và Ruby gems.
- Mở rộng mối quan hệ.

Gặp gỡ những dev mới, chia sẻ kinh nghiệm bản thân.
