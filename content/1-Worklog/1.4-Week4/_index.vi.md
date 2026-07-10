---
title: "Worklog Tuần 4"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Nghiên cứu và tổng hợp các phương án chuyển dịch cơ sở dữ liệu trên AWS.
* Hệ thống hóa kiến thức chuyên sâu về hạ tầng mạng, bảo mật và phân phối nội dung trên AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Xác định mục tiêu và nhận diện những thách thức khi di chuyển cơ sở dữ liệu: <br>&emsp; + Đảm bảo tương thích schema giữa các engine khác nhau <br>&emsp; + Hạn chế thời gian gián đoạn (downtime) trong lúc migration | 10/05/2026 | 14/05/2026 | [AWS Database Migration Service](https://docs.aws.amazon.com/dms/latest/userguide/Welcome.html) |
| 3 | - Nghiên cứu bộ công cụ hỗ trợ di chuyển của AWS: <br>&emsp; + DMS, SCT <br>&emsp; + Snow Family, DataSync <br>&emsp; + Các tình huống ứng dụng thực tế | 14/05/2026 | 15/05/2026 | [AWS Schema Conversion Tool](https://docs.aws.amazon.com/SchemaConversionTool/latest/userguide/CHAP_Welcome.html) / [AWS DataSync](https://docs.aws.amazon.com/datasync/latest/userguide/what-is-datasync.html) |
| 4 | - Quy trình chuyển dịch dữ liệu theo 4 bước: <br>&emsp; + Assessment – đánh giá dữ liệu nguồn và các rủi ro <br>&emsp; + Preparation – chuẩn bị hạ tầng đích <br>&emsp; + Execution – triển khai full load kết hợp CDC <br>&emsp; + Validation & Optimization – kiểm tra và tối ưu kết quả | 15/05/2026 | 16/05/2026 | [AWS DMS Best Practices](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_BestPractices.html) |
| 5 | - Tìm hiểu kiến trúc mạng của Amazon VPC: <br>&emsp; + Subnet, Route Table, Internet/NAT Gateway <br>&emsp; + Security Group và Network ACL <br>&emsp; + PrivateLink, VPN Site-to-Site, Direct Connect | 16/05/2026 | 17/05/2026 | [Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) / [AWS Direct Connect](https://docs.aws.amazon.com/directconnect/latest/UserGuide/Welcome.html) |
| 6 | - Hệ thống lại chức năng của Route 53 và CloudFront: <br>&emsp; + Route 53: định tuyến DNS theo Weighted, Latency-based, Failover <br>&emsp; + CloudFront: mạng phân phối nội dung CDN, Edge Location, tích hợp cùng WAF và Shield | 17/05/2026 | 17/05/2026 | [Amazon Route 53](https://docs.aws.amazon.com/route53/latest/developerguide/Welcome.html) / [Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |

### Thành tích tuần 4:

\- Nhận diện các thách thức thường gặp khi di chuyển cơ sở dữ liệu và biết cách chọn chiến lược xử lý phù hợp: <br>&emsp; \+ Đảm bảo tương thích schema giữa các database engine khác nhau <br>&emsp; \+ Hạn chế thời gian downtime trong suốt quá trình migration <br>&emsp; \+ Giữ vững hiệu năng và tính toàn vẹn dữ liệu sau khi hoàn tất chuyển đổi

\- Nắm được cách vận hành của bộ công cụ AWS Migration: <br>&emsp; \+ DMS: khởi tạo replication instance → thiết lập source/target endpoints → chạy migration task (full load + CDC) <br>&emsp; \+ SCT: tự động phân tích và chuyển đổi schema giữa các engine <br>&emsp; \+ Snow Family: Snowcone (quy mô TB), Snowball Edge (quy mô PB), Snowmobile (quy mô Exabyte) <br>&emsp; \+ DataSync: đồng bộ hóa file storage liên tục giữa hệ thống on-premises và AWS

\- Thành thạo quy trình di chuyển dữ liệu theo 4 giai đoạn: <br>&emsp; \+ Assessment – đánh giá nguồn dữ liệu và các rủi ro tiềm ẩn <br>&emsp; \+ Preparation – chuẩn bị môi trường đích cùng công cụ cần thiết <br>&emsp; \+ Execution – triển khai full load kết hợp Change Data Capture (CDC) <br>&emsp; \+ Validation & Optimization – kiểm chứng độ chính xác và tối ưu hiệu năng

\- Nắm chắc kiến trúc mạng VPC cùng các lớp bảo mật: <br>&emsp; \+ Subnet (Public/Private), Route Table, Internet Gateway, NAT Gateway <br>&emsp; \+ Security Group (có trạng thái) so với Network ACL (không trạng thái) <br>&emsp; \+ Các phương thức kết nối riêng tư: PrivateLink (trong nội bộ AWS), VPN Site-to-Site (qua internet), Direct Connect (đường truyền vật lý riêng)

\- Phân biệt được vai trò và ứng dụng thực tế của Route 53 và CloudFront: <br>&emsp; \+ Route 53: định tuyến DNS với các policy như Simple, Weighted, Latency-based, Failover, Geolocation <br>&emsp; \+ CloudFront: lưu cache nội dung tại các Edge Location, kết hợp cùng WAF và Shield để bảo vệ ứng dụng trước tấn công DDoS
