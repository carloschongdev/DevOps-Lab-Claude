# DevOps Lab — Days 30–39

Phase: Docker Deep Dive

This phase focuses on deep operational knowledge of Docker.

Goals:

* Understand container internals
* Master image builds
* Inspect container runtime
* Debug container failures
* Analyze container networking
* Manage persistent volumes
* Implement container security scanning
* Measure container performance

All commands must be executed from **repository root** unless explicitly stated.

---

# DAY 30 — Docker Environment Inspection

Type manually:

```
docker version
docker info
docker system info
docker system df
docker system events
docker context ls
docker context inspect default
docker builder ls
docker images
docker ps
docker ps -a
docker network ls
docker volume ls
docker inspect $(docker ps -aq)
docker system df -v
docker system prune --dry-run
```

Save environment reports.

```
mkdir -p reports/day30
docker info > reports/day30/docker-info.txt
docker version > reports/day30/docker-version.txt
docker images > reports/day30/docker-images.txt
docker ps -a > reports/day30/docker-containers.txt
docker network ls > reports/day30/docker-networks.txt
docker volume ls > reports/day30/docker-volumes.txt
```

---

# DAY 31 — Docker Image Fundamentals

Type manually:

```
docker pull alpine
docker pull nginx
docker pull busybox
docker images
docker inspect alpine
docker inspect nginx
docker history nginx
docker history alpine
docker image inspect nginx
docker image inspect alpine
docker save nginx -o nginx.tar
docker load -i nginx.tar
```

Save inspection reports.

```
docker history nginx > reports/day31-nginx-history.txt
docker inspect nginx > reports/day31-nginx-inspect.json
```

---

# DAY 32 — Docker Container Lifecycle

Type manually:

```
docker run alpine echo "hello"
docker run -it alpine sh
docker run -d nginx
docker ps
docker logs $(docker ps -q)
docker stop $(docker ps -q)
docker start $(docker ps -aq)
docker restart $(docker ps -aq)
docker rm $(docker ps -aq)
docker run -d --name web1 nginx
docker run -d --name web2 nginx
docker ps
docker logs web1
docker logs web2
```

Save lifecycle logs.

```
docker ps -a > reports/day32-containers.txt
docker logs web1 > reports/day32-web1.log
```

---

# DAY 33 — Docker Build Process

Type manually:

```
mkdir docker-test
cd docker-test
echo "FROM alpine" > Dockerfile
echo "RUN echo hello world" >> Dockerfile
docker build -t test-image .
docker images
docker inspect test-image
docker history test-image
docker run test-image
```

Save build data.

```
docker history test-image > ../reports/day33-build-history.txt
docker inspect test-image > ../reports/day33-build-inspect.json
```

---

# DAY 34 — Multi Stage Builds

Type manually:

```
mkdir docker-multistage
cd docker-multistage
nano Dockerfile
```

Add multistage example.

Build image.

```
docker build -t multi-stage-test .
docker images
docker history multi-stage-test
docker inspect multi-stage-test
```

Save reports.

```
docker history multi-stage-test > ../reports/day34-multistage-history.txt
```

---

# DAY 35 — Docker Networking

Type manually:

```
docker network create lab-network
docker network ls
docker network inspect lab-network
docker run -d --network lab-network --name app1 nginx
docker run -d --network lab-network --name app2 nginx
docker ps
docker inspect app1
docker inspect app2
docker exec -it app1 ping app2
docker network disconnect lab-network app2
docker network connect lab-network app2
```

Save network reports.

```
docker network inspect lab-network > reports/day35-network.json
```

---

# DAY 36 — Docker Volumes

Type manually:

```
docker volume create lab-volume
docker volume ls
docker volume inspect lab-volume
docker run -d -v lab-volume:/data nginx
docker inspect $(docker ps -q)
docker volume prune --dry-run
```

Save volume report.

```
docker volume inspect lab-volume > reports/day36-volume.json
```

---

# DAY 37 — Container Debugging

Type manually:

```
docker run -d nginx
docker ps
docker exec -it $(docker ps -q) sh
docker logs $(docker ps -q)
docker inspect $(docker ps -q)
docker top $(docker ps -q)
docker stats
docker diff $(docker ps -q)
docker events
```

Save debugging reports.

```
docker logs $(docker ps -q) > reports/day37-logs.txt
```

---

# DAY 38 — Container Security

Install Trivy.

Type manually:

```
brew install trivy
trivy --version
```

Scan images.

```
trivy image nginx
trivy image alpine
trivy fs .
```

Save scan reports.

```
trivy image nginx > reports/day38-nginx-scan.txt
trivy fs . > reports/day38-fs-scan.txt
```

---

# DAY 39 — Container Performance

Type manually:

```
docker run -d nginx
docker stats
docker inspect $(docker ps -q)
docker top $(docker ps -q)
docker events
docker system df
docker system prune --dry-run
```

Save performance reports.

```
docker stats --no-stream > reports/day39-performance.txt
docker system df > reports/day39-storage.txt
```

---

# Final Documentation

Type manually:

```
mkdir -p docs
touch docs/docker-deep-dive.md
```

Document:

* container lifecycle
* networking
* volumes
* debugging
* security scanning
* performance analysis
