# Source Systems

## Overview

HealthLake CI integrates data from multiple operational systems commonly found in modern healthcare organizations.

Each source contributes a specific type of information to the analytics platform.

---

# Operational Systems

| Source System              | Data Produced                   |
| -------------------------- | ------------------------------- |
| Hospital Management System | Admissions, Rooms, Beds         |
| Electronic Medical Records | Patients, Diagnoses, Treatments |
| Human Resources System     | Doctors, Nurses, Staff          |
| Pharmacy System            | Prescriptions, Medications      |
| Medical Equipment          | Device Inventory                |
| Connected Medical Devices  | Real-Time Vital Signs           |

---

# Data Categories

The platform ingests three categories of data.

### Master Data

* Hospitals
* Departments
* Rooms
* Staff
* Medical Equipment

### Transactional Data

* Admissions
* Treatments
* Prescriptions
* Emergency Visits

### Streaming Data

* Heart Rate
* Blood Pressure
* Oxygen Saturation
* Body Temperature
* Respiratory Rate

---

## Architecture Principle

All operational systems contribute data to a unified Microsoft Fabric platform where information is standardized, governed, and transformed into trusted analytical assets.
