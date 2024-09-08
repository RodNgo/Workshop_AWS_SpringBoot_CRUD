---
title : "Upload Project lên AWS"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 3.3. </b> "
---

1. Truy cập vào [giao diện quản trị của dịch vụ quản trị Elastic Beanstalk](https://ap-southeast-2.console.aws.amazon.com/elasticbeanstalk/home?region=ap-southeast-2#/environments). Chọn **Upload and deploy**
![Public RDS](/images/3.connect/026.png)
2. Chọn file từ đường dẫn file .war ở Project chúng ta đã đóng gói và đặt tên cho version của nó. Nhấp vào **Deploy**. Đợi 1 vài phút để hệ thống tải file .war lên AWS
 ![Public RDS](/images/3.connect/027.png)
Hệ thống hiện ra như sau thì đã deploy thành công dự án Spring Boot của chúng ta lên AWS.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/028.png)
