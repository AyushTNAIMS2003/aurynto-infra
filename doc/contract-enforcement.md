# Aurynto – Contract Enforcement Rules

This document defines non-negotiable rules for API and telemetry contracts.

---

## 1. API Contracts (aurynto-api)

- All APIs must be versioned (example: /api/v1)
- Any breaking change requires a new version (v2, v3, etc.)
- API changes are not allowed without updating OpenAPI contract
- Frontend must only consume documented APIs

Failure Result:
- CI pipeline must fail
- Pull Request must not be merged

---

## 2. Telemetry Contracts (aurynto-telemetry)

- All telemetry events must follow defined JSON schema
- Schema changes must be backward compatible
- Breaking changes require new schema version

Failure Result:
- Telemetry data must be rejected
- CI pipeline must fail

---

## 3. Frontend Rules (aurynto-frontend)

- Frontend must use versioned APIs only
- No hardcoded or undocumented endpoints

Failure Result:
- Build must fail
- PR must not be merged

---

## 4. Ownership & Approval

- API contract changes require approval from AM and TN
- Telemetry schema changes require approval from AM and UA
- Frontend build changes require approval from QA
