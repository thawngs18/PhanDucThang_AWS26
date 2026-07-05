---
title: "Event 4"
date: 2026-05-27
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# AWS FCAJ Community Day – June 2026 – Conference Call

### Event Objectives

- Share the most practical knowledge, experience, and insights from the enterprise environment about applying Cloud and AI.
- Introduce breakthrough AI solutions being applied to solve operational, DevOps, customer service, and HR management problems.
- Demonstrate live (Live Demo) how to deploy real AI Agent systems on AWS platform and secure connection architectures.

### Speakers

- **Steve Trần** - Founder of Cloud Thinker.
- **Hieu Nghi & Kiet** - Renova Cloud / Student Video Group.
- **Trung Dang** - Founder & CEO of R AI.
- **Bao & Nguyen Nguyen** - Cloud Engineer from Cloud Kinetics.
- **Truong (Wayne) & Minh Anh** - AI Solution / Solution Architect from Noventiq.
- **Toan Nguyen** - AWS Security Builder.

### Key Highlights

#### AI in Infrastructure Operations (Cloud Thinker)

- Operating large systems costs a lot of effort; people must face "technical debt" and complex systems.
- Introducing AI Operations platform: Comparing differences between Single-agent and Multi-agent.
- AI does not replace good engineers but maximally supports incident investigation, code review, FinOps, and Security.

#### Voice AI Solution for Vietnamese (R AI)

- Solving limitations of Speech-to-Speech models for Vietnamese (as it is a low-resource language).
- Standard process: Speech-to-Text → LLM (for context processing/Prompt) → Text-to-Speech.
- AI can recognize gender (anh/chị), understand interruption context, and apply tool calling (like automatically locking bank cards via hotline).

#### DevOps Agent (Cloud Kinetics)

- Solving Fragmented Telemetry problem (log/trace distributed in many places) that makes engineers waste time finding errors.
- DevOps Agent automatically classifies incidents, makes hypotheses, investigates root causes, and proposes Mitigation Plans instead of auto-executing (ensuring safety).

#### Amazon Q in HR Management (Noventiq)

- HR is spending a lot of time manually screening CVs, easily missing talents and affecting projects.
- Amazon Q helps automate Job Description (JD) creation, read and extract CV information, score candidates, and generate visual reports while maintaining data security for businesses.

#### AI Connection Security & MCP Server

- Connecting AI agents (like Amazon Q) with third-party applications (MCP Server) via Public Internet is very vulnerable to security risks (DDoS, Man-in-the-middle).
- Proposed solution: Use Private VPC Connection, through AWS ALB and Route 53 Resolver to keep data flow 100% internal.

### Key Takeaways

#### Design Mindset

- **Business-first & Real combat:** Every AI solution (like CV filtering or DevOps support) must start from real business pain points instead of just showing off technology.
- **Copilot instead of Autopilot:** AI acts as an assistant (providing mitigation plan, preparing reports); the final approval and execution rights always need Human-in-the-loop to ensure safety, especially for Production.

#### Technical Architecture

- **Multi-agent Architecture:** Understanding how to divide smaller Agents with shorter context windows to solve specialized tasks, helping optimize costs and control permissions (RBAC) more easily.
- **Architecture Security:** Clearly recognizing the importance of isolating (isolating) MCP Servers in Private Subnet when integrating AI systems into internal workflows.

#### Modernization Strategy

- When applying AI for business, evaluate costs (like data transfer in/out, round 53/VPC infrastructure) to ensure financial feasibility.
- Apply gradually (Phased approach), test in Development environment or for support-type tasks before deploying to critical environments.

### Applying to Work

- **Automate Incident Management:** Research applying DevOps Agent or AI workflows to support log reading, root cause analysis, helping reduce MTTD (Mean Time To Detect) and MTTR (Mean Time To Recovery).
- **Application for Non-Tech departments:** Survey deploying Amazon Q or automation tools for HR, Admin teams to support document reading, candidate screening, writing automatic email flows to increase productivity.
- **Redesign Voice Chatbot experience:** Note about interruption context and addressee culture (gender) if later developing voice bots serving domestic market.
- **Security review:** Update network architecture, review bringing APIs/Servers currently interacting with Public AI into Private VPC infrastructure.

### Event Experience

The event was a truly eye-opening experience, helping me realize AI today is not just about ordinary text-generating Chatbots, but is deeply penetrating core operational corners (Cloud Infrastructure, DevOps, HR).

- Live Demos directly on stage (Voice Agent calling to ask product questions, DevOps Agent sending load test requests to analyze, Amazon Q scoring CVs) were highly convincing, helping viewers easily visualize the architecture underneath.
- Had opportunities to connect with very dedicated and experienced people, learning startup building mindset from initial steps to serving Enterprise.

### Lessons Learned

- Even as AI (like Agent) technology develops quickly and strongly, the larger the system, the more important the role of (deep specialized) engineers becomes. AI amplifies capabilities but does not completely replace engineer skills.
- For low-resource languages like Vietnamese, taking the detour (Speech to Text → LLM → Text to Speech) combined with regional training data is the smartest solution at the current moment.
- Making AI for Enterprise means you must change business processes, and Security must always be a design factor considered from day one.

### Event Photos

![Event Photo 1](/images/event4-1.png)

![Event Photo 2](/images/event4-2.png)

![Event Photo 3](/images/event4-3.png)
