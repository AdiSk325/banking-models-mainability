# Appendix A — RACI Matrix

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Appendix A

---

## Overview

This RACI matrix shows the responsibility of each role across each lifecycle stage.

**Legend:**
- **R** — Responsible (does the work)
- **A** — Accountable (ultimately answerable; one per activity)
- **C** — Consulted (provides input; two-way communication)
- **I** — Informed (notified of outcomes; one-way communication)

---

## RACI Matrix

| Stage | Data Scientist / Developer | Model Owner | Independent Validator | MRM | IT / MLOps | Data Steward | Compliance | Governance Committee |
|-------|---------------------------|-------------|----------------------|-----|-----------|--------------|------------|---------------------|
| **6.1 Initiation** | R | A | — | C | — | C | C | I (Tier 1) |
| **6.2 Data Sourcing** | R | A | — | C | — | R/C | C | — |
| **6.3 Design & Development** | R | A | — | C (Tier 1) | C | — | — | — |
| **6.4 Testing & Documentation** | R | A | — | C | — | — | — | — |
| **6.5 Independent Validation** | C | A | R | A/C | — | — | C | I |
| **6.6 Approval & Governance** | C | A | C | R (facilitates) | — | — | C | A/R |
| **6.7 Deployment** | C | A | — | I | R | — | — | I |
| **6.8 Monitoring & Review** | R (MLOps/DS) | A | — | C | R | — | — | I |
| **6.9 Change Management** | R | A | R (material) | C/A | C | — | C | A (material) |
| **6.10 Retirement** | C | A | — | A | R | — | C | I |

---

## Notes

- For Tier 3 models, governance committee involvement is replaced by Model Owner approval.
- "MRM" in stage 6.6 facilitates the governance process; the Governance Committee holds final accountability for approval decisions.
- Data Steward accountability varies by institution; adjust to reflect actual data governance structure.

<!-- TODO: Validate this matrix with all relevant functions before finalising. -->

---

*Back to: [Appendices](README.md) | [Chapter 7 — Roles](../07_roles_responsibilities.md)*
