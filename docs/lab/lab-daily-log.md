Day: 28
Phase: CI/CD Hardening

Objectives:
Simulate an intentional pipeline failure in GitHub Actions.
Analyze failure logs and recover the pipeline to its original state.
Scan the repository and Docker image for vulnerabilities with Trivy.
Simulate a CI cache archive and restore cycle.

Tasks Completed:
- Created branch pipeline-failure-test
- Added pipeline-failure-test trigger and Simulate failure step to workflow
- Validated YAML syntax with python3 before committing
- Pushed failure and confirmed conclusion=failure in GitHub Actions
- Extracted run ID with gh run list --json and captured in shell variable
- Downloaded failure logs with gh run view $FAILED_RUN_ID --log
- Analyzed logs with grep for error, failed, exit keywords
- Reverted workflow to original state and validated with diff
- Merged pipeline-failure-test to main and deleted branch
- Installed Trivy and scanned filesystem, Docker image, and Dockerfile
- Filtered CRITICAL and HIGH vulnerabilities to separate report files
- Created cache archive with tar and restored to cache/restore/
- Committed 19 report files and cache artifacts
- Created and pushed tag lab-day-28

Challenges:
gh run view without explicit run ID fails in non-interactive mode.
Fix: extract run ID with gh run list --json databaseId --jq and store in variable.

Key Learnings:
GitHub Actions workflows cannot be validated functionally without a remote runner.
Content validation (grep, diff, python3 yaml) must precede every commit on file edits.
Functional validation for workflows is confirmed via gh run list after push.
Trivy scans reveal CVEs in base images even without application vulnerabilities.
tar -czf and tar -xzf reproduce the cache save/restore pattern used in GitHub Actions.
gh run view requires an explicit run ID when output is redirected to a file.

Next Step:
Day 29 — Pipeline Recovery Metrics and artifact lifecycle management.