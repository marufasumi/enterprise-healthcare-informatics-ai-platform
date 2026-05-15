
# Project Overview

![Project Overview](images/infographic_dashboard.png)

# SQL Population Health Analytics

Enterprise Healthcare SQL Analytics using Population Health Data

---

# Project Overview

This module focuses on learning SQL through real-world healthcare analytics scenarios.

Instead of practicing SQL on toy datasets, this project uses integrated healthcare Gold-layer tables to answer business questions related to:

- population health
- healthcare spending
- risk stratification
- chronic disease burden
- utilization analytics
- demographic analysis
- financial analytics

The notebook combines SQL learning with healthcare business thinking.

---

# Project Goals

Main objectives:

Learn SQL concepts:

```text
SELECT
WHERE
GROUP BY
HAVING
JOIN
Subquery
CTE
VIEW
Window Functions
```

Apply SQL to healthcare analytics:

```text
Patient demographics

Risk analysis

Population segmentation

Healthcare cost analysis

Utilization analysis
```

Generate business insights:

```text
Who are high-risk patients?

Who drives healthcare spending?

Which populations need intervention?
```

---

# Dataset Used

Primary dataset:

```sql
healthcare_catalog.gold.population_health_dashboard
```

Integrated healthcare Gold tables:

```text
patient_summary

claim_cost_summary

medication_summary

encounter_utilization_summary

chronic_disease_summary

observation_vitals_labs_summary

procedure_careplan_summary
```

---

# Repository Structure

```text
sql_analytics/

│
├── README.md
│
├── notebooks/
│      21_sql_population_health_analytics
│      22_sql_utilization_and_financial_analytics
│
├── images/
│      risk_distribution_chart.png
│      age_group_distribution.png
│      spending_by_cost_category.png
│      sql_execution_order.png
│      sql_window_functions.png
│
├── docs/
│      01_project_overview.md
│      02_dataset_description.md
│      03_business_questions.md
│      04_sql_learning_summary.md
│      05_population_health_analytics_summary.md
│      06_sql_cheatsheet_notebook21.md
│      07_healthcare_business_insights.md
│      08_window_functions_notes.md
│      09_interview_questions_notebook21.md
│      10_data_dictionary.md
│      11_sql_best_practices.md
│      12_notebook21_execution_guide.md
│      13_notebook21_summary.md
```

---

# SQL Topics Covered

Notebook 21 covers:

## Beginner SQL

```sql
SELECT
LIMIT
WHERE
ORDER BY
```

---

## Aggregations

```sql
COUNT()

SUM()

AVG()

MIN()

MAX()
```

---

## Group Analytics

```sql
GROUP BY

HAVING

DISTINCT
```

---

## Conditional Logic

```sql
CASE WHEN
```

---

## Relational SQL

```sql
INNER JOIN

LEFT JOIN
```

---

## Intermediate SQL

```sql
Subqueries

CTE

VIEW
```

---

## Advanced SQL

```sql
ROW_NUMBER()

RANK()

DENSE_RANK()

PARTITION BY
```

---

# Business Questions Answered

Examples:

### Population Questions

- How many patients exist?
- What is average age?
- What is risk distribution?

---

### Financial Questions

- Who are highest-cost patients?
- Which populations drive spending?

---

### Chronic Disease Questions

- How many diabetic patients exist?
- Does disease burden increase cost?

---

### Risk Questions

- How many High Risk patients exist?
- Which demographics show elevated risk?

---

# Key Results

Population statistics:

```text
Total Patients = 555

Average Age = 46.19

Minimum Age = 4

Maximum Age = 114
```

---

Risk distribution:

| Risk Category | Count |
|---------------|------:|
| Low Risk | 247 |
| Medium Risk | 231 |
| High Risk | 77 |

---

Age distribution:

| Group | Count |
|-------|------:|
| Adult | 339 |
| Senior |136 |
| Pediatric |80 |

---

Diabetes burden:

```text
165 diabetic patients
```

---

Major financial insight:

High-cost populations drive most healthcare spending.

---

# Example Visualizations

## Population Health Workflow

![Population Health Overview](images/population_health_overview.png)

---

## Risk Distribution

![Risk Distribution](images/risk_distribution_chart.png)

---

## Spending Distribution

![Cost Distribution](images/spending_by_cost_category.png)

---

## SQL Learning Roadmap

![SQL Learning](images/healthcare_sql_learning_path.png)

---

# Skills Demonstrated

This project demonstrates:

### SQL

- advanced SQL
- joins
- window functions
- CTEs

### Healthcare Analytics

- population health
- risk analytics
- utilization analytics

### Business Intelligence

- KPI generation
- segmentation
- dashboard metrics

### Analytics Engineering

- reusable SQL
- validation
- documentation

---

# Documentation

Detailed documentation available:

| File | Purpose |
|------|----------|
| 01_project_overview | Project overview |
| 03_business_questions | Business questions answered |
| 06_sql_cheatsheet | SQL revision |
| 08_window_functions_notes | Advanced SQL |
| 09_interview_questions | Interview preparation |
| 10_data_dictionary | Healthcare column definitions |

---

# Learning Outcome

After completing this module:

You should understand:

```text
Healthcare SQL

↓

Population Analytics

↓

Business Intelligence

↓

Advanced SQL

↓

Predictive Modeling Preparation
```

---

# Next Module

Proceed to:

```text
22_sql_utilization_and_financial_analytics
```

Goal:

Deeper healthcare utilization analysis and financial analytics.

---

# Author

Enterprise Healthcare Informatics Platform

Modules:

```text
Data Engineering

SQL Analytics

Population Health Analytics

Machine Learning

Clinical AI
```
