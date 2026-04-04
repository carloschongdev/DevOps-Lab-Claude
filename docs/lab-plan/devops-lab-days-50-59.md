# DevOps Lab — Days 50–59

Phase: Kubernetes Deep Operations

Goal:

Operate a **real Kubernetes cluster locally** and understand:

* cluster architecture
* pods
* deployments
* services
* networking
* debugging
* failure recovery
* scaling
* rolling updates

All commands executed from **repo root** unless specified.

---

# DAY 50 — Install Kubernetes Tooling

Navigate to repo.

```
pwd
ls
```

Install kubectl.

```
brew install kubectl
kubectl version --client
kubectl version --client --output=yaml
kubectl options
kubectl help
```

Install kind.

```
brew install kind
kind version
kind --help
```

Create kubernetes lab folder.

```
mkdir -p kubernetes-lab/day50
cd kubernetes-lab/day50
pwd
ls
```

Create config directory.

```
mkdir cluster-config
mkdir manifests
mkdir scripts
ls
```

Inspect environment.

```
which kubectl
which kind
kubectl version --client
kind version
```

---

# DAY 51 — Create First Kubernetes Cluster

Navigate to folder.

```
cd kubernetes-lab/day50
```

Create cluster.

```
kind create cluster --name devops-lab
kind get clusters
kubectl cluster-info
kubectl cluster-info dump
```

Inspect nodes.

```
kubectl get nodes
kubectl describe nodes
kubectl get componentstatuses
kubectl get namespaces
kubectl get pods -A
```

Inspect system namespace.

```
kubectl get pods -n kube-system
kubectl describe pod -n kube-system
```

Inspect kubeconfig.

```
kubectl config view
kubectl config current-context
kubectl config get-contexts
kubectl config get-clusters
```

---

# DAY 52 — Pods Fundamentals

Navigate workspace.

```
cd kubernetes-lab/day50/manifests
```

Create pod manifest.

```
touch pod-nginx.yaml
nano pod-nginx.yaml
```

Example pod.

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx-lab
spec:
  containers:
  - name: nginx
    image: nginx
    ports:
    - containerPort: 80
```

Create pod.

```
kubectl apply -f pod-nginx.yaml
kubectl get pods
kubectl describe pod nginx-lab
kubectl get pod nginx-lab -o yaml
```

Inspect logs.

```
kubectl logs nginx-lab
kubectl logs -f nginx-lab
```

Execute shell.

```
kubectl exec -it nginx-lab -- /bin/bash
kubectl exec nginx-lab -- ls
kubectl exec nginx-lab -- cat /etc/nginx/nginx.conf
```

Delete pod.

```
kubectl delete pod nginx-lab
kubectl get pods
```

---

# DAY 53 — Deployments

Create deployment manifest.

```
touch deployment-nginx.yaml
nano deployment-nginx.yaml
```

Deployment example.

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx
        ports:
        - containerPort: 80
```

Apply deployment.

```
kubectl apply -f deployment-nginx.yaml
kubectl get deployments
kubectl describe deployment nginx-deployment
kubectl get pods
kubectl get rs
kubectl describe rs
```

Scale deployment.

```
kubectl scale deployment nginx-deployment --replicas=5
kubectl get pods
kubectl get deployment
```

---

# DAY 54 — Services

Create service manifest.

```
touch service-nginx.yaml
nano service-nginx.yaml
```

Example service.

```
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  ports:
  - port: 80
    targetPort: 80
  type: ClusterIP
```

Apply service.

```
kubectl apply -f service-nginx.yaml
kubectl get svc
kubectl describe svc nginx-service
kubectl get endpoints
```

Inspect networking.

```
kubectl get pods -o wide
kubectl get svc -o wide
```

---

# DAY 55 — Port Forwarding and Access

Forward port.

```
kubectl port-forward deployment/nginx-deployment 8080:80
```

Test connectivity.

```
curl localhost:8080
curl -I localhost:8080
```

Stop forwarding.

```
CTRL+C
```

Run test pod.

```
kubectl run curlpod --image=curlimages/curl -it --rm -- sh
```

Test service internally.

```
curl nginx-service
```

Exit pod.

```
exit
```

---

# DAY 56 — ConfigMaps

Create configmap.

```
kubectl create configmap app-config --from-literal=env=dev
kubectl get configmaps
kubectl describe configmap app-config
```

Export configmap.

```
kubectl get configmap app-config -o yaml
```

Create manifest.

```
touch configmap.yaml
nano configmap.yaml
```

Apply configmap.

```
kubectl apply -f configmap.yaml
kubectl get configmaps
```

---

# DAY 57 — Secrets

Create secret.

```
kubectl create secret generic db-secret --from-literal=password=devpass
kubectl get secrets
kubectl describe secret db-secret
```

Inspect encoded secret.

```
kubectl get secret db-secret -o yaml
```

Decode secret.

```
echo BASE64VALUE | base64 --decode
```

Delete secret.

```
kubectl delete secret db-secret
kubectl get secrets
```

---

# DAY 58 — Debugging Pods

Inspect pods.

```
kubectl get pods
kubectl describe pods
```

Check logs.

```
kubectl logs deployment/nginx-deployment
kubectl logs -f deployment/nginx-deployment
```

Check events.

```
kubectl get events
kubectl get events --sort-by=.metadata.creationTimestamp
```

Simulate failure.

```
kubectl delete pod <pod-name>
kubectl get pods
```

Inspect rollout.

```
kubectl rollout status deployment/nginx-deployment
kubectl rollout history deployment/nginx-deployment
```

---

# DAY 59 — Rolling Updates

Update image.

```
kubectl set image deployment/nginx-deployment nginx=nginx:1.25
kubectl rollout status deployment/nginx-deployment
kubectl rollout history deployment/nginx-deployment
```

Rollback.

```
kubectl rollout undo deployment/nginx-deployment
kubectl rollout status deployment/nginx-deployment
```

Delete deployment.

```
kubectl delete deployment nginx-deployment
kubectl get deployments
```

Cleanup cluster.

```
kind delete cluster --name devops-lab
kind get clusters
```
