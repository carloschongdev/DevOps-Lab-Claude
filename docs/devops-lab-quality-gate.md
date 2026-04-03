# DevOps Lab Quality Gate

This document defines the quality requirements that every DevOps Lab task must satisfy.

The goal of this laboratory is not only to learn tools but to simulate real production engineering environments.

Claude must follow these quality rules when generating new laboratory tasks.

---

## Core Principle

Every lab day must include:

1. Conceptual learning
2. Hands-on implementation
3. Real debugging scenario
4. Validation of results

Tasks that only consist of "create something" without verification are considered low quality.

---

## Required Elements for Each Lab Day

Each lab day must include the following structure.

### 1. Learning Objective

A clear statement of what the student will learn.

Example:

- Understand Docker image layering
- Implement CI pipeline artifact storage
- Deploy a container to Kubernetes

---

### 2. Implementation Task

The student must implement something concrete such as:

- Dockerfile
- CI pipeline stage
- Kubernetes deployment
- Infrastructure configuration
- Automation script

Implementation tasks must produce a tangible artifact.

---

### 3. Failure or Debugging Scenario

Every few days the lab must include intentional failure scenarios such as:

- Broken pipeline
- Container crash
- Health check failure
- Misconfigured deployment

The student must analyze logs and resolve the issue.

---

### 4. Verification Step

Every task must end with verification.

Examples:

- container runs successfully
- pipeline passes
- endpoint responds
- logs show expected behavior

---

## Difficulty Progression

The laboratory must gradually increase difficulty.

### Phase 1

Basic tools

Examples:

- Docker
- Git workflows
- Local scripts

---

### Phase 2

CI/CD and automation

Examples:

- GitHub Actions
- artifact storage
- automated builds

---

### Phase 3

Infrastructure and orchestration

Examples:

- Kubernetes
- container orchestration
- deployments

---

### Phase 4

Observability and reliability

Examples:

- monitoring
- logging
- troubleshooting
- incident simulation

---

## Tasks That Are NOT Allowed

Claude must avoid generating tasks that are purely theoretical.

Bad examples:

- "Research Kubernetes"
- "Read documentation"
- "Learn about observability"

Every lab day must include real implementation.

---

## Validation Criteria

A lab task is considered successful if:

- a working artifact is created
- logs or output validate behavior
- debugging was required when appropriate