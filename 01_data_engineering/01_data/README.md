# Data Folder

This folder stores lightweight datasets and exports used to support the Enterprise Healthcare Informatics AI Platform documentation and reproducibility.

The repository intentionally excludes large raw healthcare datasets and instead provides:

- sample data
- metadata summaries
- dashboard exports
- schema documentation

---

# Folder Structure

```text
01_data/

├── 01_sample_data/
├── 02_metadata/
├── 03_schemas/
└── 04_dashboard_exports/
```

---

# Purpose of Each Folder

## 01_sample_data

Contains small healthcare table samples.

Purpose:

- demonstrate table structures
- show cleaned outputs
- support reproducibility

---

## 02_metadata

Contains:

- dataset counts
- validation summaries
- pipeline summaries

Purpose:

Help users understand dataset scale.

---

## 03_schemas

Contains:

- column definitions
- healthcare table schemas
- documentation

Purpose:

Explain healthcare tables.

---

## 04_dashboard_exports

Contains Gold analytics outputs.

Purpose:

Support:

- Power BI
- SQL analytics
- KPI reporting
- dashboard creation

---

# Dataset Scale

| Resource | Count |
|---|---:|
| Patients | 555 |
| Encounters | 27,812 |
| Conditions | 17,253 |
| Observations | 131,703 |
| Claims | 52,068 |

---

# Technologies

- Databricks
- Delta Lake
- PySpark
- Spark SQL
- FHIR R4
