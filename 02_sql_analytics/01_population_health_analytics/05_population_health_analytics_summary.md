# Population Health Analytics Summary

## Notebook

```text
21_sql_population_health_analytics
```

---

# Purpose of This Notebook

The purpose of this notebook was to perform SQL-based healthcare analytics using patient-level integrated healthcare data.

The notebook focused on understanding:

- patient populations
- healthcare costs
- risk categories
- chronic disease burden
- utilization patterns
- demographic distributions
- data quality
- healthcare KPIs

while simultaneously learning SQL.

---

# What Is Population Health Analytics?

Population health analytics studies groups of patients to understand:

- disease burden
- healthcare utilization
- risk distribution
- spending patterns
- demographic trends
- intervention opportunities

Goal:

Improve outcomes while reducing cost.

---

# Types of Analytics Performed

Notebook 21 covered multiple healthcare analytics domains.

---

# 1. Descriptive Population Analytics

Purpose:

Describe the healthcare population.

Questions answered:

### How many patients exist?

Result:

```text
555 patients
```

---

### What is average age?

Result:

```text
46.19 years
```

---

### What are youngest and oldest ages?

Results:

```text
Minimum Age = 4

Maximum Age = 114
```

---

### What age groups dominate?

Results:

| Age Group | Count |
|-----------|------:|
| Adult | 339 |
| Senior | 136 |
| Pediatric | 80 |

Insight:

Adults dominate the population.

---

# 2. Risk Stratification Analytics

Purpose:

Identify patient risk levels.

Questions answered:

### What is risk distribution?

Results:

| Risk Category | Count |
|---------------|------:|
| Low Risk | 247 |
| Medium Risk | 231 |
| High Risk | 77 |

Insight:

Most patients belong to Low or Medium Risk categories.

---

### Which demographics contain more risk?

Example:

Risk by gender.

Insight:

Female patients had more High Risk cases in this dataset.

---

# 3. Financial Analytics

Purpose:

Understand healthcare spending.

Questions answered:

### Which patients generate highest costs?

Top patient spending:

```text
13.5M+
```

---

### Total spending by cost group

Results:

| Cost Group | Spending |
|------------|----------:|
| High Cost | 111M |
| Medium Cost | 17.7M |
| Low Cost | 4.8M |

Major insight:

Small populations drive most spending.

---

### Average spending by cost group

Results:

| Cost Group | Avg Spending |
|------------|--------------:|
| High Cost | 685K |
| Medium Cost | 108K |
| Low Cost | 21K |

Insight:

Healthcare spending is highly concentrated.

---

# 4. Chronic Disease Analytics

Purpose:

Measure disease burden.

Questions answered:

### How many diabetic patients exist?

Results:

```text
165 diabetic patients
```

Insight:

Significant chronic disease burden exists.

---

### Does chronic disease burden increase spending?

Analysis:

Compared:

```text
chronic_disease_count

vs

total_claim_cost
```

Business implication:

Chronic conditions increase healthcare utilization and cost.

---

# 5. Utilization Analytics

Purpose:

Understand healthcare usage.

Questions answered:

### Which patients have high encounter counts?

Used:

```text
total_encounters
```

Insight:

Small populations often drive utilization.

---

### Which populations are high utilizers?

Business implication:

Targeted interventions may reduce cost.

---

# 6. Data Quality Analytics

Purpose:

Evaluate completeness.

Questions answered:

### Are glucose values missing?

Result:

```text
0 missing values
```

---

### Available glucose observations

Result:

```text
555 available values
```

Insight:

Dataset completeness is high.

---

# 7. Relational Analytics

Purpose:

Connect healthcare domains.

Performed:

```text
patient_summary

+

claim_cost_summary
```

using:

```text
patient_id
```

Learned:

- INNER JOIN
- LEFT JOIN
- relationship validation

---

### JOIN Validation Result

Result:

```text
Joined Rows = 555

No duplication
```

Insight:

Relationships are complete.

---

# 8. Comparative Analytics

Purpose:

Compare patients against population averages.

Questions answered:

### Which patients exceed average healthcare spending?

Average spending:

```text
240,605
```

Patients above average:

Identified through:

```sql
Subqueries

CTE
```

Business implication:

Target expensive populations.

---

# 9. Ranking Analytics

Purpose:

Identify extreme populations.

Performed:

---

## Highest-cost patient ranking

Used:

```sql
ROW_NUMBER()
```

Question:

```text
Who are highest-cost patients?
```

---

## Ranking with ties

Used:

```sql
RANK()

DENSE_RANK()
```

---

## Ranking within groups

Used:

```sql
PARTITION BY gender
```

Question:

```text
Who are highest-cost patients within gender?
```

---

# 10. Enterprise Analytics Engineering

Purpose:

Create reusable analytics.

Performed:

---

## Views

Created:

```text
high_cost_patients_view
```

Purpose:

Reusable dashboard layer.

---

## CTEs

Used:

```sql
WITH
```

Purpose:

Readable SQL.

---

# Major Healthcare Insights Discovered

---

## Insight 1

Adults dominate the healthcare population.

---

## Insight 2

Healthcare spending is highly concentrated among small patient groups.

---

## Insight 3

High-cost patients drive most spending.

---

## Insight 4

Chronic disease burden appears associated with higher spending.

---

## Insight 5

Most patients are Low or Medium Risk.

---

## Insight 6

Healthcare data completeness is high.

---

# Business Value Generated

Notebook 21 generated:

✓ Population insights

✓ Financial insights

✓ Risk insights

✓ Cost segmentation

✓ Demographic segmentation

✓ Dashboard KPIs

✓ Reusable SQL analytics

---

# Analytics Outputs Produced

Examples:

- risk distributions
- spending distributions
- patient rankings
- cost rankings
- demographic summaries
- dashboard metrics

---

# Dashboard Readiness

Notebook outputs can directly support:

- Power BI
- Tableau
- Databricks Dashboards
- Streamlit
- Executive Reports

---

# Final Summary

Notebook 21 transformed raw healthcare data into actionable analytics by answering:

```text
Who are our patients?

Who drives spending?

Who is high risk?

Who is expensive?

Which populations need intervention?
```

These are foundational questions in population health and healthcare analytics.
