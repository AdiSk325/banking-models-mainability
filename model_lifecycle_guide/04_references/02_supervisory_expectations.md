# Supervisory Expectations — Reference Collection

> **Purpose:** Capture the implicit and explicit supervisory expectations on model governance that should shape the Guide, even where there is no single binding rule.  
> **Priority reading for:** Governance (Ch. 9), Validation (Ch. 6.5), Monitoring (Ch. 6.8)

---

## What Supervisors Typically Look For

Based on SR 11-7, EBA Guidelines, ECB SSM priorities, and public enforcement actions, supervisors assessing model risk management frameworks typically expect institutions to demonstrate:

---

### 1. Clear Model Definition and Scope

**Expectation:** The institution has a clear, documented definition of "model" and a comprehensive inventory of all models in use.

**Common finding:** Models used in important decisions are not captured in the inventory; definition is too narrow.

**Guide relevance:** [Ch. 1 — Scope](../00_guide/01_purpose_scope_audience.md), [Appendix B — Inventory Schema](../00_guide/12_appendices/B_model_inventory_schema.md)

---

### 2. Complete and Accurate Model Inventory

**Expectation:** The model inventory is comprehensive, current, and includes all material models.

**Common finding:** Inventory is incomplete; vendor models are missing; retired models are not updated.

**Guide relevance:** [PROC-003 — Inventory Procedure](../02_procedures/PROC-003_model_inventory_procedure.md)

---

### 3. Clear Ownership and Accountability

**Expectation:** Every model has a named, accountable owner who is responsible throughout the lifecycle.

**Common finding:** Models with no designated owner, or ownership left with the development team rather than a business owner.

**Guide relevance:** [Ch. 7 — Roles](../00_guide/07_roles_responsibilities.md)

---

### 4. Independent Validation Before Deployment

**Expectation:** All material models are independently validated before deployment. Independence is functional, not just procedural.

**Common finding:** Validation conducted by the same team that developed the model; validation is superficial; major models deployed without validation.

**Guide relevance:** [Ch. 6.5 — Validation](../00_guide/06_stage_requirements/05_independent_validation.md), [STD-003](../01_supporting_standards/STD-003_validation_standard.md)

---

### 5. Controlled Deployment and Version Management

**Expectation:** Models deployed in production match the validated and approved version. Version control is enforced.

**Common finding:** Undocumented code changes between validation and production deployment.

**Guide relevance:** [Ch. 6.7 — Deployment](../00_guide/06_stage_requirements/07_deployment_implementation.md), [STD-006](../01_supporting_standards/STD-006_deployment_standard.md)

---

### 6. Ongoing Monitoring

**Expectation:** Models are monitored throughout their operational lives. Deterioration is detected and escalated.

**Common finding:** Monitoring plans are absent or inadequate; models are deployed and forgotten; monitoring reports are produced but not acted upon.

**Guide relevance:** [Ch. 6.8 — Monitoring](../00_guide/06_stage_requirements/08_monitoring_periodic_review.md), [STD-004](../01_supporting_standards/STD-004_monitoring_standard.md)

---

### 7. Change Management

**Expectation:** All model changes are documented, classified, and appropriately governed. Material changes trigger revalidation.

**Common finding:** Incremental changes accumulate without formal documentation; recalibrations treated as non-material when they should trigger revalidation.

**Guide relevance:** [Ch. 6.9 — Change Management](../00_guide/06_stage_requirements/09_change_management.md), [STD-005](../01_supporting_standards/STD-005_change_management_standard.md)

---

### 8. Comprehensive Documentation

**Expectation:** Documentation is complete, contemporaneous, and sufficient for an independent reviewer to understand and replicate the model.

**Common finding:** Documentation produced retrospectively; key methodology sections are incomplete; assumptions are not explicit.

**Guide relevance:** [Ch. 6.4 — Testing and Documentation](../00_guide/06_stage_requirements/04_testing_documentation.md), [STD-002](../01_supporting_standards/STD-002_model_documentation_standard.md)

---

### 9. Governance and Approval Process

**Expectation:** Clear approval gates exist; governance committees have appropriate oversight; approval decisions are documented.

**Common finding:** Approval processes are informal; committee minutes do not show genuine challenge; conditions attached to approvals are not monitored.

**Guide relevance:** [Ch. 6.6 — Approval](../00_guide/06_stage_requirements/06_approval_governance.md), [Ch. 9 — Controls](../00_guide/09_controls_exceptions_escalation.md)

---

### 10. Proportionality

**Expectation:** Governance rigour is commensurate with model risk; not all models are subject to maximum scrutiny.

**Common finding:** Framework is either too rigid (same level for all models, making it impractical) or too flexible (proportionality used to justify inadequate governance for material models).

**Guide relevance:** [Ch. 3 — Principles](../00_guide/03_guiding_principles.md), [Ch. 4 — Classification](../00_guide/04_model_classification_tiering.md)

---

### 11. Periodic Review

**Expectation:** Models are subject to regular periodic review of their ongoing fitness for purpose, not just monitoring.

**Common finding:** Annual reviews are superficial check-the-box exercises rather than genuine assessments.

**Guide relevance:** [Ch. 6.8 — Monitoring and Periodic Review](../00_guide/06_stage_requirements/08_monitoring_periodic_review.md)

---

### 12. AI and Machine Learning Governance

**Emerging expectation:** As ML/AI models proliferate, supervisors increasingly expect governance frameworks to address explainability, bias, fairness, and the risks specific to ML approaches.

**Recent supervisory focus areas:**
- Explainability and interpretability of algorithmic decisions.
- Data bias and discriminatory outcomes.
- Model drift and continuous retraining governance.
- Human oversight of automated decisions.
- EU AI Act obligations (where applicable).

**Guide relevance:** [STD-008 — AI/ML Explainability](../01_supporting_standards/STD-008_ai_ml_explainability_standard.md), [Ch. 4 — Classification](../00_guide/04_model_classification_tiering.md)

---

<!-- TODO: Add entries for specific KNF thematic inspection findings and ECB TRIM (Targeted Review of Internal Models) findings relevant to the bank's model types. -->
