# Chapter 5 — End-to-End Model Lifecycle Overview

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 5

---

## 5.1 Purpose

This chapter provides a **high-level map** of the complete model lifecycle — from the identification of a business need through to retirement. It serves as the navigational backbone of the Guide and the primary reference for understanding the sequence of stages, stage gates, and key decision points.

For detailed requirements at each stage, see [Chapter 6 — Stage Requirements](06_stage_requirements/README.md).

---

## 5.2 The Model Lifecycle — Stages

The bank's model lifecycle consists of **ten stages**, organised in a logical sequence. While certain stages may occur iteratively (e.g., development and testing may cycle), the overall progression and stage gates must be respected.

```
┌─────────────────────────────────────────────────────────────────┐
│                   MODEL LIFECYCLE OVERVIEW                       │
├────────────────────────────────────────────────────────────────┤
│                                                                  │
│  1. INITIATION          Business need → Concept Note → Approval  │
│        │                                                         │
│        ▼ [Stage Gate: Approval to Develop]                       │
│                                                                  │
│  2. DATA SOURCING       Data inventory → Quality assessment →    │
│     & ASSESSMENT        Lineage documentation                    │
│        │                                                         │
│        ▼ [Stage Gate: Data Readiness Sign-off]                   │
│                                                                  │
│  3. DESIGN &            Methodology design → Development →       │
│     DEVELOPMENT         Code review → Initial QA                 │
│        │                                                         │
│        ▼ [Stage Gate: Development Complete]                      │
│                                                                  │
│  4. TESTING &           Performance testing → Stress testing →   │
│     DOCUMENTATION       Documentation completed                  │
│        │                                                         │
│        ▼ [Stage Gate: Documentation & Testing Complete]          │
│                                                                  │
│  5. INDEPENDENT         Scope → Challenge → Findings →           │
│     VALIDATION          Validation report → Closure              │
│        │                                                         │
│        ▼ [Stage Gate: Validation Passed / Conditional Approval]  │
│                                                                  │
│  6. APPROVAL &          Governance review → Risk committee →     │
│     GOVERNANCE          Formal approval                          │
│        │                                                         │
│        ▼ [Stage Gate: Formal Approval]                           │
│                                                                  │
│  7. DEPLOYMENT &        UAT → Implementation → Controls →        │
│     IMPLEMENTATION      Inventory update → Handover              │
│        │                                                         │
│        ▼ [Stage Gate: Go-Live Readiness]                         │
│                                                                  │
│  8. MONITORING &        Ongoing metrics → Triggers →             │
│     PERIODIC REVIEW     Annual / periodic review                 │
│        │                                                         │
│        ├──[Trigger: Material Change] ──► 9. CHANGE MANAGEMENT   │
│        │                                        │                │
│        │                                        ▼ (may loop back │
│        │                                     to stage 3, 4, 5)  │
│        │                                                         │
│        └──[Trigger: Retirement Decision] ► 10. RETIREMENT        │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## 5.3 Stage Summary Table

| Stage | Name | Key Input | Key Output | Stage Gate |
|-------|------|-----------|------------|------------|
| 1 | Initiation | Business need, use case | Model Concept Note, Tier assignment | Approval to develop |
| 2 | Data Sourcing & Assessment | Raw data sources | Data assessment report, data lineage | Data readiness sign-off |
| 3 | Design & Development | Approved concept, data | Model code, methodology doc, dev documentation | Development complete sign-off |
| 4 | Testing & Documentation | Developed model | Test results, complete documentation package | Documentation & testing complete |
| 5 | Independent Validation | Documentation package, model code | Validation report, findings log | Validation passed (or conditional) |
| 6 | Approval & Governance | Validation report | Formal approval record | Formal approval |
| 7 | Deployment & Implementation | Approved model | Deployed model, inventory update, monitoring plan | Go-live readiness sign-off |
| 8 | Monitoring & Periodic Review | Deployed model + data | Monitoring reports, review records | Ongoing — triggers escalation |
| 9 | Change Management | Change request | Assessed change, updated documentation | Proportionate to change materiality |
| 10 | Retirement & Archiving | Retirement trigger / decision | Retirement record, archived materials | Retirement approval |

---

## 5.4 Lifecycle Principles in Practice

The lifecycle is governed by three overarching structural principles:

### 5.4.1 Stage Gates Are Mandatory

No model may progress to the next stage without satisfying the exit criteria of the current stage. Stage gate decisions are documented and retained in the model's governance record.

For Tier 1 models, stage gate approvals require formal committee action. For Tier 2 and Tier 3, delegated authority may apply (see [Chapter 4 — Tier Requirements](04_model_classification_tiering.md)).

### 5.4.2 The Lifecycle Is Iterative, Not Purely Sequential

Development and testing may cycle (e.g., a failed test cycle returns to development). Monitoring may trigger change management, which in turn triggers re-validation and re-approval.

### 5.4.3 All Stages Are Documented

Every stage produces documented evidence. Documentation requirements by stage are detailed in [Chapter 8 — Required Artifacts](08_required_artifacts.md).

---

## 5.5 Simplified Lifecycle for Tier 3 Models

Tier 3 (lower-risk) models follow an abbreviated lifecycle:

```
Initiation → Development + Documentation → Peer Review → Owner Approval
     → Deployment → Annual Monitoring Review → Retirement
```

Even for Tier 3 models, a minimum documentation set is required and inventory registration is mandatory.

---

## 5.6 Lifecycle for Vendor / Third-Party Models

For models acquired externally:

- **Stage 1 (Initiation):** Business need and vendor assessment are required. Tier must be assigned.
- **Stages 2–4:** The bank must obtain sufficient vendor documentation to support validation. Where documentation is insufficient, compensating controls or enhanced monitoring are required.
- **Stage 5 (Validation):** Independent validation by the bank (or commissioned third party) is required for Tier 1 and Tier 2 vendor models.
- **Stages 6–10:** Same requirements as internally developed models.

<!-- TODO: Cross-reference with any vendor management / third-party risk policy. -->

---

## 5.7 Relationship Between Lifecycle Stages and Roles

Each stage has defined roles. Full role definitions and the RACI matrix are in:
- [Chapter 7 — Roles and Responsibilities](07_roles_responsibilities.md)
- [Appendix A — RACI Matrix](12_appendices/A_raci_matrix.md)

---

*Previous: [Chapter 4 — Model Classification and Risk Tiering](04_model_classification_tiering.md)*  
*Next: [Chapter 6 — Stage Requirements](06_stage_requirements/README.md)*
