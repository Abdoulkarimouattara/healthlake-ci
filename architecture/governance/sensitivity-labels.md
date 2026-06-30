# Data Classification & Sensitivity Labels

## Overview

Healthcare information contains varying levels of sensitivity.

HealthLake CI adopts a classification strategy to help protect confidential information while supporting secure data sharing and governance.

---

# Data Classification

| Classification      | Examples                                    |
| ------------------- | ------------------------------------------- |
| Public              | Hospital directory, department names        |
| Internal            | Operational KPIs, occupancy metrics         |
| Confidential        | Patient records, medical history            |
| Highly Confidential | Personal identifiers, clinical observations |

---

# Protection Strategy

Sensitive information is protected through:

* Sensitivity Labels.
* Role-Based Access Control.
* Row-Level Security.
* Governed Semantic Models.

---

# Governance Objectives

The classification framework helps the platform:

* Protect sensitive healthcare information.
* Support regulatory compliance.
* Promote responsible data sharing.
* Increase trust in analytical assets.

---

# Design Principle

Data protection begins with classification. Every analytical asset should be assigned an appropriate sensitivity level before being shared across the organization.
