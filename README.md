#**I.Tìm hiểu các sử dụng VMWare WorkStation**

##**1. Cài đặt VMware Workstation trên Windowns**
- Đăng ký và download bản Free Trial VMware Workstation 9.0 
+Trong màn hình Welcome bạn bấm nút next.
+Trong màn hình Setup Type, bạn chọn Typical. 
+Trong màn hình Destination Folder, bạn chấp nhận vị trí cài đặt mặc định và bấm nút Next.
+Trong màn hình Software Updates, bạn bấm Next.
+Trong màn hình User Experience Improvement Program, bạn nhấn nút Next 
+Trong màn hình Shortcuts, bạn chọn vị trí tạo các shortcut cho VMware Workstation, sau đó nhấn Next:  
+Tại màn hình Ready to Perform the Requested Operations, bạn nhấn Continue. Sau bước này VMware Workstation sẽ được cài đặt. 
+Tại màn hình Enter License Key, bạn nhập Key được cấp qua Email khi bạn đăng ký tải VMware Workstation, sau đó nhấn Enter. 
+Nhấn nút Finish ở màn hình Setup Wizard Complete, sau đó khởi động lại máy để hoàn tất quá trình cài đặt.

##**2. Tạo máy ảo**
Sau khi mở phần mềm Vmware (phiên bản Vmware 9), bạn vào File, chọn New Virtual Machine.          
- Sau đó sẽ xuất hiện 1 hộp thoại: 
+ Mặc định của phần mềm là Typical: bạn sẽ tạo được ổ đĩa ảo với cái bước rất dễ. 
+ Còn ở phần Custom thì bạn có thể tạo ổ ảo với những gì mà mình thích.            
Bạn nhấn Next. Tiếp theo bảng hộp thoại xuất hiện nhằm hỏi bạn muốn tạo phần mềm gì để chạy trên hệ thống ổ đĩa ảo của mình và đường dẫn để cài đặt phần mềm đó. Ở đây chúng ta có 3 sự lựa chọn: Install from disc: bạn sẽ cài đặt phần mềm từ đĩa CD Installer disc image file (.iso): bạn sẽ cài đặt phần mềm có đuôi là .iso. File iso hiểu theo một cách thông thường thì đó là 1 dạng file nén. Có thể dùng được bằng cách giải nén hoặc chạy được trên ổ đĩa ảo. Mục còn lại thì Vmware sẽ tự động tạo 1 ổ đĩa trống và chờ bạn cài đặt phần mềm tùy thích để chạy.      

Ở đây tôi chọn mục 2 vì đã có sẵn file iso. Sau đó bạn nhấn thẻ Browse để chọn file iso cần chạy (phần mềm đó là Win8 bản Beta). Sau đó nhấn Next.   
 
-Kế đến, một hộp thoại khác sẽ xuất hiện giúp bạn chọn Hệ điều hành. Ở đây tôi chọn hệ điều hành Microsoft và phiên bản là Win8. Sau đó nhấn Next.              
 
-Một hộp thoại khác xuất hiện nhằm hỏi bạn về 2 vấn đề: Virtual Machine Name: tên của ổ đĩa ảo. Các bạn có thể đặt tên tùy theo ý thích của mình. Location: nơi sẽ lưu ổ đĩa. Vì bước tiếp theo bạn phải chọn dung lượng của ổ đĩa ảo. Nên tôi khuyến cáo các bạn nên chọn ổ đĩa nào dung lượng còn nhiều và không ảnh hưởng đến hoạt động của máy chủ thật.  Sau đó bạn nhấn Next.          
-Kế đến, Vmware sẽ hỏi bạn về dung lượng của ổ đĩa cứng trên máy ảo mà bạn muốn chia sẻ từ ổ cứng của máy chủ thật. Vmware sẽ tự động mặc định dung lượng tối thiểu là 60.0Gb, bạn có thể tùy chỉnh dung lượng theo ý thích của mình. Sau khi tùy chỉnh dung lượng tùy thích, bạn nhấn Next.             

-Bước cuối cùng, bạn sẽ điều chỉnh những thông số như: RAM, CPU, Display, Sound Card,… theo ý muốn của mình. Khuyến cáo: tạo vừa phải, đúng với các thông số của máy chủ thật của mình.             
Để tùy chỉnh, bạn nhấn thẻ Customize Hardware.             

Sau khi đã hoàn thành hết những gì theo ý muốn của mình trong bảng tùy chỉnh, bạn nhấn Close và nhấn Finish để hoàn thành việc tạo ổ đĩa ảo của mình.             
Sau khi nhấn Finish, cửa sổ Vmware của bạn sẽ như thế này.            
 
Để có thể chạy được ổ đĩa ảo vừa tạo, bạn nhấn vào nút Power on this virtual machine (có biểu tượng là một hình tam giác màu xanh lá cây) Nếu bạn chưa hài lòng với những thông số kĩ thuật mà mình vừa tạo thì nhấn vào Edit virtual machine setting để thiết lập lại những gì mong muốn.
