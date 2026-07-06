---
title: "Blogs Posted"
date: 2026-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Here are the blogs that the group has researched and shared on [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj).

###  [Blog 1 - Software Supply Chain Security Best Practices](3.1-Blog1/)
This blog discusses software supply chain security based on the **AWS Well-Architected Security Pillar**, covering **5 core best practices** from the AWS Security Blog. Key topics include eliminating long-term credentials and applying least privilege, implementing defense in depth with AWS Signer and Amazon ECR managed signing, centralized dependency management using AWS CodeArtifact to mitigate typosquatting risks, automated continuous scanning with Amazon Inspector for early detection of sleeper packages, and enhanced logging and monitoring with AWS CloudTrail, GuardDuty, and EventBridge to detect threats and trigger automated response workflows.

###  [Blog 2 - Building Secure, Verifiable Blockchain Key Management on AWS Nitro Enclaves at Turnkey](3.2-Blog2/)
This blog introduces Turnkey's secure blockchain key management solution built on **AWS Nitro Enclaves**, combining cryptography and hardware isolation to process keys entirely within an enclave environment. Key points include challenges in current key management architectures, Nitro Enclaves' isolation with no persistent storage or interactive access, cryptographic data initialization and storage using an HD Wallet model and Quorum Key symmetric encryption, the split architecture separating external management and internal computing partitions through a 5-step closed-loop process, and remote mathematical verification using Remote Attestation and Reproducible Builds with QuorumOS.

###  [Blog 3 - How AWS DevOps Agent Uses Multi-Agent Reasoning to Find Root Causes](3.3-Blog3/)
This blog explains how AWS DevOps Agent overcomes confirmation bias in incident investigations using a **multi-agent reasoning** architecture. Key points include the Topology Graph as the foundational system map that captures service relationships, runtime communication patterns, and CI/CD deployment lineage, the 4-step incident lifecycle with specialized Triage, Investigation, Mitigation, and Prevention agents, how Investigation generates multiple competing hypotheses and validates each with supporting and counter-evidence before converging on root cause, Mitigation generating safe remediation plans with rollback procedures without executing changes, and Prevention clustering past incidents to identify patterns and propose architectural improvements to prevent recurrence.
