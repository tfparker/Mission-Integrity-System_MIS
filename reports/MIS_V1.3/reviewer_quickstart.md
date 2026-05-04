# Reviewer Quickstart — MIS V1.3

**Scenario:** `compound_degradation`
**Generated:** 2026-05-04T14:19:27Z

---

## Review Checklist

1. **Inspect the canonical output** → `run_001/canonical_output.json`
   - Machine-readable complete run output: all enriched rows, all events
   - Verify `scenario_id`, `run_id`, `release_label`, `final_state`, and `event_count`
   - All 60 rows of `enriched_rows` and full `events` array are present

2. **Open the PDF report** → `run_001/scenario_report.pdf`
   - Review the Scenario Summary table (final state, integrity scores)
   - Review the Event Log (state transitions, threshold breaches, integrity drops)
   - Review the integrity score chart for trend direction

3. **Review the event log** → `run_001/event_log.csv`
   - Structured CSV of all events emitted during the run
   - Columns: `Time`, `Severity`, `Type`, `Message`, `Step`
   - Quiet scenarios list headers with an explicit no-event marker

4. **Review the data excerpt** → `run_001/data_excerpt.csv`
   - Last 15 steps of the enriched pipeline output
   - Columns include all 7 raw signal channels, 3 integrity scores, state, explanation

5. **Check the integrity score chart** → `charts/integrity_scores.png`
   - Navigation, Sensor, and Communication integrity plotted over all 60 steps
   - Confirm the trend matches the expected scenario behavior

6. **Check the raw signal chart** → `charts/raw_signals.png`
   - All 7 raw signal channels plotted over time
   - Confirm signal degradation pattern matches the scenario description

7. **Review the validation report** → `VALIDATION_REPORT.md`
   - Summarizes artifact counts, run metadata, and package-level assertions
   - All values are derived from pipeline output — no fabricated claims

8. **Verify the manifest** → `MANIFEST.json`
   - Complete file inventory with file sizes and SHA-256 checksums
   - Cross-reference with `provenance/artifact_checksums.txt` for independent verification

9. **Review the operator receipt** → `OPERATOR_RECEIPT.md`
   - Confirms scenario, run ID, release label, timestamp, and canonical limitations
   - Intended as a top-level acknowledgment record

10. **Verify checksums** → `provenance/artifact_checksums.txt`
    - SHA-256 checksums for every artifact in this package
    - Verify on Linux/macOS: `sha256sum -c provenance/artifact_checksums.txt`
    - Verify on Windows: `Get-FileHash <file> -Algorithm SHA256`

---

## Key Facts

| Property | Value |
|---|---|
| MIS version | V1.3 |
| Scenario | `compound_degradation` |
| Steps | 60 |
| Random seed | 42 (deterministic) |
| Prediction | None |
| ML / AI | None |
| Real telemetry | None |
| Operational recommendations | None |

---

Demonstration report generated from simulated data

© 2026 Tripp Parker / Fueled Analytics. All rights reserved. Generated for demonstration purposes only.
