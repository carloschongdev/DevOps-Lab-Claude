# AI Mentoring History

This document records important engineering decisions and mentoring interactions
used during the DevOps Lab.

Its purpose is to give context to AI mentors (Claude, ChatGPT) about the evolution
of the project and the decisions taken during development.

---

# DevOps Lab 2026

This repository is part of a structured DevOps learning path progressing through:

Docker → CI/CD → Infrastructure as Code → Kubernetes → Observability → Security.

The lab simulates real engineering practices including:

• container development
• CI/CD pipelines
• infrastructure automation
• debugging workflows
• documentation discipline

---

# AI Mentoring Strategy

Two AI mentors are used during the lab.

ChatGPT:
Provides architectural guidance, debugging assistance, and DevOps best practices.

Claude:
Acts as the structured mentor responsible for generating deterministic
daily instructions and lab progression.

This hybrid mentoring model allows deeper technical reasoning while
keeping the learning process structured.

---

# Key Engineering Decisions

## Decision — Introduce Claude Mentor Prompt

A structured mentor prompt was created to ensure the AI behaves like a
Senior DevOps Engineer guiding the lab.

Goals:

• prevent the AI from guessing repository state
• enforce deterministic instructions
• encourage concept-first learning
• require reviewing files before modifying them

---

## Decision — Create DevOps Lab Rules

The file `docs/devops-lab-rules.md` was introduced to define the operational
rules of the lab.

These rules enforce:

• incremental development
• debugging before guessing
• documentation of decisions
• structured commits

---

## Decision — Implement Local CI Pipeline

The repository introduced a local pipeline script:

run-pipeline.sh

This script simulates CI behavior locally and performs:

• Docker image build
• container execution
• health checks
• artifact generation
• cleanup

This allows testing CI behavior before pushing changes.

---

## Decision — Introduce Git Workflow Automation

A custom Git workflow was created to simplify daily commits.

Initial command:

git sync

Later evolved to:

git smart-sync

Capabilities:

• auto stage changes
• automatic commit generation
• rebase with remote branch
• push updates

This mirrors workflows used by DevOps engineers.

---

## Decision — Strengthen Repository Documentation

Additional documentation files were introduced:

docs/lab-environment.md
docs/devops-lab-rules.md
docs/lab-daily-log.md

These files provide context for both human readers and AI mentors.

---

# Current Progress

The lab is currently progressing through:

Phase 4 — CI/CD Hardening

Completed:

Day 25 — CI/CD pipeline implementation

Next step:

Day 26 — OCI Image Metadata
