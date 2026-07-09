---
title : "Deploy Simulation Stack"
date : "2025-10-10"
weight : 6
chapter : false
pre : " <b> Step 6 </b> "
---
# Step 6: Deploy Simulation Stack

---

## Description

This stack creates supporting services for the simulation system.

---

## Commands

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO\infrastructure
cdk deploy CloudNexus-Simulation --require-approval never
```

---

## Expected Output

```
✅  CloudNexus-Simulation
Outputs:
  CloudNexusSimulationStack.ResultBucketName = cloudnexus-results-<ACCOUNT_ID>-ap-southeast-1
  CloudNexusSimulationStack.StateMachineArn = arn:aws:states:ap-southeast-1:<ACCOUNT_ID>:stateMachine:CloudNexus-SimOrchestrator
  CloudNexusSimulationStack.AlertTopicArn = arn:aws:sns:ap-southeast-1:<ACCOUNT_ID>:CloudNexus-Alerts
```

---

## Resources Created

| Resource | AWS Service | Purpose |
|----------|-------------|---------|
| `CloudNexus-ScanQueue` | SQS | Scan job queue |
| `CloudNexus-ResultsTable` | DynamoDB | Store results |
| `CloudNexus-ResultBucket` | S3 | Large result files |
| `CloudNexus-SimOrchestrator` | Step Functions | Workflow orchestration |
| `CloudNexus-Alerts` | SNS | Alert notifications |

---

## Screenshot Verification Guide

📸 **Screenshot 1: CDK Deploy Output**

**How to capture:**
1. Run the deploy command
2. Screenshot the success output with Outputs

**What to verify:**
- ✅ checkmark for CloudNexus-Simulation
- CloudFormation outputs displayed

---

📸 **Screenshot 2: CloudFormation Stack (AWS Console)**

**How to capture:**
1. Go to AWS Console → CloudFormation
2. Find `CloudNexus-Simulation` stack
3. Screenshot the stack status

**What to verify:**
- Stack status: CREATE_COMPLETE
- Resources tab shows all services
