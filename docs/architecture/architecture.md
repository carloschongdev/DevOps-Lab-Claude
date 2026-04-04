# System Architecture

This repository simulates a simplified DevOps pipeline architecture.

The goal is to reproduce key components of a production DevOps workflow.

---

# Architecture Overview

The system consists of the following components:

Developer Environment
Local CI Pipeline
Docker Container Runtime
GitHub Actions CI Pipeline

---

# Workflow

Developer Workflow

1. Developer writes code
2. Local pipeline is executed
3. Container is built and tested
4. Changes are committed
5. CI pipeline runs in GitHub Actions

---

# CI Pipeline Responsibilities

The CI pipeline performs:

• Docker image build
• container startup
• health checks
• artifact generation
• pipeline logging
• cleanup of resources

---

# Container Responsibilities

The container simulates an application service that exposes an HTTP endpoint.

This endpoint is used to verify container health during CI execution.

---

# Future Architecture Evolution

Later phases of the lab will introduce:

Infrastructure as Code (Terraform)

Kubernetes orchestration

Observability stack (Prometheus + Grafana)

Security scanning

Cloud deployment
