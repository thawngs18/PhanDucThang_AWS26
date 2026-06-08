---
title: "Week 3 Worklog"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Master infrastructure: Deploy and manage core services (EC2, S3, IAM) proficiently.
* Multi-layer security: Set up firewall (WAF) and automated monitoring (GuardDuty, Lambda).
* Standardize thinking: Apply international security frameworks (NIST CSF, AWS CAF) to real scenarios.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Launch EC2 instances (Windows & Linux) and set up basic networking <br> - Install Web Server and successfully deploy the Node.js "AWS User Management" application <br> - Use IAM deployment limits for cost management and resource cleanup | 04/05/2026 | 04/05/2026 | <https://000004.awsstudygroup.com/> |
| 3   | - Create S3 Bucket and deploy a sample web application <br> - Configure Web ACLs with Managed Rules and Custom Rules to block malicious access <br> - Set up logging, verify rule behavior, and clean up resources | 05/05/2026 | 05/05/2026 | <https://000004.awsstudygroup.com/> |
| 4   | - Enable GuardDuty to analyze security threat alerts <br> - Configure EventBridge Event Rules to capture GuardDuty findings <br> - Connect Lambda Function for automated incident remediation | 06/05/2026 | 06/05/2026 | <https://000026.awsstudygroup.com/> |
| 5   | - Apply NIST CSF functions (Protect, Detect, Respond) to the system <br> - Implement AWS CAF security perspectives (Preventive, Detective, Responsive) <br> - Systematize defense layers from network, identity to data per AWS standards | 07/05/2026 | 07/05/2026 | <https://000098.awsstudygroup.com/> |
| 6   | - Practice incident response when EC2 is compromised <br> - Drill IAM credential leak scenarios and immediate privilege revocation <br> - Handle IAM abuse from external servers calling APIs and clean up the lab | 08/05/2026 | 08/05/2026 | <https://000098.awsstudygroup.com/> |

### Week 3 Achievements:

* Successfully deployed Node.js application on both Linux/Windows and learned cost optimization.
* Built Web ACL rules to block application-layer attacks and configured monitoring logs.
* Established automated detection and remediation workflow instead of manual operations.
* Mastered emergency response for 3 scenarios (Compromised EC2, Leaked Credentials, IAM Abuse).
