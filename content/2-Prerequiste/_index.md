---
title: "Preparation Steps"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

{{% notice info %}}
You need to have a working Spring Boot CRUD API project ready to deploy to AWS.
{{% /notice %}}

In this step, we need to create an **EC2 Key Pair** and **Instance Profile**. When deploying an application with Elastic Beanstalk, creating a key pair and an instance profile for EC2 is crucial for you to access and manage the created resources.

### Contents
  - [Prepare EC2 Key Pair](2.1-createec2/)
  - [Create Instance Profile](2.2-createiamrole/)