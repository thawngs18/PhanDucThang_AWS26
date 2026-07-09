---
title : "Deploy Frontend Stack"
date : "2025-10-10"
weight : 10
chapter : false
pre : " <b> Step 10 </b> "
---
# Step 10: Deploy Frontend Stack

---

## Description

Creates S3 bucket and CloudFront distribution for static website hosting.

---

## Commands

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO\infrastructure
cdk deploy CloudNexus-Frontend --require-approval never
```

---

## Expected Output

```
✅  CloudNexus-Frontend
Outputs:
  CloudNexus-Frontend.WebsiteURL = https://d3rs3evkmfvesp.cloudfront.net
  CloudNexus-Frontend.BucketName = cloudnexus-frontend-<SUFFIX>
  CloudNexus-Frontend.DistributionId = <DIST_ID>
```

---

## S3 Configuration

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

## Screenshot Verification Guide

📸 **Screenshot 1: CDK Deploy Frontend Stack Output**

**How to capture:**
1. Run the deploy command
2. Screenshot the success output

**What to verify:**
- ✅ checkmark for CloudNexus-Frontend
- CloudFront URL is displayed

---

📸 **Screenshot 2: CloudFront Distribution in AWS Console**

**How to capture:**
1. Go to AWS Console → CloudFront
2. Find your distribution
3. Screenshot the distribution details

**What to verify:**
- Status: Deployed
- Alternate Domain Name: d3rs3evkmfvesp.cloudfront.net
- Origin: S3 bucket
