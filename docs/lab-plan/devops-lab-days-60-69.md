# DevOps Lab — Days 60–69

Phase: Kubernetes Platform Engineering

Goal:

Build a **production-style Kubernetes platform layer**.

You will learn:

* namespaces
* RBAC
* Helm package manager
* ingress controllers
* autoscaling
* metrics server
* resource quotas
* cluster governance
* multi-environment workloads

All commands executed from **repo root** unless specified.

---

# DAY 60 — Namespaces and Multi-Environment Layout

Navigate to lab.

Type manually:

```
cd kubernetes-lab
pwd
ls
```

List namespaces.

```
kubectl get namespaces
kubectl describe namespaces
```

Create namespaces.

```
kubectl create namespace dev
kubectl create namespace staging
kubectl create namespace prod
```

Verify.

```
kubectl get namespaces
```

Create test pods in namespaces.

```
kubectl run nginx-dev --image=nginx -n dev
kubectl run nginx-staging --image=nginx -n staging
kubectl run nginx-prod --image=nginx -n prod
```

Inspect pods.

```
kubectl get pods -n dev
kubectl get pods -n staging
kubectl get pods -n prod
```

Describe pods.

```
kubectl describe pod nginx-dev -n dev
kubectl describe pod nginx-staging -n staging
kubectl describe pod nginx-prod -n prod
```

Delete pods.

```
kubectl delete pod nginx-dev -n dev
kubectl delete pod nginx-staging -n staging
kubectl delete pod nginx-prod -n prod
```

---

# DAY 61 — Resource Quotas

Create quota manifest.

```
mkdir -p manifests/platform
cd manifests/platform
touch resource-quota.yaml
nano resource-quota.yaml
```

Example quota.

```
apiVersion: v1
kind: ResourceQuota
metadata:
 name: dev-quota
 namespace: dev
spec:
 hard:
   pods: "10"
   requests.cpu: "2"
   requests.memory: 2Gi
   limits.cpu: "4"
   limits.memory: 4Gi
```

Apply quota.

```
kubectl apply -f resource-quota.yaml
kubectl get resourcequota -n dev
kubectl describe resourcequota dev-quota -n dev
```

Test quota enforcement.

```
kubectl run quota-test --image=nginx -n dev
kubectl get pods -n dev
```

Delete pod.

```
kubectl delete pod quota-test -n dev
```

---

# DAY 62 — RBAC Basics

Create service account.

```
kubectl create serviceaccount dev-user -n dev
kubectl get serviceaccounts -n dev
```

Create role manifest.

```
touch role-dev.yaml
nano role-dev.yaml
```

Example role.

```
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
 name: pod-reader
 namespace: dev
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get","watch","list"]
```

Apply role.

```
kubectl apply -f role-dev.yaml
kubectl get roles -n dev
```

Create role binding.

```
touch rolebinding-dev.yaml
nano rolebinding-dev.yaml
```

Apply rolebinding.

```
kubectl apply -f rolebinding-dev.yaml
kubectl get rolebindings -n dev
```

---

# DAY 63 — Helm Installation

Install Helm.

```
brew install helm
helm version
helm help
```

Add Helm repositories.

```
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
helm repo list
```

Search charts.

```
helm search repo nginx
helm search repo redis
helm search repo prometheus
```

Create workspace.

```
mkdir -p helm-lab
cd helm-lab
```

---

# DAY 64 — Helm Deployments

Install nginx chart.

```
helm install nginx-lab bitnami/nginx
```

Inspect release.

```
helm list
helm status nginx-lab
helm get values nginx-lab
```

Inspect resources.

```
kubectl get pods
kubectl get svc
kubectl get deployments
```

Upgrade chart.

```
helm upgrade nginx-lab bitnami/nginx
helm history nginx-lab
```

Rollback.

```
helm rollback nginx-lab 1
```

Uninstall release.

```
helm uninstall nginx-lab
```

---

# DAY 65 — Metrics Server

Install metrics server.

```
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
```

Verify deployment.

```
kubectl get deployment metrics-server -n kube-system
kubectl get pods -n kube-system
```

Check metrics.

```
kubectl top nodes
kubectl top pods
```

Inspect resource usage.

```
kubectl top pods -A
kubectl top nodes
```

---

# DAY 66 — Horizontal Pod Autoscaling

Create deployment.

```
kubectl create deployment autoscale-nginx --image=nginx
```

Expose deployment.

```
kubectl expose deployment autoscale-nginx --port=80
```

Create autoscaler.

```
kubectl autoscale deployment autoscale-nginx --cpu-percent=50 --min=1 --max=5
```

Inspect HPA.

```
kubectl get hpa
kubectl describe hpa autoscale-nginx
```

Inspect scaling.

```
kubectl get deployments
kubectl get pods
```

Delete deployment.

```
kubectl delete deployment autoscale-nginx
kubectl delete svc autoscale-nginx
```

---

# DAY 67 — Ingress Controller

Install ingress controller.

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```

Inspect resources.

```
kubectl get pods -n ingress-nginx
kubectl get svc -n ingress-nginx
```

Create ingress manifest.

```
touch ingress.yaml
nano ingress.yaml
```

Apply ingress.

```
kubectl apply -f ingress.yaml
kubectl get ingress
kubectl describe ingress
```

---

# DAY 68 — Cluster Debugging

Inspect cluster components.

```
kubectl get componentstatuses
kubectl get nodes
kubectl describe node
```

Inspect kube-system.

```
kubectl get pods -n kube-system
kubectl logs -n kube-system
```

Inspect events.

```
kubectl get events
kubectl get events --sort-by=.metadata.creationTimestamp
```

Simulate failure.

```
kubectl delete pod -n kube-system <pod>
```

Observe recovery.

```
kubectl get pods -n kube-system
```

---

# DAY 69 — Platform Cleanup and Documentation

Cleanup workloads.

```
kubectl delete namespace dev
kubectl delete namespace staging
kubectl delete namespace prod
```

Verify cleanup.

```
kubectl get namespaces
kubectl get pods -A
```

Delete cluster.

```
kind delete cluster
```

Document platform architecture.

```
mkdir -p docs/platform
touch docs/platform/kubernetes-platform.md
```

Document:

* namespaces
* RBAC
* Helm
* ingress
* autoscaling
* quotas
* observability
* debugging
