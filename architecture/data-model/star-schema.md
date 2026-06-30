# Star Schema Design

## Overview

The Enterprise Data Warehouse is designed using dimensional modeling to support scalable, high-performance analytics.

Business events are stored in fact tables, while descriptive business entities are organized into reusable dimension tables. This approach simplifies reporting, improves query performance, and ensures consistent business definitions across the analytics platform.

---

# Design Principles

The warehouse follows several core principles:

* Business-oriented dimensional modeling.
* Reusable dimensions across analytical domains.
* Optimized analytical performance.
* Consistent business definitions.
* Support for enterprise reporting and Semantic Models.

---

# Dimension Tables

| Dimension     | Description                     |
| ------------- | ------------------------------- |
| DimDate       | Calendar and time analysis      |
| DimHospital   | Healthcare facilities           |
| DimRegion     | Administrative regions          |
| DimDepartment | Hospital departments            |
| DimRoom       | Patient rooms                   |
| DimBed        | Hospital beds                   |
| DimPatient    | Patient demographic information |
| DimStaff      | Doctors and nurses              |
| DimEquipment  | Medical monitoring devices      |

---

# Fact Tables

## FactAdmissions

Business event representing every patient admission.

### Measures

* Admission Count
* Length of Stay
* Admission Duration

---

## FactVitalSigns

Business event capturing patient monitoring measurements.

### Measures

* Heart Rate
* Oxygen Saturation
* Body Temperature
* Blood Pressure
* Respiratory Rate

---

## FactEmergencyVisits

Business event describing emergency department activity.

### Measures

* Waiting Time
* Visit Count
* Triage Level

---

## FactBedOccupancy

Business event measuring hospital capacity utilization.

### Measures

* Occupied Beds
* Available Beds
* Occupancy Rate

---

## FactHospitalPerformance

Business event supporting executive reporting.

### Measures

* Daily Admissions
* Daily Discharges
* Average Length of Stay
* Critical Patient Count
* Equipment Utilization Rate

---

# Analytical Model

The warehouse supports multiple analytical perspectives through shared dimensions.

```text
                    DimDate
                       │
                       │
      ┌────────────────┼────────────────┐
      │                │                │
DimHospital     DimDepartment     DimPatient
      │                │                │
      └──────── FactAdmissions ─────────┘
                       │
                  DimBed
```

```text
                    DimDate
                       │
                       │
                 FactVitalSigns
                ┌───────────────┐
                │               │
          DimPatient     DimEquipment
                │               │
                └──── DimHospital
```

---

# Semantic Model

The Star Schema serves as the foundation for the Microsoft Fabric Semantic Model.

The Semantic Model exposes trusted business metrics, relationships, and KPIs while hiding warehouse complexity from report developers and business users.

---

# Business Value

This dimensional model enables:

* Executive healthcare dashboards.
* Hospital performance benchmarking.
* Operational KPI reporting.
* Patient flow analysis.
* Real-time and historical analytics.
* Consistent enterprise reporting across all healthcare organizations.

---

# Next Step

The Star Schema will be implemented in the Microsoft Fabric Warehouse and exposed through a centralized Semantic Model for Power BI reporting.
