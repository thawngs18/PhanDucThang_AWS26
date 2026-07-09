---
title : "Điều kiện tiên quyết"
date : "2025-10-10"
weight : 0
chapter : false
pre : " <b> Step 0 </b> "
---
# Step 0: Điều Kiện Tiên Quyết

---

## Công Cụ Cần Thiết

| Công cụ | Yêu cầu | Cài đặt |
|---------|---------|---------|
| AWS Account | Active | [Đăng ký AWS](https://aws.amazon.com) |
| Region | `ap-southeast-1` | Chọn trong AWS Console |
| AWS CLI | v2.x | `winget install Amazon.AWSCLI` |
| Node.js | v18+ | `winget install OpenJS.NodeJS.LTS` |
| Python | 3.12 | `winget install Python.Python.3.12` |
| npm | v9+ | (kèm Node.js) |
| AWS CDK | v2.170+ | `npm install -g aws-cdk` |
| Git | Latest | `winget install Git.Git` |
| Google API Key | Gemini free | [Lấy tại đây](https://aistudio.google.com/app/apikey) |

---

## Xác Minh Cài Đặt

```powershell
aws --version
node --version
npm --version
cdk --version
python --version
```

---

## Hướng Dẫn Chụp Ảnh Xác Minh

**Ảnh 1: Xác minh công cụ đã cài đặt**

📸 **Cách chụp:**
1. Mở terminal PowerShell
2. Chạy từng lệnh bên trên
3. Chụp ảnh màn hình hiển thị tất cả các version outputs

**Kết quả mong đợi:** Tất cả công cụ hiển thị số version mà không có lỗi.

---

## Quyền IAM Cần Thiết

```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Action": [
      "cloudformation:*", "s3:*", "iam:*", "lambda:*",
      "apigateway:*", "cognito-idp:*", "dynamodb:*",
      "sqs:*", "sns:*", "states:*", "secretsmanager:*",
      "logs:*", "ssm:GetParameter", "ecr:*"
    ],
    "Resource": "*"
  }]
}
```

---

## Chi Phí Ước Tính

> Tất cả service trong bài đều nằm trong AWS Free Tier hoặc chi phí rất thấp (< $1/tháng nếu không sử dụng nhiều).
