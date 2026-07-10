---
title: "Các bài blogs đã đăng"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Phần này tổng hợp các bài blog em đã chia sẻ trên [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj) xuyên suốt thời gian thực tập tại Amazon Web Services Việt Nam.

### [Blog 1 - Tối ưu hóa bảo mật với Session Policies trong Amazon EKS Pod Identity](3.1-Blog1/)
Bài viết giới thiệu tính năng Session Policies mới được bổ sung cho Amazon EKS Pod Identity, cho phép thu hẹp quyền IAM một cách linh hoạt và chính xác cho từng Pod mà không cần tạo thêm các IAM Role riêng lẻ. Đây là một bước tiến đáng chú ý, giúp việc áp dụng nguyên tắc Least Privilege trở nên hiệu quả hơn trong các môi trường Kubernetes có quy mô lớn.

### [Blog 2 - Kiến trúc Event-Driven trên AWS: EventBridge, SNS và SQS trong hệ thống Serverless](3.2-Blog2/)
Bài viết phân tích mô hình kiến trúc Event-Driven trên AWS, nơi các thành phần trong hệ thống tương tác với nhau thông qua sự kiện (Event) thay vì gọi trực tiếp qua REST API. Nội dung tập trung làm rõ vai trò của Amazon EventBridge, Amazon SNS và Amazon SQS trong việc giảm sự phụ thuộc giữa các thành phần, mở rộng hệ thống dễ dàng hơn và xử lý các tác vụ bất đồng bộ trong kiến trúc Serverless.

### [Blog 3 - Xây dựng Data Lake với Amazon S3 và Amazon Athena](3.3-Blog3/)
Bài viết trình bày cách xây dựng một Data Lake trên AWS, sử dụng Amazon S3 làm nơi lưu trữ dữ liệu thô, AWS Glue để quản lý metadata, và Amazon Athena để truy vấn dữ liệu trực tiếp bằng SQL mà không cần vận hành hạ tầng riêng. Giải pháp này giúp tiết kiệm chi phí lưu trữ, dễ dàng mở rộng quy mô, đồng thời đặt nền móng cho các ứng dụng phân tích dữ liệu và Machine Learning sau này.