# Aurynto API Versioning Rules

This document defines how API versions are managed.

---

## 1. Versioning Strategy

- All APIs must be versioned
- Version is part of the URL path

Example:
 /api/v1/assets
 /api/v1/telemetry

---

## 2. Breaking Changes

- Breaking changes require a new version (v2, v3)
- Older versions remain supported until explicitly deprecated

---

## 3. CI Enforcement (Future)

- CI will validate OpenAPI specs
- API paths without version prefix will fail CI

---

## 4. Consumer Responsibility

- Frontend must explicitly call versioned APIs
- No default or unversioned endpoints allowed
