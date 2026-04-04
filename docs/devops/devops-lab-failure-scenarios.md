# DevOps Lab Failure Scenarios

This document defines intentional failure situations that should be included in the laboratory.

Real DevOps engineers learn by diagnosing failures in systems.

Claude should integrate these scenarios across the lab timeline.

---

# Failure Scenario Categories

## CI/CD Failures

Examples:

- pipeline stage fails
- missing artifact
- incorrect build command
- failing test stage

Student responsibilities:

- inspect pipeline logs
- identify failing stage
- correct configuration

---

## Container Failures

Examples:

- container exits immediately
- incorrect ENTRYPOINT
- missing dependency
- broken health check

Student responsibilities:

- inspect container logs
- debug Dockerfile
- rebuild image

---

## Deployment Failures

Examples:

- Kubernetes pod crash
- incorrect port mapping
- misconfigured environment variables

Student responsibilities:

- inspect pod logs
- use kubectl describe
- correct deployment configuration

---

## Networking Failures

Examples:

- service unreachable
- incorrect port exposure
- container network misconfiguration

Student responsibilities:

- test endpoints
- inspect container networking
- fix configuration

---

## Observability Failures

Examples:

- missing metrics
- incorrect logging configuration
- monitoring alerts not triggered

Student responsibilities:

- analyze logs
- verify monitoring configuration
- restore observability

---

# Scenario Distribution

Failure scenarios should appear approximately every 3–4 lab days.

Example pattern:

Day 28 — pipeline failure  
Day 32 — container crash  
Day 35 — deployment issue  
Day 38 — monitoring failure

This ensures the student practices troubleshooting continuously.