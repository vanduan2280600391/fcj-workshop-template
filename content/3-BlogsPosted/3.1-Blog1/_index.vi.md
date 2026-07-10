---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
# Tối ưu hóa bảo mật với Session Policies trong Amazon EKS Pod Identity

Amazon EKS Pod Identity là cơ chế giúp Pod truy cập các dịch vụ AWS một cách an toàn mà không cần lưu trữ khóa truy cập cố định. Mới đây, tính năng Session Policies đã được bổ sung vào Amazon EKS, cho phép gắn thêm các chính sách IAM tạm thời ngay tại thời điểm Pod đảm nhận (assume) một IAM Role. Nhờ đó, quyền truy cập của từng Pod có thể được thu hẹp một cách linh hoạt mà vẫn tận dụng được các IAM Role sẵn có, giúp việc quản lý phân quyền trong các cụm Kubernetes lớn trở nên đơn giản hơn nhiều.

![Session Policies trong Amazon EKS Pod Identity](/images/blogs/blog1.jpeg)

## Những điểm chính cần biết

* Session Policies phát huy tác dụng ngay tại thời điểm Pod assume IAM Role: chính sách này được áp dụng trong bước AssumeRole nhằm thu hẹp quyền truy cập tài nguyên AWS của Pod, mà không đòi hỏi phải tạo thêm một IAM Role mới.
* Quyền thực tế là phần giao nhau giữa IAM Role và Session Policy: Pod chỉ có thể thực hiện các hành động được cả IAM Role lẫn Session Policy cùng cho phép. Session Policy chỉ có tác dụng thu hẹp quyền, không thể mở rộng thêm quyền so với IAM Role gốc.
* Giúp việc quản lý IAM gọn nhẹ hơn: một IAM Role có thể được nhiều Pod dùng chung, còn Session Policies sẽ đảm nhiệm việc tinh chỉnh mức quyền phù hợp cho từng workload, nhờ đó số lượng IAM Role cần duy trì giảm đi đáng kể.
* Củng cố nguyên tắc Least Privilege: quyền hạn của mỗi Pod được giới hạn sát với nhu cầu thực tế, hạn chế rủi ro nếu Pod hoặc ứng dụng bị tấn công/khai thác.
* Linh hoạt trong triển khai: Session Policies được khai báo thông qua Pod Identity Association, có thể thao tác qua AWS Management Console, AWS CLI hay AWS SDK — dễ dàng lồng ghép vào quy trình triển khai và tự động hóa hạ tầng.
* Thích hợp cho các cụm Amazon EKS quy mô lớn: nhờ giảm số lượng IAM Role, việc quản trị trở nên đơn giản hơn, tránh được nguy cơ chạm giới hạn IAM (IAM limits) và dễ mở rộng khi số Pod/ứng dụng tăng lên.

Tính năng này đặc biệt có giá trị trong các kiến trúc Microservices, nơi nhiều Pod cùng chia sẻ một IAM Role nhưng lại cần phạm vi truy cập tài nguyên AWS khác nhau. Chẳng hạn, một Pod chỉ cần quyền đọc dữ liệu từ một Amazon S3 Bucket nhất định, trong khi một Pod khác lại cần thêm quyền thao tác với Amazon DynamoDB hoặc Amazon SQS. Khi kết hợp Pod Identity cùng Session Policies, hệ thống vẫn giữ được cách quản lý tập trung, đồng thời đảm bảo mỗi Pod chỉ sở hữu đúng những quyền hạn cần thiết cho chức năng của nó.

[Xem bài đăng trên AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2203235167108110/?rdid=fZAE516uaJXkvqmj&share_url=https%3A%2F%2Fwww.facebook.com%2Fshare%2Fp%2F1Bf61McbW7%2F)

---

## Nguồn tham khảo

* [Amazon EKS Pod Identity – AWS Documentation](https://docs.aws.amazon.com/eks/latest/userguide/pod-identities.html)
* [Session Policies – AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#policies_session)