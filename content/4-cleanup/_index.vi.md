+++
title = "Dọn dẹp tài nguyên  "
date = 2024
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

Chúng ta sẽ tiến hành các bước sau để xóa các tài nguyên chúng ta đã tạo trong workshop này.

#### Xóa Elastic Beanstalk Application

1. Truy cập [giao diện quản trị dịch vụ Elastic Beanstalk](https://ap-southeast-2.console.aws.amazon.com/elasticbeanstalk/home?region=ap-southeast-2#/applications).
  + Click tab **Aplication**.
  + Click chọn vào Application cần xóa **CRUD_SpringBoot_Exercise**.
  + Click chọn **Action**
  + click chọn **Delete Action**
![Clean](/images/4.clean/001-.png)

#### Xóa EC2 Key Pair và EC2 Instance Profile

1. Truy cập [giao diện EC2 Key Pair](https://ap-southeast-2.console.aws.amazon.com/ec2/home?region=ap-southeast-2#KeyPairs:).
  + Click chọn vào Key Pair cần xóa **EC2_RODNGO**.
  + Click chọn **Action**
  + click chọn **Delete**
![Clean](/images/4.clean/002-.png)

2. Truy cập [giao diện quản trị dịch vụ IAM](https://us-east-1.console.aws.amazon.com/iam/home?region=ap-southeast-2#/home)
  + Click **Roles**.
  + Click chọn vào các Roles cần xóa.
  + Click **Delete**.
![Clean](/images/4.clean/003-.png)




