---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* Cải thiện hiệu năng hệ thống FlashLearn bằng cơ chế caching, tự động hóa xử lý ảnh và kiểm thử API một cách toàn diện.
* Xây dựng tính năng đề xuất học tập thông minh dựa trên lịch sử tương tác của người dùng.
* Dựng hệ thống giám sát và theo dõi hiệu năng ứng dụng trên nền tảng AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Họp nhóm lên kế hoạch cải thiện hiệu năng: <br>&emsp; + Cải thiện tốc độ truy vấn trên RDS PostgreSQL (bổ sung Index) <br>&emsp; + Cấu hình caching CloudFront với thời gian TTL hợp lý | 21/06/2026 | 22/06/2026 | |
| 3 | - Thực hành tối ưu quy trình xử lý ảnh bằng Lambda: <br>&emsp; + Lambda tự động kích hoạt khi có ảnh tải lên S3 <br>&emsp; + Điều chỉnh ảnh về các kích thước chuẩn (thumbnail, medium, large) <br>&emsp; + Nén ảnh sang định dạng WebP để giảm dung lượng lưu trữ | 22/06/2026 | 23/06/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| 4 | - Kiểm thử toàn diện API bằng Postman: <br>&emsp; + Kiểm tra các thao tác CRUD thông qua API Gateway <br>&emsp; + Xác minh cấu hình CORS cho phía frontend <br>&emsp; + Kiểm tra cơ chế phân quyền IAM Authorization | 23/06/2026 | 24/06/2026 | |
| 5 | - Họp nhóm triển khai tính năng gợi ý học tập thông minh: <br>&emsp; + Xây dựng thuật toán dựa trên lịch sử học (tần suất ôn, tỷ lệ đúng/sai) <br>&emsp; + Thiết kế luồng xử lý: Lambda truy xuất Progress table → tính toán → trả về kết quả | 24/06/2026 | 26/06/2026 | |
| 6 | - Dựng hệ thống giám sát trên AWS: <br>&emsp; + CloudWatch Dashboard theo dõi CPU, Memory, Network của EC2 (ARM64) <br>&emsp; + CloudWatch Alarms cảnh báo khi CPU của RDS vượt 80% <br>&emsp; + AWS X-Ray truy vết API nội bộ để xác định điểm nghẽn | 26/06/2026 | 28/06/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |

### Thành tích tuần 10:

\- Cải thiện thành công hiệu năng truy vấn RDS PostgreSQL cùng cơ chế caching CloudFront: <br>&emsp; \+ Bổ sung Index cho những cột thường xuyên được truy vấn (user_id, deck_id, created_at) <br>&emsp; \+ Cấu hình CloudFront Cache Policy với TTL phù hợp cho từng loại nội dung tĩnh <br>&emsp; \+ Rút ngắn thời gian phản hồi trung bình đối với các truy vấn phức tạp

\- Dựng thành công pipeline xử lý ảnh tự động sử dụng Lambda: <br>&emsp; \+ Lambda kích hoạt tự động mỗi khi có ảnh được tải lên S3 <br>&emsp; \+ Điều chỉnh kích thước ảnh theo chuẩn (thumbnail, medium, large) và nén sang định dạng WebP <br>&emsp; \+ Lưu trữ các phiên bản ảnh vào các prefix S3 riêng biệt, giúp giảm đáng kể dung lượng lưu trữ

\- Hoàn tất việc kiểm thử API một cách toàn diện bằng Postman: <br>&emsp; \+ Kiểm tra trọn vẹn các thao tác CRUD (GET, POST, PUT, DELETE) thông qua API Gateway <br>&emsp; \+ Xác nhận cấu hình CORS hoạt động chính xác cho phía frontend <br>&emsp; \+ Kiểm tra phân quyền IAM để đảm bảo chỉ những role được cấp phép mới có thể gọi API

\- Xây dựng và hoàn thiện tính năng gợi ý học tập thông minh: <br>&emsp; \+ Phát triển thuật toán gợi ý dựa trên lịch sử học tập (tần suất ôn luyện, tỷ lệ đúng/sai, thời gian học) <br>&emsp; \+ Thiết kế luồng xử lý dữ liệu: Lambda đọc Progress table → thực hiện tính toán → trả về danh sách từ vựng ưu tiên

\- Dựng hệ thống giám sát toàn diện trên AWS: <br>&emsp; \+ CloudWatch Dashboard theo dõi CPU, Memory, Network của EC2 (ARM64) <br>&emsp; \+ CloudWatch Alarms phát cảnh báo khi CPU của RDS vượt 80% hoặc số kết nối vượt ngưỡng <br>&emsp; \+ AWS X-Ray truy vết các lệnh gọi API nội bộ, giúp xác định điểm nghẽn trong luồng xử lý
