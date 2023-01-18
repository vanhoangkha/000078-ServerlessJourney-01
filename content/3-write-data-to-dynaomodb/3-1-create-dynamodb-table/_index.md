---
title : "Create DynamoDB table"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---
1. Open [DynamoDB console](https://ap-southeast-1.console.aws.amazon.com/dynamodbv2/home?region=ap-southeast-1#dashboard) 
![DynamoDBConsole](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-4.png?featherlight=false&width=90pc)
2. Click **Create table**
![CreateTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-5.png?featherlight=false&width=90pc)
3. Enter table name: **Books**
- Enter parition key: **id**
![CreateTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-6.png?featherlight=false&width=90pc)
4. Scroll down to **Table settings** pattern, select **Customize settings**
- Then, select **On-demand**
![CreateTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-7.png?featherlight=false&width=90pc)
5. Scroll to the bottom, click **Create table**
![CreateTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-8.png?featherlight=false&width=90pc)
So you have created the **Books** table