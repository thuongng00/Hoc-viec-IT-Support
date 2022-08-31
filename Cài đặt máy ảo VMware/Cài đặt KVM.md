# Cài đặt KVM trên CentOS-7

Kiểm tra hỗ trợ ảo hóa
Để kiểm tra máy có hỗ trợ ảo hóa hay không

# egrep -c "svm|vmx" /proc/cpuinfo
2
Nếu kết quả trả về 0 thì máy không hỗ trợ ảo hóa. Còn khác 0 tức là máy có hỗ trợ ảo hóa.

# Cài đặt KVM trên Ubuntu
