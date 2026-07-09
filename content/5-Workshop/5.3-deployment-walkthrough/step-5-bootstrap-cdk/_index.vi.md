---
title : "Bootstrap CDK"
date : "2025-10-10"
weight : 5
chapter : false
pre : " <b> Step 5 </b> "
---
# Step 5: Bootstrap CDK

---

## Mục Đích

Tạo S3 bucket `cdk-hnb659fds-assets-<ACCOUNT>-<REGION>` để lưu template và assets khi deploy.

---

## Các Lệnh

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO\infrastructure
cdk bootstrap aws://<ACCOUNT_ID>/ap-southeast-1
```

---

## Kết Quả Mong Đợi

```
 ✅  Environment aws://<ACCOUNT_ID>/ap-southeast-1 bootstrapped.
```

---

## Hướng Dẫn Chụp Ảnh Xác Minh

📸 **Ảnh 1: CDK Bootstrap Thành Công**

**Cách chụp:**
1. Chạy `cdk bootstrap aws://<ACCOUNT_ID>/ap-southeast-1`
2. Chụp ảnh thông báo thành công

**Cần xác minh:**
- ✅ dấu tích indicating thành công
- Environment URL với account ID của bạn

**Kết quả mong đợi:** Thông báo Environment bootstrapped successfully

---

📸 **Ảnh 2: S3 Bucket Đã Tạo (AWS Console)**

**Cách chụp:**
1. Vào AWS Console → S3
2. Tìm bucket bắt đầu bằng `cdk-hnb659fds-assets-`
3. Chụp ảnh chi tiết bucket

**Cần xác minh:**
- Bucket tồn tại với pattern đúng
- Region phù hợp với `ap-southeast-1`
