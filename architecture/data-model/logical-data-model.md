# Logical Data Model

## Overview

The logical data model transforms the conceptual business model into a structured relational design.

It defines the entities, attributes, primary keys, and relationships that will serve as the foundation for the Lakehouse, Enterprise Data Warehouse, and analytical models.

---

# Master Data

## Region

| Attribute     | Type    |
| ------------- | ------- |
| RegionID (PK) | Integer |
| RegionCode    | String  |
| RegionName    | String  |

---

## Hospital

| Attribute       | Type    |
| --------------- | ------- |
| HospitalID (PK) | Integer |
| HospitalCode    | String  |
| HospitalName    | String  |
| HospitalType    | String  |
| RegionID (FK)   | Integer |
| Capacity        | Integer |
| Status          | String  |

---

## Department

| Attribute         | Type    |
| ----------------- | ------- |
| DepartmentID (PK) | Integer |
| HospitalID (FK)   | Integer |
| DepartmentName    | String  |
| DepartmentType    | String  |

---

## Room

| Attribute         | Type    |
| ----------------- | ------- |
| RoomID (PK)       | Integer |
| DepartmentID (FK) | Integer |
| RoomNumber        | String  |
| RoomType          | String  |

---

## Bed

| Attribute   | Type    |
| ----------- | ------- |
| BedID (PK)  | Integer |
| RoomID (FK) | Integer |
| BedNumber   | String  |
| Status      | String  |

---

## Staff

| Attribute         | Type    |
| ----------------- | ------- |
| StaffID (PK)      | Integer |
| HospitalID (FK)   | Integer |
| DepartmentID (FK) | Integer |
| FirstName         | String  |
| LastName          | String  |
| Role              | String  |

---

## Patient

| Attribute        | Type    |
| ---------------- | ------- |
| PatientID (PK)   | Integer |
| NationalHealthID | String  |
| FirstName        | String  |
| LastName         | String  |
| Gender           | String  |
| BirthDate        | Date    |
| BloodType        | String  |

---

## Medical Equipment

| Attribute         | Type    |
| ----------------- | ------- |
| EquipmentID (PK)  | Integer |
| HospitalID (FK)   | Integer |
| DepartmentID (FK) | Integer |
| EquipmentType     | String  |
| SerialNumber      | String  |
| Status            | String  |

---

# Transactional Data

## Admission

| Attribute         | Type     |
| ----------------- | -------- |
| AdmissionID (PK)  | Integer  |
| PatientID (FK)    | Integer  |
| HospitalID (FK)   | Integer  |
| DepartmentID (FK) | Integer  |
| RoomID (FK)       | Integer  |
| BedID (FK)        | Integer  |
| AdmissionDate     | DateTime |
| AdmissionType     | String   |
| Status            | String   |

---

## Diagnosis

| Attribute            | Type    |
| -------------------- | ------- |
| DiagnosisID (PK)     | Integer |
| AdmissionID (FK)     | Integer |
| DiagnosisCode        | String  |
| DiagnosisDescription | String  |

---

## Treatment

| Attribute        | Type     |
| ---------------- | -------- |
| TreatmentID (PK) | Integer  |
| AdmissionID (FK) | Integer  |
| StaffID (FK)     | Integer  |
| TreatmentName    | String   |
| TreatmentDate    | DateTime |

---

## Prescription

| Attribute           | Type    |
| ------------------- | ------- |
| PrescriptionID (PK) | Integer |
| AdmissionID (FK)    | Integer |
| MedicationName      | String  |
| Dosage              | String  |
| StartDate           | Date    |
| EndDate             | Date    |

---

## Discharge

| Attribute        | Type     |
| ---------------- | -------- |
| DischargeID (PK) | Integer  |
| AdmissionID (FK) | Integer  |
| DischargeDate    | DateTime |
| Outcome          | String   |

---

## Emergency Visit

| Attribute             | Type     |
| --------------------- | -------- |
| EmergencyVisitID (PK) | Integer  |
| PatientID (FK)        | Integer  |
| ArrivalTime           | DateTime |
| TriageLevel           | Integer  |
| WaitingTimeMinutes    | Integer  |

---

# Real-Time Monitoring

## Device Session

| Attribute        | Type     |
| ---------------- | -------- |
| SessionID (PK)   | Integer  |
| EquipmentID (FK) | Integer  |
| PatientID (FK)   | Integer  |
| StartTime        | DateTime |
| EndTime          | DateTime |

---

## Telemetry Event

| Attribute      | Type     |
| -------------- | -------- |
| EventID (PK)   | Integer  |
| SessionID (FK) | Integer  |
| EventTimestamp | DateTime |
| DeviceStatus   | String   |

---

## Vital Sign Reading

| Attribute              | Type     |
| ---------------------- | -------- |
| ReadingID (PK)         | Integer  |
| SessionID (FK)         | Integer  |
| ReadingTimestamp       | DateTime |
| HeartRate              | Integer  |
| OxygenSaturation       | Decimal  |
| BodyTemperature        | Decimal  |
| BloodPressureSystolic  | Integer  |
| BloodPressureDiastolic | Integer  |
| RespiratoryRate        | Integer  |

---

## Clinical Alert

| Attribute      | Type     |
| -------------- | -------- |
| AlertID (PK)   | Integer  |
| ReadingID (FK) | Integer  |
| AlertType      | String   |
| Severity       | String   |
| AlertTimestamp | DateTime |
| Status         | String   |

---

# Next Step

The logical model will be transformed into a dimensional Star Schema optimized for enterprise analytics and Power BI reporting.
