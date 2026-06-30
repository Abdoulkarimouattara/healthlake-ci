# Security Model

## Overview

HealthLake CI follows a role-based security model designed to protect sensitive healthcare information while providing each user with the level of access required for their responsibilities.

Security is implemented as a core architectural principle rather than an afterthought.

---

# Security Objectives

The platform is designed to:

* Protect sensitive healthcare information.
* Restrict access based on business responsibilities.
* Support secure analytics across multiple hospitals.
* Ensure consistent access policies across Microsoft Fabric workloads.

---

# Security Architecture

```text
Identity
     │
     ▼
Role Assignment
     │
     ▼
Workspace Permissions
     │
     ▼
Semantic Model Security
     │
     ▼
Power BI Dashboards
```

---

# Security Layers

| Layer              | Purpose                             |
| ------------------ | ----------------------------------- |
| Workspace Security | Control access to Fabric workspaces |
| Data Security      | Protect analytical datasets         |
| Semantic Security  | Secure business metrics             |
| Dashboard Security | Restrict report visibility          |

---

# Design Principle

Security is applied consistently across every layer of the analytics platform to ensure that sensitive healthcare data remains protected while enabling trusted decision-making.
