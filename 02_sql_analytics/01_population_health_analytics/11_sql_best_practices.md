# SQL Best Practices — Notebook 21

## Purpose

This document summarizes SQL best practices learned while working on:

```text
21_sql_population_health_analytics
```

These practices improve:

- readability
- maintainability
- performance
- debugging
- collaboration
- production readiness

They are commonly expected in:

- analytics engineering
- healthcare analytics
- BI roles
- data engineering
- production SQL systems

---

# Why SQL Best Practices Matter

Poor SQL may:

- create duplicates
- reduce performance
- introduce errors
- confuse collaborators

Good SQL improves:

```text
Accuracy

Maintainability

Scalability

Readability
```

---

# Practice 1 — Avoid SELECT *

Avoid:

```sql
SELECT *

FROM patient_summary;
```

Prefer:

```sql
SELECT

patient_id,
age,
gender

FROM patient_summary;
```

---

## Why?

Benefits:

✓ faster queries

✓ reduced memory

✓ improved readability

✓ stable schemas

---

# Practice 2 — Use Meaningful Aliases

Avoid:

```sql
SELECT *

FROM patient_summary p
```

if alias unclear.

Prefer:

```sql
SELECT *

FROM patient_summary AS patient
```

or:

```sql
FROM patient_summary AS p
```

when simple.

---

# Practice 3 — Format SQL Consistently

Bad:

```sql
SELECT age,total_claim_cost FROM table WHERE age>65
```

Good:

```sql
SELECT

age,
total_claim_cost

FROM table

WHERE age > 65
```

---

## Why?

Improves:

```text
Readability

Collaboration

Debugging
```

---

# Practice 4 — Comment Complex Logic

Example:

Good:

```sql
-- identify expensive patients

SELECT *
FROM table
WHERE cost > 500000
```

---

## Why?

Future users understand intent.

---

# Practice 5 — Validate Row Counts After JOINs

VERY IMPORTANT.

After JOIN:

Always check:

```sql
COUNT(*)
```

before and after.

---

Example:

Expected:

```text
555 rows
```

Actual:

```text
555 rows
```

No duplication.

---

## Why?

JOIN errors are common.

---

# Practice 6 — Validate Duplicates

Check:

```sql
COUNT(*)

vs

COUNT(DISTINCT patient_id)
```

---

## Why?

Duplicate patients create incorrect analytics.

---

# Practice 7 — Check Missing Values

Always inspect:

```sql
IS NULL

IS NOT NULL
```

Example:

```sql
WHERE avg_glucose IS NULL
```

---

## Why?

Missing values affect:

- analytics
- ML
- dashboards

---

# Practice 8 — Use CAST for Presentation

Avoid:

```text
46.185585585
```

Prefer:

```sql
CAST(

AVG(age)

AS DECIMAL(10,2)

)
```

Output:

```text
46.19
```

---

## Why?

Cleaner dashboards.

---

# Practice 9 — Prefer CTEs Over Complex Nested Queries

Avoid:

Large unreadable subqueries.

Prefer:

```sql
WITH avg_cost AS

(
SELECT AVG(cost)
FROM table
)

SELECT *
FROM avg_cost
```

---

## Why?

Improves:

```text
Maintainability

Debugging

Readability
```

---

# Practice 10 — Reuse Logic Using Views

Avoid:

Repeated SQL.

Prefer:

```sql
CREATE VIEW
```

Example:

```text
high_cost_patients_view
```

---

## Why?

Reusable analytics.

---

# Practice 11 — Use Window Functions Instead of Self-Joins When Appropriate

Prefer:

```sql
ROW_NUMBER()

RANK()
```

instead of complex joins.

---

## Why?

Cleaner ranking logic.

---

# Practice 12 — Use Descriptive Column Names

Bad:

```text
x

y

z
```

Good:

```text
total_claim_cost

population_health_risk_category
```

---

# Practice 13 — Filter Early

Prefer:

```sql
WHERE age >65
```

before expensive operations.

---

## Why?

Improves performance.

---

# Practice 14 — Use LIMIT During Exploration

Example:

```sql
LIMIT 10
```

---

## Why?

Avoid scanning huge datasets.

---

# Practice 15 — Separate Business Logic From Raw Data

Use:

```text
CASE WHEN

Views

CTEs
```

to build analytics layers.

---

# Practice 16 — Build Reusable Analytics Objects

Examples:

Created in Notebook 21:

```text
CTE

VIEW
```

---

## Why?

Supports:

- dashboards
- BI
- ML pipelines

---

# Practice 17 — Name Objects Clearly

Bad:

```text
table1

view2
```

Good:

```text
high_cost_patients_view
```

---

# Practice 18 — Validate Results Against Business Expectations

Example:

Question:

```text
Average age = 46
```

Reasonable?

Always think critically.

---

## Why?

Correct SQL can still produce unrealistic insights.

---

# Practice 19 — Interpret Results, Not Just Generate Them

Bad analyst:

```text
Shows output
```

Good analyst:

```text
Explains meaning
```

Example:

Observation:

```text
High-cost patients drive most spending
```

Interpretation:

Potential intervention needed.

---

# Practice 20 — Think Like a Business User

Always ask:

```text
What decision could this analysis support?
```

Examples:

- staffing
- budgeting
- intervention
- care coordination

---

# SQL Best Practices Learned in Notebook 21

Completed:

✓ Avoid SELECT *

✓ Validate JOINs

✓ Handle NULLs

✓ Use CTEs

✓ Use Views

✓ Use Window Functions

✓ Format SQL

✓ Interpret results

---

# Final Summary

Notebook 21 introduced not only SQL syntax but also professional analytics practices required for:

- healthcare analytics
- BI engineering
- analytics engineering
- production SQL workflows

Good SQL is not only correct SQL.

Good SQL is:

```text
Readable

Maintainable

Reusable

Interpretable
```
