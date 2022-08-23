# Mục lục

# Giao thức SSH

## Giao thức SSH là gì?

### Khái niệm
SSH, còn được gọi là Secure Socket Shell, là một giao thức mạng cung cấp cho quản trị viên một cách an toàn để truy cập máy tính từ xa. SSH cũng đề cập đến bộ tiện ích thực hiện giao thức. Secure Shell cung cấp khả năng xác thực mạnh và bảo mật thông tin liên lạc giữa hai máy tính kết nối qua mạng không an toàn như Internet. SSH được sử dụng rộng rãi bởi các quản trị viên mạng, để quản lý hệ thống và ứng dụng từ xa, cho phép họ đăng nhập vào một máy tính khác qua mạng, thực thi lệnh và di chuyển các file từ máy tính này sang máy tính khác.
### Cơ chế hoạt động
SSH gồm cả giao thức mạng và bộ tiện ích cơ bản để triển khai chính giao thức đó. Cụ thể, SSH ứng dụng ảnh mô hình client-server, kết nối với vùng hiển thị Session và vùng Session chạy.

Khi triển khai SSH hệ thống sẽ hỗ trợ cả giao thức ứng dụng, sử dụng cho trình giả lập Terminal hoặc truyền file. Trong thực tế, người ta còn sử dụng SSH để phát triển tunnel bảo mật cho các giao thức ứng dụng. 

Mục đích SSH được tạo ra là để thay thế cho trình giả lập Terminal, cơ chế đăng nhập không an toàn (Telnet, Rlogin). Giao thức SSH hỗ trợ tính năng đăng nhập, khởi chạy Terminal Session thông qua hệ thống điều khiển từ xa.

Chức năng cơ bản nhất của giao thức SSH là liên kết với một host từ xa, ứng với một phiên Terminal bằng dòng lệnh “ssh server.example.org”. Dòng lệnh này có thể liên kết Client với một máy chủ server.example.com thông qua ID người dùng UserName.

### Chức năng chính
Giao thức đảm nhiệm khá nhiều chức năng trong hệ thống điều khiển, liên kết máy chủ. Các chức năng cơ bản phải kể đến như:
- Hỗ trợ truy cập từ xa vào những hệ thống, thiết bị ứng dụng giao thức SSH.
- Cho phép dịch chuyển file an toàn.
- Thực thi lệnh bảo mật, an toàn trên hệ thống điều khiển từ xa.
- Quản lý an toàn và hiệu quả thành phần hạ tầng mạng.
- SSH có thể kết hợp với Terminal Session thay thế cho những chương trình Telnet có tính bảo mật thấp.

## Kỹ thuật mã hóa trong SSH

Ưu điểm lớn nhất của SSH nằm ở khả năng mã hóa, truyền tải dữ liệu an toàn giữa thành phần Host và Client. Trong đó, Host chính là máy chủ từ xa cần liên kết với máy tính Client. Kỹ thuật mã hóa thông qua SSH có thể triển khai theo 3 phương thức khác nhau.

**Mã hóa Symmetric Encryption**

Symmetric Encryption chính là một phương thức mã hóa ứng dụng Secret Key theo hai chiều, giải mã tin cho Host và Client. Như vậy, bất kỳ ai sở hữu mã khóa đều có khả năng giải mã tin nhắn trong quá trình truyền tin.
Symmetric Key được ứng dụng để mã hóa hoàn toàn phiên giao dịch diễn ra trong giao thức SSH. Trong đó, Host và Client có nhiệm vụ tạo Key bí mật, tuyệt đối không để lộ cho bên thứ ba.

Chính bởi Key không truyền tải giữa Client và Host nên thuật toán rất bảo mật. Cả hai máy tính có thể chia sẻ thông tin chung, ứng dụng chúng xác định mã Key bí mật. Bất kỳ máy tính khác có thể nắm bắt thông tin hay không, chúng cũng không dò được mã khóa bí mật.

Tuy nhiên cũng cần lưu ý rằng, Secret Token chỉ có thời hạn sử dụng trong một phiên SSH, nó hình thành từ chứng thực Client. Khi tạo mới Key, toàn bộ Packets giữa hai máy cần trải qua mã hóa bởi Private Key. Quá trình này gồm cả bước cung cấp mật khẩu bởi người dùng.

**Mã hóa Asymmetric Encryption**
Khác với Symmetric Encryption, phương thức Asymmetric Encryption lại dùng 2 khóa riêng biệt để phục vụ mã hóa và giải mã. Bao gồm khóa công khai Public Key và khóa riêng tư Private Key, hình thành cặp khóa Public-private key pair.
Khóa Public Key công khai trên tất cả các thành phần liên quan. Tuy nhiên, nó cũng liên hệ trực tiếp với khóa riêng tư Private Key. Chính sự phụ thuộc này nên Public Key gần như không thể tự mã hóa thư, giải mã bất cứ thứ gì đã mã hóa bởi Private Key.

Trong khi đó Private Key lại luôn tuyệt mật, không chia sẻ với bất kỳ bên thứ ba nào. Khóa riêng tư có khả năng giải mã thư. Vậy nên khi bên nào giải thành công thư gửi đến Public Key có nghĩa bên thứ đó đang sở hữu Private Key.

Vậy nhưng cũng cần lưu ý rằng Asymmetric Encryption không thể mã hóa tất cả SSH. Nó chỉ có thể sử dụng khi trao đổi thuật toán khóa. Trước thời điểm bắt đầu một phiên, phía 2 đầu trao đổi cần đồng ý khởi tạo cặp khóa Public – Private trong ngắn hạn. Đồng thời, chia sẻ Private Key để tạo ra một Secret Key chung.

Mỗi khi liên kết Symmetric chính thức thiết lập an toàn, máy chủ Server cũng đồng thời sử dụng Public Key của Client. Từ đó khởi tạo, thay đổi và truyền đến Client phục vụ quá trình chứng thực. Trường hợp Client giải thành công tin nhắn có nghĩa nó đang giữ Private Key. Phiên giao dịch SSH cũng đồng thời bắt đầu.

**Mã hóa Hashing**
Hashing một chiều là phương thức mã hóa ứng dụng phổ biến trong Secure Shell Connection. Khác với Symmetric Encryption và Asymmetric Encryption, Hashing không sử dụng vào mục đích giải mã. Chúng hình thành sau mỗi lần nhập liệu, không thể khai thác. Như vậy, Hashing sẽ không thể quay lại để giải mã.
Thông thường, để tạo ra một mật mã Hash rất đơn giản qua một lần Input. Thế nhưng chúng ta lại không thể tạo ra Input thông qua chính lần Hash đó. Nói cách khác, Client đang giữ Input đó. Điều này có nghĩa chỉ Client có thể tạo một crypto-graphic hash để tiến hành xác định hai bên nhập Input.

Giao thức SSH cần đến Hash để kiểm tra tính xác thực của tin nhắn. Quy trình xác thực này đảm bảo rằng lệnh không thể giả danh bởi bất cứ phương thức nào.

## Cách thức xử lý các dạng mã hóa trong giao thức SSH
Trong phần tiếp theo của chuyên mục giải đáp SSH là gì, FPT Cloud sẽ giúp bạn giải thích sâu hơn về cách thức xử lý các dạng mã hóa. Như đã đề cập, SSH hoạt động theo mô hình Client – Server để chứng thực hai máy từ xa.

### Giai đoạn Session Encryption Negotiation
Để liên kết Client với Server thông qua TCP, Server cần xuất trình Encrytpion Protocal và các phiên bản hỗ trợ. Trường hợp Client có Protocol tương thích, phiên bản cũng phải đúng như vậy. Khi đó một thỏa thuận cũng đồng thời được khởi tạo, tiếp nhận Protocol. Mỗi Server còn sử dụng Symmetric Public Key để xác thực.
Nếu đã thiết lập thành công, cả hai phía cần sử dụng thuật toán chung Diffie-Hellman Key Exchange Algorithm. Thanh toán này có nhiệm vụ tạo Symmetrical Key, đồng bộ quá trình liên lạc sau này.

Dưới đây là phần tóm tắt cách thức hoạt động của thuật toán:

- Client và Server phải đồng ý với nguyên tắc sử dụng seed value. 
- Cả hai phía ra cần thiết được lưu ý thách thức mã hóa triển khai bởi seed value thông qua thuật đặc biệt. Đó là cơ chế tạo mã hóa, tác động lớn đến seed value.
- Cả hai bên tạo ra Private Key.
- Private Key này chung thuật toán với mã hóa AES ứng dụng để tạo ra Public Key, phân phối đến máy còn lại.
- Cả hai bên có quyền sử dụng Private Key. Trong khi đó, Public Key của máy còn lại sẽ kết hợp với Public Key để tạo ra một Key chung.
- Khi cả hai đều có sẵn Shared Key, quá trình mã hóa Symmetric cho phiên SSH chính thức được khởi động.

### Giai đoạn chứng thực người dùng 
Đây là bước cuối cùng để người dùng có thể truy cập vào server, thực hiện xác nhận thông tin trên chính hệ thống đăng nhập. Người dùng trước tiên cần nhập tên đăng nhập, sau đó là mật khẩu. Thông tin người dùng cung cấp tiếp tục được truyền đến một hệ thống bảo mật Symmetric, không cho bất kỳ bên thứ ba nào thu thập.

Mật khẩu mặc dù đã trải qua mạng mã hóa nhưng nếu người dùng không cẩn thận vẫn có thể bị lộ. Khi một bên nào đó thu thập thành công mật khẩu, tài khoản của người dùng dễ bị chiếm đoạt. Theo nhiều chuyên gia bảo mật, người dùng nên sử dụng SSH Key Pair, bộ khóa Asymmetric có chức năng xác thực thành viên không yêu cầu nhập mật khẩu.

## SSH nên sử dụng khi nào?

Trong mô hình TCP / IP, giao thức SSH sẽ hoạt động tại tầng thứ 4. Đối tượng nhiệm vụ tương tác duy trì kết nối giữa máy chủ và máy khách. Thông qua cơ chế mã hóa chuyên biệt, giao thức này có thể đảm bảo dữ liệu truyền đi an toàn. So với Telnet, Rlogin đã khắc phục yếu điểm tốt về mặt bảo mật.

- Sử dụng trong mọi datacenter

Giao thức SSH có mặt trong hầu hết datacenter và luôn đi kèm phần lớn Server Unix, Mac và Linux. Kết nối SSH hiệu ứng dụng phổ biến để xây dựng giao thức bảo mật cho hệ thống mấy cục bộ, Host từ xa.

Chẳng hạn như ứng dụng xây dựng quyền truy cập an toàn từ xa vào hệ thống tài nguyên, cập nhật phần mềm,.. Ngoài chức năng tạo đường dẫn an toàn cho máy cục bộ và Host từ xa, SSH cũng hỗ trợ quản lý Router, phần cứng máy chủ, một số nền tảng ảo hóa.

- Kết nối hệ thống server

SSH có phải là kết nối hệ thống server. Từ đó thực hiện các thay đổi, nâng cấp thông qua công cụ hoặc Terminal. SSH Key thử sử dụng để truy cập tập vào server trong cách tự động, ứng dụng chủ yếu trong Script, backup, công cụ quản lý cấu hình.

- Ứng dụng cho hệ thống đăng nhập một lần

Giao thức SSH hỗ trợ hoàn hảo để ứng dụng vào hệ thống đăng nhập một lần SSO. Theo đó, người dùng sẽ đăng nhập nhanh chóng, di chuyển qua lại giữa tài khoản mà không cần tốn thời gian nhập mật khẩu.

- Mã hóa dữ liệu

Không chỉ hỗ trợ xác thực kết nối mã hóa mà SSH traffic còn tham gia trực tiếp vào quá trình lão hóa. Khi người dùng chuyển file, duyệt web, nhập lệnh hay những tác vụ khác đều diễn ra an toàn.

- Xác thực thông tin

SSH kết hợp với ID người dùng và mật khẩu khi xác thực thông tin. Tuy vậy hiện nay, giao thức này chủ yếu hỗ trợ xác thực giữa hệ thống Host với nhau. Như vậy người dùng cá nhân vẫn phải sử dụng ID user và mật khẩu khi cần kết nối với Host từ xa.

Quá trình kết nối để thực hiện thông qua việc tạo một Public Key Pair ứng với từng Host. Trong đó, mỗi Session lại yêu cầu hai Public Key Pair. Một Key phục vụ xác thực máy cục bộ từ xa, Key còn lại làm nhiệm vụ xác thực máy cục bộ trực tiếp.
