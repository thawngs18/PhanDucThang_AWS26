---
title: "Worklog Tuần 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Nắm vững kiến thức nền tảng về AWS Step Functions và cách tổ chức workflow theo state machine.
* Xây dựng và mô tả ý tưởng CloudSec Nexus theo hướng "thiết kế + mô phỏng bảo mật đám mây hỗ trợ GenAI", nổi bật bản vẽ có hành vi và có thể diễn tập tấn công.
* Hoàn thiện khung kiến trúc hệ thống từ tổng quan đến chi tiết (frontend, backend mô phỏng, AI agents, bất đồng bộ, kho tri thức bảo mật) để sẵn sàng triển khai.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Tổng hợp nội dung AWS Step Functions: workflow, state machine, Lambda điều phối dịch vụ <br> - Phác thảo mục tiêu học tập và lộ trình workshop (chuẩn bị, dispatch, cải thiện, xử lý lỗi, song song, dọn tài nguyên) <br> - Ghi chú các state quan trọng (Task, Choice, Parallel, Pause/Resume với waitForTaskToken) | 01/06/2026 | 01/06/2026 | <https://000047.awsstudygroup.com/> |
| 3   | - Viết mô tả ý tưởng CloudSec Nexus: thiết kế + mô phỏng bảo mật đám mây bằng GenAI <br> - Xác định 2 khối động cơ (GenAI Core/Bedrock và Simulation Engine), phân vai "kiến trúc sư + thợ săn mối đe dọa" và "trọng tài mô phỏng" <br> - Hoàn thiện giá trị cho cá nhân và doanh nghiệp | 02/06/2026 | 02/06/2026 | |
| 4   | - Viết tài liệu kiến trúc tổng thể: frontend canvas, API gateway, simulation engine, AI agents, kho tri thức bảo mật <br> - Mô tả nguyên tắc bất đồng bộ, cơ chế "phiếu chờ" và cập nhật thời gian thực <br> - Đặc tả frontend (canvas workspace, state manager, animation rendering) | 03/06/2026 | 03/06/2026 | |
| 5   | - Đặc tả backend "phiên dịch + trọng tài": Data Sanitizer kiểm duyệt đầu ra AI <br> - Mô tả Dynamic Simulation Engine: tick-rate, đồ thị có hướng, va chạm với thiết bị phòng thủ <br> - Định nghĩa AI agents (Architect, Threat Hunter, SOAR Agent) kèm nhiệm vụ và phạm vi đầu ra | 04/06/2026 | 04/06/2026 | |
| 6   | - Viết luồng dữ liệu cho threat modeling và live attack workflow <br> - Thiết kế mô hình dữ liệu (Node/Edge/Playbook entity) đồng bộ giữa giao diện, server và AI <br> - Bổ sung chiến lược chống lỗi, tối ưu hiệu năng và roadmap phát triển | 05/06/2026 | 05/06/2026 | |

### Kết quả đạt được tuần 7:

* Bộ ghi chú Step Functions được hệ thống hóa: mục tiêu học tập, các state quan trọng (Task/Choice/Parallel/Pause-Resume), lộ trình workshop từ chuẩn bị đến dọn tài nguyên.
* Tài liệu ý tưởng CloudSec Nexus hoàn chỉnh: định nghĩa ứng dụng, cách vận hành (GenAI Core + Simulation Engine), giá trị và kịch bản minh họa.
* Bản thuyết minh kiến trúc đầy đủ: mô hình phân tầng, đặc tả frontend/backend, AI agents, luồng threat modeling và live simulation, mô hình dữ liệu và chiến lược tối ưu.
