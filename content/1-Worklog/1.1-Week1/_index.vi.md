---
title: "Worklog Tuần 1"
date: 2026-04-17
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1:

* Tìm hiểu quy định, văn hóa doanh nghiệp, hoàn tất thủ tục với giảng viên hướng dẫn và thiết lập quy trình làm việc chung với nhóm FCJ.
* Nắm bắt các chính sách của AWS Free Tier 2025, nhận diện các dịch vụ dễ phát sinh chi phí và xây dựng phương án kiểm soát ngân sách an toàn.
* Xây dựng hệ thống quản lý định danh (IAM) bảo mật cao, áp dụng triệt để nguyên tắc "Quyền tối thiểu" (Least Privilege) và hạn chế sử dụng tài khoản Root.
* Nắm vững kiến thức nền tảng về kiến trúc mạng đám mây (VPC, Subnet, IGW, NAT Gateway) và các rào chắn bảo mật mạng (Security Group, Network ACLs).
* Thực hành tự xây dựng một hạ tầng mạng ảo (VPC) độc lập và triển khai máy chủ (EC2) trên nền tảng AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 6   | - Gặp gỡ, làm quen và tạo mối quan hệ với các thành viên trong đơn vị <br> - Đọc kỹ các quy định, văn hóa doanh nghiệp và nội quy làm việc tại đơn vị thực tập | 17/04/2026 | 17/04/2026 | |
| 2   | - Liên hệ và chính thức xác nhận thông tin thực tập với GVHD <br> - Chủ động kết nối, lập nhóm và phân chia vai trò với các thành viên FCJ <br> - Thống nhất kênh liên lạc và công cụ quản lý công việc | 20/04/2026 | 20/04/2026 | |
| 3   | - Đọc tài liệu cập nhật về AWS Free Tier 2025 <br> - Lên danh sách và ghi chú các dịch vụ có nguy cơ phát sinh chi phí cao để phòng tránh <br> - Đăng ký tài khoản AWS và hoàn tất 5 task cơ bản để nhận $200 Credit <br> - Thiết lập hệ thống cảnh báo chi phí để kiểm soát ngân sách an toàn | 21/04/2026 | 21/04/2026 | <https://000001.awsstudygroup.com/> |
| 4   | - Thiết lập bộ ba User, Group và Role <br> - Sử dụng Policy để định nghĩa hành động được phép hoặc bị cấm dựa trên nguyên tắc "Quyền tối thiểu" <br> - Không dùng tài khoản Root cho việc hàng ngày và bắt buộc kích hoạt xác thực đa lớp cho tài khoản Admin <br> - Triển khai tính năng Switch Role để giúp OperatorUser biến hình thành Admin khi cần sửa hệ thống <br> - Khởi tạo thành công AdminGroup, AdminUser, OperatorUser và gán chính sách AllowSwitchAdminPolicy | 22/04/2026 | 22/04/2026 | <https://000002.awsstudygroup.com/> |
| 5   | - Tìm hiểu về Subnets, Route Table, Internet Gateway và NAT Gateway <br> - Tìm hiểu cách hoạt động của Security Group, Network ACLs và công cụ VPC Resource Map | 23/04/2026 | 23/04/2026 | <https://000003.awsstudygroup.com/> |
| 6   | - Tạo VPC, Subnet, Internet Gateway, Route Table, Security Group và bật tính năng giám sát VPC Flow Logs <br> - **Thực hành:** Khởi tạo máy chủ EC2 và kiểm tra kết nối thành công từ VSCode vào máy chủ | 24/04/2026 | 24/04/2026 | <https://000003.awsstudygroup.com/> |

### Kết quả đạt được tuần 1:

* Đã xác nhận xong thông tin thực tập, hoàn thiện cơ cấu nhóm FCJ, phân chia rõ vai trò và thống nhất được các công cụ quản lý, liên lạc.
* Đăng ký thành công tài khoản AWS, hoàn tất 5 task cơ bản để nhận $200 Credit và thiết lập xong hệ thống cảnh báo chi phí (Billing Alarm).
* Khởi tạo thành công bộ ba IAM (AdminGroup, AdminUser, OperatorUser), bắt buộc dùng xác thực đa lớp (MFA) cho Admin và cấu hình thành công tính năng Switch Role (AllowSwitchAdminPolicy) cho OperatorUser.
* Triển khai hoàn thiện hạ tầng mạng gồm VPC, Subnet, Internet Gateway, Route Table, Security Group và đã kích hoạt giám sát VPC Flow Logs.
* Khởi tạo thành công máy chủ ảo EC2 trên mạng vừa tạo và thực hiện kết nối (Test Connection) thành công từ VSCode vào máy chủ.
