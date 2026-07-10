---
title: "Worklog Tuần 12"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.12 </b> "
---

### Mục tiêu tuần 12:

* Hoàn chỉnh các tính năng tương tác cộng đồng cho hệ thống FlashLearn.
* Xây dựng cơ chế tính điểm và bảng xếp hạng người dùng.
* Dựng hệ thống bình luận theo cấu trúc phân cấp.
* Ghi nhận lịch sử hoạt động của người dùng vào cơ sở dữ liệu.
* Hoàn tất tài liệu kỹ thuật và thực hiện bàn giao dự án.

### Các công việc cần triển khai trong tuần này:

| Thứ | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Họp nhóm thiết kế các API phục vụ tương tác cộng đồng: <br>&emsp; + API bình chọn cho Flashcard (upvote/downvote) <br>&emsp; + API xếp hạng Quiz dựa trên thời gian làm bài và tỷ lệ trả lời đúng | 05/07/2026 | 06/07/2026 | |
| 3 | - Dựng cơ chế tính điểm và xếp hạng: <br>&emsp; + Cộng điểm cho các hành động: upvote, hoàn thành Quiz, tạo Flashcard được duyệt <br>&emsp; + Trừ điểm khi: bị downvote, vi phạm quy định <br>&emsp; + Bảng xếp hạng phân theo tuần/tháng/toàn thời gian | 06/07/2026 | 07/07/2026 | |
| 4 | - Thiết kế cơ chế bình luận theo cấu trúc phân cấp: <br>&emsp; + Cấu trúc dữ liệu cho phép trả lời lồng nhau (parent_id) <br>&emsp; + Tự động cập nhật số lượng bình luận (comment_count) <br>&emsp; + Kiểm duyệt nội dung bình luận thông qua Lambda | 07/07/2026 | 08/07/2026 | |
| 5 | - Bổ sung và hoàn thiện các tính năng còn lại: <br>&emsp; + Tính năng đánh dấu "Yêu thích" cho Flashcard/Quiz <br>&emsp; + Ghi nhận hoạt động người dùng vào bảng user_activities <br>&emsp; + Dữ liệu hoạt động làm nền tảng cho tính năng gợi ý học tập thông minh | 08/07/2026 | 09/07/2026 | |
| 6 | - Họp nhóm hoàn thiện tài liệu và thực hiện bàn giao: <br>&emsp; + Tài liệu mô tả API theo chuẩn Swagger/OpenAPI cho toàn bộ endpoint <br>&emsp; + Sơ đồ ERD tổng thể của toàn hệ thống (hơn 10 bảng) <br>&emsp; + Bộ hồ sơ bàn giao: kiến trúc hệ thống, hướng dẫn triển khai, thông tin tài khoản | 09/07/2026 | 10/07/2026 | |

### Thành tích tuần 12:

\- Hoàn thiện các API phục vụ tương tác cộng đồng cho FlashLearn: <br>&emsp; \+ API bình chọn Flashcard: POST /flashcards/{id}/vote (upvote/downvote) <br>&emsp; \+ API xếp hạng Quiz: tính điểm dựa trên thời gian hoàn thành và tỷ lệ câu trả lời đúng <br>&emsp; \+ Bảng xếp hạng được cập nhật theo thời gian thực nhờ DynamoDB

\- Dựng thành công cơ chế tính điểm và xếp hạng: <br>&emsp; \+ Cộng điểm khi người dùng upvote, hoàn thành Quiz, hoặc tạo Flashcard được duyệt <br>&emsp; \+ Trừ điểm khi bị downvote hoặc vi phạm quy định <br>&emsp; \+ Bảng xếp hạng (Leaderboard) được phân loại theo tuần/tháng/toàn thời gian

\- Xây dựng hoàn chỉnh hệ thống bình luận theo cấu trúc phân cấp: <br>&emsp; \+ Cấu trúc dữ liệu hỗ trợ bình luận cùng phản hồi lồng nhau (parent_id) <br>&emsp; \+ Tự động cập nhật số lượng bình luận (comment_count) cho từng Flashcard/Quiz <br>&emsp; \+ Kiểm duyệt nội dung bình luận qua Lambda trước khi công khai hiển thị

\- Hoàn thiện tính năng Favorite và cơ chế ghi nhận hoạt động người dùng: <br>&emsp; \+ Người dùng có thể lưu các Flashcard/Quiz yêu thích vào không gian cá nhân <br>&emsp; \+ Bảng user_activities lưu lại toàn bộ thao tác: xem, học, bình chọn, bình luận <br>&emsp; \+ Dữ liệu hoạt động này là nền tảng cho tính năng gợi ý học tập thông minh

\- Hoàn tất tài liệu kỹ thuật và bàn giao dự án thành công: <br>&emsp; \+ Tài liệu API đầy đủ theo chuẩn Swagger/OpenAPI cho toàn bộ endpoint <br>&emsp; \+ Sơ đồ ERD tổng thể của hệ thống với đầy đủ hơn 10 bảng cùng các mối quan hệ <br>&emsp; \+ Bộ hồ sơ bàn giao gồm: kiến trúc hệ thống, hướng dẫn triển khai, thông tin tài khoản và quyền truy cập
