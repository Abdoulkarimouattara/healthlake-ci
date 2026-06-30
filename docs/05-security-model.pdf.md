# HealthLake CI — Security Model

## Objective

This document defines the governance and security model for the healthcare intelligence platform.

## Security Hierarchy

[Insert Draw.io Security Model Diagram]

```text
Ministry of Health
        ↓
Regional Health Directorate
        ↓
Hospital Management
        ↓
Department Manager
        ↓
Doctor / Nurse

## Access Matrix

| Role                 | Access Scope                     |
| -------------------- | -------------------------------- |
| Ministry of Health   | National data                    |
| Regional Directorate | Assigned region                  |
| Hospital Director    | Assigned hospital                |
| Department Manager   | Assigned department              |
| Doctor               | Assigned patients                |
| Nurse                | Assigned department and patients |


Security Controls
Workspace access management
Row-Level Security
Sensitivity Labels
Semantic Model security
Data classification
Least privilege access
Design Principle

Security follows the healthcare organizational hierarchy to ensure that every user sees only the data required for their responsibility.