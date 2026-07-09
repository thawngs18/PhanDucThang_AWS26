---
title : "Deploy API Stack"
date : "2025-10-10"
weight : 9
chapter : false
pre : " <b> Step 9 </b> "
---
# Step 9: Deploy API Stack

---

## Description

Creates API Gateway, Lambda (FastAPI + Mangum), and Secrets Manager.

---

## Commands

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO\infrastructure
cdk deploy CloudNexus-Backend --require-approval never
```

---

## Expected Output

```
✅  CloudNexus-Backend
Outputs:
  CloudNexus-Backend.ApiUrl = https://<API_ID>.execute-api.ap-southeast-1.amazonaws.com/prod/
  CloudNexus-Backend.FunctionName = CloudNexus-BackendHandler-<SUFFIX>
```

---

## Resources Created

| Resource | AWS Service | Purpose |
|----------|-------------|---------|
| `CloudNexus-BackendHandler` | Lambda | FastAPI backend |
| `CloudNexus-PythonDeps` | Layer | Python dependencies |
| `CloudNexus-API` | API Gateway | REST endpoint |
| `CloudNexus-Secrets` | Secrets Manager | API key storage |

---

## Screenshot Verification Guide

📸 **Screenshot 1: CDK Deploy API Stack Output**

**How to capture:**
1. Run the deploy command
2. Screenshot the success output with Outputs

**What to verify:**
- ✅ checkmark for CloudNexus-Backend
- API URL is displayed

---

📸 **Screenshot 2: API Gateway in AWS Console**

**How to capture:**
1. Go to AWS Console → API Gateway
2. Find your API
3. Screenshot the API details page

**What to verify:**
- API type: HTTP API
- Stages: prod
- Routes: /api/*

---

📸 **Screenshot 3: Lambda Function in AWS Console**

**How to capture:**
1. Go to AWS Console → Lambda
2. Find `CloudNexus-BackendHandler`
3. Screenshot the function configuration

**What to verify:**
- Runtime: Python 3.12
- Memory: 512 MB
- Layers: CloudNexus-PythonDeps attached
