# Module 28 — Claims Analytics Foundations
# Enterprise Healthcare Analytics & Clinical AI Platform

Healthcare Claims Analytics • Population Health • HEOR • Cost Analytics • Databricks Medallion Architecture • CMS Synthetic Medicare Claims

---

## Project Overview

This module introduces healthcare claims analytics using public CMS Medicare synthetic claims data (DE-SynPUF).

The objective is to expand the existing healthcare platform beyond EHR/FHIR analytics into:

✓ Claims Analytics  
✓ Healthcare Economics  
✓ Population Health  
✓ Cost Analytics  
✓ Utilization Analytics  
✓ HEOR (Health Economics & Outcomes Research)  
✓ Real World Evidence foundations  
✓ Dashboard Analytics  
✓ Predictive Healthcare Modeling  

This module follows enterprise Databricks Medallion Architecture.

---

# Business Problem

Healthcare organizations need to answer questions such as:

- Which diseases drive the highest healthcare spending?
- Which populations generate high inpatient utilization?
- What proportion of patients are high-cost?
- Which chronic diseases are common?
- Which chronic diseases create the greatest economic burden?

Claims analytics helps hospitals, payers, pharmaceutical companies, and HEOR teams answer these questions.

---

# Dataset

Dataset:

CMS DE-SynPUF (Centers for Medicare & Medicaid Services)

Files used:

```text
DE1_0_2008_Beneficiary_Summary_File_Sample_1.csv
```

Type:

Synthetic Medicare claims data

Public use cases:

- Claims analytics
- HEOR
- Population health
- Cost studies
- Utilization analysis
- Medicare analytics

---

# Architecture

## Medallion Architecture

```text
Raw CMS ZIP File
        │
        ▼
Bronze Layer
(raw ingestion)
        │
        ▼
Silver Layer
(cleaned + standardized)
        │
        ▼
Gold Layer
(analytics tables)
        │
        ▼
Dashboard Outputs
        │
        ▼
Predictive Modeling (future)
```

---

## Recommended Architecture Diagram

Create PNG:

```text
docs/architecture/module28_claims_architecture.png
```

Diagram:

```text
CMS Dataset
   │
   ▼
Databricks Volume
   │
   ▼
Bronze
cms_beneficiary_2008_raw
   │
   ▼
Silver
cms_beneficiary_2008_clean
   │
   ▼
Gold Tables
 ├── disease_cost_burden_summary
 ├── disease_prevalence_summary
 └── disease_dashboard_summary
   │
   ▼
Power BI / Dashboard
   │
   ▼
ML Models (future)
```

Add PNG into README:

```markdown
![Architecture](docs/architecture/module28_claims_architecture.png)
```

---

# Folder Structure

```text
Enterprise_Healthcare_Analytics_Clinical_AI/

notebooks/
    28_sql_claims_analytics.ipynb

data/
    sample/
        cms_beneficiary_2008_sample.csv

silver_outputs/
        cms_beneficiary_2008_clean_sample.csv

analytics_outputs/
        disease_cost_burden_summary.csv

dashboard_outputs/
        disease_dashboard_summary.csv

docs/
    claims_analytics/
        README_Module28_Claims_Analytics.md

architecture/
        module28_claims_architecture.png
```

---

# Bronze Layer

Table:

```text
healthcare_catalog.bronze.cms_beneficiary_2008_raw
```

Purpose:

Store raw CMS beneficiary data.

Completed:

- ZIP extraction
- Raw ingestion
- Validation
- Bronze persistence

---

# Silver Layer

Table:

```text
healthcare_catalog.silver.cms_beneficiary_2008_clean
```

Transformations:

✓ Sex labels

✓ Race labels

✓ Chronic disease flags

✓ High-cost indicator

✓ Total reimbursement

✓ Standardized names

Purpose:

Analytics-ready beneficiary table

Example:

```text
beneficiary_id
sex
race
diabetes_flag
total_medicare_reimbursement
high_inpatient_cost_flag
```

---

# Gold Layer

Created Gold analytics tables:

## Disease Cost Burden Summary

Table:

```text
healthcare_catalog.gold.disease_cost_burden_summary
```

Contains:

Average inpatient reimbursement by disease

---

## Disease Prevalence Summary

Table:

```text
healthcare_catalog.gold.disease_prevalence_summary
```

Contains:

Population prevalence

---

## Dashboard Summary

Table:

```text
healthcare_catalog.gold.disease_dashboard_summary
```

Contains:

Disease prevalence + cost burden

Dashboard-ready output

---

# Key Claims Analytics KPIs

## Population

Total beneficiaries:

```text
116,352
```

---

## Cost Metrics

Average inpatient reimbursement:

```text
$2,214
```

Average outpatient reimbursement:

```text
$622
```

Total inpatient reimbursement:

```text
$257.6M
```

Total outpatient reimbursement:

```text
$72.4M
```

---

## Utilization Metrics

Inpatient utilization:

```text
13.25%
```

High-cost beneficiary rate:

```text
6.82%
```

---

# Disease Prevalence Findings

| Disease | Prevalence |
|---------|------------|
| Diabetes | 37.87% |
| CHF | 28.50% |
| Kidney Disease | 16.06% |
| COPD | 13.53% |
| Cancer | 6.37% |
| Stroke/TIA | 4.49% |

---

# Disease Cost Burden Findings

| Disease | Avg Inpatient Cost |
|---------|--------------------|
| Stroke/TIA | $12,767 |
| Kidney Disease | $9,913 |
| COPD | $9,793 |
| Cancer | $8,289 |
| CHF | $6,409 |
| Diabetes | $4,885 |

---

# Major Insight

Highest prevalence ≠ Highest cost burden

Example:

Most common:

```text
Diabetes
```

Most expensive:

```text
Stroke/TIA
```

This is a foundational HEOR concept.

---

# Skills Demonstrated

Healthcare Analytics

Claims Analytics

Databricks

SQL

Healthcare Cost Analytics

Population Health

HEOR

Medallion Architecture

Data Engineering

Gold Analytics

Dashboard Design

Healthcare Economics

---

# Portfolio Outputs

Generated outputs:

```text
cms_beneficiary_2008_sample.csv

cms_beneficiary_2008_clean_sample.csv

disease_cost_burden_summary.csv

disease_dashboard_summary.csv
```

---

# Interview Relevance

Supports preparation for:

✓ Healthcare Data Engineer

✓ Healthcare Data Scientist

✓ Claims Analyst

✓ HEOR Analyst

✓ Clinical Analytics

✓ Population Health

✓ Health Informatics

---

# Next Module

Notebook:

```text
29_sql_healthcare_cost_utilization
```

Focus:

- PMPM
- Utilization trends
- LOS
- High utilizers
- Cost segmentation
- Spending burden

---

# Status

Module 28:

Completed ✅

Architecture:

```text
Raw → Bronze → Silver → Gold → Dashboard
```
