# AI Project Bootstrap — DevOps Lab Claude

This document initializes the AI context for the **DevOps Lab Mentoring System**.

The purpose of this file is to quickly restore full understanding of the repository when starting a new AI conversation.

The AI must read this document first before performing any task.

---

# Repository Overview

This repository is **NOT the DevOps lab implementation itself**.

This repository is the **AI mentoring and learning control system** for the DevOps Lab.

The actual implementation repository is:

https://github.com/carloschongdev/devops-lab

That repository contains:

- Dockerfiles
- CI/CD pipelines
- Terraform code
- Kubernetes manifests
- Observability stack
- GitOps configuration

This repository contains the **learning framework and AI mentoring system**.

---

# Repository Purpose

The system guides a **90-day DevOps Engineering Lab** designed to simulate real engineering environments.

The AI acts as a **Senior DevOps Engineer mentor**.

The student performs hands-on implementation in the **implementation repository** while following structured instructions defined here.

---

# Learning Architecture

The lab is divided into progressive phases.

Phase 1 — DevOps Foundations  
Phase 2 — Git and Workflow Discipline  
Phase 3 — CI/CD Fundamentals  
Phase 4 — CI/CD Hardening  
Phase 5 — Docker Deep Dive  
Phase 6 — Infrastructure as Code (Terraform)  
Phase 7 — Kubernetes Operations  
Phase 8 — Platform Engineering  
Phase 9 — Observability & SRE  
Phase 10 — GitOps & Production Systems

---

# DevOps System Architecture

The DevOps system being built follows this flow:

Developer  
↓  
Git Repository  
↓  
CI Pipeline (GitHub Actions)  
↓  
Docker Build  
↓  
Container Registry  
↓  
Infrastructure Provisioning (Terraform)  
↓  
Kubernetes Cluster  
↓  
Platform Services

• Prometheus (metrics)  
• Grafana (dashboards)  
• Loki (logs)  
• Alertmanager (alerts)

↓  
GitOps Deployment (ArgoCD)

---

# AI Mentoring System

The AI behavior is controlled by documents in:



docs/ai/


Important files:


ai-context-index.md
ai-operating-rules.md
ai-reading-order.md
ai-session-start.md
ai-task-generation-rules.md
ai-learning-patterns.md
ai-mentor-state.md


These files define:

• how the AI must behave  
• how tasks are generated  
• how the lab progresses  
• how difficulty scales  

---

# Lab Execution Documents

Lab operation is controlled by:


mentor/


Key files:


claude-devops-mentor-prompt.md
lab-execution-protocol.md
lab-rules.md


These define how the AI should guide the student during the lab.

---

# DevOps Architecture Documentation

Located in:


docs/architecture/


Includes:


architecture.md
repo-architecture.md
pipeline-design.md
container-design.md
platform-architecture.md
ai-system-architecture.md


These describe the engineering architecture of the system being built.

---

# DevOps Learning System

Located in:


docs/devops/


Important documents:


devops-roadmap.md
devops-system-map.md
devops-lab-objectives.md
devops-lab-rules.md
devops-lab-skill-matrix.md
devops-lab-quality-gate.md
devops-lab-difficulty-scaling.md
devops-lab-failure-scenarios.md
incident-response-playbook.md


These define:

• learning goals  
• skill progression  
• difficulty scaling  
• failure simulations  

---

# Lab Tracking

Located in:


docs/lab/


Important files:


lab-progress.md
lab-daily-log.md
lab-phase-map.md
lab-environment.md
lab-simulation-engine.md
lab-ai-mentoring-history.md


These track the progress and state of the lab.

---

# Lab Plan Blocks

Detailed lab instructions are located in:


docs/lab-plan/


Files:


devops-lab-days-26-29.md
devops-lab-days-30-39.md
devops-lab-days-40-49.md
devops-lab-days-50-59.md
devops-lab-days-60-69.md
devops-lab-days-70-79.md
devops-lab-days-80-90.md
DevOps-Lab-Full-Curriculum.md


Each file contains the detailed execution plan for that block.

---

# Standards

Engineering standards are defined in:


standards/


Files:


commit-standards.md
container-standards.md
pipeline-standards.md


---

# Notes and Engineering Decisions

Located in:


notes/


Files:


devops-architecture-notes.md
engineering-decisions.md


---

# Current Lab Status

Completed Days:

Day 1 → Day 25

Current Phase:

Phase 4 — CI/CD Hardening

Current Block:

Days 26–29

Next Task:

Execute the expanded lab instructions in:


docs/lab-plan/devops-lab-days-26-29.md


---

# AI Operational Rules

The AI must follow these principles:

1. Never assume file contents.
2. Always inspect files before suggesting changes.
3. Provide deterministic instructions.
4. Prefer inspection and debugging tasks over theory.
5. Maintain progressive difficulty.
6. Do not skip lab phases.

---

# Pending Repository Improvements

The following tasks remain for this repository:

1. Improve the main README.md to clearly explain the system.
2. Create an AI context snapshot document.
3. Possibly add a DevOps system flow diagram.
4. Continue expanding lab blocks after completion.
5. Maintain troubleshooting documentation.

---

# Instructions for the AI

When this document is provided in a new conversation:

1. Read the repository architecture.
2. Understand the mentoring system.
3. Confirm the current lab status.
4. Ask if any files have changed.
5. Continue mentoring according to the lab plan.

Do not regenerate the lab plan unless explicitly asked.