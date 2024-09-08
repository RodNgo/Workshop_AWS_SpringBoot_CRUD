---
title : "Gán link RDS vào Project"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3.3. </b> "
---

Ở bước này chúng ta sẽ thiết lập RDS với quyền truy cập "Anywhere IPv4". Thiết lập RDS với quyền truy cập "Anywhere IPv4" (0.0.0.0/0) cho phép mọi địa chỉ IP có thể truy cập cơ sở dữ liệu của bạn từ Internet. Điều này hữu ích khi bạn cần kết nối từ bên ngoài AWS, như trong quá trình phát triển hoặc kiểm thử.

Tuy nhiên, nó tiềm ẩn nhiều rủi ro bảo mật, như tấn công brute force. Trong môi trường sản xuất, nên hạn chế quyền truy cập bằng cách chỉ cho phép IP cụ thể hoặc sử dụng VPN/SSH Tunnel để bảo vệ kết nối.

Các bước thực hiện:

1. Truy cập vào [giao diện quản trị của dịch vụ quản trị Elastic Beanstalk](https://ap-southeast-2.console.aws.amazon.com/elasticbeanstalk/home?region=ap-southeast-2#/environments).
2. Ở thanh menu bên trái, click chọn vào môi trường đã được tạo có tên là **CRUD_SpringBoot_Excercise**. Chọn vào mục **Configuration**
 ![Public RDS](/images/3.connect/016-.png)
3. Trượt xuống mục **Networking and database**, chọn vào Edit.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/017-.png)
4. Tiếp theo trượt xuống mục **Database**, chúng ta sẽ thấy endpoint của database chúng ta đã tạo, copy đường dẫn đó.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/018-.png)
5. Truy cập vào Project Spring Boot của chúng ta đã chuẩn bị, vào phần **application.properties** của project, thay đổi **localhost:5432** thành đường dẫn endpoint chúng ta đã copy ở bước trước.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/019-.png)
Tại bước này, chúng ta đã xong gán link RDS cho project nhưng chúng ta sẽ thực hiện thêm 1 số thao tác để hoàn chỉnh.
6. Truy cập vào pgAdmin4. pgAdmin4 là một công cụ quản lý cơ sở dữ liệu PostgreSQL với giao diện đồ họa. Nó giúp quản lý cơ sở dữ liệu, bảng, và các đối tượng khác dễ dàng, đồng thời cung cấp trình quản lý truy vấn để chạy các lệnh SQL một cách trực quan. Tại thanh menu bên trái, click chuột phải vào **Server**, chọn **Register**, **Server**. Nhập tên của Server, chuyển qua tab **Connection**, thêm hostname là endpoint database của chúng ta đã copy, nhập username và password đã cài đặt vào, nhấn **Save** để hệ thống kết nối vào user của database server của chúng ta.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/020-.png)
![Elastic_Beanstalk_Home_Screen](/images/3.connect/021-.png)
7. Click phải chuột vào Server vừa kết nối, chọn **Create**, **Database** vào tạo 1 database có tên **excercise** đúng với database đã cấu hình ở project, nhấp **Save** để lưu database.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/022-.png)
![Elastic_Beanstalk_Home_Screen](/images/3.connect/023-.png)
8. Quay trở lại project, trước khi khởi chạy project để khởi tạo các table vào database chúng ta kết nối thì cần chỉnh spring.jpa.hibernate.ddl-auto=**update** thành spring.jpa.hibernate.ddl-auto=**create**. Chạy Project để hệ thống tạo các table.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/024.png)
9. Sau khi khởi chạy xong, chúng ta sẽ tiến hành nén file .war để có thể upload và deploy nó lên AWS. Tại thanh menu bên phải, nhấp vào biểu tượng logo của maeven, nhấp tiếp vào **Lifecycle**, sau khi màn hình sổ xuống, nháy đúp vào **package**, hệ thống sẽ tiến hành đóng gói Project thành file .war. Sau khi đóng gói thành công thì sẽ hiện màn hình như thế này cùng với đường dẫn tới file .war đã đóng gói.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/025.png)
