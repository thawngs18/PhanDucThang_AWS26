---
title: "Worklog Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Xây dựng hoàn chỉnh nền tảng giao diện (Frontend) sử dụng React.js và thư viện React Flow để vẽ sơ đồ mạng.
* Khởi tạo và cấu hình thành công máy chủ xử lý logic (Backend) bằng Python và framework FastAPI.
* Tích hợp thành công API Google Gemini vào hệ thống Backend để chuẩn bị cho các tác vụ phân tích AI.
* Hoàn thiện luồng kết nối API hai chiều (Frontend ↔ Backend), cho phép gửi cấu trúc mạng dưới dạng JSON và nhận phản hồi.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Tạo tệp `.gitignore` bảo vệ tệp nhạy cảm, bỏ qua môi trường cục bộ <br> - Khởi tạo Git Repository và thiết lập cấu trúc phân nhánh (dev, frontend-ui, backend-api) <br> - Liên kết kho cục bộ với GitHub và push mã nguồn khởi tạo | 15/06/2026 | 15/06/2026 | <https://git-scm.com/doc> |
| 3   | - Tạo và kích hoạt môi trường ảo Python (venv), thiết lập `requirements.txt` <br> - Lập trình `main.py` khởi tạo máy chủ FastAPI chạy trên Uvicorn <br> - Cấu hình CORSMiddleware cho phép Frontend gọi API không bị lỗi CORS | 16/06/2026 | 16/06/2026 | <https://fastapi.tiangolo.com/> |
| 4   | - Dùng Vite khởi tạo bộ khung Frontend React, cài đặt `reactflow` <br> - Làm sạch mã nguồn mặc định, cấu hình canvas trống full-screen <br> - Xử lý ESLint warnings về biến/thư viện chưa sử dụng | 17/06/2026 | 17/06/2026 | <https://vitejs.dev/guide/> |
| 5   | - Thiết kế thành phần Sidebar chứa thiết bị mạng (Firewall, Router, Server, PC) <br> - Áp dụng HTML Drag and Drop API kết hợp React Flow để kéo thả thiết bị vào canvas <br> - Xây dựng Panel điều khiển (góc trên phải): Gen AI, Save, Scan Attack | 18/06/2026 | 18/06/2026 | <https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API> |
| 6   | - Cài đặt `google-generativeai` vào Backend, bảo mật API key qua `.env` <br> - Xử lý sự kiện nút Save: trích xuất dữ liệu đồ thị thành JSON bằng `toObject()` <br> - Viết hàm bất đồng bộ `fetch()` gửi JSON tới cổng 8000 và hiển thị phân tích AI trả về | 19/06/2026 | 19/06/2026 | <https://ai.google.dev/docs> <br> <https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API> |

### Kết quả đạt được tuần 9:

* Giao diện người dùng hoạt động trơn tru với tính năng thiết kế kiến trúc mạng bằng thao tác kéo thả trực quan.
* Dữ liệu mạng được thu thập và chuyển đổi thành công sang JSON chuẩn, đáp ứng yêu cầu đầu vào của mô hình ngôn ngữ lớn.
* Máy chủ FastAPI sẵn sàng lắng nghe và xử lý HTTP, kết nối thành công với Google AI Studio.
* Luồng dữ liệu từ người dùng → Frontend → Backend → AI → trả về giao diện hoạt động ổn định.
