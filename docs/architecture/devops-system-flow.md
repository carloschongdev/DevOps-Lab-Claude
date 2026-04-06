# DevOps System Flow

Developer
   ↓
Git Repository
   ↓
GitHub Actions CI Pipeline
   ↓
Docker Build
   ↓
Container Registry
   ↓
Infrastructure (Terraform)
   ↓
Kubernetes Cluster
   ↓
Platform Services

   • Metrics → Prometheus
   • Logs → Loki
   • Dashboards → Grafana
   • Alerts → Alertmanager

   ↓
Deployment System

   • Helm
   • ArgoCD