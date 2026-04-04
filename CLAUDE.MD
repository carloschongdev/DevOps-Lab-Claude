# CLAUDE.md

Guide for Claude AI to understand and extend the DevOps Lab repository.

Repository: DevOps-Lab-Claude
Author: Carlos Chong

---

# Purpose of this File

This file explains how Claude should interact with the repository.

Claude is used to:

* expand the DevOps lab
* add additional commands
* simulate production scenarios
* add debugging exercises
* extend platform engineering tasks
* extend SRE exercises

Claude must **never replace the structure of the repository**.

Instead, it should **extend the existing files**.

---

# Repository Overview

The repository contains a **hands-on DevOps laboratory** consisting of multiple phases.

Each phase contains a file with commands and exercises.

Structure:

```
devops-lab-days-26-29.md
devops-lab-days-30-39.md
devops-lab-days-40-49.md
devops-lab-days-50-59.md
devops-lab-days-60-69.md
devops-lab-days-70-79.md
devops-lab-days-80-90.md

DevOps-Lab-Full-Curriculum.md
```

Each file represents **a block of learning exercises**.

---

# Command Philosophy

The lab is command-driven.

Claude must:

* provide CLI commands
* provide debugging scenarios
* simulate failures
* simulate recovery workflows
* simulate production incidents

Commands must be **real commands** that can be executed on a developer workstation.

---

# Command Density Rule

Each day in the lab should contain **a large number of commands**.

Minimum rule:

```
100 commands per day
```

Block rules:

```
Days 26–29  → 300+ commands
Days 30–39  → 1000+ commands
Days 40–49  → 1000+ commands
Days 50–59  → 1000+ commands
Days 60–69  → 1000+ commands
Days 70–79  → 1000+ commands
Days 80–90  → 1000+ commands
```

Claude should expand files if necessary to maintain command density.

---

# Technologies Used in the Lab

Claude should extend exercises using these technologies:

CI/CD

* GitHub Actions

Containers

* Docker

Infrastructure

* Terraform

Orchestration

* Kubernetes

Platform Engineering

* Helm
* RBAC
* Namespaces
* Ingress

Observability

* Prometheus
* Grafana
* Alertmanager
* Loki

SRE

* SLI / SLO
* incident response
* chaos engineering

GitOps

* ArgoCD

---

# Claude Expansion Rules

Claude may extend the lab by adding:

* new exercises
* new commands
* debugging scenarios
* production failure simulations
* infrastructure scenarios

Claude should **append exercises** instead of rewriting entire files.

---

# File Editing Rules

Claude must follow these rules when editing files.

1. Never remove existing exercises.
2. Never reduce the number of commands.
3. Always extend files by adding new sections.
4. Always keep chronological day structure.
5. Maintain CLI-first teaching style.

---

# Example Extension Pattern

Claude should extend files using sections like:

```
DAY 65 — Advanced Helm Debugging

DAY 66 — Kubernetes Failure Recovery

DAY 67 — Platform Resource Limits

DAY 68 — Incident Response Simulation
```

---

# Failure Simulation Rule

Claude is encouraged to add exercises involving:

* container crashes
* broken deployments
* resource exhaustion
* node failures
* misconfigured services

These scenarios help simulate real DevOps work.

---

# Documentation Generation

Claude may also extend:

```
docs/platform
docs/sre
docs/final
```

Examples:

* architecture diagrams
* SLO definitions
* platform documentation

---

# Final Goal

This repository should evolve into a **large DevOps practice environment** with:

* thousands of commands
* production-like scenarios
* platform engineering workflows
* SRE reliability exercises
* GitOps delivery pipelines

Claude should help expand this repository continuously.
