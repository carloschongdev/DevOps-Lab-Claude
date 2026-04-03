# AI Learning Patterns for DevOps Lab

This document defines how the AI mentor should structure the learning progression of the DevOps Lab.

The purpose of this document is to ensure that the laboratory evolves from beginner-level tasks to production-style DevOps engineering practices.

Claude must follow these patterns when generating laboratory days.

---

# Core Philosophy

The DevOps Lab is designed as a **simulation of a real engineering environment**.

The student should not only learn tools but develop the ability to:

- build systems
- debug failures
- analyze logs
- understand system architecture
- automate repetitive work

Every phase must progressively increase technical complexity.

---

# Learning Pattern 1: Build → Break → Fix

One of the most effective learning strategies for DevOps is the cycle:

Build → Break → Fix

Claude should integrate this cycle into the laboratory.

Example:

Day 26  
Build a Docker container.

Day 27  
Introduce a configuration mistake that causes the container to fail.

Day 28  
Diagnose and repair the issue.

This pattern forces the student to understand the system rather than just following instructions.

---

# Learning Pattern 2: Increasing System Complexity

The lab should gradually move from simple systems to distributed systems.

### Level 1 – Local systems

Examples:

- Local Docker container
- Simple shell scripts
- Basic Git workflows

---

### Level 2 – Automated systems

Examples:

- CI/CD pipelines
- artifact generation
- automated builds

---

### Level 3 – Orchestrated systems

Examples:

- Kubernetes deployments
- container orchestration
- service exposure

---

### Level 4 – Production-style systems

Examples:

- monitoring
- observability
- debugging distributed systems
- system reliability practices

---

# Learning Pattern 3: Real Engineering Workflow

Each lab task should simulate real engineering work.

Example workflow:

1. implement a feature
2. run validation
3. detect failure
4. inspect logs
5. apply fix
6. validate again

This pattern reflects the real daily workflow of DevOps engineers.

---

# Learning Pattern 4: Artifact-Based Learning

Every task should produce a concrete artifact.

Examples:

- Docker image
- CI pipeline
- Kubernetes manifest
- monitoring configuration
- automation script

Artifacts allow the student to inspect, test, and improve their systems.

---

# Learning Pattern 5: System Visibility

DevOps engineers must understand what is happening inside systems.

Claude should integrate tasks that require:

- inspecting logs
- reading pipeline output
- checking container status
- verifying endpoints

Examples:

docker logs  
kubectl logs  
pipeline execution logs

---

# Learning Pattern 6: Troubleshooting Skills

The laboratory must regularly include troubleshooting tasks.

Examples:

- pipeline failure
- container crash
- misconfigured environment variables
- networking issue

The student should learn to diagnose problems using logs and system inspection.

---

# Learning Pattern 7: Incremental Automation

Automation should increase progressively.

Examples:

Early stages:

- manual commands

Later stages:

- automation scripts
- reusable CI pipelines
- infrastructure automation

This teaches the core DevOps philosophy:

"If you do something twice, automate it."

---

# Learning Pattern 8: Observability First Mindset

Modern DevOps requires system observability.

Claude should introduce concepts such as:

- logging
- metrics
- monitoring
- alerting

The student should learn to detect system issues through observability tools.

---

# Learning Pattern 9: Deterministic Instructions

The AI mentor must always provide deterministic instructions.

Each task should clearly specify:

- where commands should be executed
- which files must be edited
- how success is validated

This ensures reproducible results.

---

# Learning Pattern 10: Progressive Responsibility

As the lab progresses, the student should take more responsibility.

Early tasks:

Step-by-step guidance.

Later tasks:

High-level objectives with fewer hints.

This simulates real engineering growth.

---

# Final Rule

Claude must generate laboratory tasks that follow:

- Quality Gate rules
- Failure Scenarios
- Learning Patterns defined in this document

If a generated task does not include:

- implementation
- verification
- debugging potential

then the task is considered incomplete.