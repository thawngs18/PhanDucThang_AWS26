---
title: "Week 6 Worklog"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Define standard data structure (JSON Schema) and design seamless API communication between frontend, backend, and Amazon Bedrock (GenAI).
* Build security logic foundation: Threat Modeling and automated response workflows (Playbook/SOAR).
* Design Simulation Engine algorithms and interactive visualization (React Flow) for attack-defense scenario simulation.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Design JSON Schema representing security infrastructure (VPC, EC2, WAF, Snort IDS) <br> - Learn Prompt Engineering on Amazon Bedrock for structured JSON output <br> - Sketch API Data Flow between frontend, FastAPI backend, and Amazon Bedrock | 25/05/2026 | 25/05/2026 | <https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-engineering-guidelines.html> |
| 3   | - Research security frameworks (MITRE ATT&CK, STRIDE) for risk identification <br> - Design "Threat Scan" prompts for AI to analyze attack vectors from architecture JSON <br> - Plan Risk Scoring mechanism (red/green alerts when adding defense measures) | 26/05/2026 | 26/05/2026 | <https://attack.mitre.org/matrices/enterprise/cloud/> |
| 4   | - Study representing security automation as If/Else flowcharts <br> - Define Playbook node data structure (Read Log → Check Threshold → Block Action) <br> - Read AWS Step Functions and SOAR docs for realistic UI simulation design | 27/05/2026 | 27/05/2026 | <https://docs.aws.amazon.com/security-ir/latest/userguide/security-incident-response-guide.html> |
| 5   | - Learn React Flow: render nodes from JSON on drag-and-drop canvas <br> - Study State Management when updating node properties (Allow/Drop on Firewall) <br> - Read Edge animation guides for traffic flow visualization | 28/05/2026 | 28/05/2026 | <https://reactflow.dev/learn> |
| 6   | - Draw overall System Architecture Diagram: from user prompt to canvas and alerts <br> - Design Simulation Engine logic: determine if attacks are blocked at WAF or reach Database <br> - Write 2–3 attack scenarios (DDoS, Brute-force) with expected outcomes | 29/05/2026 | 29/05/2026 | <https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html> |

### Week 6 Achievements:

* Completed System Architecture Diagram and data structure documentation ready for coding phase.
* Successfully packaged specialized Prompt Engineering sets for AI vulnerability detection and incident response flowcharts.
* Mastered frontend state management, animation techniques, and defined 2–3 real attack scenarios for product acceptance testing.
