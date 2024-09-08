---
title : "Chuẩn bị EC2 Key Pair"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

Trong bước này, chúng ta sẽ cần tạo một tạo một EC2 Key Pair.

**Key Pair** là một cặp khóa mã hóa được sử dụng để truy cập vào EC2 instance thông qua SSH.


1. Truy cập vào AWS Management Console.
2. Chuyển đến dịch vụ EC2.
![EC2 Key Pair](/images/2.prerequisite/000-.png)
3. Trong phần Network & Security, chọn "Key pairs".
 ![EC2 Key Pair](/images/2.prerequisite/001-.png)
4. Chọn Create Key Pair.
 ![EC2 Key Pair](/images/2.prerequisite/002-.png)
5. Đặt tên cho key pair của bạn và chọn định dạng. Chọn vào "Create key pair" để tạo EC2 Key Pair.
 
 {{% notice info %}}
Định dạng của key pair bạn chọn sẽ phụ thuộc vào hệ điều hành bạn sử dụng để kết nối với EC2 instance khi triển khai ứng dụng Spring Boot lên AWS.
{{% /notice %}}
 - .pem (Privacy Enhanced Mail): Định dạng .pem thường được sử dụng trên hệ điều hành Linux và macOS. Các hệ điều hành này hỗ trợ việc sử dụng tệp .pem trực tiếp để kết nối SSH với EC2 instance. Công cụ SSH tích hợp sẵn trên Linux và macOS sẽ sử dụng tệp .pem để xác thực.

 - .ppk (PuTTY Private Key): Định dạng .ppk được sử dụng trên hệ điều hành Windows khi bạn sử dụng PuTTY (một trình SSH client phổ biến trên Windows). PuTTY không hỗ trợ tệp .pem trực tiếp, vì vậy bạn sẽ cần chuyển đổi tệp .pem thành .ppk bằng công cụ PuTTYgen

![EC2 Key Pair](/images/2.prerequisite/003-.png)
6. Tải key pair xuống máy tính của bạn. Bạn sẽ cần file này để truy cập vào EC2 instance.

![EC2 Key Pair](/images/2.prerequisite/004-.png)

![EC2 Key Pair](/images/2.prerequisite/005-.png)
