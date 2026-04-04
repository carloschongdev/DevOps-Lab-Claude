# Repository Architecture

Repository: DevOps Lab
Author: Carlos Chong

---

# Purpose of this Document

This document explains the **architecture and organization of the repository**.

The repository is designed as a **structured DevOps learning environment** supported by AI mentoring systems.

It contains:

* DevOps lab exercises
* system documentation
* AI mentoring configuration
* engineering standards
* technical notes

The goal is to maintain a **clear separation between learning, documentation, and system rules**.

---

# High-Level Structure

Repository structure overview:

```
/
├── CLAUDE.md
├── README.md
│
├── docs/
├── mentor/
├── standards/
├── notes/
```

Each directory has a **specific role** in the DevOps Lab ecosystem.

---

# Root Level Files

## CLAUDE.md

Defines how Claude AI should interact with the repository.

It includes:

* AI behavior rules
* repository interpretation guidelines
* lab expansion strategy

Claude reads this file **before analyzing the rest of the repository**.

---

## README.md

Public entry point of the repository.

Contains:

* project overview
* DevOps Lab explanation
* how to navigate the repository
* quick start information

---

# docs Directory

The `docs/` directory contains **the main knowledge base of the repository**.

It includes documentation describing:

* the lab structure
* engineering decisions
* AI mentoring system
* system architecture

Examples:

```
docs/
├── devops-roadmap.md
├── devops-system-map.md
├── architecture.md
├── pipeline-design.md
├── container-design.md
```

These documents describe **how the DevOps environment is designed**.

---

# AI Mentoring Documentation

Several files in `docs/` define how the **AI mentoring system operates**.

Examples:

```
ai-learning-patterns.md
ai-operating-rules.md
ai-session-start.md
ai-reading-order.md
ai-task-generation-rules.md
```

These files instruct AI systems such as Claude to:

* generate tasks
* mentor the learner
* simulate DevOps scenarios
* expand the lab exercises

Together they form the **AI mentoring framework**.

---

# Lab Tracking Documents

Some documents track the progress of the laboratory.

Examples:

```
lab-progress.md
lab-daily-log.md
lab-phase-map.md
lab-environment.md
```

These files help maintain:

* lab history
* execution progress
* learning milestones

---

# Lab Design Documents

The repository also contains documents describing the **structure of the lab itself**.

Examples:

```
devops-lab-objectives.md
devops-lab-skill-matrix.md
devops-lab-quality-gate.md
devops-lab-rules.md
devops-lab-difficulty-scaling.md
devops-lab-failure-scenarios.md
```

These documents define:

* the skills being trained
* the difficulty progression
* failure simulations
* lab constraints

---

# lab-plan Directory

Inside `docs/` there is a `lab-plan/` directory.

This folder contains the **detailed structure of the laboratory phases**.

Example structure:

```
docs/lab-plan/
```

This directory describes:

* daily objectives
* lab phase progression
* exercise structure

These files act as the **design blueprint of the lab exercises**.

---

# mentor Directory

The `mentor/` directory defines the **AI mentoring system prompts**.

Example files:

```
mentor/
├── claude-devops-mentor-prompt.md
├── lab-execution-protocol.md
├── lab-rules.md
```

These files configure:

* AI mentor behavior
* session execution rules
* mentoring workflow

This allows Claude to act as a **DevOps mentor instead of a simple assistant**.

---

# standards Directory

The `standards/` directory defines **engineering standards used in the lab**.

Examples:

```
standards/
├── commit-standards.md
├── container-standards.md
├── pipeline-standards.md
```

These documents define rules for:

* commit messages
* container design
* CI pipeline structure

This simulates **real engineering team standards**.

---

# notes Directory

The `notes/` directory contains **engineering thinking and technical notes**.

Examples:

```
notes/
├── devops-architecture-notes.md
├── engineering-decisions.md
```

These files capture:

* reasoning behind architecture decisions
* system exploration
* experimentation results

---

# How the Repository Works

The DevOps Lab operates in the following cycle:

1. AI mentor generates tasks
2. Lab exercises are executed
3. results are logged
4. architecture is refined
5. system documentation evolves

This cycle simulates a **real DevOps engineering workflow**.

---

# AI Integration

The repository is designed to work with AI tools such as:

* Claude
* ChatGPT

AI systems use the documentation to:

* understand repository context
* generate new exercises
* extend the laboratory
* simulate engineering mentoring

---

# Long-Term Vision

This repository aims to evolve into:

A **complete DevOps training environment** including:

* CI/CD systems
* container platforms
* Kubernetes operations
* platform engineering practices
* reliability engineering exercises

The architecture allows the repository to grow without losing structure.
