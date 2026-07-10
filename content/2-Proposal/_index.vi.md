---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# FlashLearn – Đề xuất kiến trúc hạ tầng đám mây trên AWS

### 1. Tổng quan dự án

FlashLearn là một ứng dụng web hỗ trợ học tiếng Anh một cách tương tác thông qua flashcard, quiz và không gian cộng đồng. Thay vì đi theo hướng triển khai nguyên khối (monolithic) truyền thống, dự án hướng tới việc dựng một kiến trúc hạ tầng đám mây hiện đại trên nền tảng Amazon Web Services (AWS), tại khu vực Asia Pacific (Singapore). Kiến trúc được thiết kế bám sát các tiêu chuẩn cấp doanh nghiệp về khả năng phân tán, nhiều lớp bảo mật và mức độ tự động hóa cao.

---

### 2. Mục tiêu

Đảm bảo tính sẵn sàng cao: hệ thống vận hành liên tục 24/7 nhờ trải hạ tầng theo mô hình Multi-AZ trên 2 Availability Zone.

Tăng cường bảo mật nhiều lớp: chặn các mối đe dọa ngay tại biên mạng bằng AWS WAF, đồng thời cách ly hoàn toàn tầng xử lý (EC2) và tầng dữ liệu (RDS) bên trong các Private Subnet.

Tối ưu hiệu năng vận hành: phân phối nội dung tĩnh với tốc độ cao thông qua mạng CDN toàn cầu, đồng thời giảm tải cho server bằng cách tách các tác vụ nền ra xử lý riêng.

Mở rộng tính năng lõi của sản phẩm: tích hợp AI để hỗ trợ phát âm tiếng Anh một cách chuẩn xác.

---

### 3. Vấn đề cần giải quyết

Nhiều hệ thống e-learning hiện nay vẫn lưu trực tiếp file media ngay trên server và đặt server trong vùng mạng công cộng, dẫn đến rủi ro bảo mật đáng kể (dễ bị tấn công DDoS, rò rỉ dữ liệu) cũng như tình trạng nghẽn băng thông khi có nhiều học viên truy cập cùng lúc.

Giải pháp đưa ra là đặt S3 và CloudFront ở tuyến đầu để đảm nhiệm việc xử lý nội dung tĩnh, trong khi toàn bộ logic nghiệp vụ (EC2) và dữ liệu (RDS) được giấu kín bên trong lớp mạng riêng (Private). Mọi kết nối ra Internet của phần backend đều phải đi qua NAT Gateway, và traffic vào hệ thống được phân phối an toàn thông qua Application Load Balancer.

---

### 4. Kiến trúc giải pháp

Toàn bộ hệ thống được thiết kế bên trong một VPC duy nhất (10.0.0.0/16), trải rộng trên 2 Availability Zone để đảm bảo khả năng chịu lỗi.

![Sơ đồ kiến trúc FlashLearn trên AWS](/images/2-Proposal/flashlearn_architecture.png)

Chi tiết các thành phần và luồng xử lý:

Tầng biên (Edge Layer) – bảo mật & định tuyến: mọi yêu cầu từ người dùng đều đi qua Amazon Route 53 (quản lý DNS) kết hợp cùng AWS WAF để lọc bỏ các luồng truy cập độc hại trước khi vào sâu bên trong hệ thống.

Tầng phân phối nội dung: Amazon CloudFront đóng vai trò CDN, lấy và lưu cache các nội dung tĩnh từ Amazon S3 (ảnh flashcard, thư mục /wwwroot), rút ngắn thời gian nội dung đến tay người dùng.

Tầng mạng công cộng & cân bằng tải: hai Public Subnet (10.0.1.0/24 và 10.0.2.0/24) đặt Application Load Balancer để tiếp nhận traffic API từ Internet Gateway, đồng thời đặt các NAT Gateway giúp các máy chủ ở tầng trong có thể ra Internet để tải bản cập nhật.

Tầng xử lý nghiệp vụ & dữ liệu (Private Subnet): các máy chủ EC2 (t4g.micro, kiến trúc ARM64) đảm nhiệm xử lý logic backend, được đặt hoàn toàn bên trong 2 Private Subnet (10.0.3.0/24 và 10.0.4.0/24) và chỉ tiếp nhận traffic được chuyển tới từ ALB. Cơ sở dữ liệu sử dụng Amazon RDS PostgreSQL, áp dụng cơ chế đồng bộ hóa dữ liệu tức thời (Synchronous Replication) giữa 2 Availability Zone để đảm bảo không mất dữ liệu nếu một trung tâm dữ liệu gặp sự cố.

Tầng tự động hóa & tích hợp AI: máy chủ EC2 gọi API nội bộ tới Amazon Polly để cung cấp tính năng chuyển văn bản thành giọng nói (Text-to-Speech). Amazon EventBridge được cấu hình như một bộ lập lịch (Cron Scheduler) để tự động kích hoạt AWS Lambda xử lý các tác vụ chạy ngầm, và Lambda sẽ gửi email thông báo định kỳ (ví dụ nhắc deadline) thông qua Amazon SES.

---

### 5. Lộ trình triển khai

Tuần 1 – Nền tảng mạng & phân giải tên miền: dựng VPC, phân chia Public/Private Subnet, thiết lập Route 53, WAF và Internet Gateway.

Tuần 2 – Tính toán & cân bằng tải: khởi chạy các EC2 instance kiến trúc ARM64 trong Private Subnet, dựng ALB ở Public Subnet để điều hướng traffic vào EC2, cấu hình NAT Gateway.

Tuần 3 – Dữ liệu & lưu trữ: khởi tạo RDS PostgreSQL Multi-AZ, tạo S3 bucket và cấu hình CloudFront OAC để phân phối nội dung tĩnh.

Tuần 4 – Serverless & tích hợp dịch vụ: dựng luồng EventBridge → Lambda → SES để gửi email tự động, tích hợp SDK Amazon Polly vào mã nguồn backend trên EC2.

Tuần 5 – Kiểm thử, tối ưu & bàn giao: kiểm thử chịu tải qua ALB, kiểm thử luồng chặn của WAF, hoàn thiện hệ thống và xuất báo cáo kiến trúc hạ tầng.

---

### 6. Ngân sách dự kiến

Hệ thống được triển khai tại khu vực Singapore (ap-southeast-1) theo hình thức On-Demand. Do đây là kiến trúc theo tiêu chuẩn doanh nghiệp (nhiều lớp, nhiều Availability Zone), chi phí sẽ cao hơn so với một kiến trúc đơn giản chỉ có 1 lớp:

NAT Gateway (x2): khoảng 65,70 USD/tháng (thành phần tốn kém nhất nhưng bắt buộc để EC2 trong Private Subnet có thể ra Internet).

Application Load Balancer: khoảng 16,42 USD/tháng.

Amazon RDS PostgreSQL (Multi-AZ): khoảng 46,40 USD/tháng.

Amazon EC2 (t4g.micro x2): khoảng 12,26 USD/tháng.

S3, CloudFront, Route 53, WAF: khoảng 10,00 USD/tháng (tùy theo lưu lượng truy cập thực tế).

Polly, Lambda, EventBridge, SES: khoảng 2,00 USD/tháng (chi phí rất thấp nhờ mô hình pay-as-you-go của serverless).

Tổng ngân sách tham khảo: khoảng 152,78 USD/tháng.

---

### 7. Rủi ro & khắc phục

Chi phí NAT Gateway vượt dự kiến (mức độ cao): NAT Gateway tính phí theo giờ và theo dung lượng dữ liệu xử lý. Hướng xử lý: trong giai đoạn Dev/Test có thể chỉ dùng 1 NAT Gateway hoặc tạm thời đưa EC2 ra Public Subnet để tiết kiệm chi phí, chỉ cấu hình đủ 2 NAT Gateway khi nghiệm thu hoặc lên môi trường Production.

Mất kết nối từ ALB đến EC2 (mức độ trung bình): cấu hình sai Security Group khiến ALB không thể chuyển traffic vào Private Subnet. Hướng xử lý: rà soát kỹ để đảm bảo Security Group của EC2 chỉ chấp nhận Inbound traffic đến từ Security Group của ALB, không mở rộng ra 0.0.0.0/0.

Lỗi phân giải luồng tĩnh/động ở CloudFront (mức độ trung bình): CloudFront có thể cache nhầm các request API động. Hướng xử lý: cấu hình Behavior trong CloudFront thật rõ ràng — mọi đường dẫn /api/* phải được bỏ qua cache và chuyển thẳng về ALB, chỉ những đường dẫn /wwwroot/* hoặc file media mới được truy xuất từ S3.
