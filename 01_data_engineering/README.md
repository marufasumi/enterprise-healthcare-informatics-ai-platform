
# Enterprise Healthcare Informatics AI Platform  
## Data Engineering Layer

Enterprise-scale healthcare data engineering pipeline built using Databricks Lakehouse Architecture to process FHIR R4 healthcare data into analytics-ready Delta tables.

---

# Project Goal

The purpose of this data engineering pipeline is to:

- ingest raw FHIR healthcare data
- build scalable ETL pipelines
- normalize healthcare resources
- create clean healthcare tables
- implement Medallion Architecture
- prepare analytics-ready Gold datasets
- support downstream SQL, BI, and ML pipelines

---

# Technology Stack

| Category | Tools |
|----------|--------|
| Data Platform | Databricks |
| Processing | PySpark |
| Storage | Delta Lake |
| Query Engine | Spark SQL |
| Catalog | Unity Catalog |
| Healthcare Standard | FHIR R4 |
| Architecture | Medallion Lakehouse |

---

# Architecture Overview

![Architecture Overview](05_architecture/images/de_architecture.png)

Pipeline Flow:

```text
FHIR JSON
    ↓
Bronze Layer
(raw ingestion)
    ↓
Silver Layer
(cleaning + normalization)
    ↓
Gold Layer
(KPI engineering + feature tables)
```

---

# Repository Structure

```text
01_data_engineering/

├── README.md

├── 01_notebooks/
│      ├── bronze/
│      ├── silver/
│      └── gold/
│

├── 02_sql/
│
├── 03_schemas/
│
├── 04_validation/
│
├── 05_architecture/
│      └── images/
│
├── 06_configs/
│
├── 07_docs/
│
└── 08_data/
       ├── metadata/
       ├── dashboard_exports/
       └── sample_data/
```

---

# Data Sources

FHIR resources processed:

| Resource | Count |
|----------|------:|
| Patient | 555 |
| Encounter | 27,812 |
| Condition | 17,253 |
| Observation | 131,703 |
| Procedure | 38,528 |
| MedicationRequest | 24,256 |
| Immunization | 8,100 |
| CarePlan | 1,831 |
| Allergy | 499 |
| Claim | 52,068 |

---

# Medallion Architecture

---

## Bronze Layer

Purpose:

Store raw healthcare data exactly as received.

Examples:

```text
patient_raw
encounter_raw
claim_raw
```

Tasks:

- ingestion
- metadata tracking
- schema preservation
- raw storage

---

## Silver Layer

Purpose:

Normalize healthcare resources.

Examples:

```text
patient_clean
encounter_clean
condition_clean
claim_clean
```

Tasks:

- cleaning
- flatten nested JSON
- missing value handling
- datatype correction
- normalization

---

## Gold Layer

Purpose:

Create analytics-ready healthcare tables.

Gold outputs:

```text
patient_summary
encounter_utilization_summary
chronic_disease_summary
claim_cost_summary
population_health_dashboard
```

Tasks:

- KPI engineering
- aggregations
- dashboard tables
- ML features

---

# Gold Analytics Tables Created

| Table | Purpose |
|-------|----------|
| patient_summary | patient demographics |
| encounter_utilization_summary | utilization KPIs |
| chronic_disease_summary | disease prevalence |
| medication_summary | medication burden |
| observation_vitals_labs_summary | clinical analytics |
| procedure_careplan_summary | treatment complexity |
| claim_cost_summary | financial analytics |
| population_health_dashboard | executive dashboard |

---

# Dataset Outputs

Population KPIs generated:

| KPI | Value |
|-----|------:|
| Total Patients | 555 |
| Average Age | 46.19 |
| Avg Encounters | 50.11 |
| Avg Chronic Conditions | 1.91 |
| Avg Claim Cost | 240,605 |
| Polypharmacy Patients | 260 |

---

Risk categories:

| Risk | Count |
|------|------:|
| Low Risk | 247 |
| Medium Risk | 231 |
| High Risk | 77 |

---

# Pipeline Execution Order

## Phase 1 — Bronze

Run notebooks:

```text
01_bronze_*
```

---

## Phase 2 — Silver

Run notebooks:

```text
01_silver_*
```

---

## Phase 3 — Gold

Run notebooks:

```text
13_gold_*
...
20_gold_population_health_dashboard
```

---

# Validation

Validation checks implemented:

- row counts
- null checks
- schema validation
- duplicate checks
- completeness checks

Validation docs:

```text
04_validation/
```

---

# Configuration Files

Stored under:

```text
06_configs/
```

Contains:

- catalog names
- schemas
- volume paths
- runtime configs

---

# Architecture Documentation

Stored under:

```text
05_architecture/
```

Contains:

- lakehouse architecture
- medallion architecture
- pipeline flow
- MLOps roadmap

---

# Future Extensions

This Data Engineering layer supports:

→ SQL Analytics  
→ Power BI dashboards  
→ Machine Learning  
→ MLOps pipelines

without redesigning pipelines.

---

# Enterprise Concepts Demonstrated

This project demonstrates:

✓ Databricks Lakehouse  
✓ Medallion Architecture  
✓ Delta Lake  
✓ Healthcare ETL  
✓ FHIR Processing  
✓ PySpark Engineering  
✓ Feature Engineering  
✓ Analytics Engineering  

---

# Author

Healthcare Informatics + Clinical AI + Data Engineering Portfolio Project
