# Container Design

This document explains how the Docker container used in the DevOps Lab
is structured and why certain decisions were made.

---

# Base Image

The container uses a minimal base image to reduce attack surface
and improve build speed.

Minimal images reduce:

• image size
• vulnerability exposure
• startup time

---

# Application Layer

The container runs a simple HTTP service used for health checks.

This service allows the CI pipeline to verify that the container
starts correctly.

---

# OCI Image Metadata

OCI metadata is used to enrich the container image.

Typical metadata includes:

org.opencontainers.image.title
org.opencontainers.image.description
org.opencontainers.image.version
org.opencontainers.image.source

This metadata improves traceability of container images.

---

# Health Check

A container health endpoint is used by the CI pipeline.

The CI pipeline uses curl to verify that the service responds
correctly.

---

# Future Improvements

Later phases will include:

multi-stage builds

container security hardening

non-root container users

image vulnerability scanning
