# Container Standards

All container images in the DevOps Lab must follow these guidelines.

---

## Dockerfile Structure

Dockerfiles should follow this pattern:

1. Base image
2. Dependency installation
3. Application copy
4. Runtime command

---

## Best Practices

- Use small base images
- Avoid unnecessary layers
- Pin dependency versions
- Use health checks when possible

---

## Validation

Containers must be validated using:

docker build  
docker run  
docker logs