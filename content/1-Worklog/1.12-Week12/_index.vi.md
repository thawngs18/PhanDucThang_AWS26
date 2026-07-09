---
title: "Worklog tuần 12"
date: 2026-06-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

* Triển khai frontend lên AWS (S3 + CloudFront).
* Kết nối hoàn chỉnh frontend-backend, đảm bảo CORS hoạt động.
* Tích hợp các dịch vụ AI (Gemini) và kiểm tra toàn bộ luồng chức năng.

### Công việc cần làm trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | --------- | ------------ | --------------- | ------------------ |
| 2 | - Xây dựng stack `CloudNexus-Secrets`: tạo Secrets Manager lưu `GOOGLE_API_KEY` <br> - Xây dựng stack `CloudNexus-Backend`: tạo Lambda function với FastAPI (ASGI qua Mangum), API Gateway HTTP API, IAM roles <br> - Cấu hình Lambda Layer chứa Python dependencies (`fastapi`, `mangum`, `google-genai`) <br> - Deploy lần đầu cả hai stack lên AWS <br> - Khởi tạo cấu trúc frontend: Vite + React + React Flow + Zustand + TailwindCSS <br> - Cấu hình build script triển khai frontend lên S3 bucket <br> - Deploy S3 bucket và thiết lập CloudFront distribution phục vụ frontend | 06/06/2026 | 06/06/2026 | <https://docs.aws.amazon.com/cdk/api/v2/python/> <br> <https://docs.python.org/3/library/asyncio.html> <br> <https://github.com/jmaddock/lambda-pipeline> |
| 3 | - Sửa lỗi CORS preflight (`OPTIONS`) request từ CloudFront bị API Gateway trả `400 Bad Request` <br> - Loại bỏ CORS config khỏi API Gateway để tránh xử lý trùng với FastAPI `CORSMiddleware` <br> - Bổ sung handler `@app.options` trong FastAPI xử lý preflight <br> - Cập nhật `allow_origins` trong `CORSMiddleware` với CloudFront URL và localhost <br> - Thêm Lambda Layer mới với đầy đủ dependencies <br> - Rebuild và redeploy Lambda function | 07/06/2026 | 07/06/2026 | <https://vitejs.dev/guide/build> <br> <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html> |
| 4 | - Cấu hình `VITE_API_URL` trong `.env.production` trỏ đến API Gateway endpoint production <br> - Thiết lập build configuration cho Vite production mode <br> - Deploy lại frontend bundle đã build lên S3, invalidation CloudFront cache <br> - Kiểm tra kết nối frontend từ CloudFront URL tới backend API | 08/06/2026 | 08/06/2026 | <https://fastapi.tiangolo.com/tutorial/first-steps/> <br> <https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS> |
| 5 | - Hoàn thiện FastAPI backend: thêm endpoint `GET /` trả metadata API <br> - Verify tất cả endpoint chạy đúng: `/api/health`, `/api/ai/generate`, `/api/topology/validate`, `/api/simulation/scan` <br> - Kiểm tra CORS headers trên tất cả endpoint từ CloudFront origin <br> - Test đầu cuối luồng AI generate topology từ frontend | 09/06/2026 | 09/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |
| 6 | - Tích hợp và kiểm tra toàn bộ luồng chức năng: AI generate topology, topology validation, simulation scan, simulation run, simulation with defense <br> - Test thực tế từ giao diện frontend trên CloudFront: tất cả chức năng hoạt động ổn định <br> - Fix endpoint `simulation/with-defense` đảm bảo trả đầy đủ `attack_steps` và `defense_mechanisms` <br> - Tối ưu Lambda function name và CloudFormation outputs | 10/06/2026 | 10/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |

### Kết quả đạt được tuần 12:

* Backend đã triển khai hoàn chỉnh trên AWS Lambda với FastAPI, chạy thông qua Mangum adapter.
* API Gateway HTTP API đã hoạt động, expose đầy đủ endpoint cho frontend gọi qua CloudFront.
* Secrets Manager lưu trữ `GOOGLE_API_KEY` an toàn; Lambda đọc qua IAM grant read.
* Frontend đã deploy lên S3 và phục vụ qua CloudFront CDN.
* CORS đã được xử lý đúng qua FastAPI `CORSMiddleware`, cho phép request từ CloudFront origin.
* Lambda Layer chứa `fastapi`, `mangum`, `google-genai` đảm bảo Lambda có đầy đủ dependencies.
* Toàn bộ luồng từ frontend đến backend hoạt động ổn định: AI generate → topology validate → simulation scan → simulation run → simulation with defense.
* Infrastructure được quản lý hoàn toàn qua AWS CDK, có thể redeploy bất kỳ lúc nào.
