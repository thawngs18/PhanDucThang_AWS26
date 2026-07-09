---
title : "Deploy Frontend Stack"
date : "2025-10-10"
weight : 10
chapter : false
pre : " <b> Step 10 </b> "
---
# Step 10: Deploy Frontend Stack

---

## Mô Tả

Tạo S3 bucket và CloudFront distribution cho static website hosting.

---

## Các Lệnh

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO\infrastructure
cdk deploy CloudNexus-Frontend --require-approval never
```

---

## Kết Quả Mong Đợi

```
✅  CloudNexus-Frontend
Outputs:
  CloudNexus-Frontend.WebsiteURL = https://d3rs3evkmfvesp.cloudfront.net
  CloudNexus-Frontend.BucketName = cloudnexus-frontend-<SUFFIX>
  CloudNexus-Frontend.DistributionId = <DIST_ID>
```

---

## Cấu Hình S3

```python
# frontend_stack.py
self.frontend_bucket = Bucket(self, 'FrontendBucket',
    public_read_access=True,
    block_public_access=BlockPublicAccess(block_acls=False),
    website_index_document='index.html',
    website_error_document='index.html',
    removal_policy=RemovalPolicy.RETAIN,
    versioned=True,
)
```

---

## Hướng Dẫn Chụp Ảnh Xác Minh

📸 **Ảnh 1: CDK Deploy Frontend Stack Output**

**Cách chụp:**
1. Chạy lệnh deploy
2. Chụp ảnh output thành công

**Cần xác minh:**
- ✅ dấu tích cho CloudNexus-Frontend
- CloudFront URL được hiển thị

---

📸 **Ảnh 2: CloudFront Distribution trong AWS Console**

**Cách chụp:**
1. Vào AWS Console → CloudFront
2. Tìm distribution của bạn
3. Chụp ảnh chi tiết distribution

**Cần xác minh:**
- Status: Deployed
- Alternate Domain Name: d3rs3evkmfvesp.cloudfront.net
- Origin: S3 bucket
