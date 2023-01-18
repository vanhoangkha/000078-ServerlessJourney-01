---
title : "Create resize image Lambda function"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---
1. Open [AWS Lambda console](https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/discover) 
![LambdaConsole](/images/2-1-create-lambda-function/2-1-create-lambda-function-1.png?featherlight=false&width=90pc)
2. Click **Create function** button
![CreateFunction](/images/2-1-create-lambda-function/2-1-create-lambda-function-2.png?featherlight=false&width=90pc)
3. Enter function name, such as: **resize-image**
- Choose **Node.js 16.x** for **Runtime**
- Click **Create function** button
![CreateFunction](/images/2-1-create-lambda-function/2-1-create-lambda-function-3.png?featherlight=false&width=90pc)
4. Download source code file to your device

{{%attachments title="Source code" pattern=".*\.(zip)$"/%}}

5. Click **Upload from** button
- Choose **.zip file**
![UploadSource](/images/2-1-create-lambda-function/2-1-create-lambda-function-4.png?featherlight=false&width=90pc)
6. Click **Upload** button
- Then select the downloaded source code file
- Click **Save**
![UploadSource](/images/2-1-create-lambda-function/2-1-create-lambda-function-5.png?featherlight=false&width=90pc)
7. Next, add environment variables to adjust the width and height of the image
- Click **Configuration** tab
- Click **Environment variables** on the left menu
- Click **Edit**
![UploadSource](/images/2-1-create-lambda-function/2-1-create-lambda-function-6.png?featherlight=false&width=90pc)
8. Click **Add environment variable**, then add the following environment variables:
- **WIDTH**: enter the new width of the photo, such as 200px.
- **HEIGHT**: enter the new hight of the photo, such as 280px.
- **DES_BUCKET**: S3 bucket name to store the changed image, **book-image-resize-storage**.

Then, click **Save**
![UploadSource](/images/2-1-create-lambda-function/2-1-create-lambda-function-7.png?featherlight=false&width=90pc)
So we have completed the step of creating a Lambda function and configuring the environment variables for it. Next step, we will create an S3 bucket to store uploaded and edited images.
