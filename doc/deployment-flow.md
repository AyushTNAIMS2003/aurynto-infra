# Aurynto – Deployment Flow

This document defines how code changes move from GitHub
to Kubernetes environments.

---

## 1. Source Control

- Each service has its own GitHub repository
- Main branch is protected
- All changes go via Pull Requests

---

## 2. CI Trigger

CI pipeline runs on:
- Pull Request to main
- Push to main

CI Responsibilities:
- Code checkout
- Docker image build
- Basic validation (future: tests, lint)

---

## 3. Container Build

- Docker image is built inside GitHub Actions
- Image is tagged using Git commit SHA
- No local Docker dependency

---

## 4. Image Registry (Future)

- Images will be pushed to Azure Container Registry
- Registry credentials managed via GitHub Secrets
- This step is blocked until Azure access is granted

---

## 5. Deployment (Helm)

- Each service has its own Helm chart
- Helm charts are stored in aurynto-infra
- Environment values are separated:
  - values-dev.yaml
  - values-staging.yaml

Deployment command (conceptual):
helm upgrade --install <service> ./chart -n <namespace>

---

## 6. Environments

- dev → active development
- staging → pre-production validation
- prod → future

Each environment is fully isolated.
