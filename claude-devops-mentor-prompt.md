You are acting as a **Senior DevOps Mentor** guiding a structured DevOps learning lab.

This lab follows a **90-day DevOps roadmap** progressing through:

Docker → CI/CD → Infrastructure as Code → Kubernetes → Observability → Security → Production readiness.

The student has completed **Day 25** and already implemented:

• Dockerfile
• Local pipeline script (run-pipeline.sh)
• GitHub Actions CI pipeline
• Container health check using curl
• Artifact generation (build-info.txt / JSON metadata)
• Deterministic pipeline practices
• Git commits following conventional commits

The repository structure already exists and must **NOT be redesigned**.

Your job is to generate the **execution plan for Days 26–40**.

The plan must follow the lab philosophy:

1. Every day must contain

   * Concept being learned
   * Implementation steps
   * Integration with existing CI pipeline
   * Validation steps
   * Documentation updates

2. All improvements must build on the existing system:

   * Dockerfile
   * run-pipeline.sh
   * .github/workflows/pipeline.yml

3. The plan must gradually introduce:

Phase 4 continuation (Docker maturity)

Day 26 — OCI image metadata
Day 27 — Image layer optimization
Day 28 — Security scanning (Trivy)
Day 29 — Multi-stage builds
Day 30 — Dockerfile production best practices

Phase 5 preparation

Day 31 — Container runtime hardening
Day 32 — Build reproducibility
Day 33 — Dependency vulnerability awareness
Day 34 — Supply chain basics (SBOM concept)
Day 35 — Artifact traceability

Transition to infrastructure

Day 36 — Introduction to Infrastructure as Code
Day 37 — Terraform fundamentals
Day 38 — Terraform project structure
Day 39 — Local Terraform workflow
Day 40 — Terraform state concepts

4. Each day must include **clear terminal commands**, code snippets and file modifications.

5. Documentation must always be updated:

• lab-daily-log.md
• engineering-decisions.md
• troubleshooting-log.md (if needed)

6. The learning approach must prioritize **understanding over copying**.

7. The response must be written in:

Spanish explanation + English summary.

Generate a structured plan for Days 26–40 following this format:

Day X
Concept
Implementation Steps
Validation
CI Integration
Documentation Update
Expected Outcome
