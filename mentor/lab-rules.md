# DevOps Lab Rules

These rules guide the DevOps Lab.

---

1. Every lab day must produce at least one commit.

2. All experiments must be reproducible.

3. Pipelines must be deterministic.

4. Implementation must be validated.

5. Documentation must be updated after each implementation.

6. Architecture decisions must be recorded.

7. The lab must simulate real engineering workflows.

8. After each completed lab day, create and push a git tag in devops-lab:

git tag lab-day-<N> <commit-sha>
git push origin lab-day-<N>

Tags must follow the format: lab-day-26, lab-day-27, lab-day-28, etc.
The commit SHA must correspond to the day's final commit.