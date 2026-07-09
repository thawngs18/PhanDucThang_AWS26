---
title: "Worklog tuần 12"
date: 2026-06-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

* Triển khai frontend lên AWS bằng S3 và CloudFront.
* Hoàn thiện tích hợp frontend-backend với cấu hình CORS hoạt động ổn định.
* Tích hợp dịch vụ AI và kiểm tra toàn bộ luồng chức năng end-to-end.

### Các công việc cần triển khai trong tuần này:

|| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|| --- | --------- | ------------ | --------------- | ------------------ |
|| 2   | - Xây dựng stack `CloudNexus-Secrets`: tạo Secrets Manager lưu `GOOGLE_API_KEY` <br> - Xây dựng stack `CloudNexus-Backend`: tạo Lambda function với FastAPI qua Mangum, API Gateway HTTP API và IAM roles <br> - Cấu hình Lambda Layer chứa Python dependencies (`fastapi`, `mangum`, `google-genai`) <br> - Deploy lần đầu cả hai stack lên AWS <br> - Khởi tạo cấu trúc frontend với Vite + React + React Flow + Zustand + TailwindCSS <br> - Cấu hình build script để triển khai frontend lên S3 bucket <br> - Deploy S3 bucket và thiết lập CloudFront distribution phục vụ frontend | 06/06/2026 | 06/06/2026 | <https://docs.aws.amazon.com/cdk/api/v2/python/> |
|| 3   | - Fix CORS preflight `OPTIONS` bị API Gateway trả về `400 Bad Request` qua CloudFront <br> - Loại bỏ CORS config khỏi API Gateway để tránh xử lý trùng với FastAPI `CORSMiddleware` <br> - Bổ sung `@app.options` handler trong FastAPI xử lý preflight <br> - Cập nhật `allow_origins` trong `CORSMiddleware` với URL CloudFront và localhost <br> - Thêm Lambda Layer mới chứa đầy đủ dependencies <br> - Rebuild và redeploy Lambda function | 07/06/2026 | 07/06/2026 | <https://vitejs.dev/guide/build> |
|| 4   | - Cấu hình `VITE_API_URL` trong `.env.production` trỏ đến endpoint API Gateway production <br> - Thiết lập build configuration cho Vite production mode <br> - Deploy lại frontend bundle lên S3 và invalidation cache CloudFront <br> - Kiểm tra kết nối frontend từ URL CloudFront đến backend API | 08/06/2026 | 08/06/2026 | <https://fastapi.tiangolo.com/tutorial/first-steps/> |
|| 5   | - Hoàn thiện FastAPI backend: thêm endpoint `GET /` trả metadata API <br> - Verify tất cả endpoint: `/api/health`, `/api/ai/generate`, `/api/topology/validate`, `/api/simulation/scan` <br> - Kiểm tra CORS headers trên tất cả endpoint từ CloudFront origin <br> - Test luồng AI generate topology từ frontend | 09/06/2026 | 09/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |
|| 6   | - Tích hợp và kiểm tra toàn bộ luồng chức năng: AI generate topology, topology validation, simulation scan, simulation run và simulation with defense <br> - Test thực tế từ giao diện frontend trên CloudFront để đảm bảo tất cả chức năng hoạt động ổn định <br> - Fix endpoint `simulation/with-defense` đảm bảo trả đầy đủ `attack_steps` và `defense_mechanisms` <br> - Tối ưu Lambda function name và CloudFormation outputs | 10/06/2026 | 10/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |

### Kết quả đạt được tuần 12:

* Backend đã triển khai hoàn chỉnh trên AWS Lambda với FastAPI, chạy thông qua Mangum adapter.
* API Gateway HTTP API đã hoạt động, expose đầy đủ endpoint cho frontend gọi qua CloudFront.
* Secrets Manager lưu trữ `GOOGLE_API_KEY` an toàn, Lambda đọc qua IAM grant read.
* Frontend đã deploy lên S3 và phục vụ qua CloudFront CDN.
* CORS đã được xử lý đúng qua FastAPI `CORSMiddleware`, cho phép request từ CloudFront origin.
* Lambda Layer chứa `fastapi`, `mangum` và `google-genai` đảm bảo Lambda có đầy đủ dependencies.
* Toàn bộ luồng từ frontend đến backend hoạt động ổn định: AI generate → topology validate → simulation scan → simulation run → simulation with defense.
* Infrastructure được quản lý hoàn toàn qua AWS CDK, có thể redeploy bất kỳ lúc nào.
