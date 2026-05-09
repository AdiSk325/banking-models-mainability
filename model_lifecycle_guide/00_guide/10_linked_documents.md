# Chapter 10 — Links to Supporting Standards, Procedures and Templates

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 10

---

## 10.1 Purpose

This chapter provides the **master reference map** linking this Guide to all supporting documents. This is a key element of the Guide's function as a framework ("constitution") — it establishes the authoritative document ecosystem and avoids duplicating content that is better maintained in subordinate documents.

---

## 10.2 Document Hierarchy Reminder

```
Level 1 — Policy:      Model Risk Management Policy
Level 2 — Guide:       ← This document
Level 3 — Standards:   Detailed rules and minimum requirements
Level 4 — Procedures:  Step-by-step operational instructions
Level 5 — Templates:   Forms, checklists, structured documents
```

---

## 10.3 Supporting Standards (Level 3)

| Code | Title | Content | Applies to Stage(s) |
|------|-------|---------|---------------------|
| [STD-001](../01_supporting_standards/STD-001_model_development_standard.md) | Model Development Standard | Coding standards, reproducibility requirements, testing criteria, feature engineering rules | 6.3, 6.4 |
| [STD-002](../01_supporting_standards/STD-002_model_documentation_standard.md) | Model Documentation Standard | Required documentation sections, minimum content, quality criteria | 6.3, 6.4 |
| [STD-003](../01_supporting_standards/STD-003_validation_standard.md) | Validation Standard | Validation scope, independence, methodology, depth by tier | 6.5, 6.9 |
| [STD-004](../01_supporting_standards/STD-004_monitoring_standard.md) | Monitoring Standard | Metrics, thresholds, frequency, reporting, triggers | 6.8 |
| [STD-005](../01_supporting_standards/STD-005_change_management_standard.md) | Change Management Standard | Change classification, materiality thresholds, versioning | 6.9 |
| [STD-006](../01_supporting_standards/STD-006_deployment_standard.md) | Deployment Standard | Environment segregation, version control, access management, MLOps requirements | 6.7 |
| [STD-007](../01_supporting_standards/STD-007_data_quality_standard.md) | Data Quality Standard | Data assessment criteria, lineage documentation, quality gates | 6.2 |
| [STD-008](../01_supporting_standards/STD-008_ai_ml_explainability_standard.md) | AI/ML Explainability Standard | Explainability requirements by tier, methods, regulatory considerations | 6.3, 6.4 |

---

## 10.4 Procedures (Level 4)

| Code | Title | Content | Applies to Stage(s) |
|------|-------|---------|---------------------|
| [PROC-001](../02_procedures/PROC-001_model_initiation_procedure.md) | Model Initiation Procedure | Step-by-step process for model concept note and approval to develop | 6.1 |
| [PROC-002](../02_procedures/PROC-002_validation_procedure.md) | Validation Procedure | How to conduct and document independent validation | 6.5, 6.9 |
| [PROC-003](../02_procedures/PROC-003_model_inventory_procedure.md) | Model Inventory Procedure | How to register, update, and retire model inventory entries | All stages |
| [PROC-004](../02_procedures/PROC-004_change_request_procedure.md) | Change Request Procedure | How to submit, assess, and approve model changes | 6.9 |
| [PROC-005](../02_procedures/PROC-005_retirement_procedure.md) | Retirement Procedure | Steps to decommission and archive a model | 6.10 |
| [PROC-006](../02_procedures/PROC-006_exception_management_procedure.md) | Exception Management Procedure | How to request, approve, and track exceptions | Any stage |

---

## 10.5 Templates (Level 5)

| Code | Title | Content | Used at Stage(s) |
|------|-------|---------|-----------------|
| [TMPL-001](../03_templates/TMPL-001_model_development_document.md) | Model Development Document | Full template for model development documentation | 6.1 (concept), 6.3, 6.4 |
| [TMPL-002](../03_templates/TMPL-002_validation_report.md) | Validation Report | Structured template for independent validation report | 6.5 |
| [TMPL-003](../03_templates/TMPL-003_monitoring_plan.md) | Monitoring Plan | Plan template with metrics, thresholds, and reporting | 6.7 (before go-live) |
| [TMPL-004](../03_templates/TMPL-004_change_request_form.md) | Change Request Form | Structured form for model change requests | 6.9 |
| [TMPL-005](../03_templates/TMPL-005_retirement_form.md) | Retirement Form | Retirement decision and archive documentation | 6.10 |
| [TMPL-006](../03_templates/TMPL-006_release_readiness_checklist.md) | Release Readiness Checklist | Pre-deployment sign-off checklist | 6.7 |

---

## 10.6 External Regulatory References

| Source | Document | Relevance |
|--------|----------|-----------|
| Federal Reserve / OCC | SR 11-7 Guidance on Model Risk Management | Foundational MRM framework; validation, governance, monitoring |
| OCC | OCC Bulletin 2011-12 | Complementary to SR 11-7 |
| EBA | Guidelines on Model Risk Management (EBA/GL/2023/xx) | EU regulatory expectations for banks |
| ECB | Guide to Internal Models | IRB and internal model governance |
| Basel Committee | BCBS 239 (Risk Data Aggregation) | Data quality and risk reporting |
| ISO/IEC | TR 24028:2020 (AI Trustworthiness) | AI governance and risk management |

See [04_references/01_regulatory_guidance.md](../04_references/01_regulatory_guidance.md) for full reference list.

---

## 10.7 Document Maintenance

All linked documents are owned by the MRM function unless otherwise specified. Changes to linked documents that materially affect the requirements of this Guide must be reviewed by the Guide owner (MRM) and may trigger a revision of this Guide.

---

*Previous: [Chapter 9 — Controls, Exceptions and Escalation](09_controls_exceptions_escalation.md)*  
*Next: [Chapter 11 — Review Cycle of This Guide](11_review_cycle.md)*
