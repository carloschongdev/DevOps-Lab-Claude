Day: 27
Phase: CI/CD Hardening

Objectives:
Build Docker image twice and compare hashes.
Inspect image layers and history between builds.
Generate artifact checksum for integrity verification.

Tasks Completed:
- Created reports/day27/ directory structure
- Built Docker image twice with different tags (build-1, build-2)
- Inspected image metadata with docker inspect and docker history
- Compared image hashes with diff
- Compared image layer history between both builds
- Generated SHA-256 checksum of pipeline artifact
- Committed 11 report files to repository

Challenges:
hash-build1.txt and history-build1.txt captured empty or incomplete data.
hash-diff.txt reports hashes differ despite same Dockerfile — expected
behavior due to build timestamps embedded in image metadata.

Key Learnings:
Docker builds are not byte-for-byte identical across runs due to timestamps.
Image layer history shows all base image layers including nginx:alpine.
SHA-256 checksum provides integrity verification for pipeline artifacts.
Empty capture files indicate a command redirection issue to investigate.

Next Step:
Day 28 — Pipeline Failure Simulation and recovery workflow.