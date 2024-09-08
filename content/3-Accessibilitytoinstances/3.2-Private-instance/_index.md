---
title : "Public RDS"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---

In this step, we will configure RDS with "Anywhere IPv4" access. Setting up RDS with "Anywhere IPv4" access (0.0.0.0/0) allows any IP address to access your database from the internet. This is useful when you need to connect from outside AWS, such as during development or testing.

However, this setup comes with security risks, such as brute force attacks. In a production environment, it is recommended to limit access by allowing only specific IPs or using a VPN/SSH Tunnel to secure the connection.

### Steps:

1. Go to the [RDS Management Console](https://ap-southeast-2.console.aws.amazon.com/rds/home?region=ap-southeast-2#).
2. In the left-hand menu, click **Databases**.
   ![Public RDS](/images/3.connect/009-.png)
3. Scroll down to the **Security group rules** section and select the security group labeled as **EC2 Security Group - Inbound**.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/010-.png)
4. On the **Security Groups** screen, click the only Security Group displayed. You can verify that this is the correct RDS instance by checking the **Security group name**. Remove the first three letters "rds", and the remaining string will be the **RDS name** created in previous steps.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/011-.png)
5. On the next screen, select the only **Security group rule** displayed and click **Edit inbound rules**.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/012-.png)
6. On the customization screen that appears, click **Delete** to remove the existing **Security group rule** and click **Add rule** to create a new one.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/013-.png)
7. Set the Type to **PostgreSQL** and the Source to **Anywhere IPv4**. Click **Save Rules** to complete the configuration.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/014-.png)

Once the system displays the following screen, your RDS instance has been successfully made public.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/015-.png)
