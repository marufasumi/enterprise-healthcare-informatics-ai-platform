# Healthcare Data Quality Rules

# Patient Rules

| Rule | Description |
|---|---|
| patient_id_not_null | patient_id must exist |
| valid_gender | gender values standardized |
| valid_birth_date | birth date must be valid |

---

# Encounter Rules

| Rule | Description |
|---|---|
| unique_encounter_id | encounter IDs unique |
| patient_link_required | encounter linked to patient |
| valid_encounter_dates | encounter timestamps valid |

---

# Condition Rules

| Rule | Description |
|---|---|
| diagnosis_required | diagnosis must exist |
| patient_link_required | condition linked to patient |

---

# Observation Rules

| Rule | Description |
|---|---|
| numeric_observation_values | numeric labs/vitals required |
| valid_observation_dates | timestamps valid |

---

# Procedure Rules

| Rule | Description |
|---|---|
| procedure_description_required | procedure description required |
| patient_link_required | procedure linked to patient |

---

# Medication Rules

| Rule | Description |
|---|---|
| medication_name_required | medication description required |
| patient_link_required | medication linked to patient |

---

# Immunization Rules

| Rule | Description |
|---|---|
| vaccine_name_required | vaccine name required |
| patient_link_required | immunization linked to patient |

---

# CarePlan Rules

| Rule | Description |
|---|---|
| careplan_status_required | status required |
| patient_link_required | careplan linked to patient |

---

# Allergy Rules

| Rule | Description |
|---|---|
| allergy_description_required | allergy description required |
| patient_link_required | allergy linked to patient |

---

# Claim Rules

| Rule | Description |
|---|---|
| claim_cost_numeric | claim amount numeric |
| claim_type_required | institutional/pharmacy required |
| patient_link_required | claim linked to patient |

---

# Enterprise Data Quality Goals

- healthcare data consistency
- downstream analytics reliability
- ML feature quality
- operational reporting stability
- patient linkage integrity
