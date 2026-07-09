---
title : "Cấu hình Google API Key"
date : "2025-10-10"
weight : 11
chapter : false
pre : " <b> Step 11 </b> "
---
# Step 11: Cấu Hình Google API Key

---

## Tổng Quan

Lambda cần Google API key để gọi Gemini. API key được lưu trong AWS Secrets Manager để bảo mật.

---

## Cách 1: Push Secret Script (Khuyến nghị)

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO
.\scripts\push-secret.ps1
```

Script này đọc `backend/.env` và upload lên Secrets Manager.

---

## Cách 2: Thủ Công qua AWS CLI

```powershell
aws secretsmanager put-secret-value `
  --secret-id cloud-nexus/google-api-key `
  --secret-string "<YOUR_GOOGLE_API_KEY>"
```

---

## Cách 3: Cập nhật Lambda Environment Variable

```powershell
aws lambda update-function-configuration --function-name CloudNexus-BackendHandler-<SUFFIX> `
  --environment "Variables={GOOGLE_API_KEY=<YOUR_KEY>}"
```

---

## Xác Minh Cấu Hình

```powershell
# Kiểm tra secret tồn tại
aws secretsmanager describe-secret --secret-id cloud-nexus/google-api-key

# Hoặc verify Lambda environment
aws lambda get-function-configuration --function-name CloudNexus-BackendHandler-<SUFFIX> --query "Environment.Variables"
```

---

## Hướng Dẫn Chụp Ảnh Xác Minh

📸 **Ảnh 1: Secrets Manager trong AWS Console**

**Cách chụp:**
1. Vào AWS Console → Secrets Manager
2. Tìm `cloud-nexus/google-api-key`
3. Chụp ảnh chi tiết secret

**Cần xác minh:**
- Secret tồn tại
- Key không hiển thị dạng plaintext (nên được ẩn)

---

📸 **Ảnh 2: API Key Push Thành Công**

**Cách chụp:**
1. Chạy `.\scripts\push-secret.ps1`
2. Chụp ảnh output thành công

**Kết quả mong đợi:** Thông báo "Secret uploaded successfully"
