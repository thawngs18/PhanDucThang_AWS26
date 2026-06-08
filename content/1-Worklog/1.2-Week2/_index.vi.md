---
title: "Worklog Tuần 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Nghiên cứu, so sánh các phương án triển khai IDS/IPS để lựa chọn giải pháp bảo mật tối ưu nhất cho hạ tầng đám mây.
* Nắm vững cơ sở lý thuyết để thiết lập hệ thống tự động phản ứng (SOAR) nhằm bảo vệ an toàn cho tài nguyên AWS.
* Hiểu rõ luồng hoạt động tự động và chức năng của từng thành phần trong hệ thống như GuardDuty, EventBridge, Lambda và WAF.
* Nâng cao kỹ năng lập trình (đặc biệt là Python) và phát triển tư duy thiết kế hệ thống bảo mật thông minh, hiện đại.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Tìm hiểu tiêu chí đánh giá các giải pháp bảo mật đám mây (nền tảng, tốc độ, quản trị, mở rộng, chi phí) <br> - Phân tích đặc điểm của Hướng 1: Open Source (Suricata trên EC2) <br> - Phân tích đặc điểm của Hướng 2: Cloud-Native (AWS Firewall/GuardDuty) <br> - Phân tích đặc điểm của Hướng 3: Tự động hóa (SOAR - Lambda) | 27/04/2026 | 27/04/2026 | <https://docs.aws.amazon.com/wellarchitected/latest/framework/security.html> |
| 3   | - Phân tích lý do chọn Hướng 3 (SOAR) làm trọng tâm cho dự án <br> - Tìm hiểu khả năng phản ứng tức thì và tính năng giảm sai sót so với con người trực log <br> - Nghiên cứu cơ chế tiết kiệm credit dựa trên mô hình Serverless của Lambda <br> - Tìm hiểu xu hướng bảo mật tiên tiến (Security Automation) | 28/04/2026 | 28/04/2026 | <https://docs.aws.amazon.com/wellarchitected/latest/framework/security.html> |
| 4   | - Tìm hiểu vai trò "Mắt thần" của Amazon GuardDuty <br> - Nghiên cứu cách phát hiện các hành vi lạ (đăng nhập sai, dữ liệu bất thường) <br> - Tìm hiểu vai trò "Hệ thần kinh" của Amazon EventBridge <br> - Phân tích cơ chế truyền tin báo động từ GuardDuty đến các bộ phận khác | 29/04/2026 | 29/04/2026 | <https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_finding-types-active.html> |
| 5   | - Tìm hiểu vai trò "Bộ não" của AWS Lambda <br> - Phân tích luồng xử lý: dùng code Python tiếp nhận báo động và ra quyết định chặn IP <br> - Tìm hiểu vai trò "Chốt chặn" của AWS WAF <br> - Nghiên cứu cơ chế chặn lọc IP bằng cách sử dụng danh sách đen (Blacklist-IP-Set) | 30/04/2026 | 30/04/2026 | <https://aws.amazon.com/vi/blogs/security/how-to-use-amazon-guardduty-and-aws-waf-v2-to-automatically-block-suspicious-hosts/> |
| 6   | - Tìm hiểu nguyên lý "Chặn có thời hạn" (TTL) giúp tránh làm chậm hệ thống <br> - Phân tích cơ chế tự động xóa IP để tránh chặn nhầm người dùng thật <br> - Tổng hợp sơ đồ luồng vận hành của một sự cố bảo mật tự động <br> - Tìm hiểu lý thuyết về giám sát qua VPC Flow Logs và AWS Budgets | 01/05/2026 | 01/05/2026 | <https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs-records-examples.html> |

### Kết quả đạt được tuần 2:

* Hiểu rõ tường tận luồng vận hành của một sự cố bảo mật trên môi trường đám mây từ lúc phát hiện đến khi xử lý.
* Có đủ kiến thức nền tảng để xây dựng thành công kịch bản tự động hóa giúp bảo vệ hệ thống liên tục 24/7.
* Nắm được phương pháp kiểm soát chi phí vận hành thông qua việc giám sát tài nguyên thông minh, bao gồm việc biết cách cấu hình AWS Budgets ở mức $10 để bảo vệ hạn mức credit của tài khoản.
* Nắm được các lưu ý vận hành quan trọng, cụ thể là việc luôn kiểm tra VPC Flow Logs để đảm bảo hệ thống không bỏ sót bất kỳ cuộc tấn công nào.
