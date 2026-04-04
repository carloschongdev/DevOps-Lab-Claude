# DevOps Lab — Days 70–79

Phase: SRE / Observability / Reliability Engineering

Goal:

Transform the Kubernetes cluster into a **production-grade observable platform**.

You will deploy:

* Prometheus monitoring
* Grafana dashboards
* Alertmanager
* Loki logging
* SLO / SLI metrics
* Chaos engineering tests
* incident simulation
* failure debugging

All commands executed from **repository root** unless specified.

---

# DAY 70 — Recreate Kubernetes Cluster for Observability Stack

Navigate to project root.

```
pwd
ls
```

Navigate to Kubernetes lab directory.

```
cd kubernetes-lab
ls
```

Create fresh cluster.

```
kind create cluster --name sre-lab
```

Verify cluster.

```
kubectl cluster-info
kubectl get nodes
kubectl get pods -A
```

Create observability namespace.

```
kubectl create namespace observability
```

Verify namespaces.

```
kubectl get namespaces
kubectl describe namespace observability
```

Inspect cluster components.

```
kubectl get componentstatuses
kubectl get events
kubectl get events --sort-by=.metadata.creationTimestamp
```

---

# DAY 71 — Install Prometheus (Helm)

Navigate to helm workspace.

```
cd ~/Projects
mkdir sre-stack
cd sre-stack
```

Verify helm.

```
helm version
helm repo list
```

Add prometheus community repo.

```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
```

Search charts.

```
helm search repo prometheus
helm search repo kube-prometheus-stack
```

Install kube-prometheus-stack.

```
helm install prometheus prometheus-community/kube-prometheus-stack \
--namespace observability
```

Verify installation.

```
kubectl get pods -n observability
kubectl get svc -n observability
kubectl get deployments -n observability
```

Inspect prometheus pods.

```
kubectl describe pod -n observability
kubectl logs -n observability
```

---

# DAY 72 — Prometheus Metrics Exploration

List services.

```
kubectl get svc -n observability
```

Find prometheus service.

```
kubectl get svc -n observability | grep prometheus
```

Port forward prometheus UI.

```
kubectl port-forward svc/prometheus-kube-prometheus-prometheus \
9090:9090 -n observability
```

Open browser.

```
http://localhost:9090
```

Explore metrics queries.

```
up
node_cpu_seconds_total
kube_pod_container_status_running
kube_node_status_condition
```

Stop port forward.

```
CTRL + C
```

Inspect prometheus config.

```
kubectl get configmaps -n observability
kubectl describe configmap -n observability
```

---

# DAY 73 — Grafana Dashboards

Find Grafana service.

```
kubectl get svc -n observability | grep grafana
```

Retrieve admin password.

```
kubectl get secret -n observability \
prometheus-grafana -o jsonpath="{.data.admin-password}" | base64 --decode
```

Port forward Grafana.

```
kubectl port-forward svc/prometheus-grafana 3000:80 -n observability
```

Open UI.

```
http://localhost:3000
```

Login.

```
admin / <password>
```

Explore dashboards.

Navigate:

```
Dashboards → Manage
```

Inspect Kubernetes dashboards.

Observe:

```
CPU usage
Memory usage
Pod health
Cluster health
```

Stop port forward.

```
CTRL + C
```

---

# DAY 74 — Alertmanager

List alertmanager resources.

```
kubectl get pods -n observability | grep alertmanager
kubectl get svc -n observability
```

Port forward alertmanager.

```
kubectl port-forward svc/prometheus-kube-prometheus-alertmanager \
9093:9093 -n observability
```

Open UI.

```
http://localhost:9093
```

Inspect alerts.

```
kubectl get prometheusrules -n observability
kubectl describe prometheusrules -n observability
```

List firing alerts.

```
kubectl get events -n observability
```

Stop port forward.

```
CTRL + C
```

---

# DAY 75 — Loki Logging Stack

Add Grafana repo.

```
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
```

Install Loki stack.

```
helm install loki grafana/loki-stack \
--namespace observability
```

Verify pods.

```
kubectl get pods -n observability
kubectl describe pods -n observability
```

Inspect services.

```
kubectl get svc -n observability
```

---

# DAY 76 — Log Aggregation

Port forward Grafana again.

```
kubectl port-forward svc/prometheus-grafana 3000:80 -n observability
```

Open Grafana.

```
http://localhost:3000
```

Navigate to Explore.

Select datasource:

```
Loki
```

Run queries.

```
{namespace="observability"}
```

Filter logs.

```
{app="nginx"}
```

Stop port forward.

```
CTRL + C
```

---

# DAY 77 — Define SLI / SLO Metrics

Create SLO documentation.

```
mkdir -p docs/sre
touch docs/sre/slo.md
```

Define example SLOs.

Example:

```
API availability: 99.9%
Latency p95 < 300ms
Error rate < 1%
```

Inspect metrics.

```
kubectl get pods -A
kubectl top nodes
kubectl top pods
```

Query prometheus.

```
up
rate(container_cpu_usage_seconds_total[5m])
```

---

# DAY 78 — Chaos Engineering Simulation

Deploy test application.

```
kubectl create deployment chaos-nginx --image=nginx
kubectl expose deployment chaos-nginx --port=80
```

Verify.

```
kubectl get pods
kubectl get svc
```

Simulate failure.

```
kubectl delete pod <pod-name>
```

Observe recovery.

```
kubectl get pods
kubectl describe deployment chaos-nginx
```

Observe metrics in Prometheus.

Check CPU spikes.

---

# DAY 79 — Incident Simulation

Simulate incident.

Scale deployment incorrectly.

```
kubectl scale deployment chaos-nginx --replicas=50
```

Inspect cluster stress.

```
kubectl get pods
kubectl top nodes
kubectl top pods
```

Check alerts.

```
kubectl get events
kubectl get events --sort-by=.metadata.creationTimestamp
```

Rollback incident.

```
kubectl scale deployment chaos-nginx --replicas=2
```

Cleanup.

```
kubectl delete deployment chaos-nginx
kubectl delete svc chaos-nginx
```

Inspect cluster health.

```
kubectl get pods -A
kubectl get nodes
```
