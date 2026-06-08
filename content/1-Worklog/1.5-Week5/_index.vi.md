---
title: "Worklog Tuần 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Xây dựng hệ thống phản ứng tự động: Nghiên cứu và triển khai thực tế mô hình SOAR trên AWS để tối ưu hóa thời gian ngăn chặn tấn công.
* Làm chủ kỹ thuật giám sát hạ tầng: Hiểu sâu về trích xuất log, bảo toàn IP client qua ALB/Nginx và nhận diện tấn công tầng ứng dụng.
* Tiếp cận quy trình vận hành SOC: Tìm hiểu nền tảng SIEM (Splunk), tích hợp dữ liệu đám mây và tư duy Threat Hunting.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Nghiên cứu phương thức rà quét tự động của Nikto, Nmap <br> - Tìm hiểu phân tích gói tin Layer 7 và kỹ thuật đối sánh User-Agent của Snort IDS <br> - Phân tích cấu trúc Alert Logs trên Linux để xác định trường dữ liệu cho chuỗi tự động hóa | 18/05/2026 | 18/05/2026 | <https://nmap.org/book/> <br> <https://cirt.net/Nikto2> <br> <https://snort.org/documents> |
| 3   | - Nghiên cứu ảnh hưởng ALB lên địa chỉ mạng và giải pháp bảo toàn IP qua X-Forwarded-For <br> - Tìm hiểu trích xuất log thời gian thực bằng Regex trong AWS Lambda <br> - Xây dựng lý thuyết vòng lặp phản ứng khép kín qua API kết nối CloudWatch và AWS WAF | 19/05/2026 | 19/05/2026 | <https://docs.aws.amazon.com/waf/> <br> <https://docs.aws.amazon.com/lambda/> <br> <https://docs.aws.amazon.com/elasticloadbalancing/> |
| 4   | - Cấu hình Nginx trích xuất IP thật (X-Forwarded-For) và xử lý CloudWatch Agent ổn định <br> - Lập trình luồng SOAR CloudWatch → Lambda → WAF, thông báo qua Amazon SNS <br> - Kiểm thử chặn Nikto, SQLMap (403 Forbidden); hoàn thiện sơ đồ kiến trúc 4 luồng trên draw.io | 20/05/2026 | 20/05/2026 | |
| 5   | - Nắm bắt bản chất SIEM của Splunk: thu thập, lập chỉ mục và Correlation <br> - Nghiên cứu tích hợp AWS × Splunk qua Kinesis Firehose hoặc Splunk Add-on <br> - Tìm hiểu tư duy Threat Hunting và truy vết IoC trên đám mây | 21/05/2026 | 21/05/2026 | <https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/send-aws-waf-logs-to-splunk-by-using-aws-firewall-manager-and-amazon-data-firehose.html> <br> <https://www.splunk.com/en_us/blog/security/cloudtrail-data-security-operations.html> |
| 6   | - Phân tích kịch bản Boss of the SOC (BOTS), làm quen ngôn ngữ SPL <br> - Khảo sát quy trình vận hành SOC L1: đánh giá rủi ro và lọc False Positives <br> - Định hướng tích hợp Splunk làm "mắt thần" giám sát cho kiến trúc SOAR hiện tại | 22/05/2026 | 22/05/2026 | <https://andickinson.github.io/blog/splunk-boss-of-the-soc-v1/> <br> <https://www.splunk.com/en_us/blog/security/cloudtrail-data-security-operations.html> |

### Kết quả đạt được tuần 5:

* Triển khai thành công chuỗi SOAR: tự động chặn (403 Forbidden) các cuộc rà quét từ Nikto, SQLMap qua CloudWatch, Lambda và AWS WAF.
* Tối ưu dữ liệu giám sát: xử lý truy xuất IP thật qua X-Forwarded-For và cấu hình CloudWatch Agent ổn định.
* Nắm vững kiến thức SIEM & Integration: Splunk (Indexing, Correlation), Kinesis Firehose và ngôn ngữ SPL.
* Hoàn thiện tư duy kiến trúc: thiết kế sơ đồ 4 luồng chuẩn AWS trên draw.io, thể hiện luồng dữ liệu và cơ chế phản ứng bảo mật.
