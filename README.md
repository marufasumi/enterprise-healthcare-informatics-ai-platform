# Data Engineering Module

## Purpose

This module contains the full Data Engineering pipeline for the Enterprise Healthcare Informatics AI Platform.

The pipeline uses Databricks, PySpark, Delta Lake, and FHIR R4 data to build a medallion architecture:

Raw FHIR JSON → Bronze → Silver → Gold

## Layers

### Bronze Layer
Raw FHIR resource ingestion from patient-level JSON bundles.

### Silver Layer
Cleaned and normalized healthcare tables.

### Gold Layer
Business-ready analytics and ML feature tables.

## Technology Stack

- Databricks
- PySpark
- Delta Lake
- Unity Catalog
- FHIR R4
- Medallion Architecture

## Main Outputs

### Bronze Tables
- patient_raw
- encounter_raw
- condition_raw
- observation_raw
- procedure_raw
- medication_request_raw
- immunization_raw
- careplan_raw
- allergy_intolerance_raw
- claim_raw

### Silver Tables
- patient_clean
- encounter_clean
- condition_clean
- observation_clean
- procedure_clean
- medication_request_clean
- immunization_clean
- careplan_clean
- allergy_intolerance_clean
- claim_clean

### Gold Tables
- patient_summary
- encounter_utilization_summary
- chronic_disease_summary
- medication_summary
- observation_vitals_labs_summary
- procedure_careplan_summary
- claim_cost_summary
- population_health_dashboard

## Dataset Scale

Final processed dataset:

- 555 patients
- 27,812 encounters
- 17,253 conditions
- 131,703 observations
- 38,528 procedures
- 24,256 medication requests
- 8,100 immunizations
- 1,831 care plans
- 499 allergy records
- 52,068 claims

## Project Status

Data Engineering pipeline completed through Gold analytics layer.ß