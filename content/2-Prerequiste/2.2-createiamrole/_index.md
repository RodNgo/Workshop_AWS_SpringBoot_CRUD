---
title: "Create Instance Profile"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

### Create Instance Profile

In this step, we will create an Instance Profile. An **Instance Profile** allows your EC2 instance to access other AWS resources such as S3, RDS, or DynamoDB.

1. Go to the [IAM service management console](https://console.aws.amazon.com/iamv2/)
2. On the left-hand navigation pane, click **Roles**.

   ![role](/images/2.prerequisite/006-.png)

3. Click **Create role**.

   ![role1](/images/2.prerequisite/007-.png)

4. Click **AWS service** and select **EC2** as the service. 
   + Click **Next**.

   ![role1](/images/2.prerequisite/008-.png)

5. In the Search box, enter **AmazonS3FullAccess** and press Enter to find this policy.
   + Select the **AmazonS3FullAccess** policy.
   + Click **Next**.

   ![createpolicy](/images/2.prerequisite/009-.png)

6. Name the Role **ElasticBeanstalk-EC2-Role** in the Role Name field.
   + Click **Create Role**.

   ![namerole](/images/2.prerequisite/010-.png)
   ![namerole](/images/2.prerequisite/011-.png)

The preparation steps are now complete. Next, we will create the RDS for the Spring Boot project.
