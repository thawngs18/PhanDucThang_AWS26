---
title: "Week 5 Worklog"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Build automated response systems: Research and deploy SOAR on AWS to optimize attack blocking time.
* Master infrastructure monitoring: Deep understanding of log extraction, client IP preservation via ALB/Nginx, and application-layer attack detection.
* Approach SOC operations: Learn Splunk SIEM platform, cloud data integration, and Threat Hunting mindset.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Research automated scanning methods of Nikto, Nmap <br> - Learn Layer 7 packet analysis and User-Agent matching in Snort IDS <br> - Analyze Alert Log structure on Linux for automation data fields | 18/05/2026 | 18/05/2026 | <https://nmap.org/book/> <br> <https://cirt.net/Nikto2> <br> <https://snort.org/documents> |
| 3   | - Study ALB impact on network addresses and IP preservation via X-Forwarded-For <br> - Learn real-time log extraction with Regex in AWS Lambda <br> - Build closed-loop response theory via API connecting CloudWatch and AWS WAF | 19/05/2026 | 19/05/2026 | <https://docs.aws.amazon.com/waf/> <br> <https://docs.aws.amazon.com/lambda/> <br> <https://docs.aws.amazon.com/elasticloadbalancing/> |
| 4   | - Configure Nginx X-Forwarded-For extraction and stable CloudWatch Agent <br> - Program SOAR flow CloudWatch → Lambda → WAF with Amazon SNS notifications <br> - Test blocking Nikto, SQLMap (403 Forbidden); complete 4-flow architecture on draw.io | 20/05/2026 | 20/05/2026 | |
| 5   | - Understand Splunk SIEM: collection, indexing, and Correlation <br> - Research AWS × Splunk integration via Kinesis Firehose or Splunk Add-on <br> - Learn Threat Hunting and IoC tracing in cloud | 21/05/2026 | 21/05/2026 | <https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/send-aws-waf-logs-to-splunk-by-using-aws-firewall-manager-and-amazon-data-firehose.html> <br> <https://www.splunk.com/en_us/blog/security/cloudtrail-data-security-operations.html> |
| 6   | - Analyze Boss of the SOC (BOTS) scenarios, learn SPL language <br> - Survey SOC L1 operations: risk assessment and False Positive filtering <br> - Plan Splunk integration as monitoring layer for current SOAR architecture | 22/05/2026 | 22/05/2026 | <https://andickinson.github.io/blog/splunk-boss-of-the-soc-v1/> <br> <https://www.splunk.com/en_us/blog/security/cloudtrail-data-security-operations.html> |

### Week 5 Achievements:

* Successfully deployed SOAR chain: auto-block (403 Forbidden) Nikto and SQLMap scans via CloudWatch, Lambda, and AWS WAF.
* Optimized monitoring data: resolved real client IP via X-Forwarded-For and configured stable CloudWatch Agent.
* Mastered SIEM & Integration: Splunk (Indexing, Correlation), Kinesis Firehose, and SPL language basics.
* Completed architecture thinking: designed 4-flow AWS diagram on draw.io showing data flows and security response mechanisms.
