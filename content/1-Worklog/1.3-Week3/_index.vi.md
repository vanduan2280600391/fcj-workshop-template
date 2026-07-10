---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Làm chủ kiến trúc Amazon EC2, cơ chế phân phối tải và các chiến lược tự động điều chỉnh quy mô tài nguyên.
* Nắm bắt các mô hình lưu trữ dữ liệu hiện đại cùng phương án chuyển dịch cơ sở dữ liệu sang AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Đi sâu vào kiến trúc EC2: <br>&emsp; + Phân nhóm Instance theo đặc điểm workload <br>&emsp; + Các thành phần liên quan: AMI, VPC, Security Group, EBS <br>&emsp; + Phương thức truy cập: SSH, EC2 Instance Connect, Session Manager | 03/05/2026 | 06/05/2026 | [Tài liệu Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) |
| 3 | - Tìm hiểu cơ chế cân bằng tải (ELB) và mở rộng tài nguyên tự động (Auto Scaling): <br>&emsp; + Application Load Balancer (ALB) <br>&emsp; + Auto Scaling Group và các Scaling Policy | 06/05/2026 | 08/05/2026 | [Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html) / [Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html) |
| 4 | - Khám phá giải pháp Container và Serverless trên AWS: <br>&emsp; + Container: ECS, EKS <br>&emsp; + Serverless: AWS Lambda, Fargate | 08/05/2026 | 09/05/2026 | [Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html) / [Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html) / [AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| 5 | - Tìm hiểu các dòng cơ sở dữ liệu trên AWS: <br>&emsp; + SQL: RDS (MySQL, PostgreSQL), Aurora <br>&emsp; + NoSQL: DynamoDB <br>&emsp; + In-memory: MemoryDB | 09/05/2026 | 10/05/2026 | [Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html) / [Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html) |
| 6 | - Nghiên cứu chiến lược di chuyển dữ liệu theo mô hình 6R: <br>&emsp; + Công cụ hỗ trợ: DMS, SCT, Snow Family, DataSync <br>&emsp; + Cách chọn giải pháp phù hợp cho từng tình huống cụ thể | 10/05/2026 | 10/05/2026 | [AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/Welcome.html) / [AWS Snow Family](https://aws.amazon.com/snow/) |

### Thành tích tuần 3:

\- Phân loại chi tiết kiến trúc EC2 theo từng loại workload và nắm chắc các thành phần cấu hình: <br>&emsp; \+ AMI, VPC, Security Group, EBS <br>&emsp; \+ Các phương thức kết nối từ xa: SSH Key Pair, EC2 Instance Connect, Session Manager

\- Hiểu rõ nguyên lý phân phối tải và tự động điều chỉnh quy mô tài nguyên: <br>&emsp; \+ Application Load Balancer (ALB) – định tuyến dựa trên path/host <br>&emsp; \+ Các Scaling Policy: Target Tracking, Step Scaling, Scheduled Scaling <br>&emsp; \+ Phối hợp ELB cùng Auto Scaling Group nhằm đảm bảo khả năng sẵn sàng cao

\- Phân biệt rõ ràng các mô hình Container và Serverless trên AWS: <br>&emsp; \+ ECS (chạy trên EC2) so với EKS (nền tảng Kubernetes) <br>&emsp; \+ Fargate – chạy container dạng serverless, không cần quản lý máy chủ <br>&emsp; \+ AWS Lambda – xử lý theo sự kiện, tính phí dựa trên số lần gọi và thời gian thực thi

\- Biết cách phân loại và chọn đúng dịch vụ cơ sở dữ liệu tùy theo nhu cầu: <br>&emsp; \+ SQL: RDS (MySQL, PostgreSQL), Aurora (hiệu năng cao) <br>&emsp; \+ NoSQL: DynamoDB (dạng key-value, document, độ trễ thấp) <br>&emsp; \+ In-memory: MemoryDB (tương thích Redis, đảm bảo tính bền vững)

\- Nắm được mô hình 6 chiến lược di chuyển dữ liệu (6R) cùng vai trò từng công cụ: <br>&emsp; \+ AWS DMS – di chuyển cơ sở dữ liệu trực tuyến (online migration) <br>&emsp; \+ AWS SCT – tự động chuyển đổi schema giữa các engine khác nhau <br>&emsp; \+ Snow Family – di chuyển dữ liệu offline ở quy mô lớn (từ TB đến PB) <br>&emsp; \+ DataSync – đồng bộ hóa file storage một cách liên tục và tự động
