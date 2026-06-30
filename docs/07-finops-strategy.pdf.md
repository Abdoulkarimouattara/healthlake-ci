# HealthLake CI — FinOps Strategy

## Objective

This document defines the cost optimization strategy for HealthLake CI.

## FinOps Principles

- Use each Fabric workload for its most appropriate purpose.
- Avoid unnecessary data duplication.
- Separate real-time workloads from historical analytics.
- Reuse Semantic Models across multiple reports.
- Optimize storage and compute based on usage patterns.

## Workload Optimization

| Workload | Cost Strategy |
|---------|---------------|
| Lakehouse | Store historical data efficiently |
| Warehouse | Use dimensional models for reporting workloads |
| Eventhouse | Store real-time events for operational analytics |
| Eventstream | Use only for streaming ingestion |
| Semantic Model | Reuse centralized KPIs |
| Power BI | Avoid duplicated datasets and reports |

## Cost Control Practices

- Archive historical raw data when appropriate
- Monitor refresh frequency
- Limit unnecessary real-time processing
- Use incremental processing where possible
- Separate development, test, and production workloads

## Business Value

FinOps ensures that the platform can scale across hospitals while keeping operational costs controlled and aligned with business value.