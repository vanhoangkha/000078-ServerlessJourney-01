---
title : "Test Lambda function operation"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---
1. Navigate to S3 bucket: **book-image-store**
- Click **Upload**

![S3Bucket](/images/2-4-test-lambda-function/2-4-test-lambda-function-1.png?featherlight=false&width=90pc)

2. Click **Add files**

![S3Bucket](/images/2-4-test-lambda-function/2-4-test-lambda-function-2.png?featherlight=false&width=90pc)

3. Select image to upload, then click **Upload**

![S3Bucket](/images/2-4-test-lambda-function/2-4-test-lambda-function-3.png?featherlight=false&width=90pc)

4. Wait for the image to be uploaded successfully, then click **Close**

![S3Bucket](/images/2-4-test-lambda-function/2-4-test-lambda-function-4.png?featherlight=false&width=90pc)

5. Wait for the Lambda function running, then check if the image has been deleted or not

![S3Bucket](/images/2-4-test-lambda-function/2-4-test-lambda-function-5.png?featherlight=false&width=90pc)

6. Navigate to other bucket - **book-image-resize-store**
- Click to image file

![S3Bucket](/images/2-4-test-lambda-function/2-4-test-lambda-function-6.png?featherlight=false&width=90pc)

7. Click **Object URL** to download image

![S3Bucket](/images/2-4-test-lambda-function/2-4-test-lambda-function-7.png?featherlight=false&width=90pc)

8. But error occurs - **Access Denied**.

![S3Bucket](/images/2-4-test-lambda-function/2-4-test-lambda-function-8.png?featherlight=false&width=90pc)

9. To download image, need add policy for bucket to allow public access.
- Back to bucket, select **Permission**
- Click **Edit** in **Bucket policy**

![S3Bucket](/images/2-4-test-lambda-function/2-4-test-lambda-function-9.png?featherlight=false&width=90pc)

- Copy the below json data into **Policy**
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::book-image-resize-store/*"
        }
    ]
}
```
- Click **Save changes**

![S3Bucket](/images/2-4-test-lambda-function/2-4-test-lambda-function-10.png?featherlight=false&width=90pc)

11. Then, repeat steps 6 and 7 to download image to local to download an image to your device to compare it with the one you've already uploaded. So Lambda resizes function is working properly.