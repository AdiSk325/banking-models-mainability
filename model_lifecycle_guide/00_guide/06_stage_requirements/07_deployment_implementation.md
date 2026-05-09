# Stage 6.7 — Deployment and Implementation Controls

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 6.7

---

## Purpose

The Deployment and Implementation Controls stage governs the controlled transition of an approved model from a development environment into production use. It ensures that the model that is deployed is **identical to the model that was validated and approved**, and that implementation controls, access management, and rollback capabilities are in place.

---

## Entry Criteria

- Formal approval obtained (Stage 6.6 complete).
- Deployment plan prepared.
- IT/MLOps resources and deployment environment are confirmed.
- Monitoring plan is prepared (see Stage 6.8 — monitoring plan must exist before go-live).

---

## Key Activities

1. **Implementation specification** — document how the approved model will be technically implemented (system, API, batch, etc.).
2. **Environment segregation** — confirm strict separation between development, testing (UAT/SIT), and production environments.
3. **Version confirmation** — confirm that the production implementation corresponds to the exact approved version of the model (code hash, model artefact hash, or equivalent).
4. **User Acceptance Testing (UAT)** — business users confirm that model outputs in the production-equivalent environment are as expected.
5. **System / Integration Testing (SIT)** — IT confirms that the model interfaces correctly with upstream and downstream systems.
6. **Access control** — implement role-based access controls; restrict model modification to authorised parties.
7. **Parallel run (where required)** — for Tier 1 models replacing an existing model, run old and new models in parallel before full cutover.
8. **Rollback plan** — document and test rollback procedure in case of production issues post-deployment.
9. **Handover to Model Owner and User** — formally hand over operational responsibility to the Model Owner and production user team.
10. **Go-live readiness sign-off** — obtain sign-off from all required parties using the Release Readiness Checklist.
11. **Update model inventory** — record deployment date, production system, version, and monitoring plan reference.

---

## Roles

| Role | Responsibility |
|------|---------------|
| Data Scientist / Developer | Supports implementation; confirms version match |
| IT / MLOps / Engineering | Implements model in production; conducts SIT |
| Model User / Business | Conducts UAT; confirms operational readiness |
| Model Owner | Accountable for go-live decision; signs release readiness |
| MRM | Confirms deployment controls are satisfied |

---

## Required Outputs / Artifacts

| Artifact | Tier 1 | Tier 2 | Tier 3 |
|----------|--------|--------|--------|
| Deployment / implementation plan | ✅ Required | ✅ Required | 🟡 Basic |
| UAT sign-off | ✅ Required | ✅ Required | 🟡 If applicable |
| SIT sign-off | ✅ Required | ✅ Required | 🟡 If applicable |
| Rollback plan | ✅ Required | ✅ Required | 🟡 Documented |
| Go-Live Release Readiness sign-off | ✅ Required | ✅ Required | ✅ Required |
| Updated model inventory entry | ✅ Required | ✅ Required | ✅ Required |
| Parallel run results (if applicable) | ✅ Required | 🟡 If replacing | — |

---

## Exit Criteria / Stage Gate

✅ **Go-Live Readiness** sign-off before model enters production.

Confirms:
- Production version matches approved version.
- UAT and SIT completed successfully.
- Rollback plan documented and tested.
- Access controls implemented.
- Monitoring plan is active.
- Model inventory is updated.

---

## Linked Documents

| Document | Type | Reference |
|----------|------|-----------|
| Deployment Standard | Standard | [STD-006](../../01_supporting_standards/STD-006_deployment_standard.md) |
| Release Readiness Checklist | Template | [TMPL-006](../../03_templates/TMPL-006_release_readiness_checklist.md) |
| Monitoring Plan template | Template | [TMPL-003](../../03_templates/TMPL-003_monitoring_plan.md) |
| Model Inventory Procedure | Procedure | [PROC-003](../../02_procedures/PROC-003_model_inventory_procedure.md) |

---

*Previous: [Stage 6.6 — Approval and Governance Review](06_approval_governance.md)*  
*Next: [Stage 6.8 — Monitoring and Periodic Review](08_monitoring_periodic_review.md)*
