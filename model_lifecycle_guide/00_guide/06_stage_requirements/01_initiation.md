# Stage 6.1 — Initiation

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 6.1

---

## Purpose

The Initiation stage marks the formal beginning of a model's lifecycle. Its purpose is to ensure that:
- There is a **clear, justified business need** for a new or replacement model.
- The model's **scope, use, and risk level** are understood before any development investment is made.
- The appropriate **governance approvals** are obtained before resource allocation begins.

This stage prevents the development of unnecessary or inappropriately scoped models and ensures that risk management considerations are built in from the start.

---

## Entry Criteria

- A business need or problem has been identified that could benefit from a model.
- A business sponsor or model owner candidate has been identified.
- Preliminary view on in-scope data and use case is available.

---

## Key Activities

1. **Document the business need** — describe the decision, process, or reporting requirement the model will support.
2. **Define the intended use** — scope, user population, decision context, frequency of use, and level of automation.
3. **Perform preliminary risk assessment** — identify the model's potential financial, regulatory, and operational risk.
4. **Assign a preliminary model tier** — based on the classification criteria in [Chapter 4](../04_model_classification_tiering.md).
5. **Assess data availability** — preliminary check on whether required data sources are accessible.
6. **Prepare the Model Concept Note** — the formal initiation document (see [TMPL-001](../../03_templates/TMPL-001_model_development_document.md)).
7. **Register the model in the inventory** — create a draft inventory entry (see [PROC-003](../../02_procedures/PROC-003_model_inventory_procedure.md)).
8. **Obtain initiation approval** — submit Concept Note for review and approval per tier requirements.

---

## Roles

| Role | Responsibility |
|------|---------------|
| Data Scientist / Developer | Prepares technical assessment of feasibility |
| Model Owner | Confirms business need; accountable sponsor |
| MRM | Reviews tier assignment; approves concept (for Tier 1–2) |
| Business Sponsor | Signs off on business justification |

See [Chapter 7 — Roles and Responsibilities](../07_roles_responsibilities.md) for full role definitions.

---

## Required Outputs / Artifacts

| Artifact | Tier 1 | Tier 2 | Tier 3 |
|----------|--------|--------|--------|
| Model Concept Note | ✅ Full | ✅ Full | ✅ Simplified |
| Preliminary Tier Assignment | ✅ | ✅ | ✅ |
| Model Inventory Draft Entry | ✅ | ✅ | ✅ |
| Approval Record | ✅ Committee | ✅ Delegated | ✅ Owner |

See [Chapter 8 — Required Artifacts](../08_required_artifacts.md) and [TMPL-001](../../03_templates/TMPL-001_model_development_document.md).

---

## Exit Criteria / Stage Gate

✅ **Approval to Develop** must be granted before the model lifecycle proceeds to Stage 6.2.

The approval confirms:
- Business need is justified.
- Scope and intended use are documented.
- Model tier has been assigned.
- Model inventory draft entry is created.
- Resources and timeline have been assessed.

<!-- TODO: Define who grants approval to develop for each tier and in what format. -->

---

## Linked Documents

| Document | Type | Reference |
|----------|------|-----------|
| Model Concept Note template | Template | [TMPL-001](../../03_templates/TMPL-001_model_development_document.md) |
| Model Initiation Procedure | Procedure | [PROC-001](../../02_procedures/PROC-001_model_initiation_procedure.md) |
| Model Inventory Procedure | Procedure | [PROC-003](../../02_procedures/PROC-003_model_inventory_procedure.md) |
| Model Classification | Guide Chapter | [Chapter 4](../04_model_classification_tiering.md) |

---

*Previous: [Chapter 5 — Lifecycle Overview](../05_lifecycle_overview.md)*  
*Next: [Stage 6.2 — Data Sourcing and Assessment](02_data_sourcing_assessment.md)*
