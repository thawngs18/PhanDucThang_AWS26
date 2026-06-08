---
title: "Week 4 Worklog"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Build and automate a Security Orchestration, Automation, and Response (SOAR) system on AWS cloud.
* Design standardized infrastructure architecture and security data processing flows.
* Deploy two automated defense scenarios: Log-Driven Automation (via S3) and Network-Driven Automation (Snort IDS via CloudWatch).
* Ensure the system automatically identifies attacker IPs (even behind Load Balancer) and executes instant blocking via AWS WAF.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Set up draw.io workspace with AWS 2026 icon set <br> - Design network infrastructure boundaries (AWS Cloud, Region, VPC, Subnets) and place service icons in correct network layers <br> - Draw 4 data flows (Attack, Log Delivery, Automation & AI, Storage) with line and color conventions | 11/05/2026 | 11/05/2026 | AWS Architecture Drawing Guide |
| 3   | - Develop basic SOAR scenario on AWS <br> - Launch EC2, set up ALB traffic routing, and integrate AWS WAF <br> - Program Lambda (Python) and configure IAM to auto-update malicious IPs to WAF blocklist <br> - Simulate incident, verify WAF blocking (HTTP 200 → 403), and clean up lab resources | 12/05/2026 | 12/05/2026 | |
| 4   | - Design Scenario 1 (Log-Driven): Diagram ALB → S3 → S3 Event → Lambda → WAF; write Python pseudocode to extract 404 IPs <br> - Design Scenario 2 (Network-Driven): Integrate Snort/Suricata on EC2; flow CloudWatch Agent → Metric Filters → Alarm → Lambda → WAF | 13/05/2026 | 13/05/2026 | |
| 5   | - Set up logging infrastructure: EC2 behind ALB, push Access Logs to Amazon S3 <br> - Build AWS WAF Web ACL with IP Set (Blacklist) <br> - Develop Lambda to analyze S3 logs and detect attacking IPs (404 threshold exceeded) <br> - Configure Lambda to auto-update WAF IP Set (403 Forbidden) | 14/05/2026 | 14/05/2026 | |
| 6   | - Deploy Snort IDS on Ubuntu EC2 with ALB and AWS WAF <br> - Build SOAR flow from CloudWatch Logs → Lambda for real-time IP blocking on WAF <br> - Configure X-Forwarded-For extraction from Nginx logs to identify real attacker IP | 15/05/2026 | 15/05/2026 | |

### Week 4 Achievements:

* Completed AWS 2026 architecture diagram on draw.io showing network boundaries and 4 core data flows.
* Successfully deployed Log-Driven flow: auto-parse ALB Access Logs on S3, detect scan IPs (404), and update WAF IP Set.
* Successfully integrated Snort IDS; solved Load Balancer IP masking via X-Forwarded-For, pushed logs through CloudWatch for Lambda to block real IPs.
* WAF automatically blocked malicious sources (HTTP 403). Lab cleaned up safely with no unexpected costs.
