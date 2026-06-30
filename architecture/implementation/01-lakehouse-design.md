# Lakehouse Design

## Overview

The Lakehouse is the central storage layer of HealthLake CI.

It stores all operational healthcare data using the Medallion Architecture, providing a governed foundation for historical analytics while supporting downstream Warehouse and Real-Time Intelligence workloads.

---

# Medallion Architecture

The platform organizes healthcare data into three logical layers.

| Layer | Purpose |
|--------|---------|
| Bronze | Raw operational data |
| Silver | Cleaned and standardized healthcare data |
| Gold | Curated analytical datasets |

---

# Design Principles

- Preserve raw source data.
- Separate ingestion from transformation.
- Improve data quality progressively.
- Publish reusable analytical datasets.
- Maintain a single source of truth.

---

# Business Value

The Lakehouse provides trusted historical healthcare data for enterprise analytics while supporting future scalability.