# Stage 6.9 — Change Management

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 6.9

---

## Purpose

Models evolve. As business conditions, data, and regulatory requirements change, models must be updated. The Change Management stage governs how model changes are assessed, approved, documented, and implemented in a controlled manner that preserves the integrity of the governance record and ensures that risks introduced by changes are appropriately managed.

---

## Entry Criteria

A model change is triggered by one of:
- A decision by the Model Owner or developer to update the model.
- A finding from monitoring that requires corrective action.
- A regulatory or supervisory requirement.
- A business or product change that affects the model's intended use.
- A periodic review recommendation.

---

## Change Classification

All model changes must be classified before implementation. Classification determines the level of governance required.

| Class | Description | Examples |
|-------|-------------|---------|
| **Material Change** | Change that significantly affects model methodology, inputs, outputs, or risk profile | New methodology, significant recalibration, new feature set, change in target variable |
| **Non-Material Change** | Minor update with no significant impact on model outputs or risk | Bug fix with no output impact, documentation update, infrastructure migration with identical outputs |
| **Emergency Change** | Urgent change required to prevent harm; expedited governance applies | Data feed failure requiring temporary override; critical production defect |

Materiality thresholds are defined in [STD-005 — Change Management Standard](../../01_supporting_standards/STD-005_change_management_standard.md).

> **When in doubt, treat the change as material.** Classification disputes are resolved by MRM.

---

## Key Activities

### For Material Changes

1. **Raise a Change Request** — use [TMPL-004](../../03_templates/TMPL-004_change_request_form.md).
2. **Classify the change** — confirm materiality with MRM.
3. **Impact assessment** — assess the effect of the change on model outputs, performance, and risk.
4. **Re-development / recalibration** — implement the change following Development standards.
5. **Re-testing** — conduct appropriate tests proportionate to the scope of the change.
6. **Re-documentation** — update all affected documentation sections; update version log.
7. **Revalidation** — material changes require independent re-validation (partial or full per scope of change).
8. **Re-approval** — obtain formal approval through appropriate governance channel.
9. **Re-deployment** — deploy per Stage 6.7 controls; update model inventory.

### For Non-Material Changes

1. **Raise a Change Request** — document the change and rationale.
2. **Classification confirmation** — MRM confirms non-materiality.
3. **Update documentation** — update version log and affected documentation sections.
4. **Model Owner sign-off** — model owner confirms and approves.
5. **Update model inventory** — record the change.

---

## Versioning Requirements

All models must maintain a **version history** in the model documentation and model inventory:
- Version number (semantic versioning recommended: MAJOR.MINOR.PATCH).
- Description of change.
- Classification (material / non-material).
- Date of change.
- Approval reference.
- Responsible developer.

---

## Roles

| Role | Responsibility |
|------|---------------|
| Data Scientist / Developer | Raises change request; implements change |
| Model Owner | Accountable; approves non-material changes; supports material change process |
| MRM | Classifies changes; oversees material change governance |
| Independent Validator | Conducts revalidation for material changes |
| Governance Forum | Approves material changes (per tier) |

---

## Required Outputs / Artifacts

| Artifact | Material | Non-Material |
|----------|----------|-------------|
| Change Request Form | ✅ Required | ✅ Required |
| Impact Assessment | ✅ Required | 🟡 Summary |
| Updated documentation / version log | ✅ Required | ✅ Required |
| Re-testing results | ✅ Required | 🟡 If applicable |
| Revalidation Report | ✅ Required | — |
| Re-approval Record | ✅ Required | ✅ Owner sign-off |
| Updated inventory entry | ✅ Required | ✅ Required |

---

## Linked Documents

| Document | Type | Reference |
|----------|------|-----------|
| Change Management Standard | Standard | [STD-005](../../01_supporting_standards/STD-005_change_management_standard.md) |
| Change Request Procedure | Procedure | [PROC-004](../../02_procedures/PROC-004_change_request_procedure.md) |
| Change Request Form | Template | [TMPL-004](../../03_templates/TMPL-004_change_request_form.md) |
| Validation Standard | Standard | [STD-003](../../01_supporting_standards/STD-003_validation_standard.md) |

---

*Previous: [Stage 6.8 — Monitoring and Periodic Review](08_monitoring_periodic_review.md)*  
*Next: [Stage 6.10 — Retirement and Archiving](10_retirement_archiving.md)*
