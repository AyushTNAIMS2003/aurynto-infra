# Aurynto Observability Design

This document defines basic observability expectations.

---

## 1. Logging

- All services must log to stdout
- JSON formatted logs preferred
- Include:
  - service name
  - environment
  - request id (if available)

---

## 2. Metrics (Future)

- Services should expose /metrics endpoint
- Metrics to include:
  - request count
  - error count
  - latency

---

## 3. Tracing (Future)

- Distributed tracing will be added later
- Trace ID propagation required across services
