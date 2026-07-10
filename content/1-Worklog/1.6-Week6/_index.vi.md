---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Đào sâu nghiên cứu các công cụ bảo mật tự động để nâng cao khả năng giám sát và ứng phó với những rủi ro tiềm ẩn.
* Rèn luyện kỹ năng cấu hình phân quyền chi tiết trong IAM, phân biệt rõ giữa roles và users nhằm áp dụng đúng nguyên tắc đặc quyền tối thiểu trên môi trường đám mây.

### Các công việc cần triển khai trong tuần này:

| Thứ | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu nền tảng an ninh của AWS: <br>&emsp; + Mô hình trách nhiệm chung (Shared Responsibility Model) <br>&emsp; + Vai trò then chốt của việc bảo vệ dữ liệu trên nền tảng đám mây | 24/05/2026 | 25/05/2026 | [Tài liệu AWS: Mô hình trách nhiệm chung](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/shared-responsibility.html) |
| 3 | - Nghiên cứu cơ chế quản trị tuân thủ trên AWS: <br>&emsp; + Các bộ tiêu chuẩn và quy định quốc tế <br>&emsp; + 5 chức năng nền tảng: Identify, Protect, Detect, Respond, Recover | 25/05/2026 | 27/05/2026 | [Tài liệu AWS: Chương trình tuân thủ trên đám mây](https://aws.amazon.com/vi/compliance/) |
| 4 | - Tìm hiểu và đánh giá các công cụ bảo mật tự động: <br>&emsp; + Security Hub <br>&emsp; + Trusted Advisor <br>&emsp; + Amazon GuardDuty | 27/05/2026 | 28/05/2026 | [Tài liệu AWS: Amazon GuardDuty](https://aws.amazon.com/vi/guardduty/) |
| 5 | - Quản lý định danh và quyền truy cập (IAM): <br>&emsp; + Nguyên tắc đặc quyền tối thiểu (Least Privilege) <br>&emsp; + Bảo vệ tài khoản root bằng MFA <br>&emsp; + Quản lý thông tin bí mật với Secrets Manager | 28/05/2026 | 29/05/2026 | [Tài liệu AWS: Quản lý nhận dạng và truy cập (IAM)](https://docs.amazonaws.cn/iam/) |
| 6 | - Đào sâu kiến thức IAM: <br>&emsp; + Phân biệt rõ IAM User và IAM Role <br>&emsp; + Xây dựng chính sách phân quyền (Policy) <br>&emsp; + Gán quyền truy cập cho tài nguyên EC2/Lambda | 29/05/2026 | 31/05/2026 | [Tài liệu AWS Builder](https://builder.aws.com/content/3C3mJwaTB5NWzcBfEugE7AUx59H/iam-identity-and-access-management) |

### Thành tích tuần 6:

\- Nắm chắc mô hình trách nhiệm chung của AWS: <br>&emsp; \+ AWS đảm nhiệm bảo mật cho hạ tầng vật lý, tầng hypervisor và các dịch vụ nền tảng <br>&emsp; \+ Người dùng chịu trách nhiệm về bảo mật dữ liệu, ứng dụng, cấu hình hệ điều hành và việc phân quyền truy cập

\- Hiểu rõ khung quản trị tuân thủ cùng 5 chức năng nền tảng: <br>&emsp; \+ Identify (Xác định) – nhận diện tài sản và các rủi ro tiềm ẩn <br>&emsp; \+ Protect (Bảo vệ) – áp dụng các biện pháp kiểm soát <br>&emsp; \+ Detect (Phát hiện) – theo dõi liên tục để phát hiện bất thường <br>&emsp; \+ Respond (Phản hồi) – xử lý kịp thời khi có sự cố <br>&emsp; \+ Recover (Khôi phục) – đưa hệ thống trở lại hoạt động sau sự cố

\- Đánh giá và vận dụng thành thạo các công cụ bảo mật tự động: <br>&emsp; \+ Security Hub – tập hợp và sắp xếp mức độ ưu tiên các cảnh báo bảo mật từ nhiều dịch vụ khác nhau <br>&emsp; \+ Trusted Advisor – rà soát cấu hình theo các thực hành tốt nhất (bảo mật, chi phí, hiệu năng) <br>&emsp; \+ GuardDuty – phát hiện thông minh các mối đe dọa nhờ ML, dựa trên phân tích CloudTrail, VPC Flow Logs, DNS logs

\- Cấu hình IAM tuân thủ đúng nguyên tắc đặc quyền tối thiểu: <br>&emsp; \+ Bảo vệ tài khoản root: bật MFA, tránh sử dụng root cho công việc hằng ngày <br>&emsp; \+ Tạo IAM User với quyền hạn được giới hạn theo từng vai trò công việc <br>&emsp; \+ Quản lý thông tin bí mật thông qua AWS Secrets Manager và Parameter Store

\- Phân biệt rạch ròi giữa IAM User và IAM Role, đồng thời thiết lập chính sách truy cập chi tiết: <br>&emsp; \+ IAM User – danh tính cố định dành cho người dùng hoặc ứng dụng <br>&emsp; \+ IAM Role – danh tính tạm thời, được gắn cho EC2/Lambda hay các dịch vụ AWS khác để truy cập tài nguyên <br>&emsp; \+ Inline Policy so với Managed Policy – khác biệt về phạm vi áp dụng và khả năng tái sử dụng
