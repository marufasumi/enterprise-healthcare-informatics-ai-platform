# Enterprise Healthcare Informatics AI Platform

## Overview

This project is a portfolio-grade enterprise healthcare analytics and clinical AI platform built using:

- Databricks
- PySpark
- Delta Lake
- FHIR R4 healthcare data
- SQL analytics
- Power BI
- Machine Learning
- MLOps architecture

The platform follows a Medallion Lakehouse Architecture:

FHIR JSON → Bronze → Silver → Gold

---

# Project Modules

## 1. Data Engineering

Enterprise healthcare lakehouse pipeline built using:
- Databricks
- Spark
- Delta Lake
- FHIR resources
- Bronze/Silver/Gold architecture

### Key Features

- scalable FHIR ingestion
- healthcare ETL pipelines
- patient-level feature engineering
- healthcare cost analytics
- population health analytics
- enterprise Gold dashboard layer

---

## 2. Analytics / BI

Healthcare business intelligence layer using:
- SQL analytics
- Power BI dashboards
- operational KPIs
- utilization analytics
- chronic disease reporting
- financial analytics

---

## 3. Machine Learning

Clinical AI and predictive modeling layer:
- risk stratification
- chronic disease prediction
- healthcare cost prediction
- patient risk scoring
- MLflow
- model serving
- MLOps

---

# Architecture

```text
FHIR JSON Files
        ↓
Bronze Layer
(raw healthcare resources)
        ↓
Silver Layer
(clean normalized healthcare tables)
        ↓
Gold Layer
(business analytics + ML feature store)


# Architecture Overview

![Architecture Overview](images/de_architecture.png)
