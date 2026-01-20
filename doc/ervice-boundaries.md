# Aurynto – Service Boundaries

This document defines clear responsibilities for each service
to avoid overlap and confusion.

---

## 1. API Service (aurynto-api)

Responsibilities:
- Asset management (vehicles, cranes, equipment)
- User and role management
- Scheduling and assignment logic
- Exposing REST APIs to frontend

Must NOT:
- Ingest raw telemetry data
- Contain frontend/UI code
- Contain infrastructure code

---

## 2. Telemetry Service (aurynto-telemetry)

Responsibilities:
- Accept telemetry data from devices
- Validate telemetry schemas
- Store or forward telemetry data

Must NOT:
- Contain business logic
- Make scheduling decisions
- Serve frontend APIs

---

## 3. Frontend (aurynto-frontend)

Responsibilities:
- User interface (dashboard)
- Calling backend APIs
- Data visualization

Must NOT:
- Contain backend logic
- Directly access databases
- Process telemetry data

---

## 4. Infrastructure (aurynto-infra)

Responsibilities:
- Kubernetes configuration
- Helm charts
- Environment setup (dev, staging)

Must NOT:
- Contain application business logic
- Contain frontend or backend code
