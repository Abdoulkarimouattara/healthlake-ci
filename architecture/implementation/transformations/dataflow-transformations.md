# Dataflow Transformations

## Overview

This document describes the transformations implemented in Dataflow Gen2 to convert Bronze tables into trusted Silver datasets.

The Silver layer improves data quality, standardizes business entities, and enriches operational data with reusable business attributes.

---

# Standard Transformations

The following transformations are applied whenever applicable:

| Transformation          | Purpose                                      |
| ----------------------- | -------------------------------------------- |
| Set Data Types          | Convert columns to appropriate data types    |
| Remove Duplicates       | Eliminate duplicate records                  |
| Trim Text               | Remove leading and trailing spaces           |
| Clean Text              | Remove non-printable characters              |
| Standardize Text Values | Ensure consistent formatting across datasets |
| Data Quality Rules      | Remove invalid or incomplete records         |

---

# Business Transformations

| Silver Table | New Column | Business Purpose | Status |
|--------------|------------|------------------|--------|
| silver_hospitals | CapacityCategory | Classify hospitals by operational capacity for reporting and benchmarking. | ✅ Implemented |
| silver_staff | YearsOfService | Measure employee experience and workforce seniority. | ✅ Implemented |
| silver_patients | Age | Calculate patient age for demographic analysis. | ✅ Implemented |
| silver_patients | AgeGroup | Group patients into meaningful age segments. | ✅ Implemented |
| silver_medical_equipment | IsOperational | Identify operational medical equipment. | ✅ Implemented |
| silver_admissions | AdmissionYear | Support yearly trend analysis. | ✅ Implemented |
| silver_admissions | AdmissionQuarter | Support quarterly reporting. | ✅ Implemented |
| silver_admissions | AdmissionMonth | Support monthly reporting. | ✅ Implemented |
| silver_admissions | AdmissionMonthNumber | Ensure chronological month sorting. | ✅ Implemented |
| silver_admissions | AdmissionWeek | Support weekly operational analysis. | ✅ Implemented |
| silver_admissions | AdmissionDay | Support daily reporting. | ✅ Implemented |
| silver_admissions | AdmissionDayOfWeek | Analyze admissions by weekday. | ✅ Implemented |
| silver_admissions | AdmissionHour | Analyze peak admission hours. | ✅ Implemented |
| silver_diagnoses | DiagnosisCode Standardization | Ensure consistent diagnosis coding for clinical analytics. | ✅ Implemented |
| silver_treatments | TreatmentName Standardization | Ensure consistent treatment categories for clinical activity analysis. | ✅ Implemented |
| silver_prescriptions | PrescriptionDuration | Measure medication prescription duration. | ✅ Implemented |
| silver_discharges | DischargeYear | Enable yearly discharge reporting. | ✅ Implemented |
| silver_discharges | DischargeQuarter | Support quarterly discharge analysis. | ✅ Implemented |
| silver_discharges | DischargeMonth | Enable monthly discharge reporting. | ✅ Implemented |
| silver_discharges | DischargeMonthNumber | Ensure chronological month sorting. | ✅ Implemented |
| silver_discharges | DischargeWeek | Analyze weekly discharge trends. | ✅ Implemented |
| silver_discharges | DischargeDay | Support daily discharge analysis. | ✅ Implemented |
| silver_discharges | DischargeDayOfWeek | Analyze discharge patterns by weekday. | ✅ Implemented |
| silver_discharges | DischargeHour | Analyze discharge activity by hour. | ✅ Implemented |
| silver_emergency_visits | ArrivalDate | Support daily emergency activity reporting. | ✅ Implemented |
| silver_emergency_visits | ArrivalHour | Analyze emergency arrival patterns by hour. | ✅ Implemented |
| silver_emergency_visits | ArrivalDayOfWeek | Analyze emergency visits by weekday. | ✅ Implemented |
| silver_emergency_visits | WaitTimeCategory | Categorize emergency waiting times for operational monitoring. | ✅ Implemented |
| silver_emergency_visits | TriageCategory | Translate triage levels into business-readable emergency categories. | ✅ Implemented |
| gold_patient_journey | LengthOfStay | Measure hospitalization duration using admission and discharge dates. | ⏳ Planned |
| silver_device_sessions | SessionDurationHours | Measure monitoring session duration. | ⏳ Planned |
| silver_vital_sign_readings | HeartRateCategory | Categorize heart rate measurements. | ⏳ Planned |
| silver_vital_sign_readings | OxygenCategory | Categorize oxygen saturation levels. | ⏳ Planned |
| silver_vital_sign_readings | TemperatureCategory | Categorize body temperature measurements. | ⏳ Planned |
| silver_vital_sign_readings | ReadingDate | Enable daily trend analysis. | ⏳ Planned |
| silver_vital_sign_readings | ReadingHour | Enable hourly monitoring analysis. | ⏳ Planned |
| silver_vital_sign_readings | IsCritical | Flag clinically critical vital sign readings. | ⏳ Planned |

---

# Design Principle

Business logic is implemented once in the Silver layer and reused across the Warehouse, Semantic Model, Real-Time Intelligence, and Power BI reports. This approach ensures consistency, simplifies maintenance, and promotes trusted enterprise analytics.
