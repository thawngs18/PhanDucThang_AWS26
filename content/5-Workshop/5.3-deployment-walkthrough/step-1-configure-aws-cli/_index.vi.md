---
title : "Cấu hình AWS CLI"
date : "2025-10-10"
weight : 1
chapter : false
pre : " <b> Step 1 </b> "
---
# Step 1: Cấu Hình AWS CLI

---

## Các Lệnh

```powershell
aws configure
# AWS Access Key ID: ********
# AWS Secret Access Key: ********
# Default region name: ap-southeast-1
# Default output format: json

aws sts get-caller-identity
```

---

## Kết Quả Mong Đợi

```json
{
  "UserId": "AIDA...",
  "Account": "<ACCOUNT_ID>",
  "Arn": "arn:aws:iam::<ACCOUNT_ID>:user/..."
}
```

---

## Hướng Dẫn Chụp Ảnh Xác Minh

📸 **Ảnh 1: AWS STS Identity**

**Cách chụp:**
1. Chạy `aws sts get-caller-identity`
2. Chụp ảnh màn hình JSON output hiển thị Account ID

**Cần xác minh:**
- Account ID được hiển thị (12 chữ số)
- ARN hiển thị tên IAM user/role của bạn

**Kết quả mong đợi:**
```
{
  "UserId": "AIDA...",
  "Account": "123456789012",
  "Arn": "arn:aws:iam::123456789012:user/your-name"
}
```
