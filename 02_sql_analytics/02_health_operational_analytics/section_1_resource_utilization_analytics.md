# Section 1: Resource Utilization Analytics

Notebook:

`22_sql_healthcare_operations_analytics`

Status:

Completed ✅

---

# Overview

This section analyzes healthcare resource consumption patterns across patient populations.

The goal is to identify:

- High utilization populations
- Operational burden drivers
- Resource-intensive patient groups
- Relationships between risk, age, chronic disease burden, and healthcare utilization

Resource utilization is a major component of:

- Population Health Management
- Healthcare Operations
- Care Coordination
- Utilization Management
- Hospital Capacity Planning
- Value-Based Care

---

# Input Table

Primary Gold Layer Table:

```text
healthcare_catalog.gold.population_health_dashboard
```

Contains:

- demographics
- encounters
- chronic disease burden
- risk categories
- utilization metrics
- claims cost
- medications
- observations

---

# Business Questions

This section answers:

1. Do high-risk patients consume more healthcare resources?

2. Which age groups generate highest utilization?

3. Does chronic disease burden increase utilization?

4. Who are the highest healthcare utilizers?

---

# Analyses Performed

---

## Query 1.1

### Risk Category vs Resource Utilization

Objective:

Determine whether higher-risk populations consume more healthcare resources.

Metrics:

- average encounters
- emergency encounters
- inpatient encounters

### Key Findings

| Risk Group | Avg Encounters | Avg Emergency | Avg Inpatient |
|------------|----------------|---------------|---------------|
| High Risk | 122 | 5.86 | 6.38 |
| Medium Risk | 53.13 | 1.70 | 0.84 |
| Low Risk | 24.87 | 0.73 | 0.05 |

### Insight

High-risk populations consume approximately 5x more healthcare encounters than low-risk populations.

Implication:

High-risk groups drive operational burden.

---

## Query 1.2

### Age Group vs Resource Utilization

Objective:

Analyze utilization patterns across age groups.

Age categories:

- Pediatric
- Adult
- Senior

### Findings

| Age Group | Avg Encounters | Avg Emergency | Avg Inpatient |
|-----------|----------------|---------------|---------------|
| Senior | 88.84 | 3.13 | 2.94 |
| Adult | 42.10 | 1.61 | 0.87 |
| Pediatric | 18.24 | 0.68 | 0.01 |

### Insight

Healthcare utilization increases significantly with age.

Senior populations create disproportionate utilization burden.

---

## Query 1.3

### Chronic Disease Burden vs Utilization

Objective:

Evaluate impact of multimorbidity on healthcare utilization.

### Findings

Patients with:

0 chronic diseases:

Average encounters:

21.54

Patients with:

6 chronic diseases:

Average encounters:

415.50

### Insight

Multimorbidity strongly increases:

- encounters
- emergency use
- inpatient burden

---

## Query 1.4

### High Utilizer Identification

Objective:

Identify patients with extreme healthcare utilization.

Metrics analyzed:

- total encounters
- chronic disease burden
- risk level
- claim cost

### Major Findings

Top utilizers showed:

- High Risk status
- Advanced age
- Multiple chronic diseases
- Very high claim costs

Example:

```text
705 encounters
↓
$13.5M claim cost
```

### Insight

A small population drives disproportionate healthcare workload.

This follows:

80/20 utilization principle

---

# Overall Findings

Resource utilization is concentrated among:

✓ High-risk populations

✓ Senior populations

✓ Multimorbidity populations

✓ High-cost patients

These groups generate substantial operational burden.

---

# Healthcare Operations Insights

Potential interventions:

- Care coordination programs
- Chronic disease management
- Preventive outreach
- Population health management
- Utilization reduction programs

---

# Executive Summary

This analysis demonstrates that healthcare utilization is highly concentrated among small high-risk populations.

Targeting these groups may improve:

- resource allocation
- hospital workload
- cost reduction
- patient outcomes

---

# SQL Concepts Used

This section practiced:

```sql
SELECT

GROUP BY

AVG()

COUNT()

MIN()

MAX()

ORDER BY

CASE WHEN

LIMIT
```

---

# Interview Topics Covered

Healthcare analytics interviews may ask:

- How do you identify high utilizers?
- What populations drive hospital burden?
- How does multimorbidity affect utilization?
- How would you reduce operational burden?

This section provides examples to answer those questions.

---

# Outputs Generated

Resource utilization KPIs

Operational burden metrics

High-utilizer rankings

Population segmentation insights

---

Status:

Section Complete ✅
