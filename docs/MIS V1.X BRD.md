# Mission Integrity System (MIS) — V1 / V1.1 BRD

## 1. Document Purpose

This Business Requirements Document defines the scope, objectives, functional requirements, boundaries, and success criteria for **Mission Integrity System (MIS) — V1** and the limited **V1.1 evidence/export hardening enhancement**.

MIS is a governance-first, deterministic classification prototype that evaluates simulated telemetry-like signals and classifies operational trustworthiness under degraded conditions.

MIS is not a UAV system, flight controller, navigation system, AI model, predictive engine, or production deployment.

---

## 2. Project Name

**Mission Integrity System (MIS) — V1**

### V1.1 Enhancement

**MIS V1.1 — Evidence & Export Hardening**

V1.1 does not change the classification model. It adds exportable demonstration reporting and accessibility-aware chart presentation to make V1 outputs easier to review, share, and discuss.

---

## 3. Problem Statement

Current operational systems often expose raw telemetry or system signals without clearly communicating whether those signals remain trustworthy under degraded conditions.

This creates several risks:

- operators may over-trust outputs produced from degraded signals
- degradation may be hidden, smoothed over, or surfaced too late
- raw telemetry may create noise without improving interpretation
- system outputs may continue to appear valid even when underlying signal integrity is declining

MIS addresses this gap by classifying operational trustworthiness directly.

The core problem is not whether a system is still producing output. The core problem is whether that output should still be trusted.

---

## 4. Objective

MIS V1 will build a deterministic classification engine that:

- ingests simulated telemetry-like mission signals
- calculates domain-specific integrity scores
- classifies operational trustworthiness into bounded states
- produces concise causal explanations
- emits meaningful events only when state or threshold changes occur
- presents the output through a minimal CLI and Streamlit interface

MIS V1.1 will add:

- scenario-specific downloadable PDF reports
- integrity score charts
- raw signal charts
- event log export
- data excerpt export
- demonstration-only limitation language
- copyright / ownership footer
- accessibility-aware chart design

V1.1 is an output/reporting enhancement only. It does not expand the analytical model.

---

## 5. Target Use Case

MIS V1 is intended as a simulation-based portfolio prototype demonstrating how deterministic classification can make signal degradation visible before downstream decision-making occurs.

The system answers the question:

> Given current degraded signal conditions, how trustworthy is the mission state being observed?

The prototype is designed for demonstration, discussion, and portfolio review purposes.

---

## 6. Users / Audience

The intended audience includes:

- technical reviewers
- hiring managers
- finance transformation leaders
- governance and control stakeholders
- data integrity / reporting readiness stakeholders
- operational risk stakeholders
- systems thinkers evaluating bounded classification logic

The system is not intended for operational UAV users, flight operators, safety engineers, or real-world mission execution.

---

## 7. Scope

### 7.1 V1 Scope

MIS V1 includes:

- synthetic scenario data generation
- deterministic signal scoring
- bounded integrity scores
- bounded state classification
- causal explanation generation
- event-based transition logging
- CLI execution
- Streamlit interface
- minimal visual output
- GitHub-ready documentation

### 7.2 V1.1 Scope

MIS V1.1 includes:

- downloadable PDF report for the selected scenario
- report header and scenario metadata
- latest state and integrity summary
- integrity score chart
- raw signal chart
- event log
- data excerpt
- limitations / non-goals statement
- copyright / ownership footer
- accessibility-aware chart formatting

### 7.3 Out of Scope

MIS does not include:

- real UAV integration
- hardware integration
- flight control logic
- autopilot functionality
- route planning
- navigation optimization
- object tracking
- targeting
- swarm coordination
- real-time mission execution
- machine learning
- predictive analytics
- probabilistic modeling
- autonomous decision-making
- prescriptive operational recommendations
- production deployment
- safety certification
- regulatory certification

MIS performs deterministic classification only.

---

## 8. Design Principles

MIS will follow these principles:

- deterministic over probabilistic
- bounded finite states over open-ended interpretation
- explicit degradation over hidden assumptions
- operator interpretability over complexity
- event-driven output over continuous alerting
- quiet-by-default presentation
- no prediction
- no forecasting
- no optimization
- no autonomous action
- no control logic
- clear separation between signal classification and human decision-making

These principles were core to the original MIS V1 concept and remain unchanged in V1.1.  [oai_citation:0‡MIS_V1 BRD.docx](sediment://file_000000007e8c722fba3621e1ac77c857)

---

## 9. Input Requirements

MIS V1 will generate simulated time-series mission data.

Each scenario should include at least 60 time steps.

### Required Signal Fields

| Field | Description | Interpretation |
|---|---|---|
| timestamp | Time step identifier | Sequential mission time |
| gps_quality | Simulated GPS signal quality | Higher is better |
| imu_stability | Simulated inertial stability proxy | Higher is better |
| wind_load | Simulated wind / turbulence load | Higher is worse |
| sensor_clarity | Simulated sensor clarity | Higher is better |
| comms_latency | Simulated communication latency | Higher is worse |
| packet_loss | Simulated packet loss | Higher is worse |
| battery_stability | Simulated battery stability | Higher is better |

Signals should use a normalized 0–100 scale where practical, with latency handled consistently and documented clearly.

---

## 10. Scenario Requirements

MIS V1 must support five simulated scenarios.

### 10.1 nominal_mission

Mostly stable signal conditions throughout the scenario.

Purpose:

- demonstrate normal system behavior
- show quiet-by-default output under stable conditions
- establish baseline interpretation

### 10.2 gradual_gps_degradation

GPS quality declines gradually over time.

Purpose:

- demonstrate early degradation detection
- show navigation integrity deterioration
- support Drift Emerging or Degraded transitions where thresholds require

### 10.3 sensor_disruption

Sensor clarity drops suddenly, potentially with related instability.

Purpose:

- demonstrate sudden localized degradation
- show sensor integrity deterioration
- produce causal explanation tied to sensor clarity and related conditions

### 10.4 comms_instability

Packet loss and latency worsen intermittently.

Purpose:

- demonstrate intermittent communication degradation
- show communication integrity response
- avoid excessive event noise

### 10.5 compound_degradation

Multiple domains degrade together.

Purpose:

- demonstrate multi-domain degradation
- support transition toward Degraded or Unreliable
- show how compound signal weakness affects trust classification

---

## 11. Processing Requirements

MIS V1 must process each scenario through a deterministic pipeline.

The processing flow should include:

1. generate synthetic scenario data
2. calculate integrity scores
3. classify bounded system state
4. generate causal explanation
5. detect meaningful events
6. return enriched scenario output
7. display output through CLI and Streamlit
8. generate PDF report in V1.1

---

## 12. Integrity Score Requirements

MIS V1 must calculate three bounded integrity scores from 0 to 100.

### 12.1 Navigation Integrity

Derived primarily from:

- gps_quality
- imu_stability
- wind_load

### 12.2 Sensor Integrity

Derived primarily from:

- sensor_clarity
- wind_load
- imu_stability

### 12.3 Communication Integrity

Derived primarily from:

- comms_latency
- packet_loss

### 12.4 Scoring Requirements

Scores must be:

- deterministic
- bounded between 0 and 100
- explainable from raw signal inputs
- calculated without machine learning
- calculated without prediction
- transparent enough to inspect in code

Weighted penalty logic is acceptable if rules are clear and centralized.

---

## 13. State Classification Requirements

MIS V1 must classify each time step into one and only one bounded state.

### Required States

| State | Meaning |
|---|---|
| Stable | All major integrity domains remain within acceptable bounds |
| Drift Emerging | Early degradation or sustained mild deterioration is detected |
| Degraded | Sustained or multi-domain degradation is present |
| Unreliable | System output should no longer be treated as trustworthy |

### Classification Rules

The classification model must be deterministic and threshold-based.

Recommended starting logic:

#### Stable

Classify as Stable when:

- all major integrity scores are within acceptable range
- no major raw signal breach exists
- no sustained degradation pattern exists

#### Drift Emerging

Classify as Drift Emerging when:

- one integrity score enters an early warning band
- one early warning pattern exists
- mild but sustained deterioration appears in one critical signal

#### Degraded

Classify as Degraded when:

- one integrity score enters a degraded band
- two or more domains show meaningful degradation
- repeated threshold breaches occur within a recent window

#### Unreliable

Classify as Unreliable when:

- any integrity score falls below minimum trust threshold
- compound multi-domain degradation occurs
- critical signal combinations indicate output should not be trusted

The state model should allow transition logic to be explainable and reversible only under defined conditions.

---

## 14. Causal Explanation Requirements

Each classified time step must include a concise causal explanation.

The explanation must:

- state why the current state was assigned
- reference actual threshold or signal behavior
- avoid generic or black-box language
- avoid prescriptive recommendations
- avoid operational commands

Example explanations:

```text
Stable: all integrity domains remain within acceptable bounds.
