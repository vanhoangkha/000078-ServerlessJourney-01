---
title : "Ghi dữ liệu với Lambda function"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---
1. Mở bảng điều khiển [AWS Lambda](https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/discover) 
![LambdaConsole](/images/2-1-create-lambda-function/2-1-create-lambda-function-1.png?featherlight=false&width=90pc)
2. Ấn nút **Create function**
![CreateFunction](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-1.png?featherlight=false&width=90pc)
3. Nhập tên cho function: **book_create**
- Chọn **Python 3.9** cho mục **Runtime**
- Ấn nút **Create function**
![CreateFunction](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-2.png?featherlight=false&width=90pc)
4. Sao chép đoạn code dưới đây vào tab **lambda_function**
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
- Ấn nút **Deploy**
![AttachPolicies](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-3.png?featherlight=false&width=90pc)
5. Tiếp theo, thêm quyền truy cập cho Lambda vào DynamoDB
- Ấn sang tab **Configure**
- Chọn mục **Permissions** phía bên trái
- Ấn vào role mà function đang thực hiện
![AttachPolicies](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-9.png?featherlight=false&width=90pc)
- Ấn nút **Attach permissions**
- Chọn mục **Attach policies**
![AttachPolicies](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-10.png?featherlight=false&width=90pc)
- Nhập **dynamoDB** để tìm policy thích hợp.
- Tích chọn policy: **AmazonDynamoDBFullAccess**
- Ấn nút **Attach policies**
![AttachPolicies](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-11.png?featherlight=false&width=90pc)
6. Tạo sự kiện để kiểm tra hoạt động của function
- Ấn sang tab **Test**
- Nhập tên cho sự kiện, ví dụ: **test_1**
- Nhập đoạn dữ liệu sau vào **Event JSON**
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
- Ấn nút **Save**
- Ấn nút **Test**
![CreateTestEvent](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-12.png?featherlight=false&width=90pc)
7. Điều hướng đến bảng điều khiển DynamoDB
- Chọn mục **Update settings** menu phía bên trái
- Tích chọn bảng **Books**
- Ấn nút **Explore table items**
![CheckTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-13.png?featherlight=false&width=90pc)
8. Bạn sẽ nhận được tất cả các dữ liệu của bảng.
![CheckTable](/images/3-write-data-to-dynaomodb/3-write-data-to-dynaomodb-14.png?featherlight=false&width=90pc)