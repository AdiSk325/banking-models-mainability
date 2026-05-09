# Chapter 2 — Key Definitions

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 2

---

## 2.1 Purpose of This Chapter

This chapter defines the key terms used throughout the Model Lifecycle Guide and its supporting documents. Consistent terminology is essential for effective governance and shared understanding across all stakeholders.

For a comprehensive glossary including all terms, see [Appendix C — Glossary](12_appendices/C_glossary.md).

---

## 2.2 Core Definitions

### Model

A quantitative or algorithmic method that applies statistical, mathematical, computational, or expert-based logic to transform input data into outputs — such as scores, ratings, estimates, classifications, recommendations, or automated decisions — that inform or directly drive business decisions.

See [Chapter 1.2.1](01_purpose_scope_audience.md#121-what-is-a-model) for scope details.

### Model Risk

The risk of adverse consequences arising from **errors or misuse of models**, including:
- Incorrect model design or methodology.
- Incorrect implementation.
- Inappropriate use.
- Use outside the model's intended scope or conditions.
- Insufficient ongoing monitoring of model performance.

### Model Lifecycle

The **complete sequence of stages** through which a model passes — from initial business need identification, through development, validation, deployment, monitoring, change management, and ultimately retirement.

### Model Tier / Model Classification

A **risk-based category** assigned to a model based on its materiality, complexity, regulatory significance, and potential impact. Tier determines the level of governance rigour required. See [Chapter 4](04_model_classification_tiering.md).

### Model Owner

The **accountable business owner** of a model — responsible for ensuring the model is fit for purpose, properly governed, monitored, and reviewed throughout its lifecycle.

### Model Developer / Data Scientist

The individual or team responsible for **designing, building, testing, and documenting** the model.

### Independent Validator

A **functionally independent** individual or team responsible for providing objective challenge to the model's conceptual soundness, data, methodology, and documentation, before deployment.

### Model Risk Management (MRM)

The **second-line function** responsible for:
- Setting and maintaining the model governance framework.
- Overseeing model risk across the bank.
- Maintaining the model inventory.
- Reviewing and approving models above applicable thresholds.

### Model User

The individual or system that applies a model's output to drive decisions, processes, or reporting.

### Model Inventory

The **central register** of all models in use or under development within the bank, containing key metadata about each model.

### Model Documentation

The **formal written record** of a model's purpose, design, data, methodology, assumptions, limitations, testing results, and governance history. See [STD-002 — Model Documentation Standard](../01_supporting_standards/STD-002_model_documentation_standard.md).

### Validation

The **independent assessment** of a model's conceptual soundness, data, methodology, implementation, and ongoing performance. Validation must be conducted by a party functionally independent of model development.

### Model Change

Any modification to a model's **methodology, inputs, code, parameters, or implementation** that may affect its outputs or risk profile. Changes are classified as material or non-material. See [Stage 6.9 — Change Management](06_stage_requirements/09_change_management.md).

### Material Change

A model change that **significantly affects outputs or risk**, and therefore triggers mandatory re-testing, re-validation, and/or re-approval. Materiality thresholds are defined in [STD-005 — Change Management Standard](../01_supporting_standards/STD-005_change_management_standard.md).

### Stage Gate

A **mandatory decision point** between lifecycle stages at which defined exit criteria must be satisfied before the model progresses.

### Exception

A **formally approved departure** from the requirements of this Guide or its supporting documents, granted for a defined period and subject to compensating controls.

### Model Retirement / Decommissioning

The **formal process** of withdrawing a model from active use, including archival of documentation and notification to relevant stakeholders.

### Monitoring

The **ongoing process** of assessing a deployed model's continued performance, stability, and fitness for purpose against pre-defined thresholds and criteria.

### Revalidation

A **new validation** of a model — triggered by material changes, passage of time, significant deterioration in performance, or regulatory requirement.

### Reproducibility

The ability to **recreate model outputs** given the same inputs, methodology, and conditions as at the time of development — a fundamental requirement for all models.

### Traceability

The ability to **trace back any model output** to the inputs, data, and logic that produced it.

<!-- TODO: Review and expand with MRM — add any institution-specific terms that are not self-evident. -->
<!-- TODO: Align terminology with Model Risk Management Policy and existing standards. -->

---

## 2.3 Acronyms

| Acronym | Full Form |
|---------|-----------|
| AI | Artificial Intelligence |
| AUC | Area Under the Curve |
| CSI | Characteristic Stability Index |
| EAD | Exposure at Default |
| EBA | European Banking Authority |
| ECB | European Central Bank |
| IFRS 9 | International Financial Reporting Standard 9 |
| IRB | Internal Ratings-Based |
| KNF | Komisja Nadzoru Finansowego (Polish Financial Supervision Authority) |
| LGD | Loss Given Default |
| MRM | Model Risk Management |
| ML | Machine Learning |
| MLOps | Machine Learning Operations |
| PD | Probability of Default |
| PSI | Population Stability Index |
| RACI | Responsible, Accountable, Consulted, Informed |
| RWA | Risk-Weighted Assets |
| SOP | Standard Operating Procedure |
| UAT | User Acceptance Testing |

---

*Previous: [Chapter 1 — Purpose, Scope and Applicability](01_purpose_scope_audience.md)*  
*Next: [Chapter 3 — Guiding Principles](03_guiding_principles.md)*
