# DevOps Lab — Days 26–29

Phase: CI/CD Pipeline Hardening

This phase focuses on strengthening the CI pipeline created in earlier phases.

Goals:

* Inspect CI execution deeply
* Validate artifacts
* Simulate pipeline failures
* Measure pipeline performance
* Debug GitHub Actions
* Ensure build reproducibility

All commands must be executed from **repository root** unless explicitly stated.

---

# DAY 26 — CI Pipeline Inspection

## Objective

Perform a deep inspection of the current CI pipeline execution.

---

## Step 1 — Inspect repository state

Type manually:

```
pwd
```

```
git status
```

```
git branch
```

```
git remote -v
```

Save repository information.

```
mkdir -p reports/day26
```

```
git status > reports/day26/git-status.txt
```

```
git branch -a > reports/day26/git-branches.txt
```

```
git log --oneline -n 20 > reports/day26/git-history.txt
```

---

## Step 2 — Inspect GitHub Actions configuration

List workflow files.

```
ls .github/workflows
```

Inspect workflow.

```
cat .github/workflows/*
```

Save workflow snapshot.

```
cat .github/workflows/* > reports/day26/workflow-snapshot.yml
```

---

## Step 3 — Install GitHub CLI

Type manually:

```
brew install gh
```

Verify installation.

```
gh --version
```

Save version.

```
gh --version > reports/day26/gh-version.txt
```

---

## Step 4 — Authenticate GitHub CLI

Type manually:

```
gh auth login
```

Verify authentication.

```
gh auth status
```

Save authentication status.

```
gh auth status > reports/day26/gh-auth-status.txt
```

---

## Step 5 — Inspect pipeline runs

List pipeline runs.

```
gh run list
```

Save run list.

```
gh run list > reports/day26/pipeline-runs.txt
```

Inspect specific run.

```
gh run view
```

Save run details.

```
gh run view > reports/day26/pipeline-run-details.txt
```

---

## Step 6 — Download artifacts

Type manually:

```
gh run download
```

Inspect downloaded artifacts.

```
ls
```

Move artifacts to directory.

```
mkdir -p artifacts/day26
```

```
mv * artifacts/day26/
```

---

# DAY 27 — Artifact Verification

---

## Step 1 — Inspect artifact directory

Type manually:

```
ls artifacts
```

```
ls artifacts/day26
```

Save artifact list.

```
ls artifacts/day26 > reports/day27-artifact-list.txt
```

---

## Step 2 — Generate checksum

Type manually:

```
shasum -a 256 artifacts/day26/*
```

Save checksum.

```
shasum -a 256 artifacts/day26/* > reports/day27-artifact-checksum.txt
```

---

## Step 3 — Verify deterministic build

Build Docker image again.

Type manually:

```
docker build -t devops-lab:test .
```

Inspect image.

```
docker images
```

Save image list.

```
docker images > reports/day27-docker-images.txt
```

Inspect image ID.

```
docker inspect devops-lab:test
```

Save image metadata.

```
docker inspect devops-lab:test > reports/day27-image-metadata.json
```

---

## Step 4 — Compare image hash

Type manually:

```
docker image inspect devops-lab:test --format='{{.Id}}'
```

Save image hash.

```
docker image inspect devops-lab:test --format='{{.Id}}' > reports/day27-image-hash.txt
```

---

## Step 5 — Rebuild image

Type manually:

```
docker build -t devops-lab:test2 .
```

Inspect second image.

```
docker image inspect devops-lab:test2 --format='{{.Id}}'
```

Save second hash.

```
docker image inspect devops-lab:test2 --format='{{.Id}}' > reports/day27-image-hash-rebuild.txt
```

Compare hashes.

```
diff reports/day27-image-hash.txt reports/day27-image-hash-rebuild.txt
```

Save diff.

```
diff reports/day27-image-hash.txt reports/day27-image-hash-rebuild.txt > reports/day27-build-diff.txt
```

---

# DAY 28 — Pipeline Failure Simulation

---

## Step 1 — Create failure branch

Type manually:

```
git checkout -b pipeline-failure-test
```

Verify branch.

```
git branch
```

Save branch list.

```
git branch > reports/day28-branches.txt
```

---

## Step 2 — Introduce pipeline failure

Edit workflow.

```
nano .github/workflows/*
```

Add failure step:

```
run: exit 1
```

Save file.

---

## Step 3 — Commit failure

Type manually:

```
git add .
```

```
git commit -m "simulate pipeline failure"
```

```
git push origin pipeline-failure-test
```

---

## Step 4 — Monitor failing pipeline

Type manually:

```
gh run list
```

Inspect failing run.

```
gh run view
```

Save logs.

```
gh run view --log > reports/day28-pipeline-failure-log.txt
```

---

## Step 5 — Analyze failure logs

Search for error.

Type manually:

```
grep -i error reports/day28-pipeline-failure-log.txt
```

Save error summary.

```
grep -i error reports/day28-pipeline-failure-log.txt > reports/day28-error-summary.txt
```

---

# DAY 29 — Pipeline Recovery and Metrics

---

## Step 1 — Fix pipeline

Type manually:

```
nano .github/workflows/*
```

Remove failure step.

Save file.

---

## Step 2 — Commit fix

Type manually:

```
git add .
```

```
git commit -m "fix pipeline failure"
```

```
git push
```

---

## Step 3 — Monitor successful run

Type manually:

```
gh run list
```

Inspect run.

```
gh run view
```

Save success logs.

```
gh run view --log > reports/day29-success-log.txt
```

---

## Step 4 — Pipeline performance metrics

Type manually:

```
gh run list --limit 10
```

Save performance data.

```
gh run list --limit 10 > reports/day29-pipeline-performance.txt
```

---

## Step 5 — Artifact validation

Type manually:

```
gh run download
```

Inspect artifacts.

```
ls
```

Save artifact list.

```
ls > reports/day29-artifacts.txt
```

---

# Final Step — Phase Documentation

Create documentation file.

Type manually:

```
mkdir -p docs
```

```
touch docs/pipeline-hardening.md
```

Document:

* CI debugging techniques
* artifact validation
* pipeline failure analysis
* reproducible builds
* pipeline recovery procedures

# Additional Modules — Pipeline Hardening

These modules extend the pipeline hardening phase.

Goals:

* Improve CI security
* Analyze pipeline performance
* Test artifact lifecycle
* Implement pipeline caching
* Validate concurrency control

All commands must be executed from **repository root** unless explicitly stated.

---

# MODULE 1 — CI Security Scanning

## Objective

Add dependency and container security validation to the CI workflow.

---

## Step 1 — Install Trivy

Type manually:

```id="trv1"
brew install trivy
```

Verify installation.

```id="trv2"
trivy --version
```

Save version.

```id="trv3"
trivy --version > reports/day28-trivy-version.txt
```

---

## Step 2 — Scan repository filesystem

Type manually:

```id="trv4"
trivy fs .
```

Save scan results.

```id="trv5"
trivy fs . > reports/day28-fs-security-scan.txt
```

---

## Step 3 — Scan Docker image

Type manually:

```id="trv6"
trivy image devops-lab:test
```

Save container scan.

```id="trv7"
trivy image devops-lab:test > reports/day28-container-scan.txt
```

---

## Step 4 — Scan Dockerfile misconfigurations

Type manually:

```id="trv8"
trivy config .
```

Save result.

```id="trv9"
trivy config . > reports/day28-dockerfile-config-scan.txt
```

---

## Step 5 — Filter vulnerabilities

Type manually:

```id="trv10"
grep -i critical reports/day28-container-scan.txt
```

```id="trv11"
grep -i high reports/day28-container-scan.txt
```

Save filtered output.

```id="trv12"
grep -i critical reports/day28-container-scan.txt > reports/day28-critical-vulns.txt
```

---

# MODULE 2 — Pipeline Caching Simulation

## Objective

Simulate cache usage in CI pipelines.

---

## Step 1 — Create cache directory

Type manually:

```id="cache1"
mkdir -p cache/test-cache
```

Create sample files.

```id="cache2"
echo "cache-test-1" > cache/test-cache/file1.txt
```

```id="cache3"
echo "cache-test-2" > cache/test-cache/file2.txt
```

Verify files.

```id="cache4"
ls cache/test-cache
```

Save cache structure.

```id="cache5"
tree cache > reports/day28-cache-tree.txt
```

---

## Step 2 — Generate cache archive

Type manually:

```id="cache6"
tar -czf cache/cache.tar.gz cache/test-cache
```

Verify archive.

```id="cache7"
ls cache
```

Save archive listing.

```id="cache8"
ls cache > reports/day28-cache-archive.txt
```

---

## Step 3 — Restore cache simulation

Type manually:

```id="cache9"
mkdir -p cache/restore
```

```id="cache10"
tar -xzf cache/cache.tar.gz -C cache/restore
```

Verify restore.

```id="cache11"
ls cache/restore
```

Save restore result.

```id="cache12"
ls cache/restore > reports/day28-cache-restore.txt
```

---

# MODULE 3 — Pipeline Concurrency Testing

## Objective

Simulate concurrent pipeline executions.

---

## Step 1 — Trigger multiple runs

Type manually:

```id="conc1"
git commit --allow-empty -m "trigger pipeline 1"
```

```id="conc2"
git push
```

Repeat multiple triggers.

```id="conc3"
git commit --allow-empty -m "trigger pipeline 2"
```

```id="conc4"
git push
```

```id="conc5"
git commit --allow-empty -m "trigger pipeline 3"
```

```id="conc6"
git push
```

---

## Step 2 — Inspect pipeline queue

Type manually:

```id="conc7"
gh run list
```

Save pipeline queue.

```id="conc8"
gh run list > reports/day28-concurrency-runs.txt
```

---

## Step 3 — Inspect specific runs

Type manually:

```id="conc9"
gh run view
```

Save details.

```id="conc10"
gh run view > reports/day28-concurrency-details.txt
```

---

# MODULE 4 — Pipeline Timing Analysis

## Objective

Analyze execution times of CI pipelines.

---

## Step 1 — List recent runs

Type manually:

```id="time1"
gh run list --limit 20
```

Save runs.

```id="time2"
gh run list --limit 20 > reports/day29-run-history.txt
```

---

## Step 2 — Extract duration

Type manually:

```id="time3"
gh run view
```

Search for duration.

```id="time4"
grep -i duration reports/day29-run-history.txt
```

Save timing info.

```id="time5"
grep -i duration reports/day29-run-history.txt > reports/day29-duration.txt
```

---

## Step 3 — Estimate average runtime

Type manually:

```id="time6"
cat reports/day29-duration.txt
```

Save manual calculation notes.

```id="time7"
echo "average runtime analysis" > reports/day29-runtime-analysis.txt
```

---

# MODULE 5 — Artifact Retention Testing

## Objective

Test artifact lifecycle management.

---

## Step 1 — Download artifacts

Type manually:

```id="art1"
gh run download
```

Verify artifacts.

```id="art2"
ls
```

Move artifacts.

```id="art3"
mkdir -p artifacts/day29
```

```id="art4"
mv * artifacts/day29/
```

---

## Step 2 — Inspect artifact metadata

Type manually:

```id="art5"
ls -lh artifacts/day29
```

Save metadata.

```id="art6"
ls -lh artifacts/day29 > reports/day29-artifact-metadata.txt
```

---

## Step 3 — Simulate artifact expiration

Type manually:

```id="art7"
mkdir -p artifacts/expired
```

```id="art8"
mv artifacts/day29/* artifacts/expired/
```

Verify move.

```id="art9"
ls artifacts/expired
```

Save expired artifact list.

```id="art10"
ls artifacts/expired > reports/day29-expired-artifacts.txt
```

---

# MODULE 6 — Pipeline Documentation

Create CI security documentation.

Type manually:

```id="doc1"
touch docs/ci-security.md
```

Create caching documentation.

```id="doc2"
touch docs/ci-caching.md
```

Create pipeline performance documentation.

```id="doc3"
touch docs/ci-performance.md
```

Add notes about:

* CI security scanning
* pipeline caching
* concurrency testing
* artifact retention
