---
title: "Worklog Tuần 9"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Bắt đầu xây dựng FlashLearn – nền tảng web hỗ trợ học tiếng Anh qua flashcard, quiz, chế độ đối kháng (battle) và không gian cộng đồng.
* Dựng kiến trúc hệ thống hiện đại trên AWS (khu vực Singapore) với VPC trải rộng trên hai Availability Zone để đảm bảo khả năng sẵn sàng cao.
* Tối ưu hiệu năng ứng dụng bằng cách kết hợp mô hình Serverless cùng các dịch vụ được quản lý như Amazon CloudFront, Lambda và EventBridge.

### Các công việc cần triển khai trong tuần này:

| Thứ | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Họp khởi động nhóm dự án FlashLearn: <br>&emsp; + Hoàn tất thiết kế Schema cho cơ sở dữ liệu PostgreSQL <br>&emsp; + Thu thập và chuẩn hóa kho dữ liệu từ vựng tiếng Anh | 14/06/2026 | 15/06/2026 | |
| 3 | - Dựng kiến trúc mạng VPC trải rộng nhiều AZ: <br>&emsp; + VPC gồm 2 Public Subnet và 2 Private Subnet <br>&emsp; + Cấu hình IAM Role cho EC2 theo nguyên tắc quyền hạn tối thiểu <br>&emsp; + Thiết lập Security Group theo từng lớp | 15/06/2026 | 16/06/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| 4 | - Cấu hình ALB và phân phối nội dung tĩnh: <br>&emsp; + ALB điều hướng traffic dựa trên health check <br>&emsp; + Tải tài nguyên tĩnh lên S3 <br>&emsp; + Tích hợp CDN CloudFront | 16/06/2026 | 18/06/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| 5 | - Họp nhóm rà soát thiết kế UI/UX trên Figma: <br>&emsp; + Đánh giá các màn hình flashcard, quiz và battle <br>&emsp; + Cải thiện luồng trải nghiệm người dùng | 18/06/2026 | 19/06/2026 | |
| 6 | - Xây dựng cơ chế thông báo và tính năng phát âm: <br>&emsp; + EventBridge kích hoạt Lambda để gửi nhắc nhở học tập <br>&emsp; + Tích hợp Amazon Polly để chuyển văn bản thành giọng nói | 19/06/2026 | 21/06/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |

### Thành tích tuần 9:

\- Hoàn tất thiết kế Schema cơ sở dữ liệu PostgreSQL cho hệ thống FlashLearn: <br>&emsp; \+ Xác định các bảng cốt lõi: Users, Flashcards, Decks, Quiz, Battle, Progress <br>&emsp; \+ Thiết lập các khóa ngoại và chỉ mục nhằm tối ưu tốc độ truy vấn <br>&emsp; \+ Thu thập và chuẩn hóa bộ dữ liệu từ vựng tiếng Anh

\- Dựng thành công kiến trúc mạng VPC nhiều vùng khả dụng trên AWS Singapore: <br>&emsp; \+ VPC gồm 2 Public Subnet và 2 Private Subnet trải trên 2 Availability Zone <br>&emsp; \+ Cấu hình IAM Role cho EC2 theo nguyên tắc quyền hạn tối thiểu <br>&emsp; \+ Thiết lập Security Group phân lớp theo từng thành phần ứng dụng

\- Cấu hình Application Load Balancer và triển khai phân phối nội dung tĩnh: <br>&emsp; \+ ALB điều hướng traffic tới các EC2 instance dựa trên kết quả health check <br>&emsp; \+ Tạo và cấu hình S3 bucket để lưu trữ tài nguyên tĩnh <br>&emsp; \+ Tích hợp CDN CloudFront nhằm phân phối nội dung với độ trễ thấp trên toàn cầu

\- Cải thiện trải nghiệm người dùng thông qua buổi họp nhóm rà soát Figma: <br>&emsp; \+ Đánh giá và tinh chỉnh UI/UX cho các màn hình flashcard, quiz và battle <br>&emsp; \+ Điều chỉnh luồng thao tác người dùng dựa trên góp ý của cả nhóm

\- Xây dựng thành công hệ thống thông báo tự động cùng tính năng phát âm: <br>&emsp; \+ EventBridge kích hoạt Lambda theo lịch trình để gửi nhắc nhở học tập <br>&emsp; \+ Tích hợp Amazon Polly để chuyển đổi văn bản từ vựng thành giọng nói <br>&emsp; \+ Lambda xử lý sự kiện và ghi kết quả vào S3
