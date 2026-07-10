---
title: "Blog 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---
# Xây dựng Data Lake với Amazon S3 và Amazon Athena

Data Lake là mô hình lưu trữ tập trung, cho phép giữ lại dữ liệu thô ở bất kỳ định dạng nào — có cấu trúc, bán cấu trúc hay phi cấu trúc — cho tới khi thực sự cần khai thác. Trên AWS, mô hình này có thể triển khai hiệu quả bằng cách dùng Amazon S3 làm lớp lưu trữ, AWS Glue để quản lý metadata, và Amazon Athena để truy vấn dữ liệu bằng SQL mà không cần vận hành bất kỳ hạ tầng máy chủ nào.

![Kiến trúc Data Lake với Amazon S3 và Amazon Athena](/images/blogs/blog3.jpeg)

## Những điểm chính cần biết

* Amazon S3 đóng vai trò lớp lưu trữ cốt lõi của Data Lake: S3 mang lại chi phí lưu trữ thấp, độ bền dữ liệu cao và khả năng mở rộng gần như vô hạn, thích hợp để tiếp nhận dữ liệu thô từ nhiều nguồn khác nhau như ứng dụng, thiết bị IoT, log hệ thống hay dữ liệu streaming.
* AWS Glue đảm nhiệm việc quản lý metadata thông qua Data Catalog: Glue Crawler tự động quét dữ liệu trong S3, xác định Schema và ghi nhận thông tin vào Glue Data Catalog, giúp các dịch vụ như Athena hiểu và truy vấn dữ liệu chính xác.
* Amazon Athena cho phép chạy truy vấn SQL trực tiếp trên dữ liệu trong S3: đây là dịch vụ truy vấn dạng serverless, dùng Presto Engine để thực thi SQL ngay trên dữ liệu lưu trong S3 mà không cần nạp vào một cơ sở dữ liệu riêng, và chỉ tính phí dựa trên lượng dữ liệu được quét.
* Việc phân vùng dữ liệu giúp tối ưu cả hiệu suất lẫn chi phí: tổ chức dữ liệu theo cấu trúc phân vùng (ví dụ theo năm, tháng, ngày) trong S3 giúp Athena chỉ cần quét đúng phần dữ liệu liên quan, nhờ đó rút ngắn thời gian truy vấn và tiết kiệm chi phí đáng kể.
* Định dạng lưu trữ ảnh hưởng lớn đến tốc độ truy vấn: dùng các định dạng dạng cột như Parquet hay ORC thay vì CSV hoặc JSON giúp cải thiện rõ rệt hiệu suất đọc và giảm lượng dữ liệu cần quét mỗi lần truy vấn.
* Kiến trúc thuần serverless, dễ dàng tích hợp mở rộng: toàn bộ luồng xử lý — từ thu thập, lưu trữ cho đến truy vấn — đều không cần quản lý máy chủ, đồng thời có thể kết hợp linh hoạt với Amazon QuickSight để trực quan hóa dữ liệu hoặc Amazon SageMaker cho các bài toán Machine Learning.

Kiến trúc Data Lake dựa trên S3, Glue và Athena trên AWS đặc biệt phù hợp với những tổ chức muốn xây dựng nền tảng phân tích dữ liệu với chi phí tối ưu, khả năng mở rộng tốt mà không muốn đầu tư vào một hạ tầng phức tạp. Đây cũng là nền móng lý tưởng để phát triển thêm các ứng dụng phân tích chuyên sâu, Business Intelligence, hay các mô hình Machine Learning trong tương lai.

[Xem bài đăng trên AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2203134240451536/?rdid=6V3UDKT1qdleFAkb&share_url=https%3A%2F%2Fwww.facebook.com%2Fshare%2Fp%2F1Bn86KFzSx%2F%3F_rdc%3D1%26_rdr)

---

## Nguồn tham khảo

* [Amazon Athena – AWS Documentation](https://docs.aws.amazon.com/athena/latest/ug/what-is.html)
* [AWS Glue – AWS Documentation](https://docs.aws.amazon.com/glue/latest/dg/what-is-glue.html)
* [Data Lakes and Analytics on AWS](https://aws.amazon.com/big-data/datalakes-and-analytics/)