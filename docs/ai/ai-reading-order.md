# AI Reading Order

This document defines the recommended order in which AI assistants should read
the documentation contained in this repository.

The goal is to ensure that the AI understands the repository context before
generating instructions for the DevOps Lab.

---

# Step 1 — Repository Context

AI assistants should first read:

docs/ai-context-index.md

This file explains the purpose of the repository and provides an overview
of the documentation structure.

---

# Step 2 — AI Operational Rules

Next read:

docs/ai-operating-rules.md

This document defines how AI assistants must reason when interacting with
the repository and generating instructions.

---

# Step 3 — Repository Structure

Then read:

docs/repository-map.md

This document explains the structure of the repository and the purpose
of each directory.

---

# Step 4 — DevOps Lab Phases

Next read:

docs/lab-phase-map.md

This file explains the phases of the DevOps Lab and ensures that
generated instructions follow the correct learning progression.

---

# Step 5 — Current Lab Progress

Then read:

docs/lab-progress.md

This document tracks the current progress of the DevOps Lab.

AI assistants must use this information to determine what the next
instruction should be.

---

# Step 6 — AI Mentor State

Read:

docs/ai-mentor-state.md

This document summarizes the current progress of the DevOps Lab
and prevents the AI from repeating already completed tasks.
# Step 7 — Architecture Context

Next read the architecture documentation:

docs/architecture.md
docs/container-design.md
docs/pipeline-design.md
docs/devops-system-map.md

These files describe the design decisions used in the lab.

---

# Step 8 — Additional Context

Finally review:

docs/lab-ai-mentoring-history.md
docs/troubleshooting-log.md
notes/engineering-decisions.md

These documents provide historical context and debugging information.

---

# Important Rule

AI assistants should always review repository context before generating
instructions or proposing modifications.
