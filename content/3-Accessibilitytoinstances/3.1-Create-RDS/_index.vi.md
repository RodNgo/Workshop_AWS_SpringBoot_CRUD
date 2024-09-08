---
title : "Tạo RDS"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---

1. Truy cập vào [giao diện quản trị của dịch vụ Elastic Beanstalk](https://ap-southeast-2.console.aws.amazon.com/elasticbeanstalk/home?region=ap-southeast-2#/applications).
2. Click chọn **Create application**.
 ![Elastic_Beanstalk_Home_Screen](/images/3.connect/000-.png)
3. Đặt tên cho Application là **CRUD_SpringBoot_Excercise**.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/001.png)
4. Chọn Platform **Tomcat** (hệ thống sẽ gợi ý cho 2 mục **Platform branch** và **Platform version**) rồi click vào Next ở cuối màn hình.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/002-.png)
5. Click Next để tiếp tục ở bước 2. Chọn vào mục "Create and use new service role". Tiếp theo ta chọn **EC2 Key Pair** và **EC2 instance profile** là những **EC2 Key Pair** và **Instance Profile** chúng ta đã tạo ở mục 2. Click Next để tiếp tục qua bước 3.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/007-.png)
6. Tại bước 3 (Set up networking, database and tags - optional), kéo xuống phần **Database**, click vào Enable database, chọn engine phù hợp (ở đây mình sẽ chọn postgres), cài đặt tài khoản và mật khẩu của user trên server database của chúng ta.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/003-.png)
![Elastic_Beanstalk_Home_Screen](/images/3.connect/004-.png)
7. Click **Next** tiếp tục cho tới bước 6 và submit, chúng ta đã tạo xong 1 application mới ở Elastic Beanstalk.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/005-.png)
{{% notice note %}}
Đồng thời cùng lúc 1 môi trường mới cũng được tạo cho application đó, sẽ mất 1 thời gian để môi trường có thể chạy xong và Application mới hoạt động được.
{{% /notice %}}
Hệ thống hiện ra như sau thì đã tạo thành công Application.
![Elastic_Beanstalk_Home_Screen](/images/3.connect/008-.png)
{{% notice info %}}
Tại màn hình đó, ở mục **Creating RDS database name** là một chuỗi mã, chúng ta sẽ dựa vào mã này - chính là tên của RDS để Public RDS trong bước sau
{{% /notice %}}

1. Truy cập vào [giao diện quản trị của dịch vụ EC2](https://console.aws.amazon.com/ec2/v2/home).
  + Click chọn **Public Linux Instance**.
  + Click **Actions**.
  + Click **Security**.
  + Click **Modify IAM role**.

![Connect](/images/3.connect/001-connect.png)

2. Tại trang Modify IAM role.
  + Click chọn **SSM-Role**.
  + Click **Save**.

{{% notice note %}}
Bạn sẽ cần chờ khoảng 10 phút trước khi thực hiện bước tiếp theo. Thời gian này EC2 instance của chúng ta sẽ tự động đăng ký với Session Manager.
{{% /notice %}}

3. Truy cập vào [giao diện quản trị của dịch vụ AWS Systems Manager](https://console.aws.amazon.com/systems-manager/home)
  + Kéo thanh trượt menu bên trái xuống dưới.
  + Click **Session Manager**.
  + Click **Start Session**.


![Connect](/images/3.connect/002-connect.png)


4. Sau đó chọn **Public Linux Instance** và click **Start session** để truy cập vào instance.

![Connect](/images/3.connect/003-connect.png)


5. Terminal sẽ xuất hiện trên trình duyệt. Kiểm tra với câu lệnh ``` sudo tcpdump -nn port 22 ``` và ```sudo tcpdump ``` chúng ta sẽ thấy không có traffic của SSH mà chỉ có traffic HTTPS.

![Connect](/images/3.connect/004-connect.png)

{{% notice note %}}
 Ở trên, chúng ta đã tạo  kết nối vào public instance mà không cần mở cổng SSH 22, giúp cho việc bảo mật tốt hơn, tránh mọi sự tấn công tới cổng SSH.\
Một nhược điểm của cách làm trên là ta phải mở Security Group outbound ở cổng 443 ra ngoài internet. Vì là public instance nên có thể sẽ không vấn đề gì nhưng nếu bạn muốn bảo mật hơn nữa, bạn có thể khoá cổng 443 ra ngoài internet mà vẫn sử dụng được Session Manager. Chúng ta sẽ đi qua cách làm này ở phần private instance dưới đây.
 {{% /notice %}}

 Bạn có thể terminate để kết thúc session đang kết nối trước khi qua bước tiếp theo.

