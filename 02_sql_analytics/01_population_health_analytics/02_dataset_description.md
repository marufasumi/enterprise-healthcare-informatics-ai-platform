# Dataset Description — Population Health Analytics

## Purpose

This document describes the healthcare dataset used in:

```text
21_sql_population_health_analytics
```

The dataset contains patient-level healthcare information used for SQL learning, population health analytics, financial analysis, risk stratification, and dashboard reporting.

---

# Source Table

Main SQL table used:

```sql
healthcare_catalog.gold.population_health_dashboard
```

This is a Gold layer analytics table created from multiple healthcare domains including:

- patient demographics
- encounters
- chronic conditions
- medications
- claims/costs
- observations/labs
- procedures
- care plans

The table represents a patient-level integrated healthcare analytics dataset.

---

# Dataset Purpose

This dataset supports analysis of:

- population health
- patient utilization
- healthcare costs
- chronic disease burden
- risk stratification
- healthcare KPIs
- financial analytics
- dashboard reporting

---

# Important Columns Used in Notebook 21

| Column Name | Data Type | Meaning | Example Business Question |
|-------------|------------|----------|----------------------------|
| patient_id | string | Unique patient identifier | How many unique patients exist? |
| gender | string | Patient gender | Are high-risk patients mostly male or female? |
| age | bigint | Patient age | What is the average patient age? |
| city | string | Patient city | Which locations have expensive patients? |
| state | string | Patient state | Which state has highest utilization? |
| total_encounters | bigint | Total healthcare visits | Who are high utilizers? |
| chronic_disease_count | int | Number of chronic conditions | Does disease burden increase cost? |
| diabetes_flag | int | Indicates diabetes | How many diabetic patients exist? |
| total_medication_requests | bigint | Total medications prescribed | Which patients have high medication burden? |
| total_claims | bigint | Number of claims | Which patients generate most claims? |
| total_claim_cost | double | Total healthcare spending | Who are highest-cost patients? |
| avg_claim_cost | double | Average claim cost | What is average spending per patient? |
| max_claim_cost | double | Highest individual claim | Which patients have extreme claims? |
| high_cost_patient_flag | int | Indicates expensive patient | How many high-cost patients exist? |
| population_health_risk_score | int | Computed risk score | Which patients are highest risk? |
| population_health_risk_category | string | Risk classification | How many Low/Medium/High risk patients exist? |
| avg_glucose | double | Average glucose measurement | Are glucose values missing? |
| avg_hba1c | double | Diabetes biomarker | Which populations show diabetic patterns? |

---

# Key Analytical Features

Notebook 21 frequently used these columns:

## Demographics

Used for:

- age analysis
- gender analysis
- population segmentation

Columns:

```text
age
gender
city
state
marital_status
```

---

## Financial Analytics

Used for:

- spending analysis
- cost distribution
- high-cost patient detection

Columns:

```text
total_claim_cost
avg_claim_cost
total_claims
high_cost_patient_flag
```

---

## Population Health Analytics

Used for:

- risk stratification
- chronic disease burden
- patient segmentation

Columns:

```text
population_health_risk_category
population_health_risk_score
chronic_disease_count
```

---

## Utilization Analytics

Used for:

- healthcare service utilization
- encounter burden

Columns:

```text
total_encounters
emergency_encounters
inpatient_encounters
```

---

# Dataset Characteristics

| Metric | Value |
|--------|-------:|
| Total Patients | 555 |
| Average Age | 46.19 |
| Minimum Age | 4 |
| Maximum Age | 114 |
| High Risk Patients | 77 |
| Medium Risk Patients | 231 |
| Low Risk Patients | 247 |

---

# Gold Layer Context

This dataset belongs to:

```text
healthcare_catalog.gold
```

Gold layer purpose:

```text
Business-ready analytics tables
```

Gold tables are optimized for:

- dashboards
- SQL analysis
- machine learning
- reporting
- executive KPIs

---

# Notebook Using This Dataset

Used in:

```text
21_sql_population_health_analytics
```

Future notebooks will continue using this dataset for:

- utilization analytics
- financial analytics
- advanced SQL
- predictive modeling preparation

---

# Summary

The `population_health_dashboard` table serves as an integrated patient-level healthcare analytics dataset combining demographic, utilization, clinical, medication, and financial information.

It enables SQL learning while supporting real-world healthcare business analytics.
