---
title: "Prepare EC2 Key Pair"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

In this step, we will need to create an EC2 Key Pair.

**Key Pair** is a pair of encryption keys used to access an EC2 instance via SSH.

1. Access the AWS Management Console.
2. Navigate to the EC2 service.
   ![EC2 Key Pair](/images/2.prerequisite/000-.png)
3. In the Network & Security section, select "Key pairs".
   ![EC2 Key Pair](/images/2.prerequisite/001-.png)
4. Select Create Key Pair.
   ![EC2 Key Pair](/images/2.prerequisite/002-.png)
5. Name your key pair and select a format. Click "Create key pair" to generate the EC2 Key Pair.
 
   {{% notice info %}}
   The format of the key pair you select will depend on the operating system you are using to connect to the EC2 instance when deploying your Spring Boot application to AWS.
   {{% /notice %}}

   - .pem (Privacy Enhanced Mail): The .pem format is typically used on Linux and macOS systems. These operating systems support using the .pem file directly to connect via SSH to an EC2 instance. The built-in SSH tool on Linux and macOS will use the .pem file for authentication.

   - .ppk (PuTTY Private Key): The .ppk format is used on Windows when using PuTTY (a popular SSH client on Windows). PuTTY does not support .pem files directly, so you will need to convert the .pem file to .ppk using the PuTTYgen tool.

   ![EC2 Key Pair](/images/2.prerequisite/003-.png)
6. Download the key pair to your computer. You will need this file to access the EC2 instance.

   ![EC2 Key Pair](/images/2.prerequisite/004-.png)

   ![EC2 Key Pair](/images/2.prerequisite/005-.png)
