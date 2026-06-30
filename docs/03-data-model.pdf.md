
---

## `docs/03-data-model.md`

```markdown
# HealthLake CI — Conceptual Data Model

## Objective

This document presents the conceptual data model used to represent the healthcare domain before technical implementation.

## Diagram

[Insert Draw.io MCD Diagram]

## Core Domains

| Domain | Main Entities |
|------|---------------|
| Healthcare Organization | Region, Hospital, Department, Room, Bed, Staff |
| Patient Care | Patient, Admission, Diagnosis, Treatment, Prescription, Discharge |
| Patient Monitoring | Equipment, Device Session, Vital Sign Reading, Clinical Alert |
| Emergency Operations | Emergency Visit, Triage, Waiting Time |
| Enterprise Analytics | KPIs, Occupancy, Performance, Alerts |

## Key Relationships

- A Region contains multiple Hospitals.
- A Hospital contains Departments, Rooms, Beds, Staff, and Equipment.
- A Patient can have multiple Admissions.
- An Admission can generate Diagnoses, Treatments, Prescriptions, and Discharge events.
- Medical Equipment can monitor Patients through Device Sessions.
- Vital Sign Readings can trigger Clinical Alerts.

## Design Goal

The model provides a business-first foundation for Lakehouse storage, Warehouse modeling, Real-Time Intelligence, and Power BI reporting.