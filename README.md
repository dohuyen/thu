
![Cấu trúc gói tin TCP](https://2466b9f4-a-62cb3a1a-s-sites.googlegroups.com/site/lexuandin/home/hhhhhhh.png?attachauth=ANoY7cqUORJMnJlfmq_UOidhurrNimAD3KNDazIfpijXXODeXsf2cAvAPgJ926IO_OiD8yAdRbFg5ApnJGHppQIIjCnTLLBD5-VzNcLNe7Q6KXpbdqWGwrhnScZbekZuj5x1cEdFSUlT_Eghpm3t425DNgimsuUxRHMyQMY_iVbYjfDIdDIuTQWZG4HDfu9sgxY1bq32FBeJ8dL1tI6IpgV8HShLrSSjxw%3D%3D&attredirects=0.png)

#**III.Tìm hiểu và cài đặt Apache làm Webserver**
- Web Server là máy chủ có dung lượng lớn, tốc độ cao, được dùng để lưu trữ thông tin như một ngân hàng dữ liệu, chứa những website đã được thiết kế cùng với những thông tin liên quan khác. (các mã Script, các chương trình, và các file Multimedia).

##**1.Apache là một phần mềm có nhiều tính năng mạnh và linh hoạt dùng để làm Web Server.**
- Hỗ trợ đầy đủ những giao thức HTTP trước đây như HTTP/1.1
- Có thể cấu hình và mở rộng với những module của công ty thứ ba.
- Cung cấp source code đầy đủ với license không hạn chế.
- Chạy trên nhiều hệ điều hành như Windows NT/9X, Netware 5.x, OS/2 và hầu hết các hệ điều hành Unix

##**2. Tính năng cơ bản**
- Máy chủ web Apache có thể được bổ sung bằng một chương trình cho phép tích hợp chức năng tìm kiếm với một website. Các đơn vị phần mềm khác nhau có sẵn với hệ thống tìm kiếm HTDig cho phép đánh chỉ số toàn bộ website. Trình Iprogram sử dụng robot để tạo ta một chỉ số tìm kiếm mà chỉ số này có thể được duyệt bằng một CGI script phù hợp. 
- Các chức năng cơ bản của phần mềm này được mô tả ở phần dưới: 
 - Tạo ra một chỉ số của máy tìm kiếm (cho 1 hoặc nhiều website và/hoặc các phần của một webiste).
 - Sử dụng bộ lọc để hạn chế chức năng đánh chỉ số. Tiêu chuẩn lọc có thể là dạng tệp và URL đặc biệt.

- Các chương trình bổ sung bên ngoài có thể được sử dụng để đánh chỉ số các định dạng tệp (PDF, DOC,…).
- Các lựa chọn yêu cầu số tồn tại và các thuật toán tìm kiếm khác nhau có thể được sử dụng (các từ, phần của từ, các từ đồng nghĩa…).
- Trang tìm kiếm và bản liệt kê tương ứng có thể được chỉnh bằng việc sử dụng các tệp mẫu template đơn giản.
- Các nguyên âm biến âm sắc trong chuỗi tìm kiếm được hỗ trợ
- Robot hỗ trợ chuẩn cho việc "Loại trừ Robot" và "Xác thực WWW cơ bản" cho việc đánh chỉ số các nội dung được bảo vệ.

##**3. Cài đặt Apache**
– Update Ubuntu server: sudo apt-get update
– Cài đặt Apache với câu lệnh: sudo apt-get install apache2
- Nó có hỏi Y/N thì cứ ấn Y rồi Enter.
- Sau khi cài đặt, hãy thử trên trình duyệt: http://localhost

![Cài đặt thành công Apache](https://assets.digitalocean.com/articles/lamp_1404/default_apache.png)

Sử dụng những lệnh sau để khởi động, kích hoạt và ngừng hoạt động của Apache:
 + sudo /etc/init.d/apache2 start #start apache
 + sudo /etc/init.d/apache2 stop #stop apache
 + sudo /etc/init.d/apache2 restart #restart apache

- Không muốn Apache tự khởi động cùng hệ thống, gõ lệnh sau: sudo update-rc.d -f apache2 remove
- Muốn Apache tự khởi động cùng hệ thống, gõ lệnh sau: sudo update-rc.d apache2 defaults

###**3.1) Cấu trúc thư mục cấu hình Apache trên Ubuntu**
- Mặc định trên Ubuntu, thư mục chứa các thiết lập của Apache sẽ nằm trong thư mục /etc/apache2. Trong thư mục đó, nó có một số thư mục và file cấu hình như sau:
	conf-available/ – Thư mục này sẽ chứa các file thiết lập cấu hình sẵn của Apache trên Ubuntu, nhưng các thiết lập trong đây sẽ chưa được áp dụng vì Ubuntu không load thiết lập cấu hình trong thư mục này.
-	conf-enabled/ – Thư mục chứa các file thiết lập cấu hình của Apache trên Ubuntu đang được bật. Hãy hiểu là nếu thư mục này có một liên kết tượng trưng (symlink) qua một file module nào đó bên thư mục conf-available thì nó sẽ được bật.
-	mods-available/ – Thư mục chứa các file từng module của Apache trên Ubuntu nhưng chưa được bật.
-	mods-enabled/ – Thư mục chứa các file từng module của Apache trên Ubuntu đang được bật.
-	site-available/ – Thư mục chứa file cấu hình VirtualHost của Apache trên Ubuntu nhưng chưa được bật.
-	site-enabled/ – Thư mục chứa file cấu hình VirtualHost của Apache trên Ubuntu đang được bật.
-	apache2.conf – File cấu hình Apache trên Ubuntu.
-	envvars – File thiết lập các biến với giá trị sẵn để sử dụng trong các file cấu hình.
-	magic – File thiết lập của module mod_mime_magic trên Apache.
-	ports.conf – File cấu hình cổng mạng của Apache (mặc định là port 80).

###**3.2: Thư mục gốc chứa dữ liệu website của Apache trên Ubuntu**
- Mặc định, Apache trên Ubuntu sẽ sử dụng thư mục /var/www/html để chứa dữ liệu website gốc (load bằng IP hoặc hostname). Khi bạn vào đây sẽ thấy một file index.html, đó chính là file giao diện chào mừng mà bạn đã thấy ở trên.

##**IV.Thiết lập card mạng ảo trong Ubuntu**

###**1. Cấu hình bằng dòng lệnh**
- eth0 NIC IP 192.168.1.5
- eth0:0 first NIC alias: 192.168.1.6

 + Set eth0:0 bằng dòng lệnh với quyền user root
- Lệnh : # ifconfig eth0:0 192.168.1.6 up

- Lệnh: 
 + # vi /etc/network/interfaces
 + auto eth0:1
 + iface eth0:1 inet static
 + name Ethernet alias LAN card
 + address 192.168.1.6
 + netmask 255.255.255.0
 + broadcast 192.168.1.255
 + network 192.168.1.0

- Lưu lại và đóng lại file, sau đó restart lại network
 + Lệnh: # /etc/init.d/networking restart






