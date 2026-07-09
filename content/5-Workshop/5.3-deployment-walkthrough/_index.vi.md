---
title : "Triển Khai & Lab Step-by-Step"
date : "2025-10-10"
weight : 3
chapter : false
pre : " <b> 5.3 </b> "
---
# 5.3. Triển Khai & Lab Step-by-Step

---

## Mục Lục

> **Lưu ý:** Vì Cloud Nexus đã được deploy, phần này tập trung vào **xác minh** từng thành phần đã deploy với hướng dẫn chụp ảnh màn hình.

| Step | Folder | Nội dung |
|------|--------|---------|
| — | `step-0-prerequisites/` | Xác minh điều kiện tiên quyết |
| 1 | `step-1-configure-aws-cli/` | Cấu hình AWS CLI |
| 2 | `step-2-get-source-code/` | Tải mã nguồn |
| 3 | `step-3-install-dependencies-build-frontend/` | Build frontend locally |
| 4 | `step-4-install-cdk-dependencies/` | Cài CDK dependencies |
| 5 | `step-5-bootstrap-cdk/` | Bootstrap CDK |
| 6 | `step-6-deploy-simulation-stack/` | Deploy Simulation Stack |
| 7 | `step-7-build-lambda-layer/` | Build Lambda Layer |
| 8 | `step-8-update-layer-arn/` | Cập nhật Layer ARN |
| 9 | `step-9-deploy-api-stack/` | Deploy API Stack |
| 10 | `step-10-deploy-frontend-stack/` | Deploy Frontend Stack |
| 11 | `step-11-configure-api-key/` | Cấu hình API Key |
| 12 | `step-12-system-test/` | Xác minh hệ thống |
| — | `clean-up/` | Dọn dẹp tài nguyên |

---

## Tổng Quan Hạ Tầng Đã Deploy

| Thành phần | Trạng thái | URL/ARN |
|-----------|-----------|---------|
| **Frontend** | Đã deploy | https://d3rs3evkmfvesp.cloudfront.net/ |
| **API Gateway** | Đã deploy | `https://<api-id>.execute-api.<region>.amazonaws.com/prod/` |
| **Lambda** | Đã deploy | `CloudNexus-Backend-<suffix>` |
| **S3 Bucket** | Đã deploy | `CloudNexus-Frontend-<suffix>` |
| **CloudFront** | Đã deploy | `d3rs3evkmfvesp.cloudfront.net` |

---

## Các Lệnh Xác Minh Nhanh

### Kiểm Tra CloudFront Frontend

```powershell
# Mở trên trình duyệt
Start-Process "https://d3rs3evkmfvesp.cloudfront.net/"

# Hoặc verify qua curl
curl -s -I "https://d3rs3evkmfvesp.cloudfront.net/" | Select-String "HTTP/"
```

### Kiểm Tra API Gateway Health

```powershell
# Lấy API URL từ CloudFormation
$apiUrl = aws cloudformation describe-stacks --stack-name CloudNexus-Backend --query "Stacks[0].Outputs[?OutputKey=='ApiUrl'].OutputValue" --output text

# Test health endpoint
curl -s "$apiUrl/api/health"
```

### Kiểm Tra Lambda Functions

```powershell
aws lambda list-functions --query "Functions[?contains(FunctionName,'CloudNexus')].FunctionName"
```
