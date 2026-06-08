---
title: "Worklog Tuần 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Xây dựng và tự động hóa hệ thống phản ứng sự cố an ninh mạng (SOAR) trên nền tảng điện toán đám mây AWS.
* Thiết kế chuẩn hóa kiến trúc hạ tầng và các luồng xử lý dữ liệu bảo mật.
* Triển khai hai kịch bản phòng thủ tự động: Log-Driven Automation (qua S3) và Network-Driven Automation (Snort IDS qua CloudWatch).
* Đảm bảo hệ thống tự động nhận diện IP tấn công (kể cả khi ẩn sau Load Balancer) và thực thi lệnh chặn tức thời qua AWS WAF.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Thiết lập môi trường làm việc trên draw.io và tích hợp bộ biểu tượng chuẩn AWS 2026 <br> - Thiết kế khung ranh giới hạ tầng mạng (AWS Cloud, Region, VPC, Subnets) và bố trí các biểu tượng dịch vụ vào đúng lớp mạng <br> - Cấu hình và vẽ sơ đồ 4 luồng dữ liệu (Tấn công, Gửi Log, Tự động hóa & AI, Lưu trữ) bằng các quy ước về nét vẽ và màu sắc | 11/05/2026 | 11/05/2026 | Hướng dẫn vẽ kiến trúc AWS |
| 3   | - Phát triển kịch bản SOAR cơ bản trên AWS <br> - Khởi tạo EC2, thiết lập ALB định tuyến lưu lượng và tích hợp AWS WAF <br> - Lập trình Lambda (Python) và cấu hình IAM để tự động cập nhật IP độc hại vào danh sách chặn WAF <br> - Giả lập sự cố, xác minh WAF chặn truy cập (HTTP 200 → 403) và dọn dẹp tài nguyên lab | 12/05/2026 | 12/05/2026 | |
| 4   | - Thiết kế Kịch bản 1 (Log-Driven): Vẽ sơ đồ ALB → S3 → S3 Event → Lambda → WAF; viết pseudocode Python bóc tách IP sinh lỗi 404 <br> - Thiết kế Kịch bản 2 (Network-Driven): Sơ đồ tích hợp Snort/Suricata trên EC2; luồng CloudWatch Agent → Metric Filters → Alarm → Lambda → WAF | 13/05/2026 | 13/05/2026 | |
| 5   | - Thiết lập hạ tầng ghi log: EC2 sau ALB, đẩy Access Logs về Amazon S3 <br> - Xây dựng AWS WAF Web ACL kết hợp IP Set (Blacklist) <br> - Phát triển Lambda phân tích log S3 nhận diện IP tấn công (lỗi 404) vượt ngưỡng <br> - Cấu hình Lambda tự động cập nhật IP vào WAF IP Set (403 Forbidden) | 14/05/2026 | 14/05/2026 | |
| 6   | - Triển khai Snort IDS trên EC2 Ubuntu, kết hợp ALB và AWS WAF <br> - Xây dựng luồng SOAR từ CloudWatch Logs → Lambda, tự động chặn IP tấn công trên WAF thời gian thực <br> - Cấu hình trích xuất Header X-Forwarded-For từ log Nginx để nhận diện IP thật của kẻ tấn công | 15/05/2026 | 15/05/2026 | |

### Kết quả đạt được tuần 4:

* Hoàn thiện bản vẽ kiến trúc hệ thống chuẩn AWS 2026 trên draw.io, thể hiện rõ ranh giới mạng và 4 luồng dữ liệu cốt lõi.
* Triển khai thành công luồng Log-Driven: tự động bóc tách Access Logs từ ALB trên S3, nhận diện IP quét dò (404) và cập nhật WAF IP Set.
* Tích hợp thành công Snort IDS; giải quyết bài toán ẩn IP của Load Balancer bằng X-Forwarded-For, đẩy log qua CloudWatch để Lambda chặn IP thật.
* WAF tự động chặn nguồn truy cập độc hại (HTTP 403). Lab được dọn dẹp an toàn, không phát sinh chi phí ngoài dự kiến.
