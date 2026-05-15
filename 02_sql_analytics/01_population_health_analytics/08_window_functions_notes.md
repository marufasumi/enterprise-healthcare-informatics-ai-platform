# SQL Window Functions Notes — Notebook 21

## Purpose

This document summarizes advanced SQL Window Functions learned in:

```text
21_sql_population_health_analytics
```

Window functions are among the most important SQL concepts for:

- SQL interviews
- analytics engineering
- healthcare analytics
- BI roles
- data analyst roles
- enterprise reporting

---

# What Are Window Functions?

Window functions perform calculations across rows while preserving individual row details.

This is VERY important.

---

## GROUP BY

Aggregates rows.

Example:

| Risk Category | Count |
|---------------|------:|
| High Risk | 77 |

Patient details disappear.

---

## Window Functions

Keep rows.

Example:

| Patient | Cost | Rank |
|---------|-----:|-----:|
| A | 1M | 1 |
| B | 900K | 2 |

Rows remain.

---

# Basic Window Function Structure

General syntax:

```sql
WINDOW_FUNCTION()

OVER(

PARTITION BY column

ORDER BY column

)
```

Components:

---

## WINDOW_FUNCTION()

Examples:

```sql
ROW_NUMBER()

RANK()

DENSE_RANK()

SUM()

AVG()
```

---

## OVER()

Defines:

```text
How the calculation window operates
```

Required for window functions.

---

## ORDER BY

Defines ranking order.

Example:

```sql
ORDER BY total_claim_cost DESC
```

---

## PARTITION BY

Divides data into groups.

Example:

```sql
PARTITION BY gender
```

---

# Window Functions Learned

Notebook 21 covered:

✓ ROW_NUMBER()

✓ RANK()

✓ DENSE_RANK()

✓ PARTITION BY

---

# 1. ROW_NUMBER()

Purpose:

Assign unique sequential ranks.

Syntax:

```sql
ROW_NUMBER()

OVER(

ORDER BY cost DESC

)
```

Example:

| Cost | Rank |
|-----:|-----:|
| 100 | 1 |
| 90 | 2 |
| 80 | 3 |

---

## Characteristics

ROW_NUMBER():

```text
Always unique

Never ties
```

Output:

```text
1

2

3

4
```

---

## Healthcare Example

Question:

```text
Who are highest-cost patients?
```

Used:

```sql
ROW_NUMBER()
```

---

# 2. RANK()

Purpose:

Allow ties.

Syntax:

```sql
RANK()

OVER(

ORDER BY cost DESC

)
```

Example:

| Cost | Rank |
|-----:|-----:|
| 100 | 1 |
| 100 | 1 |
| 90 | 3 |

Notice:

```text
Rank 2 disappears
```

---

## Characteristics

RANK():

```text
Allows ties

Skips rankings
```

Output:

```text
1

1

3
```

---

## Healthcare Example

Used when:

Patients share equal:

- spending
- risk score
- utilization

---

# 3. DENSE_RANK()

Purpose:

Allow ties without gaps.

Syntax:

```sql
DENSE_RANK()

OVER(

ORDER BY cost DESC

)
```

Example:

| Cost | Rank |
|-----:|-----:|
| 100 | 1 |
| 100 | 1 |
| 90 | 2 |

---

## Characteristics

DENSE_RANK():

```text
Allows ties

No skipped rankings
```

Output:

```text
1

1

2
```

---

# Comparison Table (IMPORTANT)

Memorize this table.

| Cost | ROW_NUMBER | RANK | DENSE_RANK |
|-----:|-----------:|-----:|------------:|
| 100 | 1 | 1 | 1 |
| 100 | 2 | 1 | 1 |
| 90 | 3 | 3 | 2 |
| 80 | 4 | 4 | 3 |

---

# Quick Memory Trick

---

## ROW_NUMBER

Think:

```text
Unique IDs
```

---

## RANK

Think:

```text
Competition ranking

1

1

3
```

---

## DENSE_RANK

Think:

```text
Continuous ranking

1

1

2
```

---

# 4. PARTITION BY

Purpose:

Create separate ranking groups.

Syntax:

```sql
ROW_NUMBER()

OVER(

PARTITION BY gender

ORDER BY cost DESC

)
```

---

# Without PARTITION BY

Global ranking:

| Patient | Gender | Rank |
|---------|--------|-----:|
| A | F | 1 |
| B | M | 2 |

---

# With PARTITION BY

Separate ranking:

Female:

| Rank |
|----:|
| 1 |
| 2 |

Male:

| Rank |
|----:|
| 1 |
| 2 |

Ranking restarts.

---

# Healthcare Example

Question answered:

```text
Who are highest-cost patients

within each gender?
```

---

# Real Healthcare Uses

Window functions support:

---

## Population Health

Rank:

- highest-risk patients
- expensive populations

---

## Financial Analytics

Rank:

- top spenders
- costly claims

---

## Utilization Analytics

Rank:

- highest utilizers
- encounter burden

---

## Clinical Analytics

Rank:

- disease burden
- medication burden

---

# Enterprise Uses

Window functions commonly used for:

---

## Deduplication

Example:

Keep latest patient record.

---

## Running Totals

Example:

Cumulative spending.

---

## Percentiles

Example:

Top 5% spenders.

---

## Dashboard Rankings

Example:

Top patients.

---

# Most Important Interview Questions

---

## Question:

Difference between GROUP BY and window functions?

Answer:

```text
GROUP BY aggregates rows.

Window functions preserve rows while performing calculations.
```

---

## Question:

Difference between ROW_NUMBER and RANK?

Answer:

```text
ROW_NUMBER:

Unique ranks

RANK:

Allows ties and skips rankings
```

---

## Question:

Difference between RANK and DENSE_RANK?

Answer:

```text
RANK skips rankings.

DENSE_RANK keeps rankings continuous.
```

---

## Question:

What does PARTITION BY do?

Answer:

```text
PARTITION BY divides rows into groups and applies window calculations separately.
```

---

## Question:

Why are window functions important?

Answer:

```text
Window functions enable ranking, comparisons, running totals, and advanced analytics while preserving row-level detail.
```

---

# SQL Interview Importance

Window functions are among the most commonly tested advanced SQL topics.

Expected knowledge for:

✓ BI Analyst

✓ Healthcare Analyst

✓ Analytics Engineer

✓ Data Analyst

✓ Data Engineer

---

# Final Summary

Notebook 21 introduced advanced SQL ranking concepts required for:

- healthcare analytics
- dashboard reporting
- enterprise SQL
- population health analytics
- technical interviews

Window functions are foundational for advanced analytics workflows.
