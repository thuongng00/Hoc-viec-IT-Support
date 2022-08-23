# Mục lục

# Giao thức SNMP

## Giao thức SNMP là gì?
SNMP (Simple Network Management Protocol) là một giao thức tầng ứng dụng được Hội đồng Kiến trúc Internet (IAB) xác định trong RFC1157 để trao đổi thông tin quản lý giữa các thiết bị mạng. Nó là một phần của Transmission Control Protocol/Internet Protocol (TCP/IP).

## Các thành phần của giao thức SMNP
### 1. SNMP Manager
Trình quản lý hoặc hệ thống quản lý là một thực thể riêng biệt có trách nhiệm giao tiếp với các thiết bị mạng được triển khai SNMP agent. Đây thường là một máy tính được sử dụng để chạy một hoặc nhiều hệ thống quản lý mạng.

Các chức năng chính của SNMP manager:
- Agent truy vấn.
- Nhận response từ các agent.
- Đặt các biến trong agent.
- Xác nhận các sự kiện không đồng bộ từ các agent.
### 2. Các thiết bị được SNMP quản lý
Thiết bị được quản lý hoặc phần tử mạng là một phần của mạng yêu cầu một số hình thức giám sát và quản lý, ví dụ: router, switches, server, máy trạm, máy in, UPS, v.v.

### 3. SNMP Agent
Agent là một chương trình được đóng gói trong các thiết bị mạng. Việc kích hoạt agent cho phép nó thu thập cơ sở dữ liệu thông tin quản lý từ thiết bị cục bộ và cung cấp nó cho SNMP manager khi được truy vấn. Các agent này có thể là tiêu chuẩn (ví dụ: Net-SNMP) hoặc cụ thể cho một nhà cung cấp (ví dụ: HP insight agent).

Các chức năng chính của SNMP agent:

Thu thập thông tin quản lý về các chỉ số hoạt động cuả thiết bị
Lưu trữ và truy xuất thông tin quản lý như được định nghĩa trong MIB.
Báo hiệu sự kiện cho trình quản lý.
Hoạt động như một proxy cho một số nút mạng không quản lý được – SNMP.
