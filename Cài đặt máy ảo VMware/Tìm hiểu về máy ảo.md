# Máy ảo

Máy ảo là một chương trình đóng vai trò như một máy vi tính ảo. Nó chạy trên hệ điều hành hiện tại - hệ điều hành chủ và cung cấp phần cứng ảo tới hệ điều hành khách. Các hệ điều hành khách chạy trên các cửa sổ của hệ điều hành chủ, giống như bất kỳ chương trình nào khác của máy. Đối với những hệ điều hành khách, máy ảo lại hiện diện như một cỗ máy vật lý thực sự.

# Hoạt động của máy ảo

Công nghệ ảo hóa cho phép bạn chia sẻ một hệ thống với nhiều môi trường ảo. Hypervisor (phần mềm giám sát máy ảo) quản lý phần cứng và tách các tài nguyên vật lý khỏi môi trường ảo. Những tài nguyên này được phân vùng khi cần thiết từ môi trường vật lý đến các máy ảo.

Khi máy ảo đang chạy và người dùng hoặc chương trình đưa ra lệnh yêu cầu tài nguyên bổ sung từ môi trường vật lý, hypervisor sẽ lập lịch yêu cầu tới tài nguyên của hệ thống vật lý để hệ điều hành và ứng dụng của máy ảo có thể truy cập nhóm tài nguyên vật lý được chia sẻ.
