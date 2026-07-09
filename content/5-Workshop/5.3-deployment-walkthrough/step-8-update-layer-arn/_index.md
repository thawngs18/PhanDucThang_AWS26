---
title : "Update Layer ARN in CDK"
date : "2025-10-10"
weight : 8
chapter : false
pre : " <b> Step 8 </b> "
---
# Step 8: Update Layer ARN in CDK

---

## Purpose

Update the Lambda Layer ARN in the CDK stack with the newly published version number.

---

## Commands

Open the backend stack file:

```powershell
notepad C:\Users\ADMIN\Desktop\BC\DEMO\infrastructure\stacks\backend_stack.py
```

Find this line:

```python
layer_arn = 'arn:aws:lambda:ap-southeast-1:<ACCOUNT_ID>:layer:CloudNexus-PythonDeps:1'
```

Update the version number at the end (e.g., `:1`, `:2`, `:3`, `:4`) depending on how many times you published the layer.

---

## Screenshot Verification Guide

📸 **Screenshot 1: Layer ARN in Code**

**How to capture:**
1. Open `backend_stack.py` in your editor
2. Find the `layer_arn` line
3. Screenshot showing the ARN with correct version number

**What to verify:**
- ARN ends with `:1` (or appropriate version number)
- Account ID is correct

**Expected result:** Code showing the Layer ARN with version matching the published layer
