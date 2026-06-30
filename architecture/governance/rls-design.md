# Row-Level Security Design

## Overview

Row-Level Security (RLS) ensures that users only access data relevant to their organizational responsibilities.

Rather than creating multiple datasets, a single governed Semantic Model serves all users while dynamically filtering data according to their assigned role.

---

# Security Hierarchy

```text
Ministry of Health
        │
        ▼
Regional Health Directorate
        │
        ▼
Hospital
        │
        ▼
Department
        │
        ▼
Clinical Staff
```

---

# Access Matrix

| User Role                   | Visible Data                     |
| --------------------------- | -------------------------------- |
| Ministry of Health          | All hospitals                    |
| Regional Health Directorate | Hospitals within assigned region |
| Hospital Director           | Assigned hospital                |
| Department Manager          | Assigned department              |
| Doctor                      | Assigned patients                |
| Nurse                       | Assigned department and patients |

---

# Business Benefits

* Single Semantic Model.
* Simplified report maintenance.
* Consistent security rules.
* Reduced data duplication.
* Secure multi-level reporting.

---

# Design Principle

Security follows the organizational hierarchy, ensuring that analytical visibility always reflects business responsibilities.
