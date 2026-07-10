---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Làm quen với các khái niệm nền tảng về Hạ tầng dưới dạng mã (IaC).
* Tìm hiểu những nguyên lý cơ bản của AWS CDK và Terraform.
* Bước đầu tiếp cận kiến thức nền tảng về NodeJS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Duy trì việc ôn luyện cho kỳ thi <br> - Tìm hiểu các tư tưởng nền tảng của IaC: <br>&emsp; + Ưu điểm so với việc cấu hình thủ công <br>&emsp; + Hai cách tiếp cận: Declarative và Imperative | 07/06/2026 | 08/06/2026 | [Tìm hiểu về Hạ tầng dạng mã](https://aws.amazon.com/what-is/infrastructure-as-code/) |
| 3 | - Bước đầu làm quen với AWS CDK: <br>&emsp; + Cấu trúc phân cấp: App → Stack → Construct (L1, L2, L3) <br>&emsp; + Các ngôn ngữ được hỗ trợ: TypeScript, Python, Java, C# <br>&emsp; + Cách synthesize CDK thành CloudFormation template | 08/06/2026 | 09/06/2026 | [Tài liệu AWS CDK](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |
| 4 | - Nghiên cứu về Terraform: <br>&emsp; + Cấu trúc các file: main.tf, variables.tf, outputs.tf <br>&emsp; + Quy trình làm việc: init → plan → apply → destroy <br>&emsp; + So sánh Terraform và AWS CDK | 09/06/2026 | 10/06/2026 | [Tài liệu Terraform](https://developer.hashicorp.com/terraform/docs) |
| 5 | - Làm quen với NodeJS: <br>&emsp; + Cài đặt Node.js cùng npm <br>&emsp; + Cơ chế Event Loop và mô hình non-blocking I/O <br>&emsp; + Các module nền tảng: fs, path, http, events | 10/06/2026 | 12/06/2026 | [Tài liệu Node.js](https://nodejs.org/docs/latest/api/) |
| 6 | - Thực hành phối hợp IaC cùng NodeJS: <br>&emsp; + Triển khai hạ tầng AWS (S3, Lambda) thông qua CDK hoặc Terraform <br>&emsp; + Viết Lambda function bằng NodeJS để xử lý sự kiện phát sinh từ S3 | 12/06/2026 | 14/06/2026 | [Trung tâm tài nguyên AWS](https://aws.amazon.com/getting-started/) |

### Thành tích tuần 8:

\- Nắm chắc các khái niệm nền tảng của Infrastructure as Code (IaC): <br>&emsp; \+ Ưu điểm so với cấu hình thủ công: khả năng tái sử dụng, quản lý phiên bản, đảm bảo tính nhất quán giữa các môi trường <br>&emsp; \+ Hai cách tiếp cận chính: Declarative (Terraform) và Imperative (AWS CDK) <br>&emsp; \+ Vòng đời của IaC: soạn thảo → kiểm thử → triển khai → cập nhật → gỡ bỏ

\- Hiểu được nền tảng cùng mô hình cấu trúc phân cấp của AWS CDK: <br>&emsp; \+ App → Stack → Construct (L1, L2, L3) <br>&emsp; \+ Hỗ trợ đa dạng ngôn ngữ lập trình: TypeScript, Python, Java, C# <br>&emsp; \+ Khả năng tổng hợp (synthesize) CDK app thành CloudFormation template

\- Nắm rõ cú pháp cũng như quy trình vận hành của Terraform: <br>&emsp; \+ Cấu trúc file: main.tf, variables.tf, outputs.tf, providers.tf <br>&emsp; \+ Quy trình thao tác: terraform init → plan → apply → destroy <br>&emsp; \+ So sánh với CDK: Terraform sử dụng ngôn ngữ riêng HCL, còn CDK dùng các ngôn ngữ lập trình quen thuộc

\- Cài đặt và bước đầu làm chủ môi trường NodeJS: <br>&emsp; \+ Cài đặt Node.js cùng npm, quản lý các package qua package.json <br>&emsp; \+ Nắm được cơ chế Event Loop và mô hình xử lý non-blocking I/O của Node.js <br>&emsp; \+ Vận dụng các module nền tảng: fs, path, http, events

\- Hoàn thành bài thực hành kết hợp giữa IaC và NodeJS: <br>&emsp; \+ Triển khai thành công hạ tầng AWS (S3 bucket, Lambda function) bằng CDK hoặc Terraform <br>&emsp; \+ Viết Lambda function bằng NodeJS để xử lý các sự kiện phát sinh từ S3
