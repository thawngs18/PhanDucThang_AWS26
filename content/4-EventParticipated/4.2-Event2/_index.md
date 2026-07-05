---
title: "Event 2"
date: 2026-05-23
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# AWS FCAJ Community Day – Conference Call

### Event Objectives

- Share in-depth knowledge and best practices about integrating AI into real products (from Prompt Engineering to Multi-Agent Systems).
- Decode technical essence of Large Language Models (LLMs) and how to manage risks, randomness in production environments.
- Guide optimization of cloud infrastructure (Cloud Infrastructure) with Amazon CloudFront to ensure security, performance, and cost optimization.
- Inspire through real case studies from Enterprise environments (Banking/Startup) to Hackathon competitions (LotusHacks).

### Speakers

- **Tinh Truong** - Platform Engineer, GoTymeX
- **Pham Ng Hai Anh** - AWS Community Builder, G-AsiaPacific Vietnam
- **Nguyen Tuan Thinh** - DevOps Engineer, FCAJ
- **Team VIB** - GenAI Engineer, VIB, Participants, LotusHacks 2026
- **Duc Dao** - Solution Architect, Cloud Kinetics
- **Vy Lam** - Senior Business Systems Analyst, VPBank

### Key Highlights

#### Mastering AI through Context

- AI failures usually stem from lack of context in input, not weak models. AI cannot "read minds".
- 4-element Framework for standard Prompt: Goal → Relevant Info → Constraints → Success criteria.
- AI evolution: From Prompt (single question) → Context (with documents) → Memory (Second Brain - learning over time).

#### Non-Determinism of LLM

- Setting Temperature = 0 does not guarantee 100% identical results (Deterministic) as many think.
- Technical reason: GPU architecture processes floating-point numbers in parallel and batching mechanism of API providers (OpenAI, Anthropic,...).
- Solution: Use temp = 0.1 to prevent model from getting stuck in loops, use structured outputs (JSON), and design systems to handle non-uniform results.

#### Enterprise-Grade Multi-Agent Systems

- Single Agent will fail with complex problems (like startup credit scoring) due to context limits, diluted expertise, and lack of checks & balances.
- Multi-Agent Paradigm: Build a "virtual committee" with specialized Agents (Finance, Market, HR, Risk, Compliance) working in parallel and debating each other.
- Enterprise-Grade Thinking: 6 pillars for AI in production: Security (Auth, encryption), Data Governance, Network (VPC, Zero-trust), Operations, Human Factors, and Compliance.

#### Optimizing Network Infrastructure with Amazon CloudFront

- Solving unpredictable CDN cost problems: Introducing Fixed-Price packages including CDN, WAF, DDoS, DNS, and Storage.
- Edge Security: More effective DDoS protection (volumetric attack) than ELB, integrated Mutual TLS, Origin Access Control (OAC) to cloak Origin server.
- Performance optimization: HTTP/3 (QUIC) multiplexing, edge data compression, and Edge Computing (CloudFront Functions, Lambda@Edge) to reduce load on Origin.

#### Building Products from Idea to Reality (Hackathon Experience)

- 36-hour journey building UTMorpho (application converting wireframes to code).
- Real challenges: AI Overgeneration phenomenon, Token limits, and physical burnout.
- Lessons: Real ideas come from real frustrations. Teamwork and Team Sync are more important than feature count.

### Key Takeaways

#### AI System Design Mindset

- Context Quality > Context Quantity: Not about stuffing documents into AI, but providing the right data (relevant evidence).
- Multi-Agent vs Single Agent: Understand when to use single AI (linear work, low risk) and when to use multi-task AI (important decisions, deep multi-domain expertise).
- Building systems tolerant of risks: Always consider LLM output as probability (probabilistic) not absolute (deterministic).

#### Technical Architecture & Infrastructure

- Defense in Depth: Completely hide servers behind CloudFront and VPC, only allowing traffic through inspection layers (WAF, OAC).
- Guardrails for AI: Apply strict 3-layer control: Input (PII, Prompt Injection), Processing (Token budget, Timeout), and Output (Hallucination, Bias).

#### Real Deployment Strategy

- Phased approach for Enterprise AI: From Local/CrewAI → AgentCore → Docker/ECR → Lambda/API Gateway. Don't skip the security step.
- Measuring ROI: Transforming processes with AI (e.g., Credit Scoring) not only saves man-hours (95% reduction in decision costs) but also increases application approval rates.

### Applying to Work

- **Improve communication with AI:** Build prompt templates for software development team following framework: Goal - Context - Constraints - Format.
- **Manage AI stability:** Experiment with temperature = 0.1 instead of 0 for JSON data extraction tasks to avoid repetition errors; add fallback/retry logic in code.
- **Review infrastructure architecture:** Evaluate applying CloudFront and WAF for current projects, consider using HTTP compression and Origin Access Control features to optimize delivery costs and security.
- **Apply Multi-Agent:** Experiment splitting complex prompts/tasks into multiple roles (Reviewer, Coder, Tester) communicating with each other instead of bundling into one massive prompt.

### Event Experience

Attending the event was an eye-opening experience, perfectly connecting the mindset layer (Context/AI behavior), application layer (Multi-agent/Hackathon), and infrastructure layer (CloudFront/AWS services).

- **Learning from experts:** Talks didn't just scratch the surface but went very deep into essence (e.g., analysis of GPU floating-point math errors affecting LLM determinism).
- **Real experience:** Understanding the gap between an AI "draft" (POC AI) and an "enterprise-ready" system.
- **Connections and exchanges:** Realizing that engineers whether working at large banks or competing in hackathons all face common problems: Token limits, Hallucination, and Cloud cost management.

### Lessons Learned

- **Enterprise AI is not about making things work, it's about making them work securely, reliably, and at scale:** GenAI is easy for demos, but bringing it into enterprise requires strict architectural thinking (Guardrails, VPC, Auditability).
- In the GenAI era, Context Engineering and AI memory system design skills will be core competencies.
- No matter how far AI develops, a solid, secure, and cost-optimized network infrastructure (like CloudFront) remains an essential pillar for distributing applications to end users.

### Event Photos

![Event Photo 1](/images/event2-1.png)

![Event Photo 2](/images/event2-2.png)

![Event Photo 3](/images/event2-3.png)
