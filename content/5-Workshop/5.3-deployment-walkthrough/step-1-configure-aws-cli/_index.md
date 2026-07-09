---
title : "Configure AWS CLI"
date : "2025-10-10"
weight : 1
chapter : false
pre : " <b> Step 1 </b> "
---
# Step 1: Configure AWS CLI

---

## Commands

```powershell
aws configure
# AWS Access Key ID: ********
# AWS Secret Access Key: ********
# Default region name: ap-southeast-1
# Default output format: json

aws sts get-caller-identity
```

---

## Expected Output

```json
{
  "UserId": "AIDA...",
  "Account": "<ACCOUNT_ID>",
  "Arn": "arn:aws:iam::<ACCOUNT_ID>:user/..."
}
```

---

## Screenshot Verification Guide

📸 **Screenshot 1: AWS STS Identity**

**How to capture:**
1. Run `aws sts get-caller-identity`
2. Screenshot the JSON output showing Account ID

**What to verify:**
- Account ID is displayed (12 digits)
- ARN shows your IAM user/role name

**Expected result:**
```
{
  "UserId": "AIDA...",
  "Account": "123456789012",
  "Arn": "arn:aws:iam::123456789012:user/your-name"
}
```
