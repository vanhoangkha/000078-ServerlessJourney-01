---
title : "Create Policy for Lambda function"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---
In this part, we will create a Policy that grants the Lambda function permission to get, write, and delete objects in the S3 bucket.
1. Navigate to console of created in step 1 Lambda function.
- In tab **Configuration**, click **Permissions**
- Click on the role being executed by the function
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-1.png?featherlight=false&width=90pc)
2. Click **Add permissions**
- Select **Attach policies**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-2.png?featherlight=false&width=90pc)
3. Click **Create policy**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-3.png?featherlight=false&width=90pc)
4. Click **Choose a service**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-4.png?featherlight=false&width=90pc)
5. Enter **S3**, then select **S3**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-5.png?featherlight=false&width=90pc)
6. Click **Action**, expand **Read** in **Access level**
- Check to **GetObject** permission
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-6.png?featherlight=false&width=90pc)
7. Then, expand **Write**
- Check to **DeleteObject** permission
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-7.png?featherlight=false&width=90pc)
8. In **Resource**, click **Add ARN** to specify resources.
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-8.png?featherlight=false&width=90pc)
9. Enter bucket name: **book-image-store**
- Check to **Any** to allow permissions for all objects in the bucket
- Click **Add**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-9.png?featherlight=false&width=90pc)
10. Click **Add additional permissions**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-10.png?featherlight=false&width=90pc)
11. Repeat steps 4 and 5
- Then, expand **Write**, check to **PutObject** permission
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-11.png?featherlight=false&width=90pc)
12. Repeat steps 8 and 9 with bucket name is **book-image-resize-store**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-12.png?featherlight=false&width=90pc)
13. Click **Next tags**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-13.png?featherlight=false&width=90pc)
14. Click **Next review**
15. Enter policy name, such as: **LambdaResizeImageS3Policy**
- Review policy information and click **Create policy**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-14.png?featherlight=false&width=90pc)
16. Back to adding policy for Lambda function screen, enter the name of the policy we just created.
- Check to the policy: **LambdaResizeImageS3Policy**
- Click **Attach policies**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-15.png?featherlight=false&width=90pc)
We have finished granting the Lambda function read, write, and delete permissions from the S3 bucket. The next step is to test the Lambda function working when uploading an image.