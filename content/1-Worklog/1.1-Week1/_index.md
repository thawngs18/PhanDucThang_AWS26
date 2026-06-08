---
title: "Week 1 Worklog"
date: 2026-04-17
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Week 1 Objectives:

* Learn company policies and culture, complete procedures with the academic supervisor, and establish a shared workflow with the FCJ team.
* Understand AWS Free Tier 2025 policies, identify services that may incur costs, and build a safe budget control plan.
* Build a secure IAM identity management system, apply the Least Privilege principle, and limit Root account usage.
* Master foundational cloud networking concepts (VPC, Subnet, IGW, NAT Gateway) and network security controls (Security Group, Network ACLs).
* Practice building an independent virtual network (VPC) and deploying an EC2 server on AWS.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 6   | - Meet and build relationships with members of the internship unit <br> - Read company policies, culture, and workplace regulations carefully | 17/04/2026 | 17/04/2026 | |
| 2   | - Contact and officially confirm internship information with the academic supervisor <br> - Proactively connect, form a team, and assign roles with FCJ members <br> - Agree on communication channels and work management tools | 20/04/2026 | 20/04/2026 | |
| 3   | - Read updated documentation on AWS Free Tier 2025 <br> - List and note high-cost-risk services to avoid <br> - Register an AWS account and complete 5 basic tasks to receive $200 Credit <br> - Set up billing alarms for safe budget control | 21/04/2026 | 21/04/2026 | <https://000001.awsstudygroup.com/> |
| 4   | - Set up User, Group, and Role <br> - Use Policies to define allowed/denied actions based on Least Privilege <br> - Avoid using the Root account for daily tasks and enable MFA for the Admin account <br> - Implement Switch Role so OperatorUser can assume Admin when needed <br> - Successfully create AdminGroup, AdminUser, OperatorUser and attach AllowSwitchAdminPolicy | 22/04/2026 | 22/04/2026 | <https://000002.awsstudygroup.com/> |
| 5   | - Learn about Subnets, Route Table, Internet Gateway, and NAT Gateway <br> - Learn how Security Groups, Network ACLs, and VPC Resource Map work | 23/04/2026 | 23/04/2026 | <https://000003.awsstudygroup.com/> |
| 6   | - Create VPC, Subnet, Internet Gateway, Route Table, Security Group, and enable VPC Flow Logs <br> - **Practice:** Launch an EC2 server and successfully test connection from VSCode | 24/04/2026 | 24/04/2026 | <https://000003.awsstudygroup.com/> |

### Week 1 Achievements:

* Confirmed internship information, completed FCJ team structure, assigned clear roles, and agreed on management and communication tools.
* Successfully registered an AWS account, completed 5 basic tasks for $200 Credit, and set up billing alarms.
* Successfully created IAM resources (AdminGroup, AdminUser, OperatorUser), enforced MFA for Admin, and configured Switch Role (AllowSwitchAdminPolicy) for OperatorUser.
* Deployed a complete network infrastructure including VPC, Subnet, Internet Gateway, Route Table, Security Group, and enabled VPC Flow Logs monitoring.
* Successfully launched an EC2 instance on the new network and verified connection from VSCode.
