---
title: "Week 8 Worklog"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Understand threat nature: Grasp modern supply chain attacks (e.g., Shai-Hulud) via maintainer credential exploitation and propagation through package consumer environments.
* Well-Architected approach: Apply AWS Well-Architected Framework Security Pillar theory to reduce threat exposure.
* Defense in Depth research: Explore combining temporary credentials, least privilege, multi-party approval, and Artifact Signing verification.
* Source code and dependency control: Analyze centralized package management against typosquatting and provenance attestation theory.
* Monitoring and response mindset: Learn differences between static CVE scanning and real-time behavioral analysis for malicious packages (zero-day, sleeper packages).

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Research supply chain attacks: Analyze Shai-Hulud, Chalk/Debug mechanisms and maintainer credential exploitation <br> - Credential risk theory: Why long-lived npm/GitHub tokens are weak points; OIDC and federated identity principles <br> - Least Privilege: Minimum permissions, audit and automatic secret rotation to narrow blast radius | 08/06/2026 | 08/06/2026 | <https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/> |
| 3   | - Defense in Depth: Multi-layer security architecture, MFA and multi-party approval to stop risk spread <br> - Artifact Signing: Cryptographic principles binding packages to creator identity <br> - Signature verification: OCI signing systems and admission controllers verifying signatures before deployment | 09/06/2026 | 09/06/2026 | <https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/> |
| 4   | - Centralized Dependency Management: Approved upstream sources to prevent typosquatting <br> - Container security architecture: Static encryption and lifecycle policies for image integrity <br> - Provenance Attestation: npm provenance, Sigstore linking CI/CD builds to source code | 10/06/2026 | 10/06/2026 | <https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/> |
| 5   | - Continuous scanning in SDLC: SCA at code review to pipeline scanning layers <br> - Behavioral analysis vs. static CVE: Limitations of traditional CVE lists; real-time analysis for zero-day and sleeper packages <br> - SBOM structure: SPDX, CycloneDX standards and blast radius assessment during incidents | 11/06/2026 | 11/06/2026 | <https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/> |
| 6   | - Centralized monitoring (Visibility): Aggregate and correlate application/service logs for early anomaly detection <br> - Audit log risk patterns: Commands from unusual IPs, image push bypassing CI/CD, irregular Access Key creation <br> - Digital forensics and automation: Exposure scope assessment and automated response rules for abnormal events | 12/06/2026 | 12/06/2026 | <https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/> |

### Week 8 Achievements:

* Comprehensive secure architecture thinking: Mastered theory for security barriers across SDLC from coding through CI/CD to deployment.
* Core risk identification and removal: Assessed long-lived credential dangers and understood migration to short-lived/temporary identity.
* Prevent sprawl: Designed checkpoints (independent cryptographic signature verification) so compromised developer accounts cannot push unverified malware to production.
* Proactive incident response: Use SBOM to quickly scope blast radius.
* Understand audit logs (CloudTrail) for digital forensics when identity leaks occur.
