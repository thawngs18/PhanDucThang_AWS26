---
title : "Deploy API Stack"
date : "2025-10-10"
weight : 9
chapter : false
pre : " <b> Step 9 </b> "
---
# Step 9: Deploy API Stack

---

## Mô Tả

Tạo API Gateway, Lambda (FastAPI + Mangum), và Secrets Manager.

---

## Các Lệnh

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO\infrastructure
cdk deploy CloudNexus-Backend --require-approval never
```

---

## Kết Quả Mong Đợi

```
✅  CloudNexus-Backend
Outputs:
  CloudNexus-Backend.ApiUrl = https://<API_ID>.execute-api.ap-southeast-1.amazonaws.com/prod/
  CloudNexus-Backend.FunctionName = CloudNexus-BackendHandler-<SUFFIX>
```

---

## Tài Nguyên Đã Tạo

| Tài nguyên | AWS Service | Mục đích |
|------------|-------------|----------|
| `CloudNexus-BackendHandler` | Lambda | FastAPI backend |
| `CloudNexus-PythonDeps` | Layer | Python dependencies |
| `CloudNexus-API` | API Gateway | REST endpoint |
| `CloudNexus-Secrets` | Secrets Manager | Lưu trữ API key |

---

## Hướng Dẫn Chụp Ảnh Xác Minh

📸 **Ảnh 1: CDK Deploy API Stack Output**

**Cách chụp:**
1. Chạy lệnh deploy
2. Chụp ảnh output thành công với Outputs

**Cần xác minh:**
- ✅ dấu tích cho CloudNexus-Backend
- API URL được hiển thị

---

📸 **Ảnh 2: API Gateway trong AWS Console**

**Cách chụp:**
1. Vào AWS Console → API Gateway
2. Tìm API của bạn
3. Chụp ảnh trang chi tiết API

**Cần xác minh:**
- API type: HTTP API
- Stages: prod
- Routes: /api/*

---

📸 **Ảnh 3: Lambda Function trong AWS Console**

**Cách chụp:**
1. Vào AWS Console → Lambda
2. Tìm `CloudNexus-BackendHandler`
3. Chụp ảnh cấu hình function

**Cần xác minh:**
- Runtime: Python 3.12
- Memory: 512 MB
- Layers: CloudNexus-PythonDeps đã attach
