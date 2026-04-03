# DevOps Architecture Notes

This document tracks the evolving architecture of the DevOps Lab.

---

# Current Architecture

Developer
↓
GitHub Repository
↓
GitHub Actions CI Pipeline
↓
Docker Image Build
↓
Container Health Check
↓
Build Artifact Generation

---

# Pipeline Flow

1. Code is pushed to GitHub
2. GitHub Actions triggers the CI pipeline
3. Docker image is built
4. Container is started
5. Health check validates the container
6. Build metadata is generated
7. Artifact is uploaded

---

# Future Architecture

Developer
↓
GitHub
↓
CI/CD Pipeline
↓
Docker Image
↓
Container Registry
↓
Kubernetes Cluster
↓
Monitoring Stack

---

# Future Components

The lab will expand to include:

- Terraform
- Kubernetes
- Observability
- Production-style pipelines