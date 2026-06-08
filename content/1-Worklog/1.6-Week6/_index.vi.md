---
title: "Worklog Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Xác định cấu trúc dữ liệu chuẩn (JSON Schema) và thiết kế luồng giao tiếp API liền mạch giữa frontend, backend và Amazon Bedrock (GenAI).
* Xây dựng nền tảng logic bảo mật: mô hình hóa mối đe dọa (Threat Modeling) và định hình quy trình ứng phó tự động (Playbook/SOAR).
* Thiết kế thuật toán Simulation Engine và giải pháp hiển thị tương tác (React Flow) để mô phỏng kịch bản tấn công – phòng thủ.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Thiết kế JSON Schema biểu diễn hạ tầng bảo mật (VPC, EC2, WAF, Snort IDS) <br> - Tìm hiểu Prompt Engineering trên Amazon Bedrock để AI trả về JSON cấu trúc <br> - Phác thảo API Data Flow giữa frontend, FastAPI backend và Amazon Bedrock | 25/05/2026 | 25/05/2026 | <https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-engineering-guidelines.html> |
| 3   | - Nghiên cứu framework bảo mật (MITRE ATT&CK, STRIDE) để nhận diện rủi ro <br> - Thiết kế bộ prompt "Threat Scan" yêu cầu AI phân tích vector tấn công từ JSON kiến trúc <br> - Lên ý tưởng cơ chế Risk Scoring (cảnh báo đỏ/xanh khi thêm biện pháp phòng thủ) | 26/05/2026 | 26/05/2026 | <https://attack.mitre.org/matrices/enterprise/cloud/> |
| 4   | - Nghiên cứu biểu diễn quy trình tự động hóa bảo mật dưới dạng lưu đồ If/Else <br> - Xác định cấu trúc dữ liệu node Playbook (Read Log → Check Threshold → Block Action) <br> - Đọc tài liệu AWS Step Functions và SOAR để thiết kế UI mô phỏng sát thực tế | 27/05/2026 | 27/05/2026 | <https://docs.aws.amazon.com/security-ir/latest/userguide/security-incident-response-guide.html> |
| 5   | - Tìm hiểu React Flow: render node từ JSON trên canvas kéo thả <br> - Nghiên cứu State Management khi cập nhật thuộc tính node (Allow/Drop trên Firewall) <br> - Đọc hướng dẫn tạo Animation cho Edges để vẽ luồng traffic | 28/05/2026 | 28/05/2026 | <https://reactflow.dev/learn> |
| 6   | - Vẽ System Architecture Diagram tổng thể: từ prompt người dùng đến canvas và cảnh báo <br> - Thiết kế thuật toán Simulation Engine: xác định luồng tấn công bị chặn tại WAF hay đi vào Database <br> - Viết 2–3 kịch bản tấn công (DDoS, Brute-force) kèm kết quả mong đợi | 29/05/2026 | 29/05/2026 | <https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html> |

### Kết quả đạt được tuần 6:

* Hoàn thiện System Architecture Diagram và tài liệu định nghĩa cấu trúc dữ liệu sẵn sàng cho giai đoạn viết code.
* Đóng gói thành công các bộ Prompt Engineering chuyên biệt để AI nhận diện lỗ hổng và sinh lưu đồ ứng phó sự cố.
* Nắm vững kỹ thuật quản lý trạng thái, animation trên frontend và xác định 2–3 kịch bản tấn công thực tế để nghiệm thu sản phẩm.
