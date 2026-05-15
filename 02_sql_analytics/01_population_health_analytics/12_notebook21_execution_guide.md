# Notebook 21 Execution Guide

## Notebook

```text
21_sql_population_health_analytics
```

---

# Purpose

This guide explains how to execute Notebook 21 from beginning to end.

The goal is to allow someone with little or no Databricks experience to reproduce the analysis.

Notebook 21 performs:

- SQL learning
- population health analytics
- financial analytics
- healthcare risk analysis
- joins
- CTEs
- views
- window functions

using healthcare Gold layer datasets.

---

# Prerequisites

Before running Notebook 21, ensure:

---

## Required Platform

Use:

```text
Databricks Workspace
```

Examples:

- Databricks Community Edition
- Databricks Free Edition
- Enterprise Workspace

---

## Required Skills

Minimal SQL knowledge.

Notebook designed for beginners.

---

# Required Catalog Structure

Notebook assumes existence of:

```text
healthcare_catalog
```

with Gold tables.

Expected:

```text
healthcare_catalog.gold.patient_summary

healthcare_catalog.gold.claim_cost_summary

healthcare_catalog.gold.population_health_dashboard

healthcare_catalog.gold.medication_summary

healthcare_catalog.gold.encounter_utilization_summary

healthcare_catalog.gold.chronic_disease_summary
```

---

# Verify Available Tables

Run:

```sql
SHOW TABLES IN healthcare_catalog.gold;
```

Expected output includes:

```text
patient_summary

claim_cost_summary

population_health_dashboard

medication_summary
...
```

---

# Step 1 — Open Databricks Workspace

Login:

```text
https://www.databricks.com/
```

Open workspace.

---

# Step 2 — Start Compute Cluster

Notebook requires active compute.

Go:

```text
Compute

↓

Start Cluster
```

Wait until:

```text
Running
```

---

# Recommended Cluster

Small cluster sufficient.

Example:

```text
Single Node

DBR Latest Runtime
```

---

# Step 3 — Open Notebook

Navigate:

```text
notebooks/

21_sql_population_health_analytics
```

Open notebook.

---

# Step 4 — Attach Compute

Top-right:

Select:

```text
Attach Cluster
```

Choose running cluster.

---

# Step 5 — Verify Catalog Access

Run:

```sql
SHOW TABLES IN healthcare_catalog.gold;
```

Expected:

Gold tables visible.

---

# Step 6 — Execute Notebook Sequentially

Run notebook cells from top to bottom.

Do NOT skip cells.

Order matters.

---

# Notebook Sections

Notebook 21 follows:

---

## Section 1 — Dataset Exploration

Topics:

```sql
SELECT

LIMIT

DESCRIBE
```

Purpose:

Understand data.

---

## Section 2 — Filtering

Topics:

```sql
WHERE

ORDER BY
```

Purpose:

Subset populations.

---

## Section 3 — Aggregation

Topics:

```sql
COUNT

AVG

SUM

GROUP BY
```

Purpose:

Population metrics.

---

## Section 4 — Business Logic

Topics:

```sql
CASE WHEN
```

Purpose:

Age groups

Cost groups

Segmentation

---

## Section 5 — Data Quality

Topics:

```sql
NULL checks
```

Purpose:

Missing values.

---

## Section 6 — JOINs

Topics:

```sql
INNER JOIN

LEFT JOIN
```

Purpose:

Combine healthcare tables.

---

## Section 7 — Validation

Topics:

```sql
COUNT(*)
```

Purpose:

Check duplicates.

---

## Section 8 — Subqueries

Topics:

```sql
Subqueries

Scalar queries
```

Purpose:

Comparative analytics.

---

## Section 9 — CTEs

Topics:

```sql
WITH
```

Purpose:

Readable SQL.

---

## Section 10 — Views

Topics:

```sql
CREATE VIEW
```

Purpose:

Reusable analytics.

---

## Section 11 — Window Functions

Topics:

```sql
ROW_NUMBER()

RANK()

DENSE_RANK()

PARTITION BY
```

Purpose:

Ranking analytics.

---

# Expected Outputs

Notebook generates:

---

## Population Metrics

Examples:

```text
Total Patients

Average Age

Risk Distribution
```

---

## Financial Metrics

Examples:

```text
Average Cost

Total Spending

High Cost Patients
```

---

## Risk Metrics

Examples:

```text
Low Risk

Medium Risk

High Risk
```

---

## Rankings

Examples:

```text
Top spenders

Rank by gender
```

---

# Common Errors and Fixes

---

## Error:

```text
Table not found
```

Fix:

Verify:

```sql
SHOW TABLES IN healthcare_catalog.gold;
```

---

## Error:

```text
Cluster terminated
```

Fix:

Restart cluster.

---

## Error:

```text
Permission denied
```

Fix:

Check catalog permissions.

---

## Error:

```text
No rows returned
```

Fix:

Review filters.

---

# Validation Checklist

Before considering notebook complete:

Verify:

✓ Total Patients = 555

✓ Average Age ≈ 46.19

✓ Risk Categories visible

✓ JOIN count = 555

✓ Views created successfully

✓ Window functions run

---

# Files Produced

Notebook creates:

Examples:

```text
high_cost_patients_view
```

Outputs:

- dashboard metrics
- ranking analytics
- SQL learning artifacts

---

# Learning Outcomes

After completing Notebook 21, user should understand:

---

## SQL Skills

✓ SELECT

✓ GROUP BY

✓ JOIN

✓ CTE

✓ VIEW

✓ Window Functions

---

## Healthcare Analytics Skills

✓ Population analytics

✓ Risk analytics

✓ Financial analytics

---

## Analytics Engineering Skills

✓ Validation

✓ Reusable SQL

✓ Dashboard preparation

---

# Next Notebook

After completion:

Proceed to:

```text
22_sql_utilization_and_financial_analytics
```

---

# Final Summary

Notebook 21 serves as the SQL foundation for the broader healthcare analytics platform.

Completion indicates readiness for:

```text
Advanced SQL

↓

Healthcare analytics

↓

Predictive modeling

↓

Clinical AI
```
