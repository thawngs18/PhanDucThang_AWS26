---
title : "Bootstrap CDK"
date : "2025-10-10"
weight : 5
chapter : false
pre : " <b> Step 5 </b> "
---
# Step 5: Bootstrap CDK

---

## Purpose

Creates S3 bucket `cdk-hnb659fds-assets-<ACCOUNT>-<REGION>` to store templates and assets during deployment.

---

## Commands

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO\infrastructure
cdk bootstrap aws://<ACCOUNT_ID>/ap-southeast-1
```

---

## Expected Output

```
 ✅  Environment aws://<ACCOUNT_ID>/ap-southeast-1 bootstrapped.
```

---

## Screenshot Verification Guide

📸 **Screenshot 1: CDK Bootstrap Success**

**How to capture:**
1. Run `cdk bootstrap aws://<ACCOUNT_ID>/ap-southeast-1`
2. Screenshot the success message

**What to verify:**
- ✅ checkmark indicating success
- Environment URL with your account ID

**Expected result:** Environment bootstrapped successfully message

---

📸 **Screenshot 2: S3 Bucket Created (AWS Console)**

**How to capture:**
1. Go to AWS Console → S3
2. Find bucket starting with `cdk-hnb659fds-assets-`
3. Screenshot the bucket details

**What to verify:**
- Bucket exists with correct naming pattern
- Region matches `ap-southeast-1`
