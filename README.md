
![Cấu trúc gói tin TCP](https://2466b9f4-a-62cb3a1a-s-sites.googlegroups.com/site/lexuandin/home/hhhhhhh.png?attachauth=ANoY7cqUORJMnJlfmq_UOidhurrNimAD3KNDazIfpijXXODeXsf2cAvAPgJ926IO_OiD8yAdRbFg5ApnJGHppQIIjCnTLLBD5-VzNcLNe7Q6KXpbdqWGwrhnScZbekZuj5x1cEdFSUlT_Eghpm3t425DNgimsuUxRHMyQMY_iVbYjfDIdDIuTQWZG4HDfu9sgxY1bq32FBeJ8dL1tI6IpgV8HShLrSSjxw%3D%3D&attredirects=0.png)


##**Curl và Wget**
- Sử dụng lệnh curl hoặc wget để tải một file từ internet mà không cần đầu cuối. Với lệnh curl, gõ curl-O đường dẫn tới file. Người sử dụng có thể sử dụng lệnh wget mà không cần thêm tùy chọn nào. File sẽ xuất hiện ở đường dẫn.
_ Curl-O website.com/file
- Wget website.com/file

##**Ping**
-	Cú pháp : `$ ping ADDRESS`
- Lệnh ping gửi các gói ECHO_REQUEST tới địa chỉ chỉ định. Câu lệnh nhằm kiểm tra máy tính có thể kết nối với Internet hay một địa chỉ IP cụ thể nào đó hay không. 
- lệnh ping trên Linux sẽ duy trì gửi các gói tin cho đến khi bạn kết thúc nó. Có thể định số lượng gói tối đa gửi đi bằng cách gõ thêm tùy chọn –c.

##**Tracepath và Traceroute**
- Lệnh tracepath cũng tương tự như traceroute nhưng nó không đòi hỏi các quyền quản trị. Nó cũng được cài đặt mặc định trên Ubuntu còn tracerout thì không. Lệnh tracepath lần dấu đường đi trên mạng tới một đích chỉ định và báo cáo về mỗi nút mạng (hop) dọc trên đường đi. Nếu gặp phải các vấn đề về mạng, lệnh tracepath có thể chỉ ra vị trí lỗi mạng.
- Tracepath example.com

##**Mtr**
- Lệnh mtr là sự kết hợp ping và tracepath trong một câu lệnh đơn lẻ. mtr sẽ gửi liên tục các gói và hiển thị thời gian ping cho mỗi nút mạng. Câu lệnh cũng giúp phát hiện một số vấn đề mạng. 

##**Host**
- Lệnh host sẽ thực hiện tìm kiếm DNS. Nhập vào tên miền khi muốn xem địa chỉ IP đi kèm và ngược lại, nhập vào địa chỉ IP khi muốn xem tên miền đi kèm.
- Host howtogeek.com
- Host 208.43.115.82

##**Whois**
- Lệnh whois sẽ đưa ra các bản ghi trên server whois (whois record) của website, vì vậy bạn có thể xem thông tin về người hay tổ chức đã đăng ký và sở hữu website đó.
- whois example.com

##**Ifplugstatus**
- Lệnh ifplugstatus giúp kiểm tra dây cáp có được cắm vào giao diện mạng hay không. Câu lệnh này không được cài đặt mặc định trên Ubuntu. Sử dụng câu lệnh sau để cài đặt nó :
- sudo apt-get install ifplugd
+ Chạy các câu lệnh sau để xem trạng thái tất cả các giao diện hay chỉ xem trạng thái một giao diện cụ thể.
 - ifplugstatus
 - ifplugstatus eth0

##**Ifconfig**
- **Ifconfig <tên interface>:** để xem thông tin chi tiết về các giao diện mạng; thông thường giao diện mạng ethernet có tên là eth(). Bạn có thể cài đặt các thiết lập mạng như địa chỉ IP hoặc bằng cách dùng lệnh này (xem man ifconfig). Nếu có điều gì đó chưa chính xác, bạn có thể stop hoặc start (tức ngừng hoặc khởi_động) giao diện bằng cách dùng lệnh ifconfig<tên_giao_diện> up/down.
Câu lệnh ifconfig có rất nhiều tùy chọn để cấu hình, điều chỉnh và dò lỗi trên các giao diện mạng hệ thống. Đây cũng là cách để xem nhanh các địa chỉ IP và các thông tin khác của giao diện mạng. Gõ ifconfig để xem trạng thái các giao diện mạng hiện đang hoạt động bao gồm tên của chúng. Bạn cũng có thể chỉ định tên một giao diện để xem thông tin trên duy nhất giao diện đó.
- ifconfig
- ifconfig eth0

##**Ifdown và ifup**
- Câu lệnh ifdown và ifup giống như ifconfig up hay ifconfig down. Hai câu lệnh thực hiện bật hoặc tắt giao diện chỉ định. Điều này yêu cầu quyền quản trị nên bạn phải dùng thêm từ khóa sudo trên Ubuntu.
- sudo ifdown eth0
- sudo ifup eth0

-Màn hình Linux sẽ báo lỗi khi được nhập những câu lệnh này. Nó thường sử dụng bộ NetworkManager cho phép quản lý giao diện mạng. Mặc dù vậy, các câu lệnh này vẫn sẽ hoạt động trên các server mà không cần dùng NetworkManager.

- Nếu bạn thực sự cần cấu hình NetworkManager từ giao diện dòng lệnh, sử dụng câu lệnh nmcli.
dhclient
- Lệnh dhclient giúp làm mới địa chỉ IP trên máy bằng cách giải phóng địa chỉ IP cũ và nhận một địa chỉ mới từ DHCP server. Công việc này yêu cầu quyền quản trị, vì vậy phải dùng thêm từ khóa sudo trên Ubuntu. Chạydhclient để nhận địa chỉ IP mới hoặc sử dụng tùy chọn –r để giải phóng địa chỉ IP hiện tại.
 - sudo dhclient –r
 - sudo dhclient

##**Netstat**
- Netstat là một công cụ cơ bản về gỡ lỗi mạng(network). Nó cung cấp cho chúng ta biết về các kết nối mạng, bảng định tuyến, cổng mạng nào đang được kích hoạt, v.v.
- Lệnh netstat có cú pháp đơn giản như sau: **$netstat -tùy chọn**
+ Dưới đây là một số tùy chọn kèm theo của lệnh netstat này.
 - **a:**  hiển thị tất cả các kết nối liên quan đến mạng
 - **n:**  không phân giải địa chỉ IP thành tên.
 - **t:**  hiển thị kết nối TCP
 - **u:** hiển thị kết nối UDP
 - **s:**  hiển thị kết nối theo giao thức: TCP,UP,ICMP .v.v.. Lệnh này còn đưa ra thống kế các gói tin ra vào trên cổng mạng.
 - **o:**  hiển thị thông tin về thời gian của kết nối.
 - **p:**  hiển thị PID và tên chương trình đang mở kết nối.
 - **l:**  chỉ hiển thị những Unix sockets.
 - **i:**  hiển thị các cổng mạng đang hoạt động.
 - **c:**  tùy chọn này sẽ làm mới (refresh) các kết quả trả về. Mặc định là 1 giây, ta có thể thay đổi thông số này.
 - **r:**  hiển thị bảng định tuyến của kernel
- Và còn nhiều tùy chọn khác.

