---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Vận dụng thành thạo IAM để quản lý người dùng và phân quyền, đồng thời triển khai giải pháp lưu trữ trên Amazon S3.
* Làm chủ việc vận hành máy chủ ảo Amazon EC2 và khởi tạo cơ sở dữ liệu quan hệ với Amazon RDS.
* Bước đầu tiếp cận nền tảng điện toán serverless AWS Lambda.

### Các công việc cần triển khai trong tuần này:

| Thứ | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu tổng quan các nhóm dịch vụ trong hệ sinh thái AWS: <br>&emsp; + Compute <br>&emsp; + Storage <br>&emsp; + Networking <br>&emsp; + Database | 27/04/2026 | 27/04/2026 | [Tổng quan sản phẩm AWS](https://aws.amazon.com/vi/products/) |
| 3 | - Nghiên cứu lộ trình kiến thức AWS Cloud Practitioner Essentials | 27/04/2026 | 29/04/2026 | [AWS Cloud Practitioner Essentials](https://skillbuilder.aws/search?searchText=aws-cloud-practitioner-essentials&showRedirectNotFoundBanner=true) |
| 4 | - Mở tài khoản Free Tier <br> - Cấu hình môi trường làm việc với AWS CLI <br> - Thực hành: <br>&emsp; + Khởi tạo AWS account <br>&emsp; + Cài đặt và cấu hình AWS CLI <br>&emsp; + Chạy thử các câu lệnh cơ bản | 29/04/2026 | 30/04/2026 | [AWS Free Tier](https://aws.amazon.com/vi/free/) |
| 5 | - Nghiên cứu lý thuyết về Amazon EC2: <br>&emsp; + Các dòng Instance (General Purpose, Compute, Memory) <br>&emsp; + Khái niệm AMI (Amazon Machine Image) <br>&emsp; + Giải pháp lưu trữ EBS <br>&emsp; + Phương thức kết nối SSH / Elastic IP | 30/04/2026 | 02/05/2026 | [Tài liệu Amazon EC2](https://docs.aws.amazon.com/ec2/) |
| 6 | - Thực hành khởi tạo EC2 và gắn kết EBS: <br>&emsp; + Tạo mới EC2 instance <br>&emsp; + Thiết lập kết nối SSH <br>&emsp; + Gắn và mount ổ đĩa EBS | 02/05/2026 | 03/05/2026 | [Hướng dẫn bắt đầu với Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html) |

### Thành tích tuần 2:

\- Có cái nhìn tổng quan về các nhóm dịch vụ AWS và vai trò của mỗi nhóm trong kiến trúc hạ tầng: <br>&emsp; \+ Compute (EC2, Lambda, ECS) <br>&emsp; \+ Storage (S3, EBS, EFS) <br>&emsp; \+ Networking (VPC, Route 53, CloudFront) <br>&emsp; \+ Database (RDS, DynamoDB, ElastiCache)

\- Hoàn tất lộ trình AWS Cloud Practitioner Essentials, nắm bắt được các dịch vụ trọng tâm cùng các tình huống áp dụng thực tế.

\- Mở thành công tài khoản Free Tier và cấu hình môi trường AWS CLI; thao tác thuần thục với các lệnh cơ bản để làm việc với AWS qua dòng lệnh.

\- Nắm chắc các thành phần cấu thành Amazon EC2: <br>&emsp; \+ Các dòng Instance (General Purpose, Compute Optimized, Memory Optimized) <br>&emsp; \+ Cách tạo và sử dụng AMI <br>&emsp; \+ Cấu hình các loại lưu trữ EBS (gp2, gp3, io1) <br>&emsp; \+ Các phương thức truy cập từ xa (SSH Key Pair, EC2 Instance Connect)

\- Thực hiện thành công trên thực tế: <br>&emsp; \+ Khởi chạy EC2 instance từ AMI có sẵn <br>&emsp; \+ Kết nối SSH từ máy tính cá nhân <br>&emsp; \+ Gắn thêm và mount ổ đĩa EBS vào instance đang hoạt động
