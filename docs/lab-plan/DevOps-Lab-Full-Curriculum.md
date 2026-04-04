# DevOps Lab — Full Curriculum (v2)

Author: Carlos Chong
Repository: DevOps-Lab-Claude
Purpose: Complete DevOps / Platform / SRE hands-on laboratory

---

# Overview

This repository contains a **complete hands-on DevOps laboratory** designed to simulate the learning path of a real DevOps / Platform / SRE engineer.

The lab contains **90 days of exercises**, with **thousands of commands**, and covers:

* DevOps pipelines
* Docker containerization
* Infrastructure as Code
* Kubernetes operations
* Platform engineering
* Observability
* SRE practices
* GitOps
* Production deployment strategies

The goal is to **learn by operating systems**, not just reading theory.

---

# Learning Philosophy

This lab follows these principles:

### 1 — Command-first learning

Every concept is executed through commands.

Most labs include:

* CLI operations
* debugging
* system inspection
* failure simulation
* recovery operations

---

### 2 — Production simulation

Instead of toy examples, the lab simulates real DevOps environments:

* CI pipelines
* Docker builds
* Kubernetes clusters
* monitoring stacks
* GitOps workflows

---

### 3 — Failure-driven learning

Many exercises simulate:

* pipeline failures
* container crashes
* Kubernetes outages
* resource exhaustion
* deployment errors

Understanding failures is critical for DevOps.

---

### 4 — Platform thinking

Later phases focus on **platform engineering concepts**:

* namespaces
* RBAC
* Helm
* ingress
* observability
* autoscaling

---

### 5 — SRE mindset

The lab introduces reliability engineering practices:

* SLI / SLO definitions
* monitoring
* alerting
* incident response
* chaos testing

---

# DevOps Lab Structure

The lab is divided into **phases**, each representing a major discipline.

---

# Phase 1 — CI Pipeline Debugging

Days:

```
26–29
```

File:

```
devops-lab-days-26-29.md
```

Topics:

* GitHub Actions
* pipeline debugging
* CI artifact management
* deterministic builds
* container health checks
* build metadata
* cleanup procedures

Goal:

Understand how CI pipelines behave internally and how to debug them.

---

# Phase 2 — Docker Advanced Operations

Days:

```
30–39
```

File:

```
devops-lab-days-30-39.md
```

Topics:

* container lifecycle
* networking
* container logs
* Docker volumes
* image layers
* container debugging
* image optimization
* multi-container environments

Goal:

Master Docker beyond basic container runs.

---

# Phase 3 — Infrastructure as Code (Terraform)

Days:

```
40–49
```

File:

```
devops-lab-days-40-49.md
```

Topics:

* Terraform CLI
* state management
* providers
* resource graphs
* infrastructure planning
* infrastructure debugging
* repeatable environments

Goal:

Understand how infrastructure can be version-controlled and reproducible.

---

# Phase 4 — Kubernetes Operations

Days:

```
50–59
```

File:

```
devops-lab-days-50-59.md
```

Topics:

* Kubernetes clusters
* pods
* deployments
* services
* configuration
* debugging
* cluster inspection

Goal:

Operate Kubernetes workloads directly.

---

# Phase 5 — Kubernetes Platform Engineering

Days:

```
60–69
```

File:

```
devops-lab-days-60-69.md
```

Topics:

* namespaces
* RBAC
* Helm
* ingress controllers
* metrics-server
* autoscaling
* resource quotas
* cluster governance

Goal:

Operate Kubernetes like a platform team.

---

# Phase 6 — SRE and Observability

Days:

```
70–79
```

File:

```
devops-lab-days-70-79.md
```

Topics:

* Prometheus
* Grafana
* Alertmanager
* Loki logging
* SLI / SLO metrics
* monitoring
* alerting
* incident simulation
* chaos engineering

Goal:

Understand how production systems are monitored and stabilized.

---

# Phase 7 — GitOps and Production Delivery

Days:

```
80–90
```

File:

```
devops-lab-days-80-90.md
```

Topics:

* ArgoCD
* GitOps workflows
* Kubernetes deployments via Git
* Blue-Green deployments
* Canary deployments
* disaster recovery
* cluster backups
* platform validation

Goal:

Operate a modern GitOps-based delivery platform.

---

# Laboratory Size

Approximate size of the laboratory:

```
9000 – 10000 commands
```

This makes the lab comparable to **months of real DevOps hands-on practice**.

---

# Repository Structure

Example structure:

```
DevOps-Lab-Claude
│
├── docs
│   ├── platform
│   ├── sre
│   └── final
│
├── kubernetes-lab
│
├── manifests
│
├── helm-lab
│
├── sre-stack
│
├── devops-lab-days-26-29.md
├── devops-lab-days-30-39.md
├── devops-lab-days-40-49.md
├── devops-lab-days-50-59.md
├── devops-lab-days-60-69.md
├── devops-lab-days-70-79.md
├── devops-lab-days-80-90.md
│
└── DevOps-Lab-Full-Curriculum.md
```

---

# How This Repository Works With Claude

The repository is designed to work with **AI-assisted iteration**.

Claude is used to:

* extend the laboratory
* add new exercises
* expand command sets
* simulate failure scenarios
* generate additional platform scenarios

The files in this repository act as the **baseline curriculum**.

Claude can expand them further.

---

# Final Goal

After completing this laboratory the learner will understand:

* DevOps pipelines
* container platforms
* Kubernetes operations
* platform engineering
* reliability engineering
* GitOps delivery

This represents a **full-stack DevOps learning environment**.

---

# Future Extensions

Possible expansions:

* multi-cluster Kubernetes
* service mesh
* advanced CI pipelines
* multi-cloud infrastructure
* platform APIs
* internal developer platforms

The lab can evolve indefinitely.
