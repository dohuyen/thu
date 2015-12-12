#**IV.Một số lệnh cấu hình Network trên Ubuntu**
##**1.Các câu lệnh kiểm tra thông tin mạng trong Ubuntu**

- **ifconfig -a** : Kiểm tra máy có bao nhiêu card mạng
- **grep eth & ifconfig** : Xem thông tin cấu hình các card mạng (MAC, địa chỉ IP, gateway..)  của tất cả các card mạng trong máy (tương tự lệnh ipconfig của Windows)
- **ifconfig card-name** : Xem thông tin cấu hình của card mạng có tên là card-name (ví dụ: ifconfìg eth0)
  
- **route -n** :Kiểm tra đường đi của gói tin (tương tự lệnh route trong Windows).
##**2.Các câu lệnh cấu hình mạng trong Ubuntu**

- **sudo ifconfig eth0 up** : Enable card mạng eth0 trong Ubuntu
- **sudo ifconfig eth0 down** : Disable card mạng eth0 trong Ubuntu
- **ifconfig card IP1 netmask IP2** : Cấu hình mạng cho Ubuntu, ví dụ: để thiết lập IP cho card eth0 IP là 192.168.1.100, netmask là                                        255.255.255.0 thì ta dùng lệnh sau: ifconfig eth0 192.168.1.2 netmask 255.255.255.0  .
                                   Lưu ý: Cách cấu hình này sẽ bị mất giá trị khi máy khởi động lại
- **vi /etc/network/interfaces** : Thiết lập file cấu hình mạng trong Ubuntu
- **/etc/init.d/networking restart vi /etc/resolv** : Khởi động lại card mạng trong Ubuntu (để thay đổi có hiệu lực)
 	                                  Thiết lập name server cho Ubuntu. Ví dụ, nhập vào nội dung file là:
                                    nameserver 8.8.8.8
                                 &  nameserver 8.8.8.4
- **route add default gw 192.168.1.1** : Đặt địa chỉ IP 192.168.1.1 làm default gateway trong Ubuntu. Ngược lại với add ta dùng lệnh                                          delete. (ví dụ: route delete default gw 192.168.1.1)
- **route add -net 192.168.5.0 mask 255.255.255.0 dev eth0** : Để add một routing tĩnh đến mạng (cho card mạng eth0). Ngược lại với                                                                 add ta dùng lệnh delete.
            	
##**3. Các câu lệnh Command Line khác về mạng trong Ubuntu**

- **netstat** : Hiển thị các kết nối mạng (tương tự trong Windows)
- **traceroute maychu** : Trace gói định tuyến tới máy chủ
- **nslookup** : Truy vấn máy chủ tên miền
- **rlogin maychu** : Kết nối với một hệ thống ở xa
- **telnet maychu** : Kết nối tới một hệ thống ở xa (tương tác tốt hơn lệnh rlogin)
- **rcp taptin maytuxa** : Sao chép taptin từ một máy tính maytuxa
- **ftp** : Truyền tập tin giữa các hệ thống trên một mạng
- **rsh lenh** : Chạy một lệnh trên một hệ thống ở xa mà không cần đăng nhập
- **ping maychu**	: Kiểm tra kết nối tới một hệ thống ở xa (tương tự trong Windows)
- **lcd path** : Thay đổi thư mục máy cục bộ khi đã đăng nhập ở trên máy ở xa
- **mesg y/n** : Đặt tùy chọn để các người dùng khác viết thông điệp cho bạn
- **write user** : Gửi tin nhắn cho người dùng khác
- **talk user** : Cho phép 2 người chat với nhau.
