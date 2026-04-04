# DevOps Lab — Days 80–90

Phase: GitOps / Production Delivery Platform

Goal:

Build a **production-style DevOps platform** where:

Git → CI → Docker → Kubernetes → Observability

and deployments are controlled using **GitOps**.

Technologies used:

* ArgoCD
* GitHub
* Kubernetes
* Helm
* GitOps workflows
* progressive delivery
* disaster recovery

All commands executed from **repository root** unless specified.

---

# DAY 80 — Recreate Production Cluster

Navigate to workspace.

Type manually:

```
pwd
ls
```

Navigate to Kubernetes lab.

```
cd kubernetes-lab
ls
```

Create production-style cluster.

```
kind create cluster --name prod-lab
```

Verify cluster.

```
kubectl cluster-info
kubectl get nodes
kubectl get pods -A
```

Create platform namespaces.

```
kubectl create namespace dev
kubectl create namespace staging
kubectl create namespace production
kubectl create namespace argocd
```

Verify namespaces.

```
kubectl get namespaces
```

Inspect nodes.

```
kubectl describe nodes
```

Inspect system pods.

```
kubectl get pods -n kube-system
```

---

# DAY 81 — Install ArgoCD

Install ArgoCD manifests.

```
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Verify installation.

```
kubectl get pods -n argocd
kubectl get svc -n argocd
```

Inspect deployments.

```
kubectl get deployments -n argocd
kubectl describe deployment -n argocd
```

Wait until pods ready.

```
kubectl get pods -n argocd
```

---

# DAY 82 — Access ArgoCD

Port forward ArgoCD server.

```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

Open UI.

```
https://localhost:8080
```

Retrieve admin password.

Open new terminal.

```
kubectl get secret argocd-initial-admin-secret \
-n argocd -o jsonpath="{.data.password}" | base64 --decode
```

Login.

```
username: admin
password: <decoded-password>
```

Stop port forward.

```
CTRL + C
```

---

# DAY 83 — Prepare GitOps Repository Structure

Navigate to projects directory.

```
cd ~/Projects
```

Create GitOps repository.

```
mkdir gitops-platform
cd gitops-platform
```

Initialize git repository.

```
git init
git status
```

Create GitOps structure.

```
mkdir apps
mkdir environments
mkdir manifests
mkdir charts
```

Verify structure.

```
tree
```

Create sample application manifest.

```
mkdir apps/nginx
touch apps/nginx/deployment.yaml
touch apps/nginx/service.yaml
```

---

# DAY 84 — Deploy Application via ArgoCD

Create ArgoCD application manifest.

```
mkdir argocd
touch argocd/nginx-app.yaml
```

Example application definition.

```
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: nginx-app
  namespace: argocd
spec:
  destination:
    namespace: dev
    server: https://kubernetes.default.svc
  source:
    repoURL: https://github.com/example/gitops-platform
    path: apps/nginx
    targetRevision: HEAD
  project: default
  syncPolicy:
    automated: {}
```

Apply application.

```
kubectl apply -f argocd/nginx-app.yaml
```

Verify.

```
kubectl get applications -n argocd
kubectl describe application nginx-app -n argocd
```

Inspect pods.

```
kubectl get pods -n dev
```

---

# DAY 85 — GitOps Workflow

Modify application manifest.

```
nano apps/nginx/deployment.yaml
```

Commit change.

```
git add .
git commit -m "update nginx deployment"
```

Push repository.

```
git remote add origin <repo-url>
git push -u origin main
```

Observe ArgoCD sync.

```
kubectl get applications -n argocd
```

Verify pods updated.

```
kubectl get pods -n dev
```

Inspect rollout.

```
kubectl rollout status deployment/nginx
```

---

# DAY 86 — Blue-Green Deployment

Create blue deployment.

```
kubectl create deployment nginx-blue --image=nginx -n production
```

Create green deployment.

```
kubectl create deployment nginx-green --image=nginx -n production
```

Expose service.

```
kubectl expose deployment nginx-blue --port=80 -n production
```

Verify deployments.

```
kubectl get deployments -n production
kubectl get pods -n production
```

Switch traffic.

```
kubectl patch svc nginx-blue -p '{"spec":{"selector":{"app":"nginx-green"}}}'
```

Verify.

```
kubectl get svc -n production
```

---

# DAY 87 — Canary Deployment

Create canary deployment.

```
kubectl create deployment nginx-canary --image=nginx:1.25 -n production
```

Scale canary small.

```
kubectl scale deployment nginx-canary --replicas=1 -n production
```

Inspect pods.

```
kubectl get pods -n production
```

Increase traffic gradually.

```
kubectl scale deployment nginx-canary --replicas=3 -n production
```

Inspect rollout.

```
kubectl rollout status deployment/nginx-canary -n production
```

---

# DAY 88 — Backup and Restore

Export cluster resources.

```
kubectl get all -A -o yaml > cluster-backup.yaml
```

Verify backup.

```
ls -lh
cat cluster-backup.yaml
```

Simulate cluster failure.

```
kind delete cluster --name prod-lab
```

Recreate cluster.

```
kind create cluster --name prod-lab
```

Restore resources.

```
kubectl apply -f cluster-backup.yaml
```

Verify restore.

```
kubectl get pods -A
```

---

# DAY 89 — Disaster Recovery Simulation

Simulate outage.

Delete deployment.

```
kubectl delete deployment nginx -n dev
```

Observe ArgoCD reconciliation.

```
kubectl get applications -n argocd
```

Verify redeployment.

```
kubectl get pods -n dev
```

Inspect events.

```
kubectl get events -A
```

Observe recovery.

---

# DAY 90 — Final Platform Validation

Inspect entire cluster.

```
kubectl get nodes
kubectl get namespaces
kubectl get pods -A
kubectl get deployments -A
kubectl get svc -A
```

Inspect ArgoCD.

```
kubectl get applications -n argocd
kubectl get pods -n argocd
```

Inspect observability stack.

```
kubectl get pods -n observability
```

Inspect resource usage.

```
kubectl top nodes
kubectl top pods -A
```

Generate final architecture documentation.

```
mkdir -p docs/final
touch docs/final/devops-platform.md
```

Document:

* CI pipeline
* Docker builds
* Kubernetes cluster
* GitOps
* Observability
* SRE practices
* deployment strategies
