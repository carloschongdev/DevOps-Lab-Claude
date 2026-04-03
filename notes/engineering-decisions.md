# Engineering Decisions

This document records important decisions made during the DevOps Lab.

---

# Decision: Separate Documentation Repository

Two repositories are used.

devops-lab

Contains implementation.

devops-lab-claude

Contains documentation.

Reason:

Separating documentation from implementation keeps the technical repository clean and focused.

---

# Decision: Use GitHub Actions

GitHub Actions was selected for CI/CD.

Reason:

- native GitHub integration
- easy pipeline automation
- widely used in modern DevOps workflows

---

# Decision: Deterministic Pipelines

All pipelines must produce reproducible results.

Reason:

Reproducibility is critical in real DevOps environments.