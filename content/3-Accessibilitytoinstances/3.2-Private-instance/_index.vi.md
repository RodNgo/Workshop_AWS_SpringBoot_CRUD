---
title : "Public RDS"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---

Ở bước này chúng ta sẽ thiết lập RDS với quyền truy cập "Anywhere IPv4". Thiết lập RDS với quyền truy cập "Anywhere IPv4" (0.0.0.0/0) cho phép mọi địa chỉ IP có thể truy cập cơ sở dữ liệu của bạn từ Internet. Điều này hữu ích khi bạn cần kết nối từ bên ngoài AWS, như trong quá trình phát triển hoặc kiểm thử.

Tuy nhiên, nó tiềm ẩn nhiều rủi ro bảo mật, như tấn công brute force. Trong môi trường sản xuất, nên hạn chế quyền truy cập bằng cách chỉ cho phép IP cụ thể hoặc sử dụng VPN/SSH Tunnel để bảo vệ kết nối.

Các bước thực hiện:

1. Truy cập vào [giao diện quản trị của dịch vụ quản trị RDS](https://ap-southeast-2.console.aws.amazon.com/rds/home?region=ap-southeast-2#).
2. Ở thanh menu bên trái, click chọn **Database**.
 ![Public RDS](/images/3.connect/009-.png)
3. Trượt xuống mục **Security group rules**, chọn vào security group có dạng là **EC2 Sercurity Group - Inbound**.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/010-.png)
4. Tại màn hình **Security Groups**, click chọn vào Security Group duy nhất hiện trên màn hình. Chúng ta có thể kiểm tra nó có phải đúng RDS mà mình đã tạo hay không bằng cách nhìn vào **Security group name**, bỏ đi 3 chữ "rds" ở đầu, sau đó chính là **RDS name** của chúng ta đã tạo ở các bước trước.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/011-.png)
5. Ở màn hình hiện ra tiếp theo, chọn vào **Security group rule** duy nhất trên màn hình, chọn vào **Edit inbound rules**. 
![Elastic_Beanstalk_Home_Screen](/images/3.connect/012-.png)
6. Hệ thống hiện ra màn hình tùy chỉnh, click chọn **Delete** để xóa **Security group rule** ban đầu và click vào **Add rule** để thêm mới.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/013-.png)
7. Chọn Type là **PostgreSQL** và Source là **Anywhere IPv4**. Click chọn **Save Rules** để hoàn thành
![Elastic_Beanstalk_Home_Screen](/images/3.connect/014-.png)

Hệ thống hiện ra như sau thì đã public thành công RDS của chúng ta .
![Elastic_Beanstalk_Home_Screen](/images/3.connect/015-.png)

