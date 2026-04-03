# Lab Environment

This document describes the environment used to run the DevOps Lab.

---

# Operating System

macOS

The environment uses Homebrew to install tools.

---

# Core Tools Installed

Git
Docker
Docker Compose
GitHub CLI
Bash (Homebrew version)

---

# Bash Location

The lab uses Homebrew bash.

However scripts should use:

#!/usr/bin/env bash

This ensures compatibility with Linux environments.

---

# Container Runtime

Docker Desktop

Containers are used to simulate deployment environments.

---

# CI/CD Platform

GitHub Actions

The repository contains a workflow located in:

.github/workflows/pipeline.yml

The pipeline performs:

• Docker image build
• Container startup
• Health check
• Artifact generation
• Cleanup

---

# Repository Structure

Expected structure:

docs/
notes/
scripts/
.github/workflows/

---

# Local Pipeline

The project includes a local pipeline script:

run-pipeline.sh

This script simulates CI behavior locally.

---

# Future Phases

Later phases will introduce:

Terraform
Kubernetes
Monitoring
Security Scanning
