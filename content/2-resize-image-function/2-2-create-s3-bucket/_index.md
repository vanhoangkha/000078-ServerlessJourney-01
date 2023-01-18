---
title : "Create S3 bucket"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---
In this part, we will create two S3 buckets:
- Bucket **book-image-store**: to store uploaded image
- Bucket **book-image-resize-store**: to store iamge after resize
1. Open [Amazon S3 console](https://s3.console.aws.amazon.com/s3/get-started?region=ap-southeast-2) 
![S3Console](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-1.png?featherlight=false&width=90pc)
2. Click **Create bucket**
![S3Console](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-2.png?featherlight=false&width=90pc)
3. Enter bucket name, **book-image-store**
- Choose the region closest to you.
![CreateBucket](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-3.png?featherlight=false&width=90pc)
4. Uncheck access block - **Block all public access** 
- Check the box - **I acknowledge that the current settings might result in this bucket and the objects within becoming public**
![CreateBucket](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-4.png?featherlight=false&width=90pc)
5. Click **Create bucket**
![CreateBucket](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-5.png?featherlight=false&width=90pc)
6. To create bucket - **book-image-resize-store**, repeat steps 1 to 5.
7. After creating the two buckets, we add the trigger for the lambda function created earlier
- Click **Add Trigger**
![AddTrigger](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-6.png?featherlight=false&width=90pc)
8. Enter **S3** and select **S3** service
![AddTrigger](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-7.png?featherlight=false&width=90pc)
9. Select bucket that trigger lambda, **book-image-store**
- Select **All object create events** for **Event type**
- Check the box - **I acknowledge that using....** as shown below
- Click **Add**
![AddTrigger](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-8.png?featherlight=false&width=90pc)
10. Check result after add trigger for Lambda function
![Trigger](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-9.png?featherlight=false&width=90pc)