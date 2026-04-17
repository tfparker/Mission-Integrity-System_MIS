Mission Integrity System (MIS) — V1.1

**Deterministic classification of operational trustworthiness under degraded conditions**

Mission Integrity System (MIS) — V1 is a governance-first, deterministic classification prototype that evaluates simulated telemetry-like signals and classifies operational trustworthiness into bounded states.

MIS V1 does not control a UAV, perform navigation, optimize behavior, predict outcomes, or automate operational decisions.

Instead, it answers a narrower question:

> Given current degraded signal conditions, how much should an operator trust what the system is observing?

---

## Current Status

MIS V1 is complete as a constrained portfolio prototype.

Current capabilities include:

- synthetic scenario generation
- deterministic integrity scoring
- bounded state classification
- causal explanation strings
- event-based transition logging
- Streamlit interface
- CLI execution
- downloadable scenario-specific PDF reports

No V2 work is currently active. The project is intentionally held at V1 to preserve scope clarity.

---

## What MIS V1 Does

MIS V1 ingests simulated mission signal data and produces:

- one bounded operational state per time step
- domain-specific integrity scores
- concise causal explanations
- event logs for meaningful transitions
- downloadable PDF reports for scenario review

The system separates two concerns that are often conflated:

1. what the system observes
2. how trustworthy those observations are

MIS V1 focuses exclusively on the second.

---

## Bounded State Model

Each time step is classified into one of four states:

| State | Meaning |
|---|---|
| Stable | All signals remain within acceptable bounds |
| Drift Emerging | Early degradation is detected |
| Degraded | Sustained or multi-domain degradation is present |
| Unreliable | Output should no longer be treated as trustworthy |

All classifications are:

- deterministic
- explainable
- based on explicit threshold logic
- limited to finite bounded states

No statistical model, machine learning layer, or predictive engine is used.

---

## Integrity Scores

MIS V1 computes three bounded integrity scores from 0 to 100:

| Integrity Domain | Primary Signal Inputs |
|---|---|
| Navigation Integrity | GPS quality, IMU stability, wind load |
| Sensor Integrity | Sensor clarity, wind load, IMU stability |
| Communication Integrity | Comms latency, packet loss |

Scores are generated through transparent, rule-based logic.

The purpose is not to claim real-world sensor accuracy. The purpose is to demonstrate how signal degradation can be represented clearly before downstream decisions are made.

---

## Included Scenarios

MIS V1 includes five simulated scenarios:

1. **nominal_mission**  
   Mostly stable signals throughout the scenario.

2. **gradual_gps_degradation**  
   GPS quality degrades gradually over time.

3. **sensor_disruption**  
   Sensor clarity drops suddenly with related instability.

4. **comms_instability**  
   Packet loss and latency worsen intermittently.

5. **compound_degradation**  
   Multiple signal domains degrade together, potentially causing transition toward Unreliable.

All scenarios use simulated data only.

---

## PDF Scenario Reports

MIS V1 includes downloadable scenario-specific PDF reports.

Each report includes:

- scenario name
- generated timestamp
- latest state
- Navigation Integrity score
- Sensor Integrity score
- Communication Integrity score
- latest causal explanation
- integrity score chart
- raw signal chart
- event log
- data excerpt
- limitations and non-goals
- copyright / ownership footer

The report is designed for demonstration, portfolio review, and discussion purposes.

It does not certify operational readiness, safety performance, regulatory compliance, or real-world mission suitability.

---

## Accessibility Considerations

Charts are designed to avoid relying on color alone.

The reporting layer uses accessibility-aware presentation principles, including:

- distinct line styles where practical
- markers where practical
- clear legends
- axis labels
- chart titles
- readable font sizing
- numeric values in summaries and tables

This supports the broader design principle that interpretability should not depend on visual assumptions alone.

---

## Example Output

```text
STATE: Degraded
NAVIGATION INTEGRITY: 68
SENSOR INTEGRITY: 42
COMMUNICATION INTEGRITY: 81

CAUSE: Sensor clarity drop combined with wind-induced instability.
