# STD-005 — Change Management Standard

> **Status: PLACEHOLDER — content to be completed**  
> **Document type:** Standard (Level 3)  
> **Parent document:** [Model Lifecycle Guide](../00_guide/README.md)  
> **Applies to lifecycle stages:** 6.9 (Change Management)  
> **Owner:** Model Risk Management

---

## Purpose

This standard defines **materiality thresholds, change classification criteria, and versioning requirements** for model changes. It implements Principle 8 (Controlled Change) from the Model Lifecycle Guide.

---

## Contents to Be Developed

<!-- TODO: Draft detailed provisions. Align with SR 11-7 guidance on model changes. -->

### 1. Change Classification Framework

#### Material Change — Definition and Examples
A change is material if it:
- Alters the model's methodology, algorithm, or underlying approach.
- Changes the target variable or prediction objective.
- Adds or removes significant input features.
- Leads to a change in model outputs beyond defined thresholds (e.g., >X% shift in mean score for Tier 1).
- Affects the model's use case or applicability scope.
- Is triggered by significant performance deterioration.

#### Non-Material Change — Definition and Examples
A change is non-material if it:
- Corrects a bug with no impact on model outputs.
- Updates documentation without changing the model.
- Migrates infrastructure without changing the model version.
- Updates monitoring thresholds (within defined guardrails).

### 2. Materiality Thresholds
<!-- TODO: Define quantitative thresholds per model type and tier. -->
- Output distribution shift thresholds by model type.
- Performance change thresholds by metric.
- Feature set change criteria.

### 3. Change Governance by Classification

| Change Type | Re-testing | Revalidation | Re-approval |
|-------------|-----------|--------------|-------------|
| Material | ✅ Required | ✅ Required | ✅ Required |
| Non-material | 🟡 If applicable | — | ✅ Owner sign-off |
| Emergency | Expedited | Expedited / retrospective | Expedited |

### 4. Emergency Change Protocol
- Definition of emergency.
- Expedited governance process.
- Retrospective documentation requirements.

### 5. Versioning Requirements
- Version numbering convention (MAJOR.MINOR.PATCH).
- What constitutes each version type.
- Where version history is maintained.

### 6. Audit Trail Requirements
- What must be recorded for each change.
- Retention requirements.

---

## Cross-References

| Document | Relationship |
|----------|-------------|
| [Model Lifecycle Guide — Stage 6.9](../00_guide/06_stage_requirements/09_change_management.md) | Parent framework |
| [PROC-004 — Change Request Procedure](../02_procedures/PROC-004_change_request_procedure.md) | Procedural implementation |
| [TMPL-004 — Change Request Form](../03_templates/TMPL-004_change_request_form.md) | Template |
| [STD-003 — Validation Standard](STD-003_validation_standard.md) | Revalidation requirements |
