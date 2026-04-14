# AI Mentor State

This document records the current state of the DevOps Lab.

Its purpose is to help AI assistants understand exactly where the lab
currently stands without having to infer progress from multiple files.

AI assistants should read this document before generating new instructions.

---

# Current Lab Status

Lab Progress Phase: Phase 4 — CI/CD Hardening

Last Completed Day: Day 27

Next Expected Task: Day 28

---

# Completed Milestones

The following milestones have been completed in the DevOps Lab:

- Git repository created
- Docker environment configured
- Dockerfile created
- Container build process implemented
- Local container execution tested
- Health check endpoint implemented
- CI pipeline concepts introduced
- GitHub Actions CI pipeline configured
- Container build in CI
- Container health check validation
- Artifact generation implemented
- Pipeline cleanup logic implemented
- GitHub CLI installed and authenticated
- CI pipeline runs inspected with gh run list and gh run view
- Pipeline logs downloaded and analyzed
- Build artifact downloaded and commit SHA verified
- Idempotent cleanup pattern identified in pipeline logs
- Docker image built twice and hashes compared
- Image layer history inspected with docker history
- Build non-determinism identified and explained
- SHA-256 artifact checksum generated
- Intentional pipeline failure introduced and observed in GitHub Actions
- Failing run logs downloaded and analyzed with grep
- Pipeline recovered and restored to original state
- Workflow diff validated against pre-edit snapshot
- Trivy installed and filesystem scanned for vulnerabilities
- Docker image scanned with Trivy for CVEs
- Dockerfile misconfiguration scan executed
- CI cache lifecycle simulated with tar archive and restore
- gh run view --log used with explicit run ID via shell variable


# Current Repository State (DevOps Lab)

The DevOps Lab repository currently contains:

Dockerfile
GitHub Actions pipeline
container health check endpoint
artifact generation script
reports/day26/ with 10 inspection report files
reports/day27/ with 11 build comparison report files
reports/day28/ with pipeline failure logs, trivy scans, workflow snapshots and diffs
cache/test-cache/ with simulated cache files
cache/cache.tar.gz
notes/day26-reflection.md
notes/day27-reflection.md
Tag: lab-day-28

The CI pipeline was intentionally broken and recovered during Day 28.
Trivy scanning is now available in the local environment.
---

# Known Constraints

The DevOps Lab follows a strict progression model.

New instructions must:

• follow the phase progression defined in docs/lab-phase-map.md
• respect the progress recorded in docs/lab-progress.md
• introduce concepts incrementally

AI assistants must not skip phases of the lab.

---

# Mentor Instructions

Before generating new tasks, the AI mentor should:

1. Read docs/ai-reading-order.md
2. Review docs/lab-progress.md
3. Review docs/lab-phase-map.md
4. Confirm the next logical step of the lab

The mentor should avoid generating instructions that repeat already
completed milestones.

---

# State Update Rule

Whenever a major milestone of the lab is completed, this document
should be updated to reflect the new state.

This ensures that future AI sessions always start with accurate
context about the lab progress.
