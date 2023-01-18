---
title : "Tạo bảng trong AWS DynamoDB"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---
1. Mở bảng điều khiển [DynamoDB](https://ap-southeast-1.console.aws.amazon.com/dynamodbv2/home?region=ap-southeast-1#dashboard) 
![DynamoDBConsole](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-4.png?featherlight=false&width=90pc)
2. Ấn nút **Create table**
![CreateTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-5.png?featherlight=false&width=90pc)
3. Nhập tên cho bảng: **Books**
- Nhập parition key: **id**
![CreateTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-6.png?featherlight=false&width=90pc)
4. Kéo xuống phần **Table settings**, chọn **Customize settings**
- Sau đó, chọn **On-demand**
![CreateTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-7.png?featherlight=false&width=90pc)
5. Kéo xuống cuối trang, ấn nút **Create table**
![CreateTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-8.png?featherlight=false&width=90pc)
Vậy là bạn đã tạo xong bảng **Books**