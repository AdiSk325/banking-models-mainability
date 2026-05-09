# Stage 6.2 — Data Sourcing and Assessment

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 6.2

---

## Purpose

The Data Sourcing and Assessment stage ensures that the data underpinning the model is **fit for purpose, well-understood, and appropriately governed** before model development begins. Poor data quality is a leading cause of model failure and model risk. This stage creates the data foundation on which all subsequent model work depends.

---

## Entry Criteria

- Approval to develop has been granted (Stage 6.1 complete).
- Data sources required for the model have been preliminarily identified.
- Data access requests are in progress or completed.

---

## Key Activities

1. **Identify data sources** — document all sources of data required for model development, including training data, validation data, and ongoing production data feeds.
2. **Data lineage documentation** — trace the origin, transformation, and flow of each data element from source to model input.
3. **Data quality assessment** — assess data for completeness, accuracy, consistency, timeliness, and relevance.
4. **Assess representativeness** — confirm that the development sample is representative of the target population (out-of-time testing, coverage analysis).
5. **Identify data limitations** — document known gaps, biases, or quality issues and their potential impact on the model.
6. **Data governance check** — confirm appropriate data access permissions, data privacy compliance (GDPR), and data retention obligations.
7. **Prepare Data Assessment Report** — document findings from all of the above.

---

## Roles

| Role | Responsibility |
|------|---------------|
| Data Scientist / Developer | Conducts data analysis; prepares assessment report |
| Data Owner / Data Steward | Confirms data availability, access, and governance |
| MRM | Reviews data assessment for Tier 1–2 models |
| Compliance / DPO | Confirms GDPR and data privacy compliance where applicable |

---

## Required Outputs / Artifacts

| Artifact | Tier 1 | Tier 2 | Tier 3 |
|----------|--------|--------|--------|
| Data Assessment Report | ✅ Full | ✅ Standard | 🟡 Summary |
| Data Lineage Documentation | ✅ Required | ✅ Required | 🟡 Basic |
| Data Dictionary / Variable Inventory | ✅ Full | ✅ Full | 🟡 Key fields |
| Data Privacy / GDPR Assessment | ✅ Required | ✅ Required | 🟡 If personal data |
| Known Limitations Register | ✅ Required | ✅ Required | ✅ Required |

---

## Exit Criteria / Stage Gate

✅ **Data Readiness Sign-off** before proceeding to Stage 6.3.

The sign-off confirms:
- All required data sources have been documented.
- Data quality is assessed and documented.
- Material data limitations are identified and their risk implications understood.
- Data access and governance permissions are confirmed.

<!-- TODO: Define who provides data readiness sign-off per tier. -->

---

## Key Risk Considerations

- **Sample bias:** Development data may not represent future population (e.g., through-the-cycle vs. point-in-time, reject inference for scorecards).
- **Survivorship bias:** Retrospective data may systematically exclude failed observations.
- **Data leakage:** Future information inadvertently included in training data.
- **Feature drift:** Relationships between variables may change over time (addressed in monitoring plan).

These risks must be explicitly acknowledged in the Data Assessment Report and mitigated or monitored accordingly.

---

## Linked Documents

| Document | Type | Reference |
|----------|------|-----------|
| Data Quality Standard | Standard | [STD-007](../../01_supporting_standards/STD-007_data_quality_standard.md) |
| Model Development Standard | Standard | [STD-001](../../01_supporting_standards/STD-001_model_development_standard.md) |
| Model Development Document template | Template | [TMPL-001](../../03_templates/TMPL-001_model_development_document.md) |

---

*Previous: [Stage 6.1 — Initiation](01_initiation.md)*  
*Next: [Stage 6.3 — Design and Development](03_design_development.md)*
