# STD-008 — AI/ML Explainability Standard

> **Status: PLACEHOLDER — content to be completed**  
> **Document type:** Standard (Level 3)  
> **Parent document:** [Model Lifecycle Guide](../00_guide/README.md)  
> **Applies to lifecycle stages:** 6.3 (Development), 6.4 (Testing)  
> **Owner:** Model Risk Management

---

## Purpose

This standard defines the **minimum explainability and interpretability requirements** for AI and ML models, aligned with regulatory expectations and the bank's obligations under consumer protection and fair lending laws.

---

## Contents to Be Developed

<!-- TODO: Draft detailed provisions. Reference EBA Guidelines, EU AI Act, NIST AI RMF, and SR 11-7. -->

### 1. Explainability Requirements by Tier

| Tier | Explainability requirement |
|------|--------------------------|
| Tier 1 | Full explainability documentation required; global and local explanations; must support regulatory and audit review |
| Tier 2 | Global explainability required; local explanation capability expected for individual decisions |
| Tier 3 | Feature importance documentation; local explanations recommended |

### 2. Explainability Methods
- Global methods: feature importance, partial dependence plots (PDPs), SHAP summary plots.
- Local methods: LIME, SHAP (individual observation).
- Model-specific interpretability (for inherently interpretable models: logistic regression, decision trees, scorecards).

### 3. Documentation Requirements
- What must be documented for each model regarding explainability.
- Required outputs in the Model Development Document.
- How to explain model decisions to regulators, auditors, and affected individuals.

### 4. Right to Explanation (GDPR / Consumer Protection)
- Requirements for models making automated decisions about individuals.
- Obligation to provide human-readable explanations.
- Adverse action explanation requirements (e.g., credit refusal).

### 5. Bias and Fairness Assessment
- When a bias/fairness assessment is mandatory.
- Fairness metrics and their interpretation.
- Protected characteristics to assess.
- Remediation requirements.

### 6. Explainability in Monitoring
- How to monitor for explanation drift.
- Updating explanations post-retraining.

---

## Cross-References

| Document | Relationship |
|----------|-------------|
| [Model Lifecycle Guide — Stage 6.4](../00_guide/06_stage_requirements/04_testing_documentation.md) | Parent framework |
| [STD-002 — Documentation Standard](STD-002_model_documentation_standard.md) | Documentation requirements |
| [STD-001 — Development Standard](STD-001_model_development_standard.md) | Development context |

---

*Key references: EU AI Act, EBA/ESAs Joint Advice on AI, NIST AI RMF 1.0, ISO/IEC TR 24028:2020, SR 11-7, OCC 2011-12, GDPR Art. 22.*
