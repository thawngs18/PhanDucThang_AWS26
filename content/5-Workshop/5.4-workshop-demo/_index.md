---
title : "Workshop Demo & Video"
date : "2026-07-09"
weight : 4
chapter : false
pre : " <b> 5.4 </b> "
---
# 5.4. Workshop Demo & Video

---

## Live Demo

**Try Cloud Nexus now:** [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/)

![Cloud Nexus Live Demo](https://d3rs3evkmfvesp.cloudfront.net/)

---

## Demo Video

> **Video Demo:** [Cloud Nexus Workshop Demo Video](youtube.com/watch?v=j0-aYoJ2xpY&feature=youtu.be)

*Video demonstration of the complete Cloud Nexus platform including:*
- *Creating network topology*
- *AI-powered vulnerability scanning*
- *Attack path simulation*
- *Defense recommendations*

---

## Demo Features

### Feature 1: Visual Topology Editor

The ReactFlow-based editor allows users to drag and drop network components onto the canvas.

**Steps to demo:**
1. Open the application at [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/)
2. Select a node type from the left panel (Server, Database, Firewall, etc.)
3. Drag and drop onto the canvas
4. Connect nodes by dragging from one handle to another

**Expected result:** Nodes appear on canvas with edges connecting them

---

### Feature 2: AI-Powered Topology Generation

Type commands in the terminal to generate network topologies using AI.

**Steps to demo:**
1. Click on the terminal panel
2. Type: `generate a secure web application with load balancer`
3. Press Enter
4. Watch as AI generates the topology

**Expected result:** Network nodes and edges appear on canvas automatically

---

### Feature 3: Vulnerability Scanning

Scan the current topology for potential security vulnerabilities.

**Steps to demo:**
1. Create or generate a network topology
2. Type: `scan` in the terminal
3. View the attack scenarios panel

**Expected result:** List of potential attack scenarios with severity levels

---

### Feature 4: Attack Simulation

Simulate attack paths and see them visualized on the canvas.

**Steps to demo:**
1. Run a vulnerability scan first
2. Select an attack scenario from the panel
3. Click "Simulate Attack"
4. Watch the animated attack path

**Expected result:** Animated attack path highlights the route from attacker to target

---

### Feature 5: Defense Recommendations

Get AI-powered recommendations for securing the network.

**Steps to demo:**
1. After simulation, view the recommendations
2. Add defense nodes (Firewall, WAF, IDS) to the topology
3. Run simulation again to see improved security

**Expected result:** Attack paths blocked or mitigated by defense nodes

---

## Screenshot Verification Guide

📸 **Screenshot 1: Full Application Interface**

**How to capture:**
1. Open [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/)
2. Wait for full page load
3. Screenshot the complete interface

**What to verify:**
- Left panel: Node types available
- Center: ReactFlow canvas with grid
- Right panel: Terminal interface
- Bottom: Attack scenarios panel (if visible)

---

📸 **Screenshot 2: Topology Created**

**How to capture:**
1. Create a simple topology with 3+ nodes
2. Screenshot showing nodes connected by edges

---

📸 **Screenshot 3: AI Response in Terminal**

**How to capture:**
1. Type `help` in terminal
2. Screenshot the available commands

---

## Architecture Verification

| Component | URL | Status |
|-----------|-----|--------|
| Frontend (CloudFront) | https://d3rs3evkmfvesp.cloudfront.net/ | ✅ Deployed |
| API Gateway | https://\<id\>.execute-api.ap-southeast-1.amazonaws.com/prod/ | ✅ Deployed |
| Lambda | CloudNexus-BackendHandler | ✅ Deployed |
| S3 | cloudnexus-frontend-\<suffix\> | ✅ Deployed |

---

## Testing Checklist

| Test | Command | Expected Result |
|------|---------|-----------------|
| Health Check | `curl <api-url>/api/health` | `{"status":"ok"}` |
| Generate | `generate simple network` | Topology JSON |
| Scan | `scan` | Attack scenarios |
| Validate | POST `/api/topology/validate` | Validation result |

