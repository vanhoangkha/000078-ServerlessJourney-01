---
title : "Tạo Lambda function chỉnh ảnh"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---
1. Mở bảng điều khiển [AWS Lambda](https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/discover) 
![LambdaConsole](/images/2-1-create-lambda-function/2-1-create-lambda-function-1.png?featherlight=false&width=90pc)
2. Ấn nút **Create function**
![CreateFunction](/images/2-1-create-lambda-function/2-1-create-lambda-function-2.png?featherlight=false&width=90pc)
3. Nhập tên function, ví dụ: **resize-image**
- Chọn **Node.js 16.x** cho mục Runtime
- Nhấn nút **Create function**
![CreateFunction](/images/2-1-create-lambda-function/2-1-create-lambda-function-3.png?featherlight=false&width=90pc)
4. Tải tệp source code về máy của bạn

{{%attachments title="Source code" pattern=".*\.(zip)$"/%}}

5. Ấn nút **Upload from**
- Chọn **.zip file**
![UploadSource](/images/2-1-create-lambda-function/2-1-create-lambda-function-4.png?featherlight=false&width=90pc)
6. Nhấn nút **Upload**
- Sau đó chọn tệp source code mà bạn đã tải về
- Nhấn **Save**
![UploadSource](/images/2-1-create-lambda-function/2-1-create-lambda-function-5.png?featherlight=false&width=90pc)
7. Tiếp theo, thêm biến môi trường để chỉnh chiều rộng và cao cho ảnh
- Chọn tab **Configuration**
- Ấn **Environment variables** ở bên trái
- Ấn nút **Edit**
![UploadSource](/images/2-1-create-lambda-function/2-1-create-lambda-function-6.png?featherlight=false&width=90pc)
8. Ấn nút **Add environment variable**, sau đó thêm các biến môi trường sau:
- **WIDTH**: nhập chiều rộng mới của ảnh, ví dụ 200px.
- **HEIGHT**: nhập cao mới của ảnh, ví dụ 280px.
- **DES_BUCKET**: tên của S3 bucket lưu ảnh sau khi thay đổi, **book-image-resize-storage**.

Sau đó ấn **Save**
![UploadSource](/images/2-1-create-lambda-function/2-1-create-lambda-function-7.png?featherlight=false&width=90pc)
Vậy là chúng ta đã hoàn thành xong bước tạo một Lambda function và cấu hình biến môi trường cho nó. Tiếp theo sẽ tạo S3 bucket để lưu ảnh tải lên và ảnh sau khi qua chỉnh sửa.
