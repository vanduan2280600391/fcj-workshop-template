---
title: "Worklog Tuần 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1:

* Hoàn tất việc đăng ký tài khoản AWS và ổn định cơ cấu nhóm làm việc.
* Kích hoạt khoản tín dụng $200 và lên kế hoạch kiểm soát chi phí sử dụng.
* Củng cố kiến thức cơ bản về các mô hình điện toán đám mây.
* Triển khai và cấu hình thành công công cụ dòng lệnh AWS CLI.

### Các công việc cần triển khai trong tuần này:

| Thứ | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Gặp gỡ, làm quen với các thành viên trong nhóm FCAJ <br> - Xem qua và ghi nhớ nội quy, quy định của đơn vị thực tập <br> - Hoàn thành việc đăng ký tài khoản AWS <br> - Lập nhóm làm việc chung | 20/04/2026 | 21/04/2026 | [Video giới thiệu AWS](https://www.youtube.com/watch?v=2QSXYi6Ofmc&t=1s) |
| 3 | - Thực hiện các bước cần thiết để được cấp $200 Credit AWS | 21/04/2026 | 22/04/2026 | [Chiến lược nhận $200 AWS Credit](https://000001.awsstudygroup.com/3-chi%E1%BA%BFn-l%C6%B0%E1%BB%A3c-nh%E1%BA%ADn-%C4%91%E1%BB%A7-200-credit/) |
| 4 | - Lên kế hoạch quản lý ngân sách AWS: <br>&emsp; + Cấu hình AWS Budgets và Cost Explorer <br>&emsp; + Phân bổ khoản tín dụng $200 cho toàn bộ thời gian thực tập | 22/04/2026 | 23/04/2026 | [Quản lý chi phí trên AWS](https://aws.amazon.com/vi/aws-cost-management/) |
| 5 | - Tìm hiểu kiến thức cơ bản về điện toán đám mây: <br>&emsp; + Các mô hình triển khai: Public, Private, Hybrid Cloud <br>&emsp; + Các mô hình dịch vụ: IaaS, PaaS, SaaS | 23/04/2026 | 24/04/2026 | [Video tổng quan mô hình điện toán đám mây](https://www.youtube.com/watch?v=HxYZAK1coOI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=5) |
| 6 | - Cài đặt và thiết lập môi trường làm việc với AWS CLI: <br>&emsp; + Tiến hành cài đặt AWS CLI <br>&emsp; + Khai báo Access Key, Region, Output Format <br>&emsp; + Luyện tập các câu lệnh AWS CLI cơ bản | 24/04/2026 | 26/04/2026 | [Hướng dẫn cài đặt & cấu hình AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html) |

### Thành tích tuần 1:

\- Hoàn tất đăng ký tài khoản AWS, kích hoạt thành công gói tín dụng $200 và thành lập nhóm làm việc đúng như kế hoạch.

\- Cấu hình AWS Budgets cùng Cost Explorer, đồng thời xây dựng phương án phân bổ ngân sách $200 để sử dụng xuyên suốt kỳ thực tập.

\- Phân biệt được ba mô hình triển khai điện toán đám mây: <br>&emsp; \+ Public Cloud <br>&emsp; \+ Private Cloud <br>&emsp; \+ Hybrid Cloud

\- Hiểu rõ ba tầng dịch vụ đám mây kèm ví dụ minh họa trên AWS: <br>&emsp; \+ IaaS (EC2, VPC, S3) <br>&emsp; \+ PaaS (Elastic Beanstalk, RDS) <br>&emsp; \+ SaaS (Amazon WorkMail, Chime)

\- Cài đặt và cấu hình thành công AWS CLI, gồm: <br>&emsp; \+ Access Key & Secret Key <br>&emsp; \+ Region mặc định <br>&emsp; \+ Output format

\- Vận dụng AWS CLI để thực hiện các thao tác cơ bản như: <br>&emsp; \+ Kiểm tra thông tin tài khoản (`aws sts get-caller-identity`) <br>&emsp; \+ Xem danh sách các region (`aws ec2 describe-regions`) <br>&emsp; \+ Truy vấn các tài nguyên EC2 đang hoạt động
