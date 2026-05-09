# Stage 6.6 — Approval and Governance Review

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 6.6

---

## Purpose

The Approval and Governance Review stage is the formal decision point at which authorised governance bodies review the model's full record — including development documentation, validation findings, and proposed use — and grant or withhold approval to deploy.

This stage ensures that **accountability for model deployment rests with governance, not development**. It provides the formal control and audit trail required by regulators and internal policy.

---

## Entry Criteria

- Validation Report issued and all critical findings resolved (Stage 6.5 complete).
- Approval submission package prepared.
- Approval forum or delegated authority identified per model tier.

---

## Key Activities

1. **Prepare approval submission** — compile the full package: model overview, development documentation summary, validation report, findings and resolution, tier assignment, and intended use.
2. **Schedule governance forum** — arrange review by the appropriate approval authority.
3. **Present model to governance forum** — developer and/or model owner presents the model; validator presents validation conclusions.
4. **Governance deliberation** — approval body reviews materials, challenges assumptions, and evaluates residual risks.
5. **Issue formal approval decision** — documented decision: Approved / Approved with conditions / Rejected.
6. **Record approval conditions** — if approved with conditions, conditions are documented, monitored, and time-limited.
7. **Update model inventory** — record approval status, approval date, approving body, and any conditions.

---

## Approval Authority by Tier

<!-- TODO: Confirm actual committee structure with governance. -->

| Tier | Required Approval Authority |
|------|-----------------------------|
| Tier 1 | Senior Model Risk Committee (or equivalent) |
| Tier 2 | Delegated authority (e.g., MRM function head, sub-committee) |
| Tier 3 | Model Owner + MRM acknowledgement |

---

## Roles

| Role | Responsibility |
|------|---------------|
| Model Owner | Accountable; presents business case |
| Data Scientist / Developer | Supports technical questions; may present |
| Independent Validator | Presents validation conclusions and findings status |
| MRM | Provides risk assessment; facilitates governance |
| Approval Authority / Committee | Reviews, challenges, and decides |

---

## Required Outputs / Artifacts

| Artifact | Tier 1 | Tier 2 | Tier 3 |
|----------|--------|--------|--------|
| Approval submission package | ✅ Full | ✅ Standard | 🟡 Simplified |
| Formal approval record / minutes | ✅ Required | ✅ Required | ✅ Required |
| Conditions register (if applicable) | ✅ Required | ✅ Required | 🟡 If conditions |
| Updated model inventory entry | ✅ Required | ✅ Required | ✅ Required |

---

## Exit Criteria / Stage Gate

✅ **Formal Approval** before proceeding to Stage 6.7.

Approval record must document:
- Approving body and date.
- Approval decision (approved / approved with conditions / rejected).
- Any conditions attached to approval.
- Validity period (if time-limited).

---

## Linked Documents

| Document | Type | Reference |
|----------|------|-----------|
| Exception Management Procedure | Procedure | [PROC-006](../../02_procedures/PROC-006_exception_management_procedure.md) |
| Controls, Exceptions and Escalation | Guide Chapter | [Chapter 9](../09_controls_exceptions_escalation.md) |
| Model Inventory Procedure | Procedure | [PROC-003](../../02_procedures/PROC-003_model_inventory_procedure.md) |

---

*Previous: [Stage 6.5 — Independent Validation](05_independent_validation.md)*  
*Next: [Stage 6.7 — Deployment and Implementation Controls](07_deployment_implementation.md)*
