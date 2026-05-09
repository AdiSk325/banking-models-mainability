# Stage 6.10 — Retirement and Archiving

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 6.10

---

## Purpose

All models eventually reach the end of their useful life. The Retirement and Archiving stage ensures that models are **decommissioned in a controlled, documented, and auditable manner** — preserving the historical record of decisions driven by the model and satisfying regulatory and legal retention requirements.

Uncontrolled model retirement is a governance risk: it can result in loss of audit trail, failure to account for outstanding decisions, or accidental continued use of a decommissioned model.

---

## Entry Criteria

A retirement trigger occurs when:
- The model is being replaced by a successor model.
- The business use or product supported by the model has been discontinued.
- The model is no longer performing adequately and no recalibration is warranted.
- A regulatory or supervisory requirement mandates retirement.
- The model owner decides retirement is appropriate following periodic review.

---

## Key Activities

1. **Initiate retirement** — Model Owner raises a formal retirement decision.
2. **Retirement impact assessment** — assess the impact of retirement on:
   - Active decisions or processes currently using the model.
   - Users who must transition to the replacement or alternative.
   - Regulatory reporting or disclosure that depends on the model.
3. **Transition plan** — if the model is being replaced, define the transition plan including parallel run period (if applicable) and cutover date.
4. **Decommission from production** — remove the model from active production systems per the deployment controls in [STD-006](../../01_supporting_standards/STD-006_deployment_standard.md).
5. **Archive model artefacts** — archive all model artefacts in accordance with retention requirements:
   - Model code (tagged version in version control).
   - Training data (or reference to data location per retention policy).
   - All documentation (development, validation reports, approval records, monitoring history).
   - Audit trail of all governance decisions.
6. **Update model inventory** — record retirement date, reason for retirement, archive location, and successor model reference (if applicable).
7. **Notify stakeholders** — communicate retirement to all affected users, downstream system owners, and governance parties.
8. **Obtain retirement approval** — formal sign-off from Model Owner and MRM.

---

## Archival Requirements

| Category | Minimum Retention Period | Notes |
|----------|--------------------------|-------|
| Model code | 10 years | Or per regulatory requirement, whichever is longer |
| Development documentation | 10 years | |
| Validation reports | 10 years | |
| Approval records | 10 years | |
| Monitoring reports | 7 years | |
| Governance decisions / minutes | 10 years | |
| Training data reference | Per data retention policy | Actual data may be subject to GDPR deletion obligations |

<!-- TODO: Confirm retention periods with Compliance and Legal. -->

---

## Roles

| Role | Responsibility |
|------|---------------|
| Model Owner | Initiates retirement; accountable for transition and sign-off |
| Data Scientist / Developer | Supports archival of code and documentation |
| IT / MLOps | Removes model from production systems; archives artefacts |
| MRM | Approves retirement; updates model inventory |
| Compliance / Legal | Confirms retention and data deletion obligations |

---

## Required Outputs / Artifacts

| Artifact | Required |
|----------|---------|
| Retirement decision document | ✅ Required |
| Impact assessment | ✅ Required |
| Transition plan (if applicable) | ✅ If replacing |
| Archive record (location of all artefacts) | ✅ Required |
| Updated model inventory entry (retired status) | ✅ Required |
| Stakeholder notification record | ✅ Required |

---

## Linked Documents

| Document | Type | Reference |
|----------|------|-----------|
| Retirement Procedure | Procedure | [PROC-005](../../02_procedures/PROC-005_retirement_procedure.md) |
| Retirement Form template | Template | [TMPL-005](../../03_templates/TMPL-005_retirement_form.md) |
| Model Inventory Procedure | Procedure | [PROC-003](../../02_procedures/PROC-003_model_inventory_procedure.md) |
| Deployment Standard | Standard | [STD-006](../../01_supporting_standards/STD-006_deployment_standard.md) |

---

*Previous: [Stage 6.9 — Change Management](09_change_management.md)*  
*Next: [Chapter 7 — Roles and Responsibilities](../07_roles_responsibilities.md)*
