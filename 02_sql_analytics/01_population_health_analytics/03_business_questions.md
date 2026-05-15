# Business Questions Answered — Population Health SQL Analytics

## Purpose

This document summarizes all healthcare business questions explored and answered in:

```text
21_sql_population_health_analytics
```

The objective of Notebook 21 was not only to learn SQL syntax, but also to answer real healthcare analytics questions using enterprise healthcare data.

---

# Analysis Categories Covered

Notebook 21 answered questions across several analytics domains:

- Population Health Analytics
- Healthcare Financial Analytics
- Risk Stratification Analytics
- Utilization Analytics
- Demographic Analytics
- Data Quality Analytics
- Relational Analytics (JOINs)
- Comparative Analytics
- Ranking Analytics

---

# 1. Population Health Analytics Questions

Population health analytics studies patient populations to understand disease burden, risk, and healthcare utilization.

---

## Question:

### How many patients exist in the healthcare population?

SQL Concepts:

```sql
COUNT(*)
```

Business Value:

Estimate population size for reporting and planning.

Answer:

```text
Total Patients = 555
```

---

## Question:

### What is the average patient age?

SQL Concepts:

```sql
AVG()
```

Business Value:

Understand population demographics.

Answer:

```text
Average Age = 46.19
```

---

## Question:

### What are the youngest and oldest patient ages?

SQL Concepts:

```sql
MIN()
MAX()
```

Business Value:

Understand age distribution.

Answer:

```text
Minimum Age = 4

Maximum Age = 114
```

---

## Question:

### How many Pediatric, Adult, and Senior patients exist?

SQL Concepts:

```sql
CASE WHEN
GROUP BY
```

Business Value:

Support age-based healthcare programs.

Answer:

| Age Group | Count |
|-----------|------:|
| Adult | 339 |
| Senior | 136 |
| Pediatric | 80 |

---

# 2. Risk Stratification Analytics Questions

Risk stratification identifies high-risk populations.

---

## Question:

### What is the distribution of healthcare risk categories?

SQL Concepts:

```sql
GROUP BY
COUNT()
```

Business Value:

Identify population risk burden.

Answer:

| Risk Category | Patient Count |
|---------------|---------------:|
| Low Risk | 247 |
| Medium Risk | 231 |
| High Risk | 77 |

---

## Question:

### Which gender has more High Risk patients?

SQL Concepts:

```sql
GROUP BY multiple columns
```

Business Value:

Identify demographic disparities.

Answer:

Example:

| Risk | Gender | Count |
|------|--------|-------:|
| High Risk | Female | 57 |
| High Risk | Male | 20 |

---

# 3. Healthcare Financial Analytics Questions

Financial analytics evaluates healthcare spending.

---

## Question:

### Which patients have the highest healthcare cost?

SQL Concepts:

```sql
ORDER BY DESC
LIMIT
```

Business Value:

Identify expensive patients.

Answer:

Top patient cost exceeded:

```text
13.5 million dollars
```

---

## Question:

### What is total healthcare spending by cost category?

SQL Concepts:

```sql
SUM()
CASE WHEN
GROUP BY
```

Business Value:

Measure financial burden.

Answer:

| Cost Category | Total Spending |
|---------------|---------------:|
| High Cost | 111M |
| Medium Cost | 17.7M |
| Low Cost | 4.8M |

---

## Question:

### What is average healthcare spending by category?

SQL Concepts:

```sql
AVG()
GROUP BY
```

Business Value:

Normalize spending comparisons.

Answer:

| Category | Avg Cost |
|----------|----------:|
| High Cost | 685K |
| Medium Cost | 108K |
| Low Cost | 21K |

---

## Question:

### Which cost groups drive most spending?

Business Insight:

A relatively small high-cost population drives the majority of spending.

---

# 4. Chronic Disease Analytics Questions

---

## Question:

### How many diabetic patients exist?

SQL Concepts:

```sql
SUM(diabetes_flag)
```

Business Value:

Estimate disease burden.

Answer:

```text
165 diabetic patients
```

---

## Question:

### Does chronic disease burden increase cost?

SQL Concepts:

```sql
GROUP BY
```

Business Value:

Understand disease-cost relationship.

---

# 5. Utilization Analytics Questions

Healthcare utilization measures service usage.

---

## Question:

### Which patients have the highest encounter counts?

SQL Concepts:

```sql
ORDER BY total_encounters DESC
```

Business Value:

Identify high utilizers.

---

## Question:

### Which populations have high utilization?

Business Value:

Target interventions.

---

# 6. Data Quality Analytics Questions

---

## Question:

### Are glucose values missing?

SQL Concepts:

```sql
IS NULL
COUNT()
```

Business Value:

Assess data completeness.

Answer:

```text
Missing Glucose Values = 0
```

---

## Question:

### How many glucose values are available?

SQL Concepts:

```sql
IS NOT NULL
```

Answer:

```text
Available Glucose Values = 555
```

---

## Question:

### Difference between COUNT(*) and COUNT(column)?

Business Value:

Understand NULL behavior.

---

# 7. Relational Analytics Questions (JOINs)

---

## Question:

### Can patient demographics be combined with claim costs?

SQL Concepts:

```sql
INNER JOIN
```

Business Value:

Integrated healthcare analytics.

Answer:

Successfully joined:

```text
patient_summary

+

claim_cost_summary
```

---

## Question:

### Did JOINs duplicate or remove rows?

SQL Concepts:

```sql
COUNT(*)
JOIN validation
```

Answer:

```text
Joined Row Count = 555

No duplication detected
```

---

## Question:

### Are any patients missing claim records?

SQL Concepts:

```sql
LEFT JOIN
WHERE IS NULL
```

Answer:

```text
No missing patients
```

---

# 8. Comparative Analytics Questions

---

## Question:

### Which patients spend more than average healthcare cost?

SQL Concepts:

```sql
Subqueries
CTE
```

Business Value:

Identify expensive populations.

---

## Question:

### How does each patient compare against average spending?

SQL Concepts:

```sql
Scalar Subquery
```

Business Value:

Benchmarking.

---

# 9. Ranking Analytics Questions

---

## Question:

### Who are the highest-cost patients?

SQL Concepts:

```sql
ROW_NUMBER()
```

Business Value:

Top spender identification.

---

## Question:

### How do rankings change with ties?

SQL Concepts:

```sql
RANK()

DENSE_RANK()
```

Business Value:

Fair ranking systems.

---

## Question:

### Who are highest-cost patients within gender?

SQL Concepts:

```sql
PARTITION BY
```

Business Value:

Segmented analytics.

---

# 10. Enterprise Analytics Engineering Questions

---

## Question:

### How can SQL logic be reused?

SQL Concepts:

```sql
CREATE VIEW
```

Business Value:

Reusable analytics pipelines.

---

## Question:

### How can SQL become more readable?

SQL Concepts:

```sql
CTE
WITH
```

Business Value:

Maintainable enterprise SQL.

---

# Summary of Major Business Questions Answered

Notebook 21 answered:

✓ How many patients exist?

✓ What is average age?

✓ What is disease burden?

✓ What is risk distribution?

✓ Who are highest-cost patients?

✓ Which populations drive spending?

✓ Are healthcare values missing?

✓ Which patients exceed averages?

✓ Which groups rank highest?

✓ How do we combine healthcare tables?

✓ How do we validate JOINs?

✓ How do we build reusable analytics?

---

# Final Outcome

Notebook 21 transformed raw healthcare data into:

- population health insights
- financial insights
- utilization insights
- risk analytics
- dashboard-ready KPIs
- reusable SQL analytics

This notebook serves as a foundational healthcare analytics and SQL engineering module.
