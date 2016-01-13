
![Cấu trúc gói tin TCP](https://2466b9f4-a-62cb3a1a-s-sites.googlegroups.com/site/lexuandin/home/hhhhhhh.png?attachauth=ANoY7cqUORJMnJlfmq_UOidhurrNimAD3KNDazIfpijXXODeXsf2cAvAPgJ926IO_OiD8yAdRbFg5ApnJGHppQIIjCnTLLBD5-VzNcLNe7Q6KXpbdqWGwrhnScZbekZuj5x1cEdFSUlT_Eghpm3t425DNgimsuUxRHMyQMY_iVbYjfDIdDIuTQWZG4HDfu9sgxY1bq32FBeJ8dL1tI6IpgV8HShLrSSjxw%3D%3D&attredirects=0.png)

#**I.Cách cài đặt phần mềm trên các distro khác nhau**

##**Biên dịch phần mềm**
- Phương pháp này **không phụ thuộc bạn dùng distro nào miễn là dùng Linux** là đều có thể dùng. Bước đầu tiên khi muốn thực hiện phương pháp cài đặt này là bạn phải có file source của nó(có định dạng thường là file nén tag.gz. tar.bz2,..). Sau khi down file source về bạn tiến hành giải nén nó ra, sau đó vào trong thư mục giải nén thực hiện quá trình đầu tiên là check thư viện và các config file. biên dịch phần mềm cần phải đầy đủ thư viện thì mới có thể biên dịch được. Nó không thể tự động tìm các gói phụ thuộc để cài đặt . 
- Biên dịch phần mềm làm giảm thiểu rủi ro một cách tối ưu nhất có thể cho hệ thống phát sinh từ những thành phần hay module trong phần mềm. Bạn có thể tùy chỉnh cài đặt những thành phần nào vào hệ thống ở bước đầu tiên.
- Ngoài ra, sử dụng phương pháp này bạn có thể tối ưu hóa tài nguyên hệ thống . Đối với kiến thức trong tương lai, biên dịch có thể cho bạn những kiến thức cơ bản đầu tiên về biên dịch kernel trên Linux và đích cuối cùng chính là tự mình biên dịch một distro linux cho riêng mình.

###**Bên dịch phần mềm httpd:**
- **Bước 1:** Tải httpd-2.4.10.tar.bz2
 
- **Bước 2:** Giải nén tập tin
 + #unzip                  để giải nén                       name_package.zip
 + #tar -xvzf              để giải nén                       name_package.tar.gz
 + #tar -jvxf              để giải nén                       name_package.tar.bz2
 + #tar -x                 để giải nén                       name_package.tgz
 
- **Bước 3:** Tạo thư mục để cài phần mềm
 + Tạo thư mục httpd trong thư mục /usr/local/
 + Sử dụng lệnh #ll để kiểm tra thư mục vừa tạo
 
- **Bước 4:** Vào thư mục vừa giải nén để chuẩn bị biên dịch
 + [root@localhost ~]# cd httpd-2.4.10
- Đọc file README hoặc INSTALL để xem hướng dẫn cài đặt.
 + [root@localhost httpd-2.4.10]# vi README
 + [root@localhost httpd-2.4.10]# vi INSTALL

- **Bước 5:** Cấu hình cho gói phần mềm (Bước này xảy ra lỗi nhiều nhất)
 + [root@localhost httpd-2.4.10]# ./configure –prefix=/usr/local/httpd/ –with-included-apr
 + #–prefix là nơi sẽ cài phần mềm vào giống như chọn đường dẫn để cài phần mềm trong windows.
 + #–with-included-apr: trong tập tin INSTALL có hướng dẫn là tải apr và apr-util rồi copy vào /httpd-2.4.10/srclib/
 
- **Bước 6:** Biên dịch cho gói phần mềm:
 + #make
 + [root@localhost httpd-2.4.10]# make

- **Bước 7:** Cài đặt gói phần mềm httpd vừa biên dịch:
 + #make install
 + [root@localhost httpd-2.4.10]# make install
- Khởi động dịch vụ httpd:
 + [root@localhost ~]# /usr/local/httpd/bin/apachectl start
+ Xong các bước trên các bạn cài phần mềm w3m để lướt web trên giao diện dòng lệnh:
+ [root@localhost ~]# yum install w3m 
+ [root@localhost ~]# w3m localhost





