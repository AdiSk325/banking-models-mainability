# Model Lifecycle Guide — Authoring Roadmap

> **Purpose:** Track completion status of every section, standard, procedure, and template in this documentation framework.  
> **Update frequency:** After each working session.  
> **Legend:** ✅ Done | 🔄 In Progress | 📋 Planned | ⛔ Blocked

---

## 00 — Main Guide Chapters

| # | File | Status | Owner | Notes |
|---|------|--------|-------|-------|
| 1 | `01_purpose_scope_audience.md` | 📋 Planned | — | Define model definition, scope, applicability, exclusions |
| 2 | `02_definitions.md` | 📋 Planned | — | Key terms: model, model risk, tier, owner, validator, etc. |
| 3 | `03_guiding_principles.md` | 📋 Planned | — | 10–12 principles: risk-based, proportionality, reproducibility, etc. |
| 4 | `04_model_classification_tiering.md` | 📋 Planned | — | Tiering criteria, risk matrix, tier-based requirements |
| 5 | `05_lifecycle_overview.md` | 📋 Planned | — | End-to-end map; stage-gate diagram in Mermaid |
| 6 | `07_roles_responsibilities.md` | 📋 Planned | — | All roles defined; link to RACI in appendix |
| 7 | `08_required_artifacts.md` | 📋 Planned | — | Minimum artifact table per tier |
| 8 | `09_controls_exceptions_escalation.md` | 📋 Planned | — | Governance forums, approval gates, exception process |
| 9 | `10_linked_documents.md` | 📋 Planned | — | Map of all linked standards, procedures, templates |
| 10 | `11_review_cycle.md` | 📋 Planned | — | Guide's own review, ownership, version control |

---

## 06 — Stage Requirements (One File per Lifecycle Stage)

| Stage | File | Status | Owner | Notes |
|-------|------|--------|-------|-------|
| 1 | `01_initiation.md` | 📋 Planned | — | Business need, model concept note, approval to develop |
| 2 | `02_data_sourcing_assessment.md` | 📋 Planned | — | Data inventory, quality assessment, lineage |
| 3 | `03_design_development.md` | 📋 Planned | — | Methodology, assumptions, feature engineering, code |
| 4 | `04_testing_documentation.md` | 📋 Planned | — | Testing criteria, model documentation requirements |
| 5 | `05_independent_validation.md` | 📋 Planned | — | Validation scope, independence, findings closure |
| 6 | `06_approval_governance.md` | 📋 Planned | — | Governance committees, approval criteria, conditions |
| 7 | `07_deployment_implementation.md` | 📋 Planned | — | Deployment controls, UAT, rollback, inventory |
| 8 | `08_monitoring_periodic_review.md` | 📋 Planned | — | KPIs, drift, thresholds, trigger events, periodic review |
| 9 | `09_change_management.md` | 📋 Planned | — | Change classification, materiality, re-validation triggers |
| 10 | `10_retirement_archiving.md` | 📋 Planned | — | Retirement decision, archival requirements, audit trail |

---

## 12 — Appendices

| # | File | Status | Owner | Notes |
|---|------|--------|-------|-------|
| A | `A_raci_matrix.md` | 📋 Planned | — | RACI table: roles × lifecycle stages |
| B | `B_model_inventory_schema.md` | 📋 Planned | — | Required fields for model inventory entry |
| C | `C_glossary.md` | 📋 Planned | — | Full glossary of terms used in the guide |

---

## 01 — Supporting Standards

| Code | Document | Status | Owner | Notes |
|------|----------|--------|-------|-------|
| STD-001 | Model Development Standard | 📋 Planned | — | Coding standards, reproducibility, feature engineering |
| STD-002 | Model Documentation Standard | 📋 Planned | — | Required sections, detail level, templates cross-ref |
| STD-003 | Validation Standard | 📋 Planned | — | Scope, methodology, independence rules |
| STD-004 | Monitoring Standard | 📋 Planned | — | Metrics, thresholds, frequency, reporting |
| STD-005 | Change Management Standard | 📋 Planned | — | Change classification, version control |
| STD-006 | Deployment Standard | 📋 Planned | — | MLOps controls, environment segregation |
| STD-007 | Data Quality Standard | 📋 Planned | — | Data assessment, lineage, quality gates |
| STD-008 | AI/ML Explainability Standard | 📋 Planned | — | Explainability requirements by tier |

---

## 02 — Procedures / SOPs

| Code | Document | Status | Owner | Notes |
|------|----------|--------|-------|-------|
| PROC-001 | Model Initiation Procedure | 📋 Planned | — | Step-by-step for model concept note and approval |
| PROC-002 | Validation Procedure | 📋 Planned | — | How validation is conducted and documented |
| PROC-003 | Model Inventory Procedure | 📋 Planned | — | How to register, update, and retire model inventory entries |
| PROC-004 | Change Request Procedure | 📋 Planned | — | How to submit and approve model changes |
| PROC-005 | Retirement Procedure | 📋 Planned | — | Steps to decommission and archive a model |
| PROC-006 | Exception Management Procedure | 📋 Planned | — | How to request, approve, and track exceptions |

---

## 03 — Templates

| Code | Document | Status | Owner | Notes |
|------|----------|--------|-------|-------|
| TMPL-001 | Model Development Document | 📋 Planned | — | Full template for development documentation |
| TMPL-002 | Validation Report | 📋 Planned | — | Structured template for independent validation |
| TMPL-003 | Monitoring Plan | 📋 Planned | — | Plan template: metrics, thresholds, owners, freq |
| TMPL-004 | Change Request Form | 📋 Planned | — | Form for requesting and documenting model changes |
| TMPL-005 | Retirement Form | 📋 Planned | — | Retirement decision documentation |
| TMPL-006 | Release Readiness Checklist | 📋 Planned | — | Pre-deployment gate checklist |

---

## 04 — References

| File | Status | Notes |
|------|--------|-------|
| `01_regulatory_guidance.md` | ✅ Seeded | SR 11-7, OCC 2011-12, EBA GL, ECB Guide |
| `02_supervisory_expectations.md` | ✅ Seeded | KNF, EBA, ECB supervisory expectations |
| `03_international_standards.md` | ✅ Seeded | ISO/IEC TR 24028, ISO 31000, BCBS |
| `04_industry_practices.md` | ✅ Seeded | MLOps, MRM maturity models, FMEA |
| `05_consulting_materials.md` | ✅ Seeded | Big4, BCG, McKinsey, Moody's |
| `06_internal_inspiration.md` | ✅ Seeded | Placeholders for internal examples |

---

## 05 — Working Notes

| File | Status | Notes |
|------|--------|-------|
| `drafting_notes.md` | 🔄 Active | Open drafting notes and decisions |
| `open_questions.md` | 🔄 Active | Questions to resolve before finalizing |

---

## Overall Progress

```
Main Guide Chapters:        0 / 10  ░░░░░░░░░░  0%
Stage Requirements:         0 / 10  ░░░░░░░░░░  0%
Appendices:                 0 /  3  ░░░░░░░░░░  0%
Supporting Standards:       0 /  8  ░░░░░░░░░░  0%
Procedures:                 0 /  6  ░░░░░░░░░░  0%
Templates:                  0 /  6  ░░░░░░░░░░  0%
References:                 6 /  6  ██████████  100% (seeded)
```

---

*Update this file after each working session.*
