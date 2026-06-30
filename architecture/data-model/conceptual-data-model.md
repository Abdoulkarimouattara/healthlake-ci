# Conceptual Data Model

## Overview

The conceptual data model defines the core business entities and their relationships independently of any technology or database implementation.

Its objective is to establish a common understanding of the healthcare domain before designing the Lakehouse, Warehouse, and analytical models.

---

# Business Domains

The platform is organized around five business domains.

| Domain                  | Description                                  |
| ----------------------- | -------------------------------------------- |
| Healthcare Organization | Hospital structure and operational resources |
| Patient Care            | Complete patient journey                     |
| Patient Monitoring      | Real-time monitoring of connected patients   |
| Emergency Operations    | Emergency department activities              |
| Enterprise Analytics    | Business KPIs and strategic reporting        |

---

# Core Business Entities

## Healthcare Organization

* Region
* Hospital
* Department
* Room
* Bed
* Medical Equipment
* Staff

---

## Patient Care

* Patient
* Admission
* Diagnosis
* Treatment
* Prescription
* Discharge

---

## Patient Monitoring

* Medical Device
* Telemetry
* Vital Sign
* Clinical Alert

---

## Emergency Operations

* Emergency Visit
* Triage

---

# Business Relationships

```text
Region
   │
   └── Hospital
          │
          ├── Department
          │      │
          │      ├── Room
          │      │      │
          │      │      └── Bed
          │      │
          │      └── Medical Equipment
          │
          └── Staff
                 │
                 ▼
Patient
    │
    ├── Admission
    │
    ├── Diagnosis
    │
    ├── Treatment
    │
    ├── Prescription
    │
    ├── Discharge
    │
    └── Vital Sign
            │
            ▼
      Clinical Alert
```

---

# Modeling Principles

The conceptual model follows several design principles:

* Represent the healthcare business before the technology.
* Separate organizational, operational, and monitoring domains.
* Establish clear business ownership for every entity.
* Create a foundation for scalable analytical models.
* Support both historical and real-time analytics.

---

# Next Step

The conceptual model will be transformed into a logical data model defining attributes, primary keys, foreign keys, and relationships required for implementation within Microsoft Fabric.
