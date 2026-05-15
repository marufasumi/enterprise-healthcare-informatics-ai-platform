# SQL Cheatsheet — Notebook 21

## Purpose

This document summarizes all SQL concepts learned in:

```text
21_sql_population_health_analytics
```

Use this file for:

- interview preparation
- SQL revision
- healthcare analytics projects
- dashboard development
- Databricks SQL review

---

# SQL Query Structure (Execution Order)

Understand SQL execution order.

SQL is written:

```sql
SELECT
FROM
WHERE
GROUP BY
HAVING
ORDER BY
LIMIT
```

But executes approximately as:

```text
FROM

↓

WHERE

↓

GROUP BY

↓

HAVING

↓

SELECT

↓

ORDER BY

↓

LIMIT
```

Interview question:

> What is SQL execution order?

---

# 1. SELECT

Purpose:

Choose columns.

Syntax:

```sql
SELECT column_name
FROM table;
```

Example:

```sql
SELECT
patient_id,
age

FROM healthcare_catalog.gold.patient_summary;
```

---

# 2. SELECT *

Purpose:

Return all columns.

Syntax:

```sql
SELECT *
FROM table;
```

Best practice:

Avoid in production.

---

# 3. LIMIT

Purpose:

Return first N rows.

Syntax:

```sql
LIMIT 10
```

Example:

```sql
SELECT *
FROM table
LIMIT 10;
```

---

# 4. WHERE

Purpose:

Filter rows.

Syntax:

```sql
WHERE condition
```

Example:

```sql
WHERE age > 65
```

---

# AND

All conditions must be true.

Example:

```sql
WHERE age > 65

AND gender='female'
```

---

# OR

At least one condition true.

Example:

```sql
WHERE risk='High'

OR risk='Medium'
```

---

# 5. ORDER BY

Purpose:

Sort rows.

Ascending:

```sql
ORDER BY age ASC
```

Descending:

```sql
ORDER BY cost DESC
```

---

# 6. Aggregate Functions

---

## COUNT()

Purpose:

Count rows.

Example:

```sql
COUNT(*)
```

or:

```sql
COUNT(column)
```

Difference:

| Function | Meaning |
|----------|----------|
| COUNT(*) | all rows |
| COUNT(column) | non-null rows |

---

## SUM()

Purpose:

Total.

Example:

```sql
SUM(total_claim_cost)
```

---

## AVG()

Purpose:

Average.

Example:

```sql
AVG(age)
```

---

## MIN()

Purpose:

Smallest value.

Example:

```sql
MIN(age)
```

---

## MAX()

Purpose:

Largest value.

Example:

```sql
MAX(age)
```

---

# 7. CAST()

Purpose:

Change datatype.

Example:

```sql
CAST(

AVG(age)

AS DECIMAL(10,2)

)
```

Result:

```text
46.19
```

instead of:

```text
46.185585...
```

---

# 8. DISTINCT

Purpose:

Unique values.

Example:

```sql
SELECT DISTINCT risk_category
FROM table;
```

---

# 9. GROUP BY

Purpose:

Aggregate within groups.

Example:

```sql
GROUP BY risk_category
```

---

Business question:

```text
How many patients per risk category?
```

---

# 10. HAVING

Purpose:

Filter grouped results.

Example:

```sql
GROUP BY gender

HAVING COUNT(*) > 100
```

---

Difference:

| WHERE | HAVING |
|-------|---------|
| filters rows | filters groups |

---

# 11. CASE WHEN

Purpose:

Create categories.

Example:

```sql
CASE

WHEN age <18

THEN 'Pediatric'

WHEN age <65

THEN 'Adult'

ELSE 'Senior'

END
```

---

# 12. IS NULL

Purpose:

Find missing values.

Example:

```sql
WHERE avg_glucose IS NULL
```

---

# IS NOT NULL

Purpose:

Find available values.

Example:

```sql
WHERE avg_glucose IS NOT NULL
```

---

# 13. INNER JOIN

Purpose:

Keep matching rows.

Syntax:

```sql
INNER JOIN table2

ON table1.id=table2.id
```

---

# 14. LEFT JOIN

Purpose:

Keep all left table rows.

Example:

```sql
LEFT JOIN
```

Used to detect missing relationships.

---

# 15. Subquery

Purpose:

Query inside query.

Example:

```sql
WHERE cost >

(

SELECT AVG(cost)

FROM table

)
```

---

# 16. Scalar Subquery

Returns:

```text
one value only
```

Examples:

```sql
AVG()

MAX()

COUNT()
```

---

# 17. CTE (WITH)

Purpose:

Readable SQL.

Example:

```sql
WITH average_cost AS

(
SELECT AVG(cost)

FROM table
)
```

---

# 18. VIEW

Purpose:

Reusable SQL logic.

Example:

```sql
CREATE VIEW high_cost_patients AS

SELECT ...
```

---

# 19. Window Functions

---

## ROW_NUMBER()

Purpose:

Unique ranking.

Example:

```sql
ROW_NUMBER()

OVER(

ORDER BY cost DESC

)
```

Output:

```text
1

2

3
```

---

## RANK()

Purpose:

Allow ties.

Output:

```text
1

1

3
```

---

## DENSE_RANK()

Purpose:

Allow ties without gaps.

Output:

```text
1

1

2
```

---

# 20. PARTITION BY

Purpose:

Group window calculations.

Example:

```sql
ROW_NUMBER()

OVER(

PARTITION BY gender

ORDER BY cost DESC

)
```

Meaning:

Rank inside each gender.

---

# Most Important Interview Questions

---

Q:

Difference between WHERE and HAVING?

Answer:

```text
WHERE filters rows.

HAVING filters aggregated groups.
```

---

Q:

Difference between INNER JOIN and LEFT JOIN?

Answer:

```text
INNER JOIN keeps matches only.

LEFT JOIN keeps all rows from left table.
```

---

Q:

Difference between COUNT(*) and COUNT(column)?

Answer:

```text
COUNT(*) counts all rows.

COUNT(column) ignores NULLs.
```

---

Q:

Difference between ROW_NUMBER(), RANK(), DENSE_RANK()?

Answer:

```text
ROW_NUMBER:

1,2,3

RANK:

1,1,3

DENSE_RANK:

1,1,2
```

---

Q:

What does PARTITION BY do?

Answer:

```text
Divides rows into groups and applies window functions separately.
```

---

# SQL Topics Learned in Notebook 21

Completed:

✓ SELECT

✓ WHERE

✓ ORDER BY

✓ COUNT

✓ AVG

✓ GROUP BY

✓ CASE WHEN

✓ JOIN

✓ Subquery

✓ CTE

✓ VIEW

✓ Window Functions

✓ PARTITION BY

---

# SQL Skill Level After Notebook 21

Approximate level:

```text
Strong Intermediate SQL

+

Early Advanced SQL
```

---

# Final Summary

Notebook 21 built SQL skills required for:

- healthcare analytics
- BI analyst roles
- data analyst interviews
- analytics engineering
- population health projects
- dashboard development
