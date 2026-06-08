---
title: "Week 2 Worklog"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Research and compare IDS/IPS deployment options to select the optimal security solution for cloud infrastructure.
* Master the theoretical foundation for building a Security Orchestration, Automation, and Response (SOAR) system to protect AWS resources.
* Understand the automated workflow and the role of each component such as GuardDuty, EventBridge, Lambda, and WAF.
* Improve programming skills (especially Python) and develop modern, intelligent security system design thinking.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Learn evaluation criteria for cloud security solutions (platform, speed, management, scalability, cost) <br> - Analyze Option 1: Open Source (Suricata on EC2) <br> - Analyze Option 2: Cloud-Native (AWS Firewall/GuardDuty) <br> - Analyze Option 3: Automation (SOAR - Lambda) | 27/04/2026 | 27/04/2026 | <https://docs.aws.amazon.com/wellarchitected/latest/framework/security.html> |
| 3   | - Analyze why Option 3 (SOAR) is chosen as the project focus <br> - Learn about instant response capability and reduced human error compared to manual log monitoring <br> - Study credit-saving mechanisms based on Lambda's Serverless model <br> - Explore advanced security trends (Security Automation) | 28/04/2026 | 28/04/2026 | <https://docs.aws.amazon.com/wellarchitected/latest/framework/security.html> |
| 4   | - Learn the role of Amazon GuardDuty as the "watchful eye" <br> - Study how to detect suspicious behavior (failed logins, abnormal data) <br> - Learn the role of Amazon EventBridge as the "nervous system" <br> - Analyze how alerts are routed from GuardDuty to other components | 29/04/2026 | 29/04/2026 | <https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_finding-types-active.html> |
| 5   | - Learn the role of AWS Lambda as the "brain" <br> - Analyze the workflow: Python code receives alerts and decides to block IPs <br> - Learn the role of AWS WAF as the "gatekeeper" <br> - Study IP blocking via Blacklist-IP-Set | 30/04/2026 | 30/04/2026 | <https://aws.amazon.com/vi/blogs/security/how-to-use-amazon-guardduty-and-aws-waf-v2-to-automatically-block-suspicious-hosts/> |
| 6   | - Learn the "time-limited blocking" (TTL) principle to avoid slowing down the system <br> - Analyze automatic IP removal to prevent blocking legitimate users <br> - Summarize the workflow diagram of an automated security incident <br> - Learn monitoring theory via VPC Flow Logs and AWS Budgets | 01/05/2026 | 01/05/2026 | <https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs-records-examples.html> |

### Week 2 Achievements:

* Fully understood the end-to-end workflow of a cloud security incident from detection to remediation.
* Gained sufficient foundational knowledge to build automation scenarios that protect the system continuously 24/7.
* Learned cost control methods through smart resource monitoring, including configuring AWS Budgets at $10 to protect account credit limits.
* Understood important operational notes, specifically always checking VPC Flow Logs to ensure no attacks are missed.
