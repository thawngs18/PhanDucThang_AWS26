---
title: "Event 1"
date: 2026-04-07
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Kick Off AWS First Cloud AI Journey

### Event Objectives

- Build learning and practice roadmap for cloud computing for engineers and students in the community.
- Provide solid foundation knowledge about AWS ecosystem (Global Infrastructure, IAM, Management Tools).
- Introduce and guide integration of Artificial Intelligence (GenAI) into software development lifecycle through AWS Kiro tools.
- Enhance core awareness about Cost Optimization and system architecture on Cloud environment.

### Speakers

- **Nguyen Gia Hung** - Head of Solution Architect, FCAJ

### Key Highlights

#### 1. Journey Kickoff (Prologue & Mindset)

- Introduction to 6 core principles: Builder & Troubleshooter, Teamwork, Resilience, Hands-on & Sharing, Invest in yourself, Lifelong learning.
- Practical goal: Practice "from scratch" and complete 5 real projects to demonstrate competence.

#### 2. AWS Infrastructure Foundation

- Benefits of Cloud Computing: Cost optimization (Pay-as-you-go), faster development speed, and global scalability.
- Global Infrastructure: Hierarchical structure from Data Center → Availability Zone (AZ - minimum 2 AZs for redundancy) → Region.
- Introduction to Edge Location (used for CloudFront CDN) and Local Zone for latency optimization in Vietnam.

#### 3. Management Tools & Basic Security

- 3 main interaction methods: AWS Management Console, AWS CLI (automation via terminal), and AWS SDK (integration into source code).
- Clearly define the dangers of using Root User. Must always use IAM User, set up MFA, and secure Access Keys absolutely.

#### 4. GenAI Application on AWS - Kiro Assistant

- Shift to **Spec-Driven Development**: Clearly define requirements (Requirement/Spec) and design before letting AI generate code.
- Kiro IDE capabilities: Agent Hook (trigger automatic actions like log/test generation when saving files), Context Management, and Property-Based Testing.
- Kiro CLI & Custom Agent: Bring AI into terminal with specialized Agents (DevOps, DB) and Kiro Power (AI plugin skill ecosystem).

#### 5. Cost Optimization

- Right-sizing principle: Only allocate resources matching current needs, avoid overbuying like On-premise environment.
- Leverage payment models: Prepay (Reserved/Savings Plans), Surplus resources (Spot Instances), or pay-as-you-go (Serverless).
- Management tools: Set up AWS Budgets for alerts, use AWS Pricing Calculator for project estimation.

### Key Takeaways

#### Design Mindset

- **Builder & Troubleshooter mindset:** Don't wait to be "hand-held", be ready to face and troubleshoot system issues.
- **Spec-driven approach:** Start with clear technical documentation, architecture, and business rules (Steering files) before asking AI to write code.
- **Cost-awareness:** Always link system architecture with cost problems. The value of an engineer is not just "making systems work" but also "helping businesses save money".

#### Technical Architecture

- **High Availability (HA) & Disaster Recovery (DR) design:** Understand how to structure applications on minimum 2 AZs to ensure uptime, and use Multi-Region for disaster prevention.
- **Edge Computing for optimized experience:** Know when to push static data (images, videos) to Edge Locations via CloudFront instead of forcing users to download directly from Region.
- **Automation with Custom AI Agents:** How to partition tasks (Code Review, Security Check, DevOps) for specific Agents through MCP Server to avoid AI Hallucination due to context overload.

#### Modernization Strategy

- **Shift to Serverless:** Consider replacing traditional virtual server systems (EC2) with Serverless for applications with volatile traffic to optimize costs.
- **Apply Well-Architected Framework:** Make it a habit to use this framework to evaluate, generate reports, and improve current systems regularly.

### Applying to Work

- **Improve personal/company security:** Immediately set up MFA for Root User, switch to using IAM User, and delete/rotate Access Keys at risk of leakage.
- **Control project budget:** Set up AWS Budgets and configure Billing Alarm via email/SMS to avoid "hidden" costs from forgetting to turn off services.
- **Adapt to new AI tools:** Download and experience Kiro IDE/CLI. Try building a small project using "Spec-driven" feature and try creating "Agent Hook" that auto-generates Changelog every time you save code.
- **Review architecture:** Use AWS Well-Architected tool on console to scan and evaluate the optimization level of a service running in the company.

### Event Experience

Participating in the first sessions of "First Cloud AI Journey" was an eye-opening experience, helping me shape the way I learn and work on Cloud combined with AI environment. Some notable experiences:

- **Learning from community:** Warm sharing from AWS Study Group speakers, not only teaching technical skills but also teaching "mindset" for the profession and "no sharing, no growing" spirit.
- **Changing perspective on practice:** Labs requiring "from scratch" building instead of just clicking through ready-made guides helped me deeply understand the nature of systems.
- **Amazed by Kiro's power:** Watching demos of Kiro Autonomous Agent and Custom Agent helped me visualize the future where programmers will work "with" AI as a true colleague.

### Lessons Learned

- Cloud and GenAI technology are changing extremely fast; integrating AI (like Kiro) into development is no longer an optional choice but a mandatory factor to increase productivity.
- Working with Cloud is not just about knowing how to use services, but also about "Cost Optimization". Cost optimization skill is one of the biggest competitive advantages of a Cloud Engineer.
- "Teamwork" spirit, resilience, and self-discipline through continuous practice with real projects are the only keys to progressing on the path to becoming an AWS expert.

### Event Photos

![Event Photo 1](/images/event1-1.png)

