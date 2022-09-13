# Cài đặt DNS trên Windows Server 2016

Bước 1: Mở Server Manager và nhấp vào Add Roles and Features, hoặc vào Manage rồi chọn Add Roles and Features.

![image](https://user-images.githubusercontent.com/111716161/189834895-2d3d7f8b-7277-4be7-b5c9-11a121724a76.png)

Bước 2: Chọn tùy chọn Role-based installation hoặc Feature-based installation và nhấp vào Next.

![image](https://user-images.githubusercontent.com/111716161/189835216-ef7e2960-f06d-4fc0-8e65-ded0dd1bb481.png)

Bước 3: Tại đây bạn cần chọn máy chủ mà bạn muốn cài đặt DNS Server (thường là máy chủ hiện tại).

![image](https://user-images.githubusercontent.com/111716161/189835324-3c36c480-2fa9-416c-b1a2-ea3a7e5027fc.png)

Bước 4: Từ danh sách Server Roles, chọn DNS server và nhấn Next. Nhấn Add Features trên cửa sổ popup - trong trường hợp này, DNS management console và PowerShell DNS module sẽ được cài đặt tự động. Nếu bạn muốn quản lý DNS server này từ xa, bạn không thể cài đặt các công cụ này.
