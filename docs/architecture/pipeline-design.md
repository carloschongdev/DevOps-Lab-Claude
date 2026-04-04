# CI/CD Pipeline Design

This document explains the design decisions behind the CI pipeline used
in the DevOps Lab.

---

# Goals

The pipeline aims to simulate real CI behavior while remaining simple enough
to understand during the early phases of the lab.

Goals include:

• deterministic execution
• reproducible builds
• container validation
• artifact generation

---

# Pipeline Stages

Build Stage

The Docker image is built from the Dockerfile.

The image is tagged using the commit SHA to guarantee reproducibility.

---

Test Stage

The container is executed locally.

A health check verifies that the service is reachable.

This ensures the container actually runs before publishing artifacts.

---

Artifact Generation

The pipeline generates build metadata such as:

build-info.txt

This file records:

• build timestamp
• commit SHA
• pipeline duration

Artifacts are uploaded in GitHub Actions.

---

# Cleanup Stage

Containers created during the pipeline are removed to prevent
resource accumulation.

---

# Future Improvements

Future phases will introduce:

parallel pipeline stages
security scanning
container vulnerability scanning
deployment automation
