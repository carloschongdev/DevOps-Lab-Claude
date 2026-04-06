# DevOps Lab Claude

AI-Driven DevOps Engineering Lab Framework

---

# Overview

This repository contains the **AI mentoring system and documentation framework** used to guide the execution of the **DevOps Lab 2026**.

The objective of this project is to develop **production-level DevOps engineering skills** through a structured **90-day hands-on laboratory**.

The lab simulates real engineering environments covering:

• Docker containerization
• CI/CD pipelines
• Infrastructure as Code
• Kubernetes platform operations
• Observability and monitoring
• Security practices
• Production deployment strategies

---

# Repository Role

This repository **does not contain the implementation of the DevOps platform**.

Instead, it contains the **learning system, documentation, and AI mentoring architecture** that guides the lab.

The actual implementation repository is:

https://github.com/carloschongdev/devops-lab

That repository contains the real technical artifacts such as:

• Dockerfiles
• GitHub Actions pipelines
• container configuration
• build and test processes
• infrastructure code

This repository functions as the **DevOps engineering notebook and mentoring system**.

---

# DevOps Platform Architecture

During the lab a full DevOps delivery platform is progressively built.

```
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
Infrastructure (Terraform)
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
```

---

# AI Mentoring System

A structured AI mentoring architecture guides the lab execution.

The AI behaves as a **Senior DevOps Engineer mentor** following deterministic rules defined in:

```
docs/ai/
```

These files define:

• AI operating rules
• task generation constraints
• learning patterns
• mentoring state tracking
• session initialization logic

This ensures that the AI provides **structured engineering guidance instead of generic answers**.

---

# Repository Structure

```
DevOps-Lab-Claude
│
├── CLAUDE.MD
├── docs
│
│   ├── ai
│   │   AI mentoring system
│   │
│   ├── architecture
│   │   DevOps platform design documentation
│   │
│   ├── devops
│   │   Learning system definitions
│   │
│   ├── lab
│   │   Lab state and progress tracking
│   │
│   ├── lab-plan
│   │   Detailed lab execution blocks
│   │
│   ├── repository-map.md
│   └── troubleshooting-log.md
│
├── mentor
│   AI mentoring prompts and execution protocols
│
├── standards
│   Engineering standards used in the lab
│
├── notes
│   Architecture notes and decisions
│
└── README.md
```

---

# Lab Plan Structure

The lab is divided into progressive blocks located in:

```
docs/lab-plan/
```

Example:

```
devops-lab-days-26-29.md
devops-lab-days-30-39.md
devops-lab-days-40-49.md
```

Each block contains:

• learning goals
• conceptual explanations
• deterministic command sequences
• validation steps
• debugging exercises

---

# Learning Philosophy

The lab follows a **depth-first engineering approach** focused on building real operational capability.

Core principles include:

• deterministic systems
• reproducible pipelines
• debugging discipline
• infrastructure thinking
• production-grade workflows

The objective is not just learning tools, but understanding **how DevOps systems behave in production environments**.

---

# Current Progress

Current status of the DevOps Lab:

Completed: **Day 26**

Active Phase:

**Phase 4 — CI/CD Hardening**

Current focus:

• container metadata
• pipeline traceability
• deterministic builds
• CI debugging techniques

---

# Development Environment

Editor configuration used during the lab is stored in:

```
dotfiles/vscode/settings.json
```

This ensures a consistent development environment across sessions.

---

# Author

Carlos Chong
DevOps Engineering Learning Project — 2026
