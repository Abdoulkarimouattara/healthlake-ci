# Gold Data Products

## Overview

The Gold layer contains curated business-ready data products built from trusted Silver datasets.

Unlike the Silver layer, which focuses on data quality and standardization, the Gold layer delivers aggregated and enriched datasets optimized for executive reporting, operational dashboards, advanced analytics, and real-time monitoring.

Each Gold table is designed around a specific business domain and consumer.

---

# Gold Architecture

Silver Tables

↓

Business Logic (PySpark)

↓

Gold Data Products

↓

Warehouse

↓

Semantic Model

↓

Power BI

---

# Gold Data Products

## 1. gold_hospital_performance

### Business Objective

Provide operational KPIs for hospitals and healthcare administrators.

### Source Tables

- silver_hospitals
- silver_admissions
- silver_discharges
- silver_emergency_visits

### Business Logic

Aggregate hospital activity by hospital and reporting period.

### KPIs

- Total Admissions
- Total Discharges
- Emergency Visits
- Average Waiting Time
- Average Length of Stay
- Hospital Capacity
- Capacity Category

### Consumers

- Ministry of Health
- Hospital Directors
- Regional Managers

---

## 2. gold_patient_journey

### Business Objective

Build a complete patient journey from admission to discharge.

### Source Tables

- silver_patients
- silver_admissions
- silver_diagnoses
- silver_treatments
- silver_prescriptions
- silver_discharges

### Business Logic

Join all clinical events related to the same patient admission.

### Business Metrics

- Length of Stay
- Diagnosis Count
- Treatment Count
- Prescription Count

### Consumers

- Physicians
- Clinical Managers
- Healthcare Analysts

---

## 3. gold_emergency_operations

### Business Objective

Analyze Emergency Department performance.

### Source Tables

- silver_emergency_visits
- silver_hospitals
- silver_departments

### KPIs

- Emergency Visits
- Average Waiting Time
- Visits by Hour
- Visits by Day
- Triage Distribution

### Consumers

- Emergency Department Managers
- Hospital Directors

---

## 4. gold_equipment_monitoring

### Business Objective

Monitor medical equipment utilization.

### Source Tables

- silver_medical_equipment
- silver_device_sessions

### KPIs

- Active Devices
- Monitoring Hours
- Utilization Rate
- Operational Devices

### Consumers

- Biomedical Engineering
- Hospital Operations

---

## 5. gold_patient_monitoring

### Business Objective

Provide aggregated patient monitoring indicators.

### Source Tables

- silver_vital_sign_readings

### KPIs

- Average Heart Rate
- Average Oxygen Saturation
- Average Temperature
- Critical Readings
- Fever Cases

### Consumers

- Intensive Care Units
- Physicians
- Clinical Supervisors

---

## 6. gold_executive_summary

### Business Objective

Provide a consolidated executive view of the healthcare network.

### Source Tables

- gold_hospital_performance
- gold_patient_journey
- gold_emergency_operations
- gold_equipment_monitoring
- gold_patient_monitoring

### KPIs

- Total Patients
- Total Admissions
- Average Length of Stay
- Emergency Activity
- Equipment Utilization
- Critical Patients

### Consumers

- Executive Leadership
- Ministry of Health