# DevOps Systems Map

## Purpose

This document describes how the different systems in the DevOps Lab connect together to form a complete production engineering workflow.

The goal is to understand not just tools, but the architecture of modern DevOps systems.

---

# 1. Development Layer

This is where engineers write and manage code.

Components:

* Git repository
* Source code
* Dockerfile
* Configuration files

Tools:

Git
GitHub

Key practices:

* commit history
* branching strategies
* reproducible builds

---

# 2. Build Layer (CI)

When code is pushed to the repository, the CI system runs automated tasks.

Components:

* CI pipeline
* build scripts
* automated checks

Tools:

GitHub Actions

Typical pipeline stages:

1. checkout repository
2. build container image
3. run tests
4. validate container health
5. generate build metadata
6. store artifacts

Outputs:

* Docker image
* logs
* build artifacts

---

# 3. Containerization Layer

The application is packaged into a portable runtime environment.

Components:

Dockerfile
container image

Tools:

Docker

Key concepts:

image layers
build caching
image tagging
reproducibility

Result:

Portable container image ready for deployment.

---

# 4. Artifact & Registry Layer

Built container images must be stored in a registry.

Components:

Container Registry

Examples:

Docker Hub
GitHub Container Registry
AWS ECR
GCP Artifact Registry

The CI pipeline pushes built images here.

---

# 5. Infrastructure Layer (IaC)

Infrastructure must be defined as code.

Tools:

Terraform

Responsibilities:

create infrastructure
configure networking
provision compute resources

Examples:

VM instances
load balancers
storage resources

---

# 6. Orchestration Layer

Containers are managed and scheduled across machines.

Tools:

Kubernetes

Key concepts:

Pods
Deployments
Services
Ingress
ConfigMaps
Secrets

Responsibilities:

schedule containers
manage scaling
handle service discovery

---

# 7. Observability Layer

Production systems must be monitored.

Tools:

Prometheus
Grafana
Loki

Observability components:

Metrics
Logs
Tracing

Goals:

system visibility
incident detection
performance analysis

---

# 8. Security Layer

Security must be integrated into the pipeline.

Tools:

Trivy
dependency scanners
secret scanners

Security checks include:

container vulnerabilities
dependency vulnerabilities
exposed secrets

---

# 9. Deployment Strategies

Production systems require safe deployment methods.

Examples:

Rolling deployments
Blue-green deployments
Canary deployments

Goals:

zero downtime
controlled rollout
safe rollback

---

# 10. Automation Layer (Python)

Python is used to automate DevOps workflows.

Examples:

deployment scripts
API integrations
monitoring utilities
CI helper scripts

Automation increases reliability and reduces manual operations.

---

# Full DevOps Flow

Developer
↓
Git Repository
↓
CI Pipeline
↓
Docker Build
↓
Container Registry
↓
Infrastructure Provisioning
↓
Kubernetes Deployment
↓
Monitoring and Observability
↓
Continuous Improvement

---

# Learning Objective

The DevOps Lab teaches not only tools but the full lifecycle of modern software systems.

Understanding how these layers interact is critical for becoming a production-level DevOps engineer.
