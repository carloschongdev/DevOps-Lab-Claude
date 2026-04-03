# AI Mentor State

This document records the current state of the DevOps Lab.

Its purpose is to help AI assistants understand exactly where the lab
currently stands without having to infer progress from multiple files.

AI assistants should read this document before generating new instructions.

---

# Current Lab Status

Lab Progress Phase: Phase 4 — CI/CD Foundations

Last Completed Day: Day 25

Next Expected Task: Day 26

---

# Completed Milestones

The following milestones have been completed in the DevOps Lab:

• Git repository created
• Docker environment configured
• Dockerfile created
• Container build process implemented
• Local container execution tested
• Health check endpoint implemented
• CI pipeline concepts introduced
• GitHub Actions CI pipeline configured
• Container build in CI
• Container health check validation
• Artifact generation implemented
• Pipeline cleanup logic implemented

---

# Current Repository State (DevOps Lab)

The DevOps Lab repository currently contains:

Dockerfile
GitHub Actions pipeline
container health check endpoint
artifact generation script

The CI pipeline successfully builds the container image and performs
health validation.

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
