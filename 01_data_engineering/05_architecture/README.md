
# Architecture Documentation

This folder contains architecture diagrams and technical documentation for the Enterprise Healthcare Informatics AI Platform Data Engineering layer.

The goal is to explain how healthcare data moves through the system from raw FHIR resources to analytics-ready Gold tables.

---

# Architecture Purpose

The architecture documentation supports:

- Databricks Lakehouse implementation
- Medallion Architecture explanation
- Healthcare ETL pipelines
- Data flow visualization
- Feature engineering preparation
- Dashboard and ML readiness

---

# Folder Contents

```text
05_architecture/

├── images/
│      ├── de_architecture.png
│      ├── lakehouse_architecture.png
│      ├── medallion_architecture.png
│      ├── pipeline_flow.png
│      └── mlops_architecture.png
│
├── 05.1_architecture_overview.md
├── 05.2_lakehouse_architecture.md
├── 05.3_medallion_architecture.md
├── 05.4_data_flow_architecture.md
├── 05.5_gold_layer_architecture.md
├── 05.6_pipeline_dependency_flow.md
├── 05.7_healthcare_domain_model.md
├── 05.8_ml_feature_store_architecture.md
├── 05.9_sql_powerbi_architecture.md
└── 05.10_future_mlops_architecture.md
```

---

# Main Architecture

![Architecture Overview](images/de_architecture.png)

Pipeline:

```text
FHIR JSON Files
        ↓
Bronze Layer
(raw ingestion)
        ↓
Silver Layer
(clean healthcare tables)
        ↓
Gold Layer
(KPI + dashboard tables)
        ↓
SQL Analytics
        ↓
Power BI
        ↓
Machine Learning
```

---

# Architecture Documents

## 05.1 Architecture Overview

Purpose:

High-level system design.

Topics:

- overall pipeline
- healthcare workflow
- ETL structure

---

## 05.2 Lakehouse Architecture

Topics:

- Databricks
- Delta Lake
- Unity Catalog
- Storage layers

---

## 05.3 Medallion Architecture

Topics:

- Bronze
- Silver
- Gold

Purpose:

Explain healthcare data transformation.

---

## 05.4 Data Flow Architecture

Topics:

Complete end-to-end movement:

```text
FHIR
→ Bronze
→ Silver
→ Gold
→ SQL
→ BI
→ ML
```

---

## 05.5 Gold Layer Architecture

Topics:

Analytics outputs:

- patient_summary
- claim_cost_summary
- population_health_dashboard

---

## 05.6 Pipeline Dependency Flow

Topics:

Notebook execution order.

Purpose:

Explain dependencies.

---

## 05.7 Healthcare Domain Model

FHIR resources:

- Patient
- Encounter
- Condition
- Observation
- Procedure
- Claim

---

## 05.8 ML Feature Store Architecture

Topics:

How Gold tables become ML features.

---

## 05.9 SQL + Power BI Architecture

Topics:

Gold → SQL → Power BI

---

## 05.10 Future MLOps Architecture

Topics:

```text
Feature Store
↓
Training
↓
MLflow
↓
Registry
↓
Serving
↓
Monitoring
```

Future deployment roadmap.

---

# Technologies Used

Architecture designed using:

- Databricks
- Delta Lake
- PySpark
- Spark SQL
- FHIR R4
- Power BI
- MLflow
- Machine Learning

---

# Enterprise Concepts Demonstrated

This architecture demonstrates:

✓ Lakehouse Architecture

✓ Medallion Architecture

✓ Healthcare ETL

✓ Analytics Engineering

✓ Feature Engineering

✓ Dashboard Engineering

✓ MLOps Planning

---

# Future Extensions

Planned additions:

- CI/CD
- Drift Monitoring
- Feature Store
- Model Registry
- Real-time pipelines
- Serving endpoints
- Clinical AI deployment

---

This architecture layer provides the foundation for:

Data Engineering → Analytics → BI → Machine Learning → MLOps
