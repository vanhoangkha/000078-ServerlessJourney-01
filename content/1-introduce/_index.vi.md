---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
#### Tổng quan
Để bắt đầu, cùng tìm hiểu về Serverless là gì, AWS Lambda là gì. Serverless là một trong những mô hình phát triển ứng dụng trên cloud.
Cloud cung cấp cho người dùng 4 mô hình phát triển như sau:
- IaaS (Infrastructure as a Service)
- PaaS (Platform as a Service)
- CaaS (Container as a Service)
- FaaS (Function as a Service)
![CloudComputingServicesModel](/images/1-Introduce.png?featherlight=false&width=90pc)

**Infrastructure as a Service**

Đây là mô hình phổ biến nhất khi sử dụng cloud, các bạn có thể đã sử dụng nó hàng ngày mà không để ý. Ở mô hình này nhà phát triển Cloud sẽ exposes những API mà tương tác với virtualized platform bên dưới, như là API tương tác với máy ảo, API tương tác với storage, ... để có thể tự tạo và quản lý hạ tầng của mình trên cloud. Ví dụ như là AWS Cloud exposes những API liên quan tới EC2, cho phép chúng ta tự tạo và quản lý EC2 của mình một cách dễ dàng bằng Web Console hoặc AWS CLI. Ở mô hình này thì chúng ta sẽ tự tạo, và tự quản lý hạ tầng cũng như việc mở rộng.

**Platform as a Service**

Đây là một mô hình phát triển mà cloud sẽ cung cấp cho bạn một Platform Framework để phát triển ứng dụng nhanh hơn. Ví dụ để triển khai một ứng dụng web trên cloud, đầu tiên cần phải tạo EC2 (máy ảo), xong rồi cấu hình security group để traffic có thể đi vào EC2, xong sau đó deploy ứng dụng trên EC2, và nhiều thiết lập khác nữa. Do đó các nhà phát triển cloud cung cấp các Platform để làm việc đó nhanh hơn. Ví dụ như AWS thì có AWS Elastic Beanstalk, là một Platform cho phép người dùng dễ dàng triển khai một ứng dụng web, mà chỉ cần dùng vài cái click chuột đơn giản trên Web Console là sẽ có được một ứng dụng web, thay vì phải đi tạo và cấu hình nhiều thứ khác.

**Software as a Service**

Mô hình này thì đơn giản là phát triển ứng dụng dựa trên container và có một tool để quản lý những container của chúng ta, ví dụ như là Kubernetes. AWS có cung cấp AWS EKS để phát triển ứng dụng trên mô hình CaaS.

**Function as a Service**

Cuối cùng và là cấp nhỏ nhất, cloud cho phép người dùng phát triển ứng dụng chỉ dựa trên các Function, mà không cần phải tạo và quản lý hạ tầng phúc tạp, chỉ cần quản lý những function. Những function này có thể tự động mở rộng mà không cần phải cấu hình gì, đây chính là thành phần chính trong mô hình Serverless của chúng ta.

Vậy Serverless là mô hình phát triển ứng dụng và dịch vụ mà không phải quan tâm đến máy chủ. Một ứng dụng theo mô hình Serverless sẽ không cần quan tâm việc phân bổ, quản lý tài nguyên của hệ điều hành, và bỏ qua các vấn đề về nâng cấp và bảo mật.

**Lợi ích của Serverless**

- Không cần quản lý máy chủ: Bạn sẽ không cần cung cấp hay duy trì bất kỳ máy chủ nào. Sẽ không cần phần mềm hoặc thời gian chạy để cài đặt, nâng cấp hoặc quản trị.
- Thay đổi quy mô linh hoạt và độ sẵn sàng cao: FaaS của chúng ta sẽ tự động scale theo traffic, không cần cấu hình gì nhiều, trừ khi người dùng muốn nó mở rộng theo một cách cụ thế nào đó. 
- Tiết kiệm chi phí: Bạn sẽ chỉ cần trả tiền cho từng function được trigger, sử dụng bao nhiêu tính tiền bấy nhiêu.
- Hỗ trợ nhiều ngôn ngữ khác nhau: có thể dùng nhiều ngôn ngữ khác nhau để viết FaaS
**Điểm yếu của Serverless**

- Khó debug.
- Cold starts: mất một khoảng thời gian nếu function được trigger lần đầu tiên, hoặc function đó ít khi được request tới thì khi nó chạy lại khá tốn thời gian.
- Khó tổ chức source code: vì mỗi function sẽ được deploy riêng nên cách tổ chức source code sẽ khó hay dễ tùy thuộc vào ngôn ngữ khác nhau.
- Khó thiết kế môi trường dev local.

#### AWS Lambda
AWS Lambda là một service của AWS cho phép chúng ta chạy và quản lý function. Đây là thành phần chính của mô hình Serverless. Ngoài AWS Lambda thì AWS còn cung cấp cho chúng ta một số dịch vụ như sau để xây dựng mô hình Serverless:
- S3 ta dùng để lưu hình ảnh
- API gateway để ta xây dựng REST API
- DynamoDB cho cơ sở dữ liệu
- Cognito dùng để xác thực người dùng
- SQS dùng cho hàng đợi
- SNS dùng cho thông báo

AWS Lambda được thiết kế cho event-driven architecture, code của chúng ta sẽ được trigger dựa theo một event nào đó, ví dụ là request của client tới API, tất cả các process trigger là độc lập vói nhau và chỉ trả tiền cho từng lần function được trigger và chạy. So sánh với EC2 thì ta phải trả tiền theo giờ, ngay cả khi code trên EC2 của chúng ta không xử lý request nào cho user cả thì ta vẫn tốn tiền trả, còn Lambda thì không như vậy.



