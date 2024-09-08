---
title: "Create RDS"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

1. Go to the [Elastic Beanstalk management console](https://ap-southeast-2.console.aws.amazon.com/elasticbeanstalk/home?region=ap-southeast-2#/applications).
2. Click **Create application**.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/000-.png)
3. Name the application **CRUD_SpringBoot_Exercise**.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/001.png)
4. Choose **Tomcat** as the platform (the system will suggest **Platform branch** and **Platform version**) and then click Next at the bottom of the screen.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/002-.png)
5. Click Next to continue to step 2. Select "Create and use new service role." Then choose the **EC2 Key Pair** and **EC2 instance profile** created in section 2. Click Next to proceed to step 3.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/007-.png)
6. In step 3 (Set up networking, database, and tags - optional), scroll down to the **Database** section, click **Enable database**, select the appropriate engine (in this case, PostgreSQL), and set up the username and password for the database server.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/003-.png)
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/004-.png)
7. Continue clicking **Next** until step 6, and then submit. You have now created a new application on Elastic Beanstalk.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/005-.png)
   
{{% notice note %}}
At the same time, a new environment will be created for the application. It will take some time for the environment to be fully set up and for the new application to be functional.
{{% /notice %}}

When the system displays the screen below, the application has been successfully created.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/008-.png)
   
{{% notice info %}}
On that screen, the **Creating RDS database name** is a string code, which will be the RDS name used to publicize the RDS in the next step.
{{% /notice %}}

1. Go to the [EC2 management console](https://console.aws.amazon.com/ec2/v2/home).
   + Click **Public Linux Instance**.
   + Click **Actions**.
   + Click **Security**.
   + Click **Modify IAM role**.
   
   ![Connect](/images/3.connect/001-connect.png)
   
2. On the Modify IAM role page:
   + Select **SSM-Role**.
   + Click **Save**.

{{% notice note %}}
Wait about 10 minutes before proceeding to the next step. During this time, the EC2 instance will automatically register with the Session Manager.
{{% /notice %}}

3. Go to the [AWS Systems Manager management console](https://console.aws.amazon.com/systems-manager/home).
   + Scroll down the left-hand menu.
   + Click **Session Manager**.
   + Click **Start Session**.

   ![Connect](/images/3.connect/002-connect.png)

4. Select **Public Linux Instance** and click **Start session** to access the instance.

   ![Connect](/images/3.connect/003-connect.png)

5. A terminal will appear in the browser. Check with the command `sudo tcpdump -nn port 22` and `sudo tcpdump`. You will see no SSH traffic, only HTTPS traffic.

   ![Connect](/images/3.connect/004-connect.png)

{{% notice note %}}
By connecting to the public instance without opening the SSH port 22, security is enhanced by preventing attacks on the SSH port.\
One drawback of this approach is that you need to open the Security Group outbound on port 443 to the internet. Since this is a public instance, it might not be an issue, but if you want extra security, you can block port 443 to the internet and still use the Session Manager. We'll go through this approach in the private instance section below.
{{% /notice %}}

You can terminate the session to disconnect before moving on to the next step.
