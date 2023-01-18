---
title : "Tạo S3 bucket"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---
Phần này, chúng ta sẽ tạo hai S3 bucket:
- Bucket **book-image-store**: để lưu ảnh lên
- Bucket **book-image-resize-store**: để lưu ảnh sau khi thay đổi kích thước
1. Mở bảng điều khiển [Amazon S3](https://s3.console.aws.amazon.com/s3/get-started?region=ap-southeast-2) 
![S3Console](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-1.png?featherlight=false&width=90pc)
2. Ấn nút **Create bucket**
![S3Console](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-2.png?featherlight=false&width=90pc)
3. Nhập tên cho bucket, **book-image-store**
- Chọn vùng gần bạn nhất.
![CreateBucket](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-3.png?featherlight=false&width=90pc)
4. Bỏ chọn chặn truy cập **Block all public access** 
- Tích vào ô **I acknowledge that the current settings might result in this bucket and the objects within becoming public**
![CreateBucket](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-4.png?featherlight=false&width=90pc)
5. Ấn nút **Create bucket**
![CreateBucket](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-5.png?featherlight=false&width=90pc)
6. Tương tự để tạo bucket **book-image-resize-store**, làm lại các bước từ 1 tới 5.
7. Sau khi tạo xong hai bucket, chúng ta thêm trigger cho lambda function tạo ra trước đó
- Ấn vào **Add Trigger**
![AddTrigger](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-6.png?featherlight=false&width=90pc)
8. Nhập **S3** và chọn dịch vụ **S3**
![AddTrigger](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-7.png?featherlight=false&width=90pc)
9. Chọn bucket để triger lambda, **book-image-store**
- Chọn **All object create events** cho mục **Event type**
- Tích chọn **I acknowledge that using....** như hình
- Ấn nút **Add**
![AddTrigger](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-8.png?featherlight=false&width=90pc)
10. Xem kết quả sau đi thêm trigger cho Lambda function
![Trigger](/images/2-2-create-s3-bucket/2-2-create-s3-bucket-9.png?featherlight=false&width=90pc)





