# Scenario Summary — MIS V1.3

**Run ID:** `run_001`
**Release Label:** MIS V1.3 — Evidence Package Readiness & Validation
**Scenario ID:** `compound_degradation`
**Scenario Purpose:** Multiple signals worsen together. Full progression to Unreliable demonstrated.
**Generated:** 2026-05-04T14:19:27Z
**Steps:** 60
**Random Seed:** 42

---

## Final State Summary

| Field | Value |
|---|---|
| Final State | Unreliable |
| Navigation Integrity | 31.8 / 100 |
| Sensor Integrity | 33.2 / 100 |
| Communication Integrity | 24.9 / 100 |
| Causal Explanation | Unreliable: Navigation and Sensor and Communication integrity below minimum trust threshold (< 40). |

---

## Integrity Summary

| Domain | Min | Max | Mean |
|---|---|---|---|
| Navigation | 30.4 | 86.8 | 57.0 |
| Sensor | 24.7 | 84.1 | 54.8 |
| Communication | 24.9 | 92.2 | 61.2 |

### State Distribution

- Degraded: 7 steps
- Drift Emerging: 14 steps
- Stable: 9 steps
- Unreliable: 30 steps

---

## Event Summary

Total events: 31

- INFO: 2
- WARNING: 19
- CRITICAL: 10

---

## Limitations

Mission Integrity System (MIS) V1.2 uses simulated telemetry-like data for demonstration and portfolio purposes only. It is not a UAV control system, flight application, autopilot, navigation engine, targeting system, safety-certified tool, predictive model, or production deployment. MIS V1.2 performs deterministic classification only and does not recommend or automate operational decisions.

---

*Demonstration report generated from simulated data*
*© 2026 Tripp Parker / Fueled Analytics. All rights reserved. Generated for demonstration purposes only.*
