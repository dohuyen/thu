#**II.Các chế độ card mạng trong VMWare WorkStation**
**Switch ảo** (*Virtual Switch*) cũng giống như switch vật lý, một Virtual Switch kết nối các thành phần mạng ảo lại với nhau. Những  switch ảo hay còn gọi là mạng ảo, chúng có tên là VMnet0, VMnet1, VMnet2… một số switch ảo được gắn vào mạng một cách mặc định. (Ta có thể thêm, bớt, chỉnh các option của VMnet bằng cách vào menu Edit -> Virtual Network Editor...).
Khi ta tạo các VMnet thì trên máy thật của ta sẽ tạo ra những card mạng ảo tương ứng, riêng VMnet0 kết nối trực tiếp với card mạng vật lý nên không tạo ra card VMnet.
**DHCP server ảo DHCP**(*Dynamic Host Configuration*) server ảo cung cấp địa chỉ IP cho các máy ảo trong việc kết nối máy ảo vào các Switch ảo không có tính năng Bridged (VMnet0).
Nếu bạn muốn bỏ chế độ DHCP của VMnet nào, bạn chỉ cần bỏ dấu check tại Use local DHCP service to distribute IP address to VMs
**Card mạng ảo** Khi bạn tạo một máy ảo mới (New Virtual Machine wizard), card mạng ảo được tạo ra cho máy ảo. Những card mạng này hiển thị trên hệ điều hành máy ảo như là AMD PCNET PCI hay Intel Pro/1000 MT Server Adapter. Thêm bớt card mạng bạn nhấn vào nút Add... hoặc Remove... trong Virtual Machine Setting.
**Card mạng trên máy tính ảo**  Khi cài đặt, VMWare tạo ra ở máy thật 2 card mạng ảo.
 VMWare Virtual Ethernet Adapter for VMnet1.
 VMWare Virtual Ethernet Adapter for Vmnet8.
 2 card mạng này có thể đựơc sử dụng để máy thật giao tiếp với các máy tính ảo.
 Khi “gắn” một card mạng vào một máy ảo, card mạng này có thể được chọn 1 trong 3 loại sau :
 - **Bridge :**
Card Bridge trên máy ảo chỉ có thể giao tiếp với card mạng thật trên máy thật.Nó  có thể giao tiếp với mạng vật lý mà máy tính thật đang kết nối.
- **Host-only :**
Card Host-only chỉ có thể giao tiếp với card mạng ảo VMnet1 trên máy thật; chỉ có thể giao tiếp với các card Host-only trên các máy ảo khác.
Card Host-only không thể giao tiếp với mạng vật lý mà máy tính thật đang kết nối.
- **NAT :**
Card NAT chỉ có thể giao tiếp với card mạng ảo VMnet8 trên máy thật; chỉ có thể giao tiếp với các card NAT trên các máy ảo khác.
Card NAT không thể giao tiếp với mạng vật lý mà máy tính thật đang kết nối. Tuy nhiên nhờ cơ chế NAT được tích hợp trong VMWare, máy tính ảo có thể gián tiếp liên lạc với mạng vật lý bên ngoài.
