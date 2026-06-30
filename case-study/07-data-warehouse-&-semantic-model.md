# 07 — Data Warehouse & Semantic Model

| Document Information |                                           |
| -------------------- | ----------------------------------------- |
| **Project**          | HealthLake CI                             |
| **Solution**         | National Healthcare Intelligence Platform |
| **Document**         | Data Warehouse & Semantic Model           |
| **Version**          | 1.0                                       |
| **Author**           | Aboudoul Karim OUATTARA                   |
| **Last Updated**     | June 2026                                 |

---

# Executive Summary

Operational data is rarely optimized for analytics. To support reliable reporting and executive decision-making, HealthLake CI introduces an enterprise Data Warehouse based on dimensional modeling.

The warehouse transforms curated healthcare data into business-oriented models that are then exposed through a centralized Semantic Model for consistent reporting across the organization.

---

# Enterprise Data Model

The analytical layer is designed using a **Star Schema**, separating measurable business events from descriptive business entities.

### Core Components

| Table Type           | Purpose                                                                |
| -------------------- | ---------------------------------------------------------------------- |
| **Fact Tables**      | Store measurable healthcare events and operational metrics.            |
| **Dimension Tables** | Describe hospitals, patients, departments, rooms, equipment, and time. |

This design simplifies analytical queries while improving reporting performance.

---

# Semantic Model

The Semantic Model provides a governed business layer between the warehouse and reporting tools.

### Responsibilities

* Centralize business relationships.
* Expose trusted KPIs.
* Deliver consistent business definitions.
* Simplify dashboard development.

Business users interact with a single, trusted analytical model rather than raw warehouse tables.

---

# Business Value

This architecture enables healthcare organizations to:

* Analyze hospital performance.
* Monitor patient activity.
* Evaluate resource utilization.
* Compare operational KPIs across hospitals.
* Support strategic planning through trusted analytics.

The combination of a dimensional warehouse and a Semantic Model ensures that every report is built on consistent, reusable, and business-ready data.

---

**Previous Document ←** `06-real-time-intelligence.md`

**Next Document →** `08-governance-security.md`
