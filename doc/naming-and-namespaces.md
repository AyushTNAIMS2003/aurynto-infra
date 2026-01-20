# Aurynto – Naming Conventions & Namespaces

This document defines standard naming rules for services,
images, and Kubernetes namespaces.

---

## 1. Kubernetes Namespaces

Namespaces will be environment-based.

- aurynto-dev
- aurynto-staging
- aurynto-prod (future)

Rule:
- One namespace per environment
- No shared namespace across environments

---

## 2. Service Naming

Service names must match repository names.

Examples:
- aurynto-api
- aurynto-telemetry
- aurynto-frontend

Rule:
- No short names
- No environment suffix in service name

---

## 3. Docker Image Naming

Image format:

<registry>/<service-name>:<tag>

Example:
auryntoacr/aurynto-api:gitsha

Rule:
- Tags must not use "latest" in staging/production
- Git SHA preferred

---

## 4. Helm Release Naming

Release format:

<service-name>-<environment>

Example:
aurynto-api-dev
aurynto-telemetry-staging
