# Chapter 3 — Guiding Principles

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 3  
> **Note:** This is the normative heart of the Guide. Every other chapter should be traceable back to these principles.

---

## 3.1 Introduction

The following **twelve principles** govern all model-related activities within the bank. They form the normative foundation of this Guide and apply throughout the full model lifecycle.

Where a specific rule or requirement in this Guide or its supporting documents conflicts with these principles, the principles take precedence and the MRM function should be consulted.

---

## 3.2 The Twelve Principles

### Principle 1 — Risk-Based Approach

> *The rigour of governance, oversight, and controls applied to a model shall be proportionate to the risk that model poses.*

The bank applies a **risk-tiered approach**: higher-risk models with greater business impact, regulatory significance, or complexity are subject to more stringent requirements. Lower-risk models benefit from a streamlined process. Risk classification is mandatory for all models (see [Chapter 4](04_model_classification_tiering.md)).

---

### Principle 2 — Proportionality

> *Requirements shall be appropriately scaled to the nature, scope, and materiality of each model and its use.*

Proportionality ensures that governance does not impose unnecessary burden on simple, low-risk tools, while ensuring robust controls are in place for models that could cause material harm.

---

### Principle 3 — Reproducibility

> *Every model and its outputs must be fully reproducible given the same inputs, data, code, and environment.*

Reproducibility is a prerequisite for governance, validation, and audit. This includes:
- Version-controlled code and configurations.
- Documented data extracts and preprocessing steps.
- Pinned library versions and documented environments.
- Seed setting for stochastic processes.

See [STD-001 — Model Development Standard](../01_supporting_standards/STD-001_model_development_standard.md).

---

### Principle 4 — Traceability

> *It must always be possible to trace any model output back to the inputs, data, methodology, and decisions that produced it.*

Traceability underpins audit, regulatory review, and accountability. It requires:
- Full documentation of data lineage.
- Version tracking of all model components.
- Retention of audit trails for decisions and approvals.

---

### Principle 5 — Documentation by Design

> *Documentation is an integral part of model development, not an afterthought.*

All models must be documented **during** development, not retrospectively. Minimum documentation requirements are defined in [Chapter 8](08_required_artifacts.md) and [STD-002 — Model Documentation Standard](../01_supporting_standards/STD-002_model_documentation_standard.md).

---

### Principle 6 — Independent Challenge

> *Models must be subject to independent, objective challenge before deployment and on an ongoing basis.*

Independent validation (see [Stage 6.5](06_stage_requirements/05_independent_validation.md)) must be conducted by parties who are functionally independent of the development team. The depth of validation is risk-tiered.

---

### Principle 7 — Segregation of Duties

> *The roles of model development, validation, and approval shall be held by separate, independent parties.*

No individual or team may independently develop, validate, and approve their own model. Exceptions require formal approval and compensating controls.

---

### Principle 8 — Controlled Change

> *Changes to models must be assessed, approved, and documented before implementation.*

All model changes — including methodology updates, recalibrations, input changes, and implementation modifications — are subject to change management controls. The level of control is proportional to the materiality of the change. See [Stage 6.9](06_stage_requirements/09_change_management.md).

---

### Principle 9 — Monitoring Throughout the Lifecycle

> *A model's performance, stability, and fitness for purpose must be monitored on an ongoing basis throughout its operational life.*

Monitoring is not an optional post-deployment activity — it is a **mandatory ongoing obligation** for all deployed models. Monitoring plans must be established before deployment and executed consistently. See [Stage 6.8](06_stage_requirements/08_monitoring_periodic_review.md).

---

### Principle 10 — Human Accountability

> *Accountability for model decisions and outcomes must rest with identifiable human owners, not with models themselves.*

Every model must have a designated **Model Owner** who is accountable for its governance, performance, and lifecycle. Automated or AI-driven decisions must have a clearly assigned human accountable party.

---

### Principle 11 — Compliance with Regulation and Internal Policy

> *All model activities must comply with applicable regulatory requirements, supervisory expectations, and internal policy.*

The bank's model governance framework is aligned with regulatory guidance including SR 11-7 (Federal Reserve), EBA Guidelines on Model Risk Management, and ECB supervisory expectations (see [04_references/01_regulatory_guidance.md](../04_references/01_regulatory_guidance.md)). Where regulation sets a higher standard than this Guide, regulation prevails.

---

### Principle 12 — Continuous Improvement

> *The model governance framework shall be reviewed and improved on a regular basis to reflect evolving best practices, regulatory expectations, and organisational learning.*

This Guide is itself subject to a defined review cycle (see [Chapter 11](11_review_cycle.md)). Lessons learned from model failures, near-misses, and audit findings shall be incorporated.

---

## 3.3 Principle Application Matrix

The table below shows how each principle manifests in specific lifecycle stages.

| Principle | Initiation | Development | Testing | Validation | Deployment | Monitoring | Change | Retirement |
|-----------|-----------|-------------|---------|------------|------------|------------|--------|------------|
| Risk-Based | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Reproducibility | | ✓ | ✓ | ✓ | ✓ | | ✓ | |
| Traceability | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Documentation by Design | ✓ | ✓ | ✓ | ✓ | | ✓ | ✓ | ✓ |
| Independent Challenge | | | | ✓ | | ✓ | ✓ | |
| Segregation of Duties | | ✓ | | ✓ | ✓ | | ✓ | |
| Controlled Change | | | | | ✓ | | ✓ | ✓ |
| Monitoring | | | | | ✓ | ✓ | ✓ | |
| Human Accountability | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Compliance | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

<!-- TODO: Review this matrix with MRM — add specific cross-references to stage requirements once drafts are complete. -->

---

*Previous: [Chapter 2 — Key Definitions](02_definitions.md)*  
*Next: [Chapter 4 — Model Classification and Risk Tiering](04_model_classification_tiering.md)*
