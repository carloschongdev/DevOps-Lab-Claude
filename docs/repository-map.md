# Repository Map

This document explains the structure of the DevOps Lab Claude control repository.

The repository contains documentation, mentoring prompts, and execution rules
used to guide the DevOps Lab.

---

# Root Directory

The root directory contains only high-level project files.

README.md
General explanation of the repository.

.claude/
Internal prompts used by Claude to maintain context.

---

# mentor/

This directory contains the configuration used to guide the AI mentor.

claude-devops-mentor-prompt.md
Defines the behavior of the DevOps mentor.

lab-execution-protocol.md
Defines how daily lab instructions must be generated.

lab-rules.md
Operational rules that the DevOps lab must follow.

---

# docs/

This directory contains documentation about the DevOps Lab architecture.

architecture.md
High-level architecture of the lab environment.

container-design.md
Design decisions related to container usage.

pipeline-design.md
Explanation of CI/CD pipeline design.

devops-roadmap.md
Long-term DevOps learning roadmap.

devops-system-map.md
Visual overview of the DevOps lab components.

lab-progress.md
Tracks the current progress of the lab.

troubleshooting-log.md
Records important debugging events.

repository-map.md
This document.

ai-operating-rules.md  
Defines how AI assistants should reason before generating instructions.

---

# notes/

Temporary notes and engineering observations during the lab.

# AI Usage

AI assistants should first read:

1. docs/ai-context-index.md
2. docs/repository-map.md
3. docs/lab-progress.md
4. mentor/claude-devops-mentor-prompt.md

These files provide the necessary context to generate correct instructions.