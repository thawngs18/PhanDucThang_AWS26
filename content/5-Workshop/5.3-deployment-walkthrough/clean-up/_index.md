---
title : "Clean Up Resources"
date : "2025-10-10"
weight : 13
chapter : false
pre : " <b> Clean Up </b> "
---
# Clean Up Resources

---

## Overview

This section shows how to clean up all AWS resources to avoid ongoing charges.

---

## Step 1: Delete CDK Stacks

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO\infrastructure
cdk destroy --all --force
```

**Expected:**
```
 ✅  CloudNexus-Frontend: destroyed
 ✅  CloudNexus-Backend: destroyed
 ✅  CloudNexus-Simulation: destroyed
```

---

## Step 2: Delete S3 Buckets (Retained)

S3 buckets with `RemovalPolicy.RETAIN` must be deleted manually:

```powershell
# List buckets
aws s3 ls | Select-String "cloudnexus"

# Delete buckets
aws s3 rb s3://cloudnexus-frontend-<SUFFIX> --force
aws s3 rb s3://cloudnexus-results-<ACCOUNT>-ap-southeast-1 --force
```

---

## Step 3: Delete Lambda Layer Versions

```powershell
aws lambda list-layer-versions --layer-name CloudNexus-PythonDeps
aws lambda delete-layer-version --layer-name CloudNexus-PythonDeps --version-number 1
```

---

## Step 4: Delete Secrets Manager

```powershell
aws secretsmanager delete-secret --secret-id cloud-nexus/google-api-key --force-delete-without-recovery
```

---

## Step 5: Delete CloudWatch Log Groups

```powershell
aws logs delete-log-group --log-group-name /aws/lambda/CloudNexus-BackendHandler
```

---

## Step 6: Delete CDK Bootstrap (Optional)

```powershell
aws s3 rb s3://cdk-hnb659fds-assets-<ACCOUNT>-ap-southeast-1 --force
aws cloudformation delete-stack --stack-name CDKToolkit
```

---

## Screenshot Verification Guide

📸 **Screenshot 1: CDK Destroy Success**

**How to capture:**
1. Run `cdk destroy --all --force`
2. Screenshot the destruction output

**Expected result:** All stacks show "destroyed" with ✅ checkmarks

---

📸 **Screenshot 2: Verify No Resources Remain**

**How to capture:**
1. Go to AWS Console
2. Check CloudFormation, Lambda, S3, CloudFront
3. Screenshot showing no CloudNexus resources

**Expected result:** No CloudNexus-named resources found
