# Interview Questions & Answers — Notebook 21

## Purpose

This document contains SQL and healthcare analytics interview questions derived from:

```text
21_sql_population_health_analytics
```

Topics covered:

- SQL fundamentals
- joins
- aggregations
- subqueries
- CTEs
- views
- window functions
- healthcare analytics
- business interpretation

Use this file for:

- SQL interviews
- healthcare analyst interviews
- BI analyst interviews
- analytics engineer interviews
- technical screening

---

# Section 1 — SQL Fundamentals

---

## Q1:

What does SQL SELECT do?

Answer:

```text
SELECT retrieves columns from a database table.
```

Example:

```sql
SELECT patient_id, age
FROM patient_summary;
```

---

## Q2:

Difference between WHERE and HAVING?

Answer:

```text
WHERE filters rows before grouping.

HAVING filters aggregated groups after GROUP BY.
```

Example:

WHERE:

```sql
WHERE age > 65
```

HAVING:

```sql
HAVING COUNT(*) > 100
```

---

## Q3:

Difference between COUNT(*) and COUNT(column)?

Answer:

```text
COUNT(*) counts all rows.

COUNT(column) ignores NULL values.
```

---

## Q4:

Difference between DISTINCT and GROUP BY?

Answer:

```text
DISTINCT returns unique values.

GROUP BY groups rows for aggregation.
```

---

# Section 2 — Aggregation Questions

---

## Q5:

What aggregate functions do you know?

Answer:

Examples:

```sql
COUNT()

SUM()

AVG()

MIN()

MAX()
```

Uses:

- counts
- averages
- totals
- smallest values
- largest values

---

## Q6:

How would you find average patient age?

Answer:

```sql
SELECT AVG(age)

FROM patient_summary;
```

---

## Q7:

How would you identify oldest patient?

Answer:

```sql
SELECT MAX(age)

FROM patient_summary;
```

---

# Section 3 — CASE WHEN Questions

---

## Q8:

What is CASE WHEN?

Answer:

```text
CASE WHEN creates conditional business logic inside SQL.
```

Example:

Age segmentation:

```sql
CASE

WHEN age <18 THEN 'Pediatric'

WHEN age <65 THEN 'Adult'

ELSE 'Senior'

END
```

---

## Q9:

Where is CASE WHEN useful?

Answer:

Examples:

- patient segmentation
- risk grouping
- cost categories

---

# Section 4 — NULL Questions

---

## Q10:

How do you identify missing values?

Answer:

```sql
WHERE column IS NULL
```

---

## Q11:

Difference between NULL and zero?

Answer:

```text
NULL means unknown or missing.

0 means an actual value.
```

---

# Section 5 — JOIN Questions

---

## Q12:

Difference between INNER JOIN and LEFT JOIN?

Answer:

```text
INNER JOIN:

Keeps matching rows only.

LEFT JOIN:

Keeps all rows from left table.
```

---

## Q13:

How would you detect missing relationships?

Answer:

Example:

```sql
LEFT JOIN

WHERE joined_table.id IS NULL
```

---

## Q14:

How do you validate a JOIN?

Answer:

Check:

```text
Row counts

Duplicates

Missing rows
```

---

# Section 6 — Subquery Questions

---

## Q15:

What is a subquery?

Answer:

```text
A query inside another query.
```

Example:

```sql
WHERE cost >

(
SELECT AVG(cost)
FROM table
)
```

---

## Q16:

What is a scalar subquery?

Answer:

```text
A subquery returning one value.
```

Examples:

```sql
AVG()

MAX()

COUNT()
```

---

# Section 7 — CTE Questions

---

## Q17:

What is a CTE?

Answer:

```text
CTE stands for Common Table Expression.

CTEs improve readability and modular SQL design.
```

Syntax:

```sql
WITH cte_name AS

(
query
)
```

---

## Q18:

Why use CTEs?

Answer:

```text
Improve readability

Improve debugging

Improve maintainability
```

---

# Section 8 — Views Questions

---

## Q19:

What is a SQL View?

Answer:

```text
A reusable virtual table generated from a stored SQL query.
```

---

## Q20:

Why are Views useful?

Answer:

```text
Views centralize business logic and simplify dashboards.
```

---

# Section 9 — Window Function Questions

(VERY IMPORTANT)

---

## Q21:

What is ROW_NUMBER()?

Answer:

```text
ROW_NUMBER() assigns unique sequential rankings.
```

---

## Q22:

Difference between ROW_NUMBER() and RANK()?

Answer:

ROW_NUMBER:

```text
1

2

3
```

RANK:

```text
1

1

3
```

---

## Q23:

Difference between RANK() and DENSE_RANK()?

Answer:

RANK:

```text
1

1

3
```

DENSE_RANK:

```text
1

1

2
```

---

## Q24:

What does PARTITION BY do?

Answer:

```text
PARTITION BY divides rows into groups and applies window functions separately.
```

---

## Q25:

Difference between GROUP BY and window functions?

Answer:

```text
GROUP BY collapses rows.

Window functions preserve row detail.
```

---

# Section 10 — Healthcare Analytics Questions

---

## Q26:

What population health questions did you answer?

Answer:

Examples:

- patient count
- risk distribution
- spending distribution
- chronic disease burden

---

## Q27:

How many patients existed?

Answer:

```text
555 patients
```

---

## Q28:

Average age?

Answer:

```text
46.19 years
```

---

## Q29:

Risk distribution?

Answer:

| Risk | Count |
|-----|------:|
| Low | 247 |
| Medium | 231 |
| High | 77 |

---

## Q30:

How many diabetic patients?

Answer:

```text
165 diabetic patients
```

---

## Q31:

Major healthcare insight?

Answer:

```text
A small high-cost population drives most spending.
```

---

## Q32:

Business implication of high-cost populations?

Answer:

Potential interventions:

- care coordination
- disease management
- preventive programs

---

## Q33:

Why analyze risk categories?

Answer:

```text
Risk stratification supports targeted healthcare interventions.
```

---

# Section 11 — Scenario Questions

(VERY COMMON)

---

## Q34:

A dashboard shows duplicate patients after JOIN. What would you check?

Answer:

Check:

```text
Primary keys

Join conditions

Duplicates

Row counts
```

---

## Q35:

Healthcare costs increase dramatically. How investigate?

Answer:

Review:

- high-cost populations
- utilization
- chronic disease burden
- expensive claims

---

## Q36:

A table has missing values. What do you do?

Answer:

Check:

```sql
IS NULL
```

Assess impact.

---

# Section 12 — Portfolio Questions

---

## Q37:

Explain Notebook 21 in simple language.

Answer:

```text
Notebook 21 uses SQL to analyze healthcare populations, risk, spending, utilization, and patient demographics while learning enterprise SQL concepts.
```

---

## Q38:

What SQL topics were learned?

Answer:

```text
SELECT

WHERE

GROUP BY

JOIN

Subquery

CTE

VIEW

Window Functions
```

---

# Final Interview Summary

After Notebook 21 you should comfortably answer questions on:

✓ SQL Fundamentals

✓ Aggregations

✓ Joins

✓ Subqueries

✓ CTEs

✓ Views

✓ Window Functions

✓ Healthcare Analytics

✓ Population Health

✓ Risk Analytics

✓ Financial Analytics

---

# Expected SQL Level After Notebook 21

Approximate level:

```text
Strong Intermediate SQL

+

Early Advanced SQL
```

---

# Final Note

Notebook 21 provides sufficient SQL depth for:

- healthcare analyst interviews
- BI analyst interviews
- analytics engineering interviews
- technical screening rounds
