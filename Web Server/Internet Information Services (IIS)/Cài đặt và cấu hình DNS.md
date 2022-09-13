# Mục Lục

[Cài đặt DNS](#caidat)

[Cấu hình DNS Server](#cauhinh)

<a name="caidat"></a>

# Cài đặt DNS trên Windows Server 2016

Bước 1: Mở Server Manager và nhấp vào Add Roles and Features, hoặc vào Manage rồi chọn Add Roles and Features.

![image](https://user-images.githubusercontent.com/111716161/189834895-2d3d7f8b-7277-4be7-b5c9-11a121724a76.png)

Bước 2: Chọn tùy chọn Role-based installation hoặc Feature-based installation và nhấp vào Next.

![image](https://user-images.githubusercontent.com/111716161/189835216-ef7e2960-f06d-4fc0-8e65-ded0dd1bb481.png)

Bước 3: Tại đây bạn cần chọn máy chủ mà bạn muốn cài đặt DNS Server (thường là máy chủ hiện tại).

![image](https://user-images.githubusercontent.com/111716161/189835324-3c36c480-2fa9-416c-b1a2-ea3a7e5027fc.png)

Bước 4: Từ danh sách Server Roles, chọn DNS server và nhấn Next. Nhấn Add Features trên cửa sổ popup - trong trường hợp này, DNS management console và PowerShell DNS module sẽ được cài đặt tự động. Nếu bạn muốn quản lý DNS server này từ xa, bạn không thể cài đặt các công cụ này.

![image](https://user-images.githubusercontent.com/111716161/189835573-ded1c968-576f-401a-adf9-deaa80bb56e4.png)

Bước 5: Bây giờ bạn có thể thấy rằng mục DNS được chọn. Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189835770-ea7c744a-bf93-4ebd-ab46-282054fa1a5e.png)

Bước 6: Không có tính năng bổ sung cần thiết cho bước này, nhưng ta muốn chắc chắn rằng DNS Server Tools đã được chọn. Để kiểm tra điều này, hãy nhấp vào Remote Server Administration > Role Administration Tools. Sau đó bấm vào Next.

![image](https://user-images.githubusercontent.com/111716161/189836118-be96cc1e-5282-4b1a-a2a1-adb1272c261a.png)

Bước 7: Nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189836347-a929f02c-a96d-4fe6-8b24-718dc802566f.png)

Bước 8: Để xác nhận cài đặt, bấm Install.

![image](https://user-images.githubusercontent.com/111716161/189836415-be824976-5287-4a10-b62b-b846fc90e578.png)

Bước 9: Chờ cho quá trình cài đặt hoàn tất. 

![image](https://user-images.githubusercontent.com/111716161/189836641-4e01dc8a-4ea6-447a-b98f-a7434adf458a.png)

Nhấn Close. Như vậy ta đã cài đặt xog DNS. 

![image](https://user-images.githubusercontent.com/111716161/189836769-7b184513-026e-4255-aa75-8afd00e270e8.png)

<a name="cauhinh"></a>

# Cấu hình DNS Server trên Windows Server 2016

Bước 1: Khi máy chủ DNS được cài đặt, hãy mở cửa sổ Server Manager, nhấp vào tab Tools trong menu drop-down xuất hiện và nhấp vào biểu tượng DNS để mở nó.

![image](https://user-images.githubusercontent.com/111716161/189845704-96e2cb38-befe-4525-89c3-f03f8d501337.png)

Bước 2: Những gì chúng ta cần làm là tạo một vùng. Nó là một phần của DNS mà các bản ghi được khôi phục. Để thực hiện việc này, nhấn chuột phải vào tên máy chủ DNS trên máy tính của bạn và bấm vào New zone.

![image](https://user-images.githubusercontent.com/111716161/189845271-746aa376-9d59-4caf-b9b2-0d0436df021a.png)

Bước 3: Nhấn Next trên trang chào mừng. Sang trang tiếp theo, bạn sẽ thấy ba loại khu vực có sẵn.

- Primary zone: Là vùng được viết lại, chứ không phải được sao chép từ đâu đó.
- Secondary zone: Là bản sao của một vùng khác. Khi bạn tạo một secondary zone, bạn nên sao chép các bản ghi từ một nguồn khác.
- Stub zone: Vùng này cung cấp thông tin về bất cứ máy chủ nào đang nắm giữ một vùng đặc biệt.

Vì đang muốn tạo một vùng chính, nên ta sẽ nhấp vào primary zone, rồi nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189845370-6b8555c0-d7ae-498b-99fd-f75a35d6292d.png)

Bước 4: Trong trang tiếp theo, bạn sẽ được hỏi về phương pháp sao chép.

- Tùy chọn đầu tiên, To all DNS servers running on domain controllers in the domain: <domain name>, được sử dụng khi bạn muốn sao chép với các tên miền chính và tên miền phụ trong toàn bộ domain. Lưu ý rằng điều này sẽ làm tăng lưu lượng mạng.
- Tùy chọn thứ hai, To all DNS servers running on domain controllers in the domain: <domain name>, được sử dụng khi bạn muốn máy chủ DNS sao chép tất cả các máy chủ DNS trong domain của riêng bạn.
- Tùy chọn thứ ba, To all domain controllers in this domain (for Windows 2000 compatibility): <domain name> được sử dụng khi bạn muốn máy chủ của mình chỉ sao chép các domain controller trong domain của riêng bạn.

Hãy chọn tùy chọn thứ 2 rồi bấm Next.

![image](https://user-images.githubusercontent.com/111716161/189844703-c66fe70a-1baa-4b8b-a1b2-6798a56b563a.png)

Bước 5: Trong trang Forward or Reverse Lookup Zone, chọn Forward lookup zone. Forward lookup zone sẽ dịch tên DNS thành địa chỉ IP và tùy chọn thứ 2, Reverse lookup zone, sẽ dịch IP thành tên DNS. Chỉ cần chọn Forward lookup zone rồi nhấn Next. Reverse lookup zone sẽ được cấu hình sau.

![image](https://user-images.githubusercontent.com/111716161/189837831-6d88ceac-e87d-4458-bda9-1ab6c1ab4ae5.png)

Bước 6: Chỉ định tên cho khu vực, sau đó nhấp vào nút Next.

![image](https://user-images.githubusercontent.com/111716161/189838204-18f08658-6a5c-4ec5-a6ee-147a7fb9029c.png)

Bước 7:  Tùy chọn được đề xuất chỉ cho phép cập nhật bảo mật. Tùy chọn này sẽ giúp bạn không bị ảnh hưởng bởi máy chủ DNS và phần mềm gián điệp (spyware). Hãy chọn tùy chọn đầu tiên và nhấn Next.

![image](https://user-images.githubusercontent.com/111716161/189845928-d4550196-6121-4192-a5d1-eb83b98347b5.png)

Bước 8: Sau khi tiếp tục, primary zone của bạn sẽ được tạo, chỉ cần nhấp vào nút Finish để bắt đầu làm việc.
  
![image](https://user-images.githubusercontent.com/111716161/189846151-80027442-af98-4214-8152-4a99fa08c553.png)

