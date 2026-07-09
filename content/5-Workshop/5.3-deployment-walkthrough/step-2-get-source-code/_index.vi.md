---
title : "Tải mã nguồn"
date : "2025-10-10"
weight : 2
chapter : false
pre : " <b> Step 2 </b> "
---
# Step 2: Tải Mã Nguồn

---

## Các Lệnh

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO
Get-ChildItem -Directory
```

---

## Cấu Trúc Dự Án

```
DEMO/
├── src/                    # React frontend source (Vite)
│   ├── components/
│   ├── hooks/
│   │   ├── useAI.js        # Tích hợp AI
│   │   └── useSimulation.js # Logic mô phỏng
│   ├── store/
│   │   └── useStore.js     # Quản lý state
│   └── api.js
├── backend/                # FastAPI backend
│   ├── main.py             # FastAPI app
│   ├── ai_service.py       # Tích hợp Gemini
│   ├── handler.py          # Lambda entry (Mangum)
│   ├── .env                # API keys (KHÔNG commit)
│   └── requirements.txt
├── infrastructure/         # AWS CDK code
│   ├── app.py              # CDK entry point
│   ├── stacks/
│   │   ├── frontend_stack.py    # S3 + CloudFront
│   │   ├── backend_stack.py    # Lambda + API Gateway
│   │   └── secrets_stack.py    # Secrets Manager
│   ├── cdk.json
│   └── requirements.txt
├── scripts/
│   ├── deploy.ps1          # Deployment Windows
│   ├── deploy.sh           # Deployment Mac/Linux
│   ├── push-secret.ps1     # Đẩy API key lên Secrets Manager
│   └── teardown.ps1        # Xóa AWS resources
├── dist/                   # Frontend build output
└── package.json
```

---

## Hướng Dẫn Chụp Ảnh Xác Minh

📸 **Ảnh 1: Cấu Trúc Thư Mục Dự Án**

**Cách chụp:**
1. Mở PowerShell
2. Di chuyển đến thư mục `DEMO`
3. Chạy `Get-ChildItem -Directory`
4. Chụp ảnh màn hình danh sách thư mục

**Kết quả mong đợi:** Bạn sẽ thấy các thư mục như `src`, `backend`, `infrastructure`, `scripts`, `dist`.
