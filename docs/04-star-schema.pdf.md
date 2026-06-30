# HealthLake CI — Star Schema Design

## Objective

This document describes the enterprise analytical model used for reporting and semantic modeling.

## Diagram

[Insert Draw.io Star Schema Diagram]

## Dimension Tables

| Dimension | Purpose |
|----------|---------|
| DimDate | Calendar analysis |
| DimRegion | Regional reporting |
| DimHospital | Hospital-level analytics |
| DimDepartment | Department-level analysis |
| DimRoom | Room-level analysis |
| DimBed | Bed occupancy analysis |
| DimPatient | Patient demographics |
| DimStaff | Doctors and nurses |
| DimEquipment | Medical equipment analytics |

## Fact Tables

| Fact Table | Purpose |
|-----------|---------|
| FactAdmissions | Patient admission analysis |
| FactVitalSigns | Vital sign monitoring |
| FactEmergencyVisits | Emergency department activity |
| FactBedOccupancy | Capacity and occupancy reporting |
| FactHospitalPerformance | Executive healthcare KPIs |

## Business Value

The Star Schema simplifies analytics, improves reporting performance, and provides a trusted foundation for the Semantic Model and Power BI dashboards.