---
title : "Tạo Instance Profile"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

### Tạo Instance Profile

Trong bước này chúng ta sẽ tiến hành tạo Instance Profile. **Instance Profile** cho phép EC2 instance của bạn truy cập vào các tài nguyên AWS khác như S3, RDS, hoặc DynamoDB.

1. Truy cập vào [giao diện quản trị dịch vụ IAM](https://console.aws.amazon.com/iamv2/)
2. Ở thanh điều hướng bên trái, click  **Roles**.  

![role](/images/2.prerequisite/006-.png)

3. Click **Create role**.  

![role1](/images/2.prerequisite/007-.png)

4. Click **AWS service** và chọn Service là **EC2**. 
  + Click **Next**.  

![role1](/images/2.prerequisite/008-.png)

5. Trong ô Search, điền **AmazonS3FullAccess** và ấn phím Enter để tìm kiếm policy này.
  + Click chọn policy **AmazonS3FullAccess**.
  + Click **Next**

![createpolicy](/images/2.prerequisite/009-.png)

6. Đặt tên cho Role là **ElasticBeanstalk-EC2-Role** ở Role Name  
  + Click **Create Role** \.

![namerole](/images/2.prerequisite/010-.png)
![namerole](/images/2.prerequisite/011-.png)


Vậy các bước chuẩn bị đã xong, chúng ta tiến hàng tạo RDS cho dự án Spring Boot.