# Warehouse Star Schema

## Overview

The Enterprise Data Warehouse organizes curated Gold data products into a dimensional model optimized for analytical workloads.

The model follows the **Star Schema** design pattern, separating business events (facts) from descriptive business entities (dimensions).

This approach improves query performance, simplifies reporting, and provides a consistent analytical foundation for the Semantic Model and Power BI.

---

# Warehouse Architecture

Silver Layer

↓

Gold Data Products (Notebook)

↓

Warehouse

↓

Semantic Model

↓

Power BI

---

# Design Principles

- Star Schema
- Single Source of Truth
- Business-Oriented Modeling
- High Query Performance
- Reusable Dimensions
- Optimized for Analytics

---

# Dimensions

## dim_date

### Business Purpose

Provide a reusable calendar dimension shared across all fact tables.

### Attributes

- DateKey
- Date
- Year
- Quarter
- Month
- MonthNumber
- WeekOfYear
- Day
- DayOfWeek
- IsWeekend

---

## dim_patient

### Business Purpose

Store patient demographic information.

### Attributes

- PatientKey
- PatientID
- Gender
- AgeGroup
- BloodType
- City

---

## dim_hospital

### Business Purpose

Describe hospitals within the healthcare network.

### Attributes

- HospitalKey
- HospitalID
- HospitalName
- HospitalType
- Capacity
- CapacityCategory
- Region

---

## dim_department

### Business Purpose

Describe hospital departments.

### Attributes

- DepartmentKey
- DepartmentID
- DepartmentName
- DepartmentType

---

## dim_equipment

### Business Purpose

Describe medical monitoring equipment.

### Attributes

- EquipmentKey
- EquipmentID
- EquipmentType
- Manufacturer
- IsOperational

---

## dim_diagnosis

### Business Purpose

Standardize diagnosis classifications.

### Attributes

- DiagnosisKey
- DiagnosisCode
- DiagnosisDescription

---

## dim_treatment

### Business Purpose

Describe treatments performed during patient care.

### Attributes

- TreatmentKey
- TreatmentName
- Category

---

# Fact Tables

## fact_admissions

### Grain

One record per patient admission.

### Measures

- LengthOfStay
- TreatmentCount
- PrescriptionCount

### Dimensions

- dim_date
- dim_patient
- dim_hospital
- dim_department
- dim_diagnosis
- dim_treatment

---

## fact_emergency

### Grain

One record per emergency visit.

### Measures

- WaitingTimeMinutes

### Dimensions

- dim_date
- dim_patient
- dim_hospital
- dim_department

---

## fact_patient_monitoring

### Grain

One record per vital sign reading.

### Measures

- HeartRate
- OxygenSaturation
- BodyTemperature
- RespiratoryRate
- CriticalFlag

### Dimensions

- dim_date
- dim_patient
- dim_equipment
- dim_hospital

---

# Relationships

dim_date
    ├── fact_admissions
    ├── fact_emergency
    └── fact_patient_monitoring

dim_patient
    ├── fact_admissions
    ├── fact_emergency
    └── fact_patient_monitoring

dim_hospital
    ├── fact_admissions
    ├── fact_emergency
    └── fact_patient_monitoring

dim_department
    ├── fact_admissions
    └── fact_emergency

dim_equipment
    └── fact_patient_monitoring

dim_diagnosis
    └── fact_admissions

dim_treatment
    └── fact_admissions

---

# Expected Benefits

- Simplified analytical queries
- Consistent business definitions
- Optimized Power BI performance
- Reusable dimensions across reports
- Scalable enterprise analytics

