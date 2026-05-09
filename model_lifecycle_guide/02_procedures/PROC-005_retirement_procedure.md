# PROC-005 — Retirement Procedure

> **Status: PLACEHOLDER — content to be completed**  
> **Document type:** Procedure (Level 4)  
> **Parent:** [Model Lifecycle Guide — Stage 6.10](../00_guide/06_stage_requirements/10_retirement_archiving.md)  
> **Owner:** Model Risk Management

---

## Purpose

This procedure provides step-by-step instructions for the controlled decommissioning and archiving of models.

---

## Steps to Be Documented

<!-- TODO: Write detailed step-by-step procedure. -->

### Step 1 — Identify Retirement Trigger
- Types of trigger (replacement, discontinuation, performance, regulatory).
- Who may initiate retirement.

### Step 2 — Prepare Retirement Decision Document
- Complete [TMPL-005 — Retirement Form](../03_templates/TMPL-005_retirement_form.md).
- Required content: reason, impact assessment, transition plan.

### Step 3 — Impact Assessment
- Identify all users and downstream systems.
- Identify any active regulatory obligations tied to the model.
- Assess data retention and deletion requirements (GDPR).

### Step 4 — Transition Plan (if model is being replaced)
- Parallel run requirements.
- Cutover date and communication plan.
- Training for users of the replacement model.

### Step 5 — Obtain Retirement Approval
- Who approves retirement (Model Owner + MRM; Tier 1 may require committee).
- Record approval.

### Step 6 — Decommission from Production
- IT/MLOps steps to remove from production.
- System update requirements.
- Access revocation.

### Step 7 — Archive Artefacts
- What must be archived (code, documentation, validation reports, approvals, monitoring history).
- Archive location and naming convention.
- Retention period requirements.
- Reference to archive in inventory.

### Step 8 — Update Model Inventory
- Set status to "Retired".
- Record retirement date, reason, archive location, successor model.

### Step 9 — Notify Stakeholders
- Communication to model users, downstream systems, governance.

---

## Related Documents

| Document | Reference |
|----------|-----------|
| Retirement Form | [TMPL-005](../03_templates/TMPL-005_retirement_form.md) |
| Model Inventory Procedure | [PROC-003](PROC-003_model_inventory_procedure.md) |
| Model Lifecycle Guide — Stage 6.10 | [Link](../00_guide/06_stage_requirements/10_retirement_archiving.md) |
