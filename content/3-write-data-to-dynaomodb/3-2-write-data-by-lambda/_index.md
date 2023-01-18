---
title : "Write data by Lambda function"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---
In this step, we create Lambda function to write data to created DynamoDB table.
1. Open [AWS Lambda console](https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/discover) 
![LambdaConsole](/images/2-1-create-lambda-function/2-1-create-lambda-function-1.png?featherlight=false&width=90pc)
2. Click **Create function**
![CreateFunction](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-1.png?featherlight=false&width=90pc)
3. Enter function name: **book_create**
- Select **Python 3.9** for **Runtime**
- Click **Create function**
![CreateFunction](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-2.png?featherlight=false&width=90pc)
4. Copy the below code into tab **lambda_function**
```
import boto3
import json

client = boto3.resource('dynamodb')
    
def lambda_handler(event, context):
    
    book_item = event["body"]
    error = None
    try:
        table = client.Table('Books')
        table.put_item(Item = book_item)
    except Exception as e:
        error = e
        
    if error is None:
        response = {
            'statusCode': 200,
            'body': 'writing to dynamoDB successfully!',
            'headers': {
                'Content-Type': 'application/json'
            },
        }
    else:
        response = {
            'statusCode': 400,
            'body': 'writing to dynamoDB fail!',
            'headers': {
                'Content-Type': 'application/json'
            },
        }
  
    return response
```
- Click **Deploy**
![AttachPolicies](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-3.png?featherlight=false&width=90pc)
5. Next, add additional permissions for Lambda access to DynamoDB
- Click to tab **Configure**
- Click **Permissions** on the left menu
- Click to role the function executing
![AttachPolicies](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-9.png?featherlight=false&width=90pc)
- Click **Attach permissions**
- Select **Attach policies**
![AttachPolicies](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-10.png?featherlight=false&width=90pc)
- Enter **dynamoDB** to search policy.
- Check to policy: **AmazonDynamoDBFullAccess**
- Click **Attach policies**
![AttachPolicies](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-11.png?featherlight=false&width=90pc)
6. Create a event to test function operation
- Click to tab **Test**
- Enter event name, such as: **test_1**
- Enter the below data into **Event JSON**
```
{
  "body": {
    "id": "1",
    "name": "Java",
    "author": "Alex",
    "category": "IT",
    "price": "10.89",
    "description": "This book guide to create Java web basic",
    "image": "https://book-image-resize-store.s3.ap-southeast-2.amazonaws.com/Java.jpg"
  }
}
```
- Click **Save**
- Click **Test**
![CreateTestEvent](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-12.png?featherlight=false&width=90pc)
7. Navigate to DynamoDB console
- Click **Update settings** on the left menu
- Check to **Books**
- Click **Explore table items**
![CheckTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-13.png?featherlight=false&width=90pc)
8. You will get all the data from the table.
![CheckTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-14.png?featherlight=false&width=90pc)