# DevOps Lab Difficulty Scaling

This document defines how the difficulty of the DevOps Lab must evolve across the laboratory timeline.

The goal is to ensure that the laboratory gradually increases complexity and avoids repetitive or trivial tasks.

Claude must consult this document when generating new laboratory tasks.

---

# Difficulty Levels

The DevOps Lab is divided into four difficulty levels.

Each phase should progressively increase the student's responsibility and system complexity.

---

# Level 1 — Guided Execution

Student follows detailed step-by-step instructions.

Characteristics:

• simple tools  
• local environments  
• deterministic instructions  

Examples:

- running containers
- basic Git workflows
- simple shell commands

Claude should provide detailed instructions.

---

# Level 2 — Structured Implementation

Student still receives guidance but must implement larger components.

Characteristics:

• multi-step implementations  
• pipeline creation  
• container image design  

Examples:

- build CI pipeline
- create Dockerfile
- configure container health checks

Instructions should remain deterministic but allow some independent decisions.

---

# Level 3 — System Debugging

Student begins diagnosing problems in systems.

Characteristics:

• intentional failures
• troubleshooting tasks
• log inspection

Examples:

- broken pipeline
- failing container
- incorrect environment variables

Students must analyze logs and resolve the issue.

---

# Level 4 — Engineering Thinking

Student behaves more like an engineer rather than a learner.

Characteristics:

• architecture decisions
• minimal instructions
• problem-driven tasks

Examples:

- design monitoring solution
- improve pipeline reliability
- optimize container builds

Claude should provide objectives rather than detailed steps.

---

# Difficulty Timeline

Example progression:

Day 1–20  
Level 1

Day 21–40  
Level 2

Day 41–65  
Level 3

Day 66–90  
Level 4

---

# Task Complexity Rules

Claude must avoid repeating the same type of task multiple days in a row.

Example of bad progression:

Day 30 — create Dockerfile  
Day 31 — create another Dockerfile  
Day 32 — create another Dockerfile  

Example of good progression:

Day 30 — container build  
Day 31 — pipeline automation  
Day 32 — pipeline debugging

---

# Responsibility Growth

As the lab progresses the student must take more responsibility.

Early phases:

step-by-step instructions.

Later phases:

high-level objectives.

This prepares the student for real DevOps engineering work.

---

# Final Rule

When generating new lab days Claude must verify that:

• task difficulty increases over time  
• new concepts are introduced gradually  
• debugging tasks appear regularly  
• the student is challenged appropriately