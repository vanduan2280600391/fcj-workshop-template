---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Xây dựng bộ API nền tảng cho hệ thống FlashLearn.
* Thiết lập cơ sở dữ liệu và dựng giao diện quản trị nội dung.
* Xây dựng cơ chế phê duyệt nội dung tự động.
* Cải thiện cách quản lý tài nguyên lưu trữ bằng S3 Presigned URL.
* Hoàn chỉnh tài liệu kỹ thuật cùng sơ đồ quan hệ thực thể (ERD).

### Các công việc cần triển khai trong tuần này:

| Thứ | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Xây dựng API RESTful phục vụ Flashcard và Quiz: <br>&emsp; + POST /flashcards (Create), GET, PUT, DELETE <br>&emsp; + Kiểm tra tính hợp lệ của dữ liệu đầu vào (giới hạn ký tự, định dạng câu hỏi) <br>&emsp; + Tích hợp xác thực JWT thông qua API Gateway Authorizer | 28/06/2026 | 29/06/2026 | [Xây dựng API RESTful với API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/getting-started.html) |
| 3 | - Thiết lập cơ sở dữ liệu và giao diện quản trị: <br>&emsp; + Tạo bảng flashcards có cột status (pending/approved/rejected) <br>&emsp; + Tạo bảng quiz_results <br>&emsp; + Xây dựng giao diện admin để quản lý nội dung (xem, duyệt, từ chối) | 29/06/2026 | 30/06/2026 | |
| 4 | - Xây dựng cơ chế phê duyệt nội dung tự động: <br>&emsp; + Khi admin phê duyệt → Lambda tự động cập nhật chỉ mục tìm kiếm <br>&emsp; + EventBridge gửi thông báo tới người tạo nội dung | 01/07/2026 | 02/07/2026 | |
| 5 | - Tạo Presigned URL của S3 phục vụ upload/download: <br>&emsp; + Presigned URL có thời hạn để tải trực tiếp lên S3 <br>&emsp; + CloudFront phân phối ảnh/âm thanh thông qua URL đã ký <br>&emsp; + Giảm tải cho băng thông server | 02/07/2026 | 03/07/2026 | [CloudJourney AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| 6 | - Hoàn thiện tài liệu kỹ thuật cùng sơ đồ ERD: <br>&emsp; + ERD đầy đủ: Users, Flashcards, Decks, Quiz, QuizResults, Battle, Progress, AuditLogs <br>&emsp; + Tài liệu mô tả API gồm endpoint, request/response schema và mã lỗi | 03/07/2026 | 05/07/2026 | [Hướng dẫn thiết kế sơ đồ quan hệ thực thể](https://lucid.co/diagram/erd/tutorial) |

### Thành tích tuần 11:

\- Xây dựng và hoàn chỉnh bộ API RESTful nền tảng cho hệ thống FlashLearn: <br>&emsp; \+ API Flashcard: POST /flashcards (Create), GET /flashcards/{id}, PUT, DELETE cùng cơ chế xác thực dữ liệu đầu vào <br>&emsp; \+ API Quiz: quy định cấu trúc câu hỏi, định dạng đáp án và giới hạn số ký tự <br>&emsp; \+ Tích hợp xác thực JWT token thông qua API Gateway Authorizer

\- Thiết lập thành công cơ sở dữ liệu và giao diện quản trị nội dung: <br>&emsp; \+ Tạo bảng flashcards với cột status (pending/approved/rejected) cùng bảng quiz_results <br>&emsp; \+ Giao diện admin hỗ trợ xem, duyệt, từ chối và chỉnh sửa nội dung flashcard <br>&emsp; \+ Phân quyền cho admin thông qua một IAM Role riêng

\- Xây dựng cơ chế phê duyệt nội dung tự động: <br>&emsp; \+ Khi admin phê duyệt nội dung → Lambda được kích hoạt tự động để cập nhật chỉ mục tìm kiếm <br>&emsp; \+ Gửi thông báo qua EventBridge đến người tạo nội dung mỗi khi trạng thái thay đổi <br>&emsp; \+ Ghi lại toàn bộ lịch sử phê duyệt vào bảng audit_logs

\- Cải thiện cách quản lý tài nguyên lưu trữ bằng S3 Presigned URL: <br>&emsp; \+ Tạo Presigned URL có thời hạn để người dùng có thể tải file trực tiếp lên S3 mà không cần qua server <br>&emsp; \+ CloudFront phân phối ảnh/âm thanh từ S3 thông qua URL đã ký, ngăn chặn truy cập trái phép vào tài nguyên <br>&emsp; \+ Giảm tải cho băng thông server, giúp tốc độ upload được cải thiện

\- Hoàn chỉnh tài liệu kỹ thuật cùng ERD của hệ thống: <br>&emsp; \+ ERD đầy đủ bao gồm các thực thể: Users, Flashcards, Decks, Quiz, QuizResults, Battle, Progress, AuditLogs <br>&emsp; \+ Xác định rõ các quan hệ 1-N và N-N, cùng khóa chính, khóa ngoại cho từng bảng <br>&emsp; \+ Tài liệu API mô tả chi tiết endpoint, cấu trúc request/response và các mã lỗi
