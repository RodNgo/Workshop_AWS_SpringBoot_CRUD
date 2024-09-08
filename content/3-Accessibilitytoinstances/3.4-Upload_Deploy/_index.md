---
title : "Upload Project to AWS"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 3.4. </b> "
---

1. Access the [Elastic Beanstalk management console](https://ap-southeast-2.console.aws.amazon.com/elasticbeanstalk/home?region=ap-southeast-2#/environments). Select **Upload and deploy**.
   ![Upload Project to AWS](/images/3.connect/026.png)
2. Choose the .war file from the path where you packaged your project and give it a version name. Click **Deploy**. Wait a few minutes for the system to upload the .war file to AWS.
   ![Upload Project to AWS](/images/3.connect/027.png)

When the screen looks like this, your Spring Boot project has been successfully deployed to AWS.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/028.png)
