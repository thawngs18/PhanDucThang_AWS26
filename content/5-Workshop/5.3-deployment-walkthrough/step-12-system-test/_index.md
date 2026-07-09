---
title : "System Test & Validation"
date : "2025-10-10"
weight : 12
chapter : false
pre : " <b> Step 12 </b> "
---
# Step 12: System Test & Validation

---

## Live Demo URL

**Access the deployed application:** [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/)

---

## Health Check

```powershell
# Get API URL from CloudFormation
$apiUrl = aws cloudformation describe-stacks --stack-name CloudNexus-Backend --query "Stacks[0].Outputs[?OutputKey=='ApiUrl'].OutputValue" --output text

# Test health endpoint
curl -s "$apiUrl/api/health"
```

**Expected:**
```json
{"status":"ok"}
```

---

## Frontend Test

Open in browser: [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/)

**Verify:**
- React app loads completely
- ReactFlow canvas displays
- Terminal interface is visible
- Dark mode theme active

---

## AI Generation Test

```powershell
$body = '{"prompt":"simple web server with database"}'
curl -s -X POST "$apiUrl/api/ai/generate" -H "Content-Type: application/json" -d $body
```

**Expected:** JSON topology with nodes and edges

---

## Screenshot Verification Guide

📸 **Screenshot 1: Frontend Loaded Successfully**

**How to capture:**
1. Open [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/) in browser
2. Wait for full page load
3. Screenshot the complete interface

**What to verify:**
- ReactFlow canvas visible on left
- Terminal interface on right
- Dark theme applied
- No loading errors

---

📸 **Screenshot 2: API Health Check Response**

**How to capture:**
1. Run curl command for health check
2. Screenshot terminal showing JSON response

**Expected result:** `{"status":"ok"}`

---

📸 **Screenshot 3: CloudWatch Lambda Logs**

**How to capture:**
1. Go to AWS Console → CloudWatch → Log groups
2. Find `/aws/lambda/CloudNexus-Backend`
3. Screenshot recent log events

**What to verify:**
- INIT_START event
- Lambda handler invoked
- No error logs

---

## Lambda Metrics

```powershell
aws cloudwatch get-metric-statistics `
  --namespace AWS/Lambda `
  --metric-name Invocations `
  --dimensions Name=FunctionName,Value=CloudNexus-BackendHandler `
  --start-time 2025-01-01T00:00:00Z `
  --end-time 2025-12-31T23:59:59Z `
  --period 3600 `
  --statistics Sum
```

| Metric | Value | Meaning |
|--------|-------|---------|
| Invocations | > 0 | Lambda is being called |
| Duration | ~60ms | Request processing |
| Errors | 0 | No errors |
