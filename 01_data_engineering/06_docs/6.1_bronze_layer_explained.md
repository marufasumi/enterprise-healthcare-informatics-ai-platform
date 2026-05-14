# Bronze Layer Documentation

## Purpose

The Bronze layer stores raw ingested FHIR healthcare resources without business transformation.

This layer preserves:
- source fidelity
- raw healthcare records
- original FHIR structure
- healthcare lineage

---

# Bronze Layer Goals

- scalable ingestion
- replayability
- raw data preservation
- healthcare traceability
- source auditing

---

# Bronze Tables

| Table | Purpose |
|---|---|
| patient_raw | raw patient resources |
| encounter_raw | raw encounter resources |
| condition_raw | raw condition resources |
| observation_raw | raw observation resources |
| procedure_raw | raw procedure resources |
| medication_request_raw | raw medication requests |
| immunization_raw | raw immunization records |
| careplan_raw | raw care plans |
| allergy_intolerance_raw | raw allergy records |
| claim_raw | raw healthcare claims |

---

# Bronze Dataset Counts

| Resource | Count |
|---|---:|
| Patients | 555 |
| Encounters | 27,812 |
| Conditions | 17,253 |
| Observations | 131,703 |
| Procedures | 38,528 |
| Medication Requests | 24,256 |
| Immunizations | 8,100 |
| Care Plans | 1,831 |
| Allergy Records | 499 |
| Claims | 52,068 |

---

# Technologies Used

- Databricks
- PySpark
- Delta Lake
- FHIR R4
- Unity Catalog
