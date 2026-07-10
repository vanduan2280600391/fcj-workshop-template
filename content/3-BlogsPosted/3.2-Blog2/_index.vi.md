---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
# Kiến trúc Event-Driven trên AWS: EventBridge, SNS và SQS trong hệ thống Serverless

Event-Driven Architecture là hướng tiếp cận thiết kế hệ thống, trong đó các thành phần trao đổi với nhau qua các sự kiện (Event) thay vì gọi trực tiếp lẫn nhau bằng REST API. Trên nền tảng AWS, mô hình này có thể triển khai hiệu quả nhờ sự kết hợp giữa Amazon API Gateway, AWS Lambda, Amazon EventBridge, Amazon SNS và Amazon SQS — giúp các service ít phụ thuộc lẫn nhau hơn, dễ mở rộng hơn, đồng thời giữ cho hệ thống vận hành ổn định khi xử lý các tác vụ bất đồng bộ.

![Kiến trúc Event-Driven trên AWS](/images/blogs/blog2.jpeg)

## Những điểm chính cần biết

* Producer chỉ đảm nhiệm việc phát sinh sự kiện: sau khi hoàn tất xử lý nghiệp vụ, AWS Lambda gửi Event tới Amazon EventBridge thay vì gọi trực tiếp đến service khác, nhờ đó giảm mức độ ràng buộc (coupling) giữa các thành phần.
* Amazon EventBridge đảm nhận việc định tuyến sự kiện: dịch vụ này tiếp nhận, lọc và chuyển tiếp Event dựa theo các Rule đã thiết lập, đồng thời có thể truyền sự kiện xuyên suốt giữa nhiều AWS Account khác nhau.
* Amazon SNS vận hành theo cơ chế Publish/Subscribe: một sự kiện có thể được phân phối cùng lúc tới nhiều Subscriber như AWS Lambda, Amazon SQS, HTTP Endpoint hay Email, mà Producer không cần thay đổi gì.
* Amazon SQS đảm nhiệm việc xử lý bất đồng bộ: hoạt động như một hàng đợi, SQS lưu tạm sự kiện, hấp thụ những đợt tăng lưu lượng đột biến, đồng thời hỗ trợ Retry và Dead Letter Queue (DLQ) để tránh thất thoát dữ liệu khi Consumer gặp sự cố.
* Kiến trúc có khả năng mở rộng dễ dàng: khi cần bổ sung thêm chức năng như gửi Email, ghi Audit Log, đẩy dữ liệu vào Data Lake hay phục vụ Machine Learning, chỉ cần đăng ký thêm một Consumer mới mà không tác động đến các thành phần đang vận hành.
* Tối ưu về chi phí lẫn khả năng mở rộng: nhờ dùng các dịch vụ Serverless như API Gateway, Lambda, EventBridge, SNS và SQS, hệ thống tự động co giãn theo lưu lượng thực tế và chỉ phát sinh chi phí khi có yêu cầu xử lý.

Mô hình kiến trúc này phù hợp đặc biệt với các hệ thống Microservices, các tác vụ xử lý bất đồng bộ, các bài toán tích hợp nhiều hệ thống hoặc môi trường sử dụng nhiều AWS Account — những nơi đòi hỏi khả năng mở rộng cao, hạn chế sự ràng buộc giữa các dịch vụ và nâng cao khả năng chịu lỗi cho toàn hệ thống.

[Xem bài đăng trên AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2203146967116930/?rdid=HY6kGYPyWz6qbEgn&share_url=https%3A%2F%2Fwww.facebook.com%2Fshare%2Fp%2F19BpYphs7p%2F)

---

## Nguồn tham khảo

* [Amazon EventBridge – AWS Documentation](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html)
* [Amazon SNS – AWS Documentation](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)
* [Amazon SQS – AWS Documentation](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)