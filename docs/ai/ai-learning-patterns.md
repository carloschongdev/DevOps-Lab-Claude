# AI Learning Patterns — DevOps Lab

Purpose:

This document teaches AI systems (Claude, ChatGPT, etc.) how to expand the DevOps Lab with high-quality exercises.

The goal is to generate **practical, realistic DevOps learning scenarios**.

---

# Core Learning Philosophy

The DevOps Lab follows these principles:

1. Learn by operating systems
2. Learn through debugging
3. Learn through failure simulation
4. Learn through real CLI workflows

Exercises must be **command-first**, not theory-first.

---

# Exercise Design Patterns

AI should generate exercises following these patterns.

---

# Pattern 1 — Exploration

The learner explores a system.

Example:

* inspect docker containers
* inspect Kubernetes pods
* inspect cluster state

Example commands:

```
docker ps
docker inspect
kubectl get pods
kubectl describe pod
kubectl get events
```

Goal:

Understand system state.

---

# Pattern 2 — Failure Simulation

The AI should intentionally break systems.

Examples:

* delete running containers
* misconfigure deployments
* create invalid YAML
* exhaust CPU limits

Example commands:

```
kubectl delete pod
kubectl scale deployment --replicas=0
docker kill
```

Goal:

Teach debugging skills.

---

# Pattern 3 — Observability

Exercises should involve monitoring tools.

Examples:

* Prometheus queries
* Grafana dashboards
* cluster metrics

Commands may include:

```
kubectl top nodes
kubectl top pods
prometheus queries
```

Goal:

Teach system visibility.

---

# Pattern 4 — Production Incidents

AI should simulate incidents.

Examples:

* service outage
* deployment failure
* scaling incident
* resource exhaustion

Example flow:

1. create failure
2. detect issue
3. inspect logs
4. recover system

---

# Pattern 5 — Progressive Complexity

Exercises should increase difficulty.

Progression example:

Level 1

```
docker run nginx
```

Level 2

```
docker run -d nginx
docker logs
```

Level 3

```
docker inspect
docker network inspect
```

Level 4

debug container networking.

---

# Pattern 6 — Platform Thinking

Later exercises should focus on platform engineering.

Examples:

* namespaces
* RBAC
* ingress
* autoscaling
* Helm

Goal:

Understand how platforms operate at scale.

---

# Pattern 7 — GitOps Workflows

AI should generate exercises involving:

* Git commits
* CI pipelines
* ArgoCD sync
* Git-based deployments

Goal:

Teach modern DevOps delivery practices.

---

# Command Density Principle

Exercises should contain **large numbers of commands**.

Minimum expectations:

```
100 commands per day
```

Large command sets help build real CLI experience.

---

# Command Realism Rule

Commands must:

* be real
* be executable
* reflect real DevOps workflows

AI must avoid pseudo commands.

---

# Expansion Strategy

When extending lab files, AI should:

1. add new sections
2. add additional debugging scenarios
3. add deeper inspection commands
4. add failure recovery exercises

AI should **never remove existing exercises**.

---

# Long-Term Vision

This repository should grow into:

A large DevOps training environment with:

* thousands of commands
* realistic production simulations
* platform engineering workflows
* reliability engineering practices

AI should continuously expand this repository.
