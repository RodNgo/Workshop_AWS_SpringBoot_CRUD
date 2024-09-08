---
title : "Link RDS to Project"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3.3. </b> "
---

In this step, we will configure RDS with "Anywhere IPv4" access. Setting RDS with "Anywhere IPv4" (0.0.0.0/0) allows any IP address to access your database from the internet. This is useful for connecting from outside AWS, such as during development or testing.

However, it poses significant security risks, such as brute force attacks. In a production environment, you should restrict access by allowing specific IPs only or use VPN/SSH Tunnel to secure the connection.

### Steps to Follow:

1. Access the [Elastic Beanstalk management console](https://ap-southeast-2.console.aws.amazon.com/elasticbeanstalk/home?region=ap-southeast-2#/environments).
2. On the left menu, select the environment named **CRUD_SpringBoot_Excercise** and click on **Configuration**.
   ![Public RDS](/images/3.connect/016-.png)
3. Scroll down to the **Networking and database** section and click **Edit**.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/017-.png)
4. Scroll down to the **Database** section, where you will see the endpoint of the database you created. Copy this endpoint.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/018-.png)
5. Go to your Spring Boot project, open the `application.properties` file, and replace `localhost:5432` with the endpoint you copied.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/019-.png)

At this point, you have linked the RDS endpoint to your project, but additional steps are needed to complete the setup.

6. Access pgAdmin4. pgAdmin4 is a PostgreSQL database management tool with a graphical interface. It helps manage databases, tables, and other objects easily and provides a query manager to run SQL commands visually. In the left menu, right-click on **Server**, select **Register**, then **Server**. Enter the server name, switch to the **Connection** tab, add the hostname as the endpoint you copied, enter the username and password, then click **Save** to connect to the database server.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/020-.png)
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/021-.png)
7. Right-click on the connected server, select **Create**, then **Database** to create a database named **excercise**, which matches the database configured in your project. Click **Save** to create the database.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/022-.png)
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/023-.png)
8. Return to your project. Before running the project to initialize tables in the database, change `spring.jpa.hibernate.ddl-auto=**update**` to `spring.jpa.hibernate.ddl-auto=**create**`. Run the project to create the tables.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/024.png)
9. After the project runs successfully, package the project into a .war file for upload and deployment to AWS. In the right menu, click on the Maven logo, then click on **Lifecycle**. When the menu expands, double-click **package** to package the project into a .war file. After packaging is complete, you will see a screen with the path to the packaged .war file.
   ![Elastic_Beanstalk_Home_Screen](/images/3.connect/025.png)
