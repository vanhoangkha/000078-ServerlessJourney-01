---
title : "Tạo Policy cho Lambda function"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---
Trong bước này chúng ta sẽ tạo Policy cấp quyền cho Lambda function có thể lấy, ghi và xoá object trong S3 bucket.
1. Điều hướng tới bảng điều khiển của Lambda bạn đã tạo.
- Trong tab **Configuration**, chọn mục **Permissions**
- Ấn vào role mà function đang thực hiện
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-1.png?featherlight=false&width=90pc)
2. Ấn nút **Add permissions**
- Chọn **Attach policies**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-2.png?featherlight=false&width=90pc)
3. Ấn nút **Create policy**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-3.png?featherlight=false&width=90pc)
4. Ấn vào **Choose a service**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-4.png?featherlight=false&width=90pc)
5. Nhập **S3**, sau đó chọn **S3**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-5.png?featherlight=false&width=90pc)
6. Ấn vào mục **Action**, mở rộng **Read** trong **Access level**
- Tích chọn quyền **GetObject**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-6.png?featherlight=false&width=90pc)
7. Sau đó mở rộng mục **Write**
- Tích chọn quyền **DeleteObject**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-7.png?featherlight=false&width=90pc)
8. Tại mục **Resource**, ấn vào **Add ARN** để chỉ định tài nguyên.
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-8.png?featherlight=false&width=90pc)
9. Nhập tên bucket: **book-image-store**
- Tích vào **Any** cho phép quyền với mọi object trong bucket
- Ấn **Add**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-9.png?featherlight=false&width=90pc)
10. Ấn **Add additional permissions**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-10.png?featherlight=false&width=90pc)
11. Lặp lại bước 4 và 5
- Sau đó mở rộng mục **Write**, tích chọn quyền **PutObject**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-11.png?featherlight=false&width=90pc)
12. Làm tương tự bước 8, 9.
- Nhập tên bucket là **book-image-resize-store**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-12.png?featherlight=false&width=90pc)
13. Ấn nút **Next tags**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-13.png?featherlight=false&width=90pc)
14. Ấn nút **Next review**
15. Nhập tên cho policy, ví dụ: **LambdaResizeImageS3Policy**
- Xem lại các thông tin và ấn nút **Create policy**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-14.png?featherlight=false&width=90pc)
16. Trở lại màn hình thêm policy cho Lambda function, nhập tên policy chúng ta vừa tạo.
- Tích chọn policy: **LambdaResizeImageS3Policy**
- Ấn nút **Attach policies**
![CreatePolicy](/images/2-3-create-policy-access-s3/2-3-create-policy-access-s3-15.png?featherlight=false&width=90pc)
Chúng ta đã hoàn thành cấp quyền đọc, ghi và xoá object trong S3 bucket cho Lambda function. Bước tiếp theo là kiểm tra hoạt động của Lambda fucntion khi tải lên một ảnh.



