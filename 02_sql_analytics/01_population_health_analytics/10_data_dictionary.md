# Data Dictionary — Population Health Analytics Dataset

## Purpose

This document defines important variables used in:

```text
21_sql_population_health_analytics
```

The purpose of a data dictionary is to explain:

- what columns mean
- datatype
- business interpretation
- healthcare significance
- possible analytical use cases

Data dictionaries are common in:

- healthcare analytics
- BI projects
- analytics engineering
- clinical informatics
- production ML systems

---

# Source Table

Main dataset:

```sql
healthcare_catalog.gold.population_health_dashboard
```

Layer:

```text
Gold Layer
```

Purpose:

```text
Business-ready analytics dataset
```

---

# Column Categories

Columns are grouped into:

1. Patient Demographics
2. Utilization Metrics
3. Chronic Disease Metrics
4. Medication Metrics
5. Observation / Lab Metrics
6. Procedure Metrics
7. Financial Metrics
8. Risk Metrics

---

# 1. Patient Demographics

---

## patient_id

Datatype:

```text
string
```

Meaning:

Unique patient identifier.

Example:

```text
b0a06ead-cc42...
```

Used for:

- joins
- tracking
- patient-level analytics

Business question:

```text
How many unique patients exist?
```

---

## gender

Datatype:

```text
string
```

Possible values:

```text
male

female
```

Used for:

- demographic analysis
- segmentation
- equity analysis

Business question:

```text
Do females show higher risk?
```

---

## age

Datatype:

```text
bigint
```

Meaning:

Patient age.

Used for:

- age segmentation
- pediatric analysis
- senior population analysis

Example categories:

```text
Pediatric

Adult

Senior
```

Business question:

```text
What is average patient age?
```

---

## city

Datatype:

```text
string
```

Meaning:

Patient city.

Possible use:

Regional analytics.

---

## state

Datatype:

```text
string
```

Meaning:

Patient state.

Possible use:

State-level healthcare comparison.

---

## marital_status

Datatype:

```text
string
```

Examples:

```text
M

S

Never Married
```

Potential use:

Social determinants analysis.

---

# 2. Utilization Metrics

Healthcare utilization measures service usage.

---

## total_encounters

Datatype:

```text
bigint
```

Meaning:

Total healthcare visits.

Used for:

- utilization analytics
- high utilizer identification

Business question:

```text
Who uses healthcare services most?
```

---

## ambulatory_encounters

Meaning:

Outpatient visits.

---

## emergency_encounters

Meaning:

Emergency department visits.

Business importance:

High emergency use may indicate poor health management.

---

## inpatient_encounters

Meaning:

Hospital admissions.

Business importance:

High inpatient burden increases cost.

---

## avg_encounter_duration_hours

Datatype:

```text
double
```

Meaning:

Average encounter duration.

---

## total_encounter_hours

Meaning:

Total care time.

---

# 3. Chronic Disease Metrics

---

## diabetes_flag

Datatype:

```text
int
```

Values:

```text
1 = diabetes present

0 = absent
```

Business question:

```text
How many diabetic patients exist?
```

---

## hypertension_flag

Meaning:

Hypertension indicator.

---

## asthma_flag

Meaning:

Asthma indicator.

---

## obesity_flag

Meaning:

Obesity indicator.

---

## chronic_kidney_disease_flag

Meaning:

CKD indicator.

---

## coronary_heart_disease_flag

Meaning:

Heart disease indicator.

---

## mental_health_flag

Meaning:

Mental health condition.

---

## cancer_flag

Meaning:

Cancer history.

---

## chronic_disease_count

Datatype:

```text
int
```

Meaning:

Number of chronic diseases.

Used for:

Disease burden analysis.

Business question:

```text
Does disease burden increase cost?
```

---

## multi_chronic_condition_flag

Meaning:

Indicates multiple chronic diseases.

---

# 4. Medication Metrics

---

## total_medication_requests

Datatype:

```text
bigint
```

Meaning:

Number of medication prescriptions.

---

## unique_medications

Meaning:

Distinct medications.

---

## polypharmacy_flag

Meaning:

Multiple medication burden.

Business importance:

Polypharmacy increases risk.

---

## high_medication_burden_flag

Meaning:

Indicates unusually high medication usage.

---

# 5. Observation / Laboratory Metrics

---

## avg_glucose

Datatype:

```text
double
```

Meaning:

Average blood glucose.

Used for:

Diabetes monitoring.

---

## avg_hba1c

Meaning:

Average HbA1c.

Business use:

Long-term diabetes assessment.

---

## avg_bmi

Meaning:

Average BMI.

---

## avg_heart_rate

Meaning:

Heart rate.

---

## avg_respiratory_rate

Meaning:

Respiration.

---

## avg_oxygen_saturation

Meaning:

Oxygen level.

---

## high_glucose_flag

Meaning:

Elevated glucose.

---

## high_hba1c_flag

Meaning:

Elevated HbA1c.

---

## obesity_from_bmi_flag

Meaning:

Obesity inferred from BMI.

---

# 6. Procedure Metrics

---

## total_procedures

Meaning:

Number of procedures.

---

## unique_procedure_count

Meaning:

Distinct procedures.

---

## total_careplans

Meaning:

Care plans assigned.

---

## active_careplans

Meaning:

Ongoing care plans.

---

## completed_careplans

Meaning:

Finished care plans.

---

## high_treatment_complexity_flag

Meaning:

Complex treatment burden.

---

# 7. Financial Metrics (VERY IMPORTANT)

---

## total_claims

Datatype:

```text
bigint
```

Meaning:

Total claims submitted.

---

## total_claim_cost

Datatype:

```text
double
```

Meaning:

Total healthcare spending.

Business importance:

One of the most important financial variables.

Used for:

- cost analysis
- ranking
- high-cost detection

Business question:

```text
Who are highest-cost patients?
```

---

## avg_claim_cost

Meaning:

Average claim amount.

---

## max_claim_cost

Meaning:

Largest single claim.

---

## pharmacy_claim_cost

Meaning:

Medication spending.

---

## institutional_claim_cost

Meaning:

Hospital/organization spending.

---

## high_cost_patient_flag

Values:

```text
1 = expensive patient

0 = otherwise
```

---

## very_high_cost_patient_flag

Meaning:

Extreme spending.

---

# 8. Risk Metrics

---

## population_health_risk_score

Datatype:

```text
int
```

Meaning:

Numerical risk measure.

Higher score:

```text
Higher risk
```

---

## population_health_risk_category

Datatype:

```text
string
```

Values:

```text
Low Risk

Medium Risk

High Risk
```

Used for:

Risk stratification.

Business question:

```text
How many High Risk patients exist?
```

---

# Important Columns Used Most in Notebook 21

Most analyzed:

```text
patient_id

age

gender

total_claim_cost

chronic_disease_count

population_health_risk_category

avg_glucose

total_encounters
```

---

# Common Business Questions Supported

Dataset answers:

✓ Who drives healthcare spending?

✓ Which patients are high risk?

✓ Which populations use healthcare most?

✓ What is disease burden?

✓ Which groups need intervention?

---

# Summary

The `population_health_dashboard` table is an integrated healthcare analytics dataset combining:

- demographics
- utilization
- chronic disease
- medications
- labs
- claims
- procedures
- risk scores

This dataset supports SQL analytics, dashboards, population health analysis, and future predictive modeling.
