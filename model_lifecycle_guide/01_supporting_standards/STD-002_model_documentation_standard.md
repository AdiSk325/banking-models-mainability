# STD-002 — Model Documentation Standard

> **Status: PLACEHOLDER — content to be completed**  
> **Document type:** Standard (Level 3)  
> **Parent document:** [Model Lifecycle Guide](../00_guide/README.md)  
> **Applies to lifecycle stages:** 6.3, 6.4  
> **Owner:** Model Risk Management

---

## Purpose

This standard defines the **minimum required content and quality** of model documentation. It implements Principle 5 (Documentation by Design) from the Model Lifecycle Guide and ensures that documentation is sufficient to support independent validation, audit, and regulatory review.

---

## Contents to Be Developed

<!-- TODO: Draft the following sections, aligned with industry standards (SR 11-7, EBA Guidelines): -->

### 1. Required Documentation Sections

Each Model Development Document must contain at minimum:

| Section | Description | Required for tier |
|---------|-------------|------------------|
| 1. Executive Summary | Non-technical overview | All |
| 2. Business Purpose and Use | What the model does and how outputs are used | All |
| 3. Model Owner and Stakeholders | Who owns, uses, and governs the model | All |
| 4. Model Scope and Applicability | What it applies to; what it does not | All |
| 5. Data Description | Sources, variables, lineage, quality assessment | All |
| 6. Methodology | Technical approach; rationale for selection | All |
| 7. Model Assumptions | Explicit list with justification and limitations | All |
| 8. Model Development Details | Feature engineering, training, calibration | All |
| 9. Model Performance | Results of all required tests | All |
| 10. Explainability | Feature importance or equivalent | Tier 1–2 |
| 11. Bias and Fairness | If model is used in decisions affecting individuals | If applicable |
| 12. Model Limitations | Known weaknesses and compensating mitigants | All |
| 13. Implementation Details | How the model is deployed; system integration | All |
| 14. Monitoring Plan Reference | Link to approved monitoring plan | All |
| 15. Change History | Version log | All |
| 16. References | Data sources, methodology references | All |

### 2. Documentation Quality Criteria
- Completeness — all required sections present.
- Accuracy — documentation matches actual model.
- Clarity — accessible to a qualified non-developer (i.e., a competent validator).
- Contemporaneity — produced during, not after, development.

### 3. Documentation Lifecycle Management
- When documentation must be updated.
- Change tracking requirements.
- Retention requirements.

### 4. Tier-Specific Requirements
- Simplified documentation requirements for Tier 3.
- Additional requirements for regulatory capital models (Tier 1).

---

## Cross-References

| Document | Relationship |
|----------|-------------|
| [Model Lifecycle Guide — Stage 6.4](../00_guide/06_stage_requirements/04_testing_documentation.md) | Parent framework |
| [STD-003 — Validation Standard](STD-003_validation_standard.md) | Validates documentation |
| [TMPL-001 — Model Development Document](../03_templates/TMPL-001_model_development_document.md) | Implementation template |

---

*See [04_references/01_regulatory_guidance.md](../04_references/01_regulatory_guidance.md) — SR 11-7 Section IV and EBA Guidelines on documentation requirements for inspiration.*
