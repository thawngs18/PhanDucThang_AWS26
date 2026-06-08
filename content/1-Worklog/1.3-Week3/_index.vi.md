---
title: "Worklog Tuần 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Làm chủ hạ tầng: Triển khai và quản trị thành thạo các dịch vụ cốt lõi (EC2, S3, IAM).
* Bảo mật đa lớp: Thiết lập tường lửa (WAF) và hệ thống giám sát tự động (GuardDuty, Lambda).
* Chuẩn hóa tư duy: Áp dụng các khung bảo mật chuẩn quốc tế (NIST CSF, AWS CAF) vào kịch bản thực tế.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Khởi chạy máy chủ ảo EC2 (Windows & Linux) và thiết lập mạng cơ bản <br> - Cài đặt Web Server và triển khai thành công ứng dụng Node.js "AWS User Management" <br> - Sử dụng IAM thiết lập giới hạn triển khai để quản lý chi phí và dọn dẹp tài nguyên | 04/05/2026 | 04/05/2026 | <https://000004.awsstudygroup.com/> |
| 3   | - Tạo S3 Bucket và triển khai ứng dụng Web mẫu để chuẩn bị môi trường <br> - Cấu hình Web ACLs với Managed Rules và Custom Rules để chặn truy cập xấu <br> - Thiết lập ghi nhật ký (logging), kiểm tra quy tắc hoạt động và dọn dẹp tài nguyên | 05/05/2026 | 05/05/2026 | <https://000004.awsstudygroup.com/> |
| 4   | - Kích hoạt GuardDuty để phân tích các cảnh báo về mối nguy hại bảo mật <br> - Cấu hình EventBridge Event Rules để bắt sự kiện từ các cảnh báo của GuardDuty <br> - Kết nối Lambda Function để thiết lập cơ chế khắc phục sự cố tự động | 06/05/2026 | 06/05/2026 | <https://000026.awsstudygroup.com/> |
| 5   | - Áp dụng 5 chức năng Khung NIST CSF (Bảo vệ, Phát hiện, Phản hồi) vào hệ thống <br> - Triển khai 3 góc nhìn bảo mật của Khung AWS CAF (Phòng chống, Truy vết, Phản ứng) <br> - Hệ thống hóa các lớp phòng thủ từ mạng, định danh đến dữ liệu theo tiêu chuẩn AWS | 07/05/2026 | 07/05/2026 | <https://000098.awsstudygroup.com/> |
| 6   | - Thực hành quy trình xử lý khi máy chủ EC2 bị tấn công hoặc xâm nhập <br> - Diễn tập kịch bản lộ thông tin xác thực IAM và cách thu hồi quyền lập tức <br> - Xử lý tình huống bị tuồn quyền IAM để gọi API từ máy chủ bên ngoài và dọn dẹp lab | 08/05/2026 | 08/05/2026 | <https://000098.awsstudygroup.com/> |

### Kết quả đạt được tuần 3:

* Triển khai thành công ứng dụng Node.js trên cả Linux/Windows và biết cách tối ưu chi phí.
* Xây dựng được bộ quy tắc Web ACLs để chặn tấn công tầng ứng dụng và cấu hình ghi log theo dõi.
* Thiết lập được luồng tự động phát hiện và xử lý sự cố (Automated Remediation) thay vì thao tác thủ công.
* Thành thục quy trình xử lý 3 tình huống khẩn cấp (Compromised EC2, Leaked Credentials, IAM Abuse).
