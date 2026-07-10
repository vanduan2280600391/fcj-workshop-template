---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Thành thạo các giải pháp lưu trữ đa dạng của AWS và cách quản lý vòng đời dữ liệu.
* Vận dụng nhuần nhuyễn các dịch vụ AI/ML, công cụ phân tích dữ liệu và tích hợp hệ thống thông qua các bài thực hành cụ thể.

### Các công việc cần triển khai trong tuần này:

| Thứ | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu các giải pháp lưu trữ của AWS: <br>&emsp; + Object Storage: S3 <br>&emsp; + Block Storage: EBS <br>&emsp; + File Storage: EFS <br>&emsp; + In-memory: ElastiCache <br> - Nghiên cứu cách quản lý vòng đời dữ liệu và thiết lập sao lưu | 17/05/2026 | 20/05/2026 | [Tài liệu S3](https://docs.aws.amazon.com/s3/) / [Tài liệu EBS](https://docs.aws.amazon.com/ebs/) / [Tài liệu EFS](https://docs.aws.amazon.com/efs/) |
| 3 | - Khám phá hệ sinh thái AI/ML của AWS: <br>&emsp; + Các dịch vụ AI dựng sẵn <br>&emsp; + Machine Learning trên nền tảng SageMaker <br>&emsp; + Công cụ hỗ trợ lập trình CodeWhisperer <br> - Tìm hiểu quy trình chuẩn để triển khai một mô hình ML trên AWS | 20/05/2026 | 22/05/2026 | [Tài liệu SageMaker](https://docs.aws.amazon.com/sagemaker/) / [Dịch vụ AI của AWS](https://aws.amazon.com/ai/services/) |
| 4 | - Tìm hiểu các dịch vụ phục vụ phân tích dữ liệu: <br>&emsp; + Truy vấn serverless: Athena <br>&emsp; + Xử lý dữ liệu luồng: Kinesis <br>&emsp; + ETL: Glue <br>&emsp; + Kho dữ liệu: Redshift <br>&emsp; + Trực quan hóa: QuickSight | 22/05/2026 | 23/05/2026 | [Tài liệu Athena](https://docs.aws.amazon.com/athena/) / [Tài liệu Kinesis](https://docs.aws.amazon.com/kinesis/) / [Tài liệu Redshift](https://docs.aws.amazon.com/redshift/) |
| 5 | - Nghiên cứu các dịch vụ tích hợp và giao tiếp giữa các ứng dụng: <br>&emsp; + EventBridge: điều hướng sự kiện <br>&emsp; + SQS: hàng đợi thông điệp <br>&emsp; + SNS: cơ chế thông báo pub/sub <br> - Tìm hiểu thêm về Connect, SES cùng một số công cụ DevOps | 23/05/2026 | 24/05/2026 | [Tài liệu EventBridge](https://docs.aws.amazon.com/eventbridge/) / [Tài liệu SQS](https://docs.aws.amazon.com/sqs/) / [Tài liệu SNS](https://docs.aws.amazon.com/sns/) |
| 6 | - Thực hành tổng hợp kiến thức trong tuần: <br>&emsp; + Thiết lập S3 Lifecycle Policy <br>&emsp; + Xây dựng model ML bằng SageMaker <br>&emsp; + Dựng data pipeline theo chuỗi Kinesis → Glue → Redshift <br>&emsp; + Triển khai hệ thống hướng sự kiện (event-driven) với EventBridge | 24/05/2026 | 24/05/2026 | [Hướng dẫn thực hành AWS](https://aws.amazon.com/vi/getting-started/hands-on/) |

### Thành tích tuần 5:

\- Phân biệt rõ bốn hình thức lưu trữ trên AWS cùng ngữ cảnh sử dụng phù hợp: <br>&emsp; \+ Object Storage (S3) – lưu file tĩnh, sao lưu, xây dựng data lake <br>&emsp; \+ Block Storage (EBS) – ổ đĩa gắn trực tiếp cho EC2, thích hợp cho database <br>&emsp; \+ File Storage (EFS) – chia sẻ file dùng chung giữa nhiều instance <br>&emsp; \+ In-memory (ElastiCache) – lưu cache dữ liệu, rút ngắn độ trễ truy vấn

\- Thiết lập thành công S3 Lifecycle Policy nhằm tự động chuyển đổi dữ liệu giữa các storage class (Standard → IA → Glacier) và cấu hình sao lưu định kỳ.

\- Hiểu rõ hệ sinh thái AI/ML trên AWS cùng quy trình triển khai một mô hình ML: <br>&emsp; \+ SageMaker – xây dựng, huấn luyện và đưa model ML vào vận hành <br>&emsp; \+ CodeWhisperer – công cụ AI hỗ trợ viết code ngay trong IDE <br>&emsp; \+ Các bước triển khai: chuẩn bị dữ liệu → huấn luyện → đánh giá → triển khai endpoint

\- Thực hành xây dựng model ML với SageMaker thành công: <br>&emsp; \+ Chuẩn bị bộ dữ liệu và tải lên S3 <br>&emsp; \+ Khởi chạy training job và theo dõi quá trình huấn luyện <br>&emsp; \+ Triển khai model lên endpoint và thực hiện dự đoán (inference)

\- Nắm vững các dịch vụ phân tích dữ liệu cùng vai trò của từng dịch vụ: <br>&emsp; \+ Athena – truy vấn SQL trực tiếp trên dữ liệu trong S3 (serverless, tính phí theo lượng dữ liệu quét) <br>&emsp; \+ Kinesis – xử lý dữ liệu dạng luồng theo thời gian thực <br>&emsp; \+ Glue – dịch vụ ETL serverless phục vụ chuẩn bị và biến đổi dữ liệu <br>&emsp; \+ Redshift – kho dữ liệu quy mô lớn phục vụ phân tích chuyên sâu <br>&emsp; \+ QuickSight – trực quan hóa dữ liệu và xây dựng dashboard báo cáo

\- Xây dựng thành công data pipeline nối liền Kinesis → Glue → Redshift, đồng thời triển khai hệ thống event-driven bằng EventBridge: <br>&emsp; \+ SQS – hàng đợi thông điệp, đảm bảo xử lý theo đúng thứ tự và không thất thoát dữ liệu <br>&emsp; \+ SNS – cơ chế pub/sub, gửi thông báo đồng thời đến nhiều subscriber <br>&emsp; \+ EventBridge – tự động định tuyến sự kiện giữa các dịch vụ AWS
