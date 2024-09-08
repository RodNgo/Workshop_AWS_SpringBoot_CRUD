+++
title = "Cleanup Resources"
date = 2024
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

We will follow these steps to delete the resources created during this workshop.

#### Delete Elastic Beanstalk Application

1. Go to the [Elastic Beanstalk management console](https://ap-southeast-2.console.aws.amazon.com/elasticbeanstalk/home?region=ap-southeast-2#/applications).
  + Click on the **Application** tab.
  + Select the application you want to delete, **CRUD_SpringBoot_Exercise**.
  + Click on **Actions**.
  + Click on **Delete Application**.
![Clean](/images/4.clean/001-.png)

#### Delete EC2 Key Pair and EC2 Instance Profile

1. Go to the [EC2 Key Pair console](https://ap-southeast-2.console.aws.amazon.com/ec2/home?region=ap-southeast-2#KeyPairs:).
  + Select the key pair you want to delete, **EC2_RODNGO**.
  + Click on **Actions**.
  + Click on **Delete**.
![Clean](/images/4.clean/002-.png)

2. Go to the [IAM management console](https://us-east-1.console.aws.amazon.com/iam/home?region=ap-southeast-2#/home).
  + Click on **Roles**.
  + Select the roles you want to delete.
  + Click on **Delete**.
![Clean](/images/4.clean/003-.png)
