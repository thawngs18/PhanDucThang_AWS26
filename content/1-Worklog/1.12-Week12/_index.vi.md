---
title: "Worklog tuần 12"
date: 2026-01-01
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

* Triển khai frontend lên AWS thông qua S3 và CloudFront.
* Hoàn thiện kết nối frontend-backend và đảm bảo CORS hoạt động end-to-end.
* Tích hợp các dịch vụ AI với Gemini và kiểm tra toàn bộ luồng chức năng.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --------- | ------------ | --------------- | ------------------ |
| 2   | - Xây dựng stack `CloudNexus-Secrets`: tạo Secrets Manager và lưu `GOOGLE_API_KEY` <br> - Xây dựng stack `CloudNexus-Backend`: tạo Lambda function với FastAPI thông qua Mangum, HTTP API Gateway và IAM roles <br> - Cấu hình Lambda Layer chứa các dependencies Python bao gồm FastAPI, Mangum và Google Generative AI <br> - Thực hiện lần deploy đầu tiên cả hai stack lên AWS <br> - Khởi tạo cấu trúc frontend với Vite, React, React Flow, Zustand và TailwindCSS <br> - Cấu hình build script để triển khai frontend lên S3 <br> - Deploy S3 bucket và thiết lập CloudFront distribution cho frontend | 06/06/2026 | 06/06/2026 | <https://docs.aws.amazon.com/cdk/api/v2/python/> <br> <https://docs.python.org/3/library/asyncio.html> <br> <https://github.com/jmaddock/lambda-pipeline> |
| 3   | - Fix CORS preflight OPTIONS request từ CloudFront bị API Gateway trả 400 Bad Request <br> - Loại bỏ CORS config khỏi API Gateway để tránh xử lý trùng lặp với FastAPI CORSMiddleware <br> - Bổ sung `@app.options` handler trong FastAPI để xử lý preflight request <br> - Cập nhật `allow_origins` trong CORSMiddleware với CloudFront URL và localhost <br> - Thêm Lambda Layer mới với đầy đủ dependencies <br> - Rebuild và redeploy Lambda function | 07/06/2026 | 07/06/2026 | <https://vitejs.dev/guide/build> <br> <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html> |
| 4   | - Cấu hình `VITE_API_URL` trong `.env.production` trỏ đến API Gateway endpoint production <br> - Thiết lập build configuration cho Vite production mode <br> - Redeploy frontend bundle đã build lên S3 và invalidate CloudFront cache <br> - Kiểm tra kết nối từ frontend trên CloudFront đến backend API | 08/06/2026 | 08/06/2026 | <https://fastapi.tiangolo.com/tutorial/first-steps/> <br> <https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS> |
| 5   | - Hoàn thiện FastAPI backend bằng cách thêm endpoint GET `/` trả về metadata API <br> - Verify tất cả endpoint chạy đúng: `/api/health`, `/api/ai/generate`, `/api/topology/validate` và `/api/simulation/scan` <br> - Kiểm tra CORS headers trên tất cả endpoint từ CloudFront origin <br> - Test end-to-end luồng AI generate topology từ frontend | 09/06/2026 | 09/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |
| 6   | - Tích hợp và kiểm tra toàn bộ luồng chức năng: AI generate topology, topology validation, simulation scan, simulation run và simulation with defense <br> - Test thực tế từ giao diện frontend trên CloudFront để đảm bảo tất cả chức năng hoạt động ổn định <br> - Fix endpoint `simulation/with-defense` để trả đầy đủ `attack_steps` và `defense_mechanisms` <br> - Tối ưu Lambda function name và CloudFormation outputs | 10/06/2026 | 10/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |

### Kết quả đạt được tuần 12:

* Backend đã triển khai hoàn chỉnh trên AWS Lambda với FastAPI, chạy thông qua Mangum adapter.
* API Gateway HTTP API đã hoạt động và expose đầy đủ endpoint cho frontend gọi qua CloudFront.
* Secrets Manager lưu trữ `GOOGLE_API_KEY` an toàn, Lambda đọc thông qua IAM grant read.
* Frontend đã deploy lên S3 và phục vụ qua CloudFront CDN.
* CORS đã được xử lý đúng qua FastAPI CORSMiddleware, cho phép request từ CloudFront origin.
* Lambda Layer chứa FastAPI, Mangum và Google Generative AI đảm bảo Lambda có đầy đủ dependencies.
* Toàn bộ luồng từ frontend đến backend hoạt động ổn định: AI generate → topology validate → simulation scan → simulation run → simulation with defense.
* Infrastructure được quản lý hoàn toàn qua AWS CDK và có thể redeploy bất kỳ lúc nào.
