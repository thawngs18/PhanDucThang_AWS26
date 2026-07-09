---
title : "Deploy Simulation Stack"
date : "2025-10-10"
weight : 6
chapter : false
pre : " <b> Step 6 </b> "
---
# Step 6: Deploy Simulation Stack

---

## Mô Tả

Stack này tạo các service hỗ trợ cho hệ thống simulation.

---

## Các Lệnh

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO\infrastructure
cdk deploy CloudNexus-Simulation --require-approval never
```

---

## Kết Quả Mong Đợi

```
✅  CloudNexus-Simulation
Outputs:
  CloudNexusSimulationStack.ResultBucketName = cloudnexus-results-<ACCOUNT_ID>-ap-southeast-1
  CloudNexusSimulationStack.StateMachineArn = arn:aws:states:ap-southeast-1:<ACCOUNT_ID>:stateMachine:CloudNexus-SimOrchestrator
  CloudNexusSimulationStack.AlertTopicArn = arn:aws:sns:ap-southeast-1:<ACCOUNT_ID>:CloudNexus-Alerts
```

---

## Tài Nguyên Đã Tạo

| Tài nguyên | AWS Service | Mục đích |
|------------|-------------|----------|
| `CloudNexus-ScanQueue` | SQS | Hàng đợi scan job |
| `CloudNexus-ResultsTable` | DynamoDB | Lưu kết quả |
| `CloudNexus-ResultBucket` | S3 | File kết quả lớn |
| `CloudNexus-SimOrchestrator` | Step Functions | Điều phối workflow |
| `CloudNexus-Alerts` | SNS | Thông báo alert |

---

## Hướng Dẫn Chụp Ảnh Xác Minh

📸 **Ảnh 1: CDK Deploy Output**

**Cách chụp:**
1. Chạy lệnh deploy
2. Chụp ảnh output thành công với Outputs

**Cần xác minh:**
- ✅ dấu tích cho CloudNexus-Simulation
- CloudFormation outputs được hiển thị

---

📸 **Ảnh 2: CloudFormation Stack (AWS Console)**

**Cách chụp:**
1. Vào AWS Console → CloudFormation
2. Tìm stack `CloudNexus-Simulation`
3. Chụp ảnh trạng thái stack

**Cần xác minh:**
- Trạng thái stack: CREATE_COMPLETE
- Tab Resources hiển thị tất cả services
