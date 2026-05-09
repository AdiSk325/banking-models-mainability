# Chapter 8 — Required Artifacts and Minimum Documentation

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 8

---

## 8.1 Purpose

This chapter defines the **minimum set of artifacts** that every model must produce throughout its lifecycle. Artifacts serve as the evidence base for governance, validation, audit, and regulatory review. They must be produced contemporaneously with the work they document — not retrospectively.

The required level of artifact completeness depends on the model's tier (see [Chapter 4 — Model Classification](04_model_classification_tiering.md)).

---

## 8.2 Artifact Categories

### Category A — Initiation and Governance

| Artifact | Description | Template / Standard | Tier 1 | Tier 2 | Tier 3 |
|----------|-------------|---------------------|--------|--------|--------|
| Model Concept Note | Business justification, intended use, preliminary scope | [TMPL-001](../03_templates/TMPL-001_model_development_document.md) | ✅ Full | ✅ Full | ✅ Simplified |
| Model Inventory Entry | Registration in central model inventory | [PROC-003](../02_procedures/PROC-003_model_inventory_procedure.md) | ✅ Full | ✅ Full | ✅ Basic |
| Tier Assignment Record | Documented classification decision | Chapter 4 | ✅ | ✅ | ✅ |
| Approval to Develop Record | Stage gate 1 approval evidence | — | ✅ Committee | ✅ Delegated | ✅ Owner |

---

### Category B — Development Documentation

| Artifact | Description | Template / Standard | Tier 1 | Tier 2 | Tier 3 |
|----------|-------------|---------------------|--------|--------|--------|
| Model Development Document | Full technical documentation of the model | [TMPL-001](../03_templates/TMPL-001_model_development_document.md) | ✅ Full | ✅ Full | 🟡 Simplified |
| Data Assessment Report | Data quality, lineage, and limitations | [STD-007](../01_supporting_standards/STD-007_data_quality_standard.md) | ✅ Full | ✅ Standard | 🟡 Summary |
| Data Dictionary / Variable Inventory | Description of all input variables | [TMPL-001](../03_templates/TMPL-001_model_development_document.md) | ✅ Full | ✅ Full | 🟡 Key vars |
| Assumptions Register | Explicit list of key modelling assumptions | — | ✅ Required | ✅ Required | ✅ Required |
| Limitations Summary | Known model limitations and proposed mitigants | — | ✅ Required | ✅ Required | ✅ Required |
| Version Control Log | History of all code commits and model versions | — | ✅ Required | ✅ Required | ✅ Required |

---

### Category C — Testing Evidence

| Artifact | Description | Standard | Tier 1 | Tier 2 | Tier 3 |
|----------|-------------|---------|--------|--------|--------|
| Performance test results | In-sample, out-of-sample, out-of-time | [STD-001](../01_supporting_standards/STD-001_model_development_standard.md) | ✅ Full | ✅ Full | ✅ Basic |
| Stability test results | PSI, CSI | [STD-001](../01_supporting_standards/STD-001_model_development_standard.md) | ✅ Required | 🟡 Recommended | — |
| Calibration test results | Predicted vs. observed | [STD-001](../01_supporting_standards/STD-001_model_development_standard.md) | ✅ Required | ✅ Required | 🟡 If applicable |
| Stress / sensitivity results | Adverse scenario testing | — | ✅ Required | 🟡 Recommended | — |
| Explainability analysis | Feature importance, SHAP, etc. | [STD-008](../01_supporting_standards/STD-008_ai_ml_explainability_standard.md) | ✅ Required | ✅ Required | 🟡 Summary |
| Bias / fairness assessment | Discriminatory impact analysis | [STD-008](../01_supporting_standards/STD-008_ai_ml_explainability_standard.md) | ✅ If applicable | ✅ If applicable | 🟡 If applicable |

---

### Category D — Validation

| Artifact | Description | Template | Tier 1 | Tier 2 | Tier 3 |
|----------|-------------|---------|--------|--------|--------|
| Validation Report | Full independent validation output | [TMPL-002](../03_templates/TMPL-002_validation_report.md) | ✅ Full | ✅ Full | 🟡 Peer review memo |
| Findings Log | Findings with severity and status | [TMPL-002](../03_templates/TMPL-002_validation_report.md) | ✅ Required | ✅ Required | 🟡 If findings |
| Findings Resolution Record | Evidence of closure or risk-acceptance | — | ✅ Required | ✅ Required | 🟡 If findings |

---

### Category E — Approval

| Artifact | Description | Tier 1 | Tier 2 | Tier 3 |
|----------|-------------|--------|--------|--------|
| Formal Approval Record | Minutes or decision document | ✅ Committee | ✅ Delegated | ✅ Owner |
| Conditions Register | Conditions attached to approval | ✅ If conditions | ✅ If conditions | — |

---

### Category F — Deployment and Operations

| Artifact | Description | Template | Tier 1 | Tier 2 | Tier 3 |
|----------|-------------|---------|--------|--------|--------|
| Release Readiness Checklist | Pre-deployment gate evidence | [TMPL-006](../03_templates/TMPL-006_release_readiness_checklist.md) | ✅ Required | ✅ Required | ✅ Required |
| UAT Sign-off | Business acceptance of production behaviour | — | ✅ Required | ✅ Required | 🟡 If applicable |
| Monitoring Plan | Plan for ongoing model monitoring | [TMPL-003](../03_templates/TMPL-003_monitoring_plan.md) | ✅ Full | ✅ Standard | ✅ Basic |

---

### Category G — Ongoing and Change

| Artifact | Description | Template | Required |
|----------|-------------|---------|---------|
| Monitoring Reports | Periodic monitoring output | [TMPL-003](../03_templates/TMPL-003_monitoring_plan.md) | ✅ All tiers |
| Annual Review Record | Periodic fitness-for-purpose assessment | — | ✅ All tiers |
| Change Request Form | Documentation of any model change | [TMPL-004](../03_templates/TMPL-004_change_request_form.md) | ✅ All changes |
| Change Impact Assessment | Assessment of change materiality and effect | — | ✅ Material changes |

---

### Category H — Retirement

| Artifact | Description | Template | Required |
|----------|-------------|---------|---------|
| Retirement Decision Document | Formal retirement approval | [TMPL-005](../03_templates/TMPL-005_retirement_form.md) | ✅ All tiers |
| Archive Record | Location and contents of archived artefacts | — | ✅ All tiers |

---

## 8.3 Documentation Quality Standards

All artifacts must satisfy the following minimum quality criteria:
- Written in clear language accessible to the intended audience.
- Include the document owner, version number, and effective date.
- Be reviewed and approved by the appropriate party before the corresponding stage gate is passed.
- Be retained in accordance with retention requirements (see [Stage 6.10 — Retirement and Archiving](06_stage_requirements/10_retirement_archiving.md)).

For detailed documentation requirements, see [STD-002 — Model Documentation Standard](../01_supporting_standards/STD-002_model_documentation_standard.md).

---

*Previous: [Chapter 7 — Roles and Responsibilities](07_roles_responsibilities.md)*  
*Next: [Chapter 9 — Controls, Exceptions and Escalation](09_controls_exceptions_escalation.md)*
