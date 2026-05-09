# TMPL-001 — Model Development Document

> **Template version:** DRAFT  
> **Standard:** [STD-002 — Model Documentation Standard](../01_supporting_standards/STD-002_model_documentation_standard.md)  
> **Instructions:** Complete all [REQUIRED] sections before Stage 6.4 sign-off. Complete [CONCEPT] sections at Stage 6.1.

---

# Model Development Document

| Field | Value |
|-------|-------|
| Model ID | [from inventory] |
| Model Name | |
| Version | |
| Document Date | |
| Model Owner | |
| Lead Developer | |
| Model Tier | 1 / 2 / 3 |
| Status | DRAFT / IN REVIEW / FINAL |

---

## Section 1 — Executive Summary [REQUIRED]

<!-- Write a 1–2 paragraph non-technical summary covering: what the model does, what it predicts/outputs, who uses it, and why it was developed. Target audience: senior stakeholders and governance. -->

*[PLACEHOLDER: Complete executive summary here.]*

---

## Section 2 — Business Purpose and Intended Use [REQUIRED — CONCEPT stage]

### 2.1 Business Problem
<!-- Describe the business decision or process the model supports. -->

### 2.2 Intended Use
<!-- Describe specifically how model outputs will be used: in what system, by whom, to drive what decision. -->

### 2.3 Intended User Population
<!-- Who will use the model output. -->

### 2.4 Out-of-Scope Uses
<!-- What the model must NOT be used for. -->

---

## Section 3 — Governance Information [REQUIRED]

| Attribute | Value |
|-----------|-------|
| Model Owner | |
| Business Line | |
| Lead Developer | |
| MRM Contact | |
| Approval date | |
| Approving body | |
| Approval conditions | [None / List] |
| Last validation date | |
| Next review due | |

---

## Section 4 — Data Description [REQUIRED]

### 4.1 Data Sources
<!-- List all data sources used. For each: source system, description, data period covered. -->

| Source | System | Description | Time period | Data quality assessment ref |
|--------|--------|-------------|-------------|-----------------------------|
| | | | | |

### 4.2 Development Sample
<!-- Describe the development dataset: population, time period, segmentation, exclusions. -->

### 4.3 Training / Validation / Test Split
<!-- Describe how data was split. Specify out-of-time periods. -->

### 4.4 Data Quality Assessment
<!-- Reference the data assessment report; summarise key findings and known limitations. -->

---

## Section 5 — Variable / Feature Description [REQUIRED]

<!-- For each input variable used in the final model, provide: -->

| Variable name | Description | Source | Type | Transformation applied | Justification for inclusion |
|---------------|-------------|--------|------|----------------------|----------------------------|
| | | | | | |

---

## Section 6 — Model Methodology [REQUIRED]

### 6.1 Methodology Overview
<!-- Describe the chosen modelling approach. Include: algorithm family, key parameters, conceptual rationale for choice. -->

### 6.2 Methodology Rationale
<!-- Why this approach was chosen over alternatives. What alternatives were considered. -->

### 6.3 Target Variable
<!-- Define the target variable precisely: what it represents, how it is calculated, any known limitations. -->

### 6.4 Model Architecture / Structure
<!-- For ML models: architecture details. For statistical models: functional form. For scorecard: score structure. -->

---

## Section 7 — Model Assumptions [REQUIRED]

| # | Assumption | Justification | Risk if assumption fails | Mitigant / monitoring |
|---|------------|---------------|--------------------------|----------------------|
| 1 | | | | |

---

## Section 8 — Model Development Details [REQUIRED]

### 8.1 Hyperparameter Tuning
<!-- Describe approach: grid search, random search, cross-validation, etc. Document final selected parameters. -->

### 8.2 Calibration
<!-- Describe calibration approach. Report predicted vs. observed rates on development and out-of-time sample. -->

### 8.3 Reproducibility
<!-- Confirm: code is version-controlled; random seeds are set; environment is documented. -->

---

## Section 9 — Model Performance [REQUIRED]

### 9.1 Performance Metrics

| Metric | In-sample | Out-of-sample | Out-of-time | Benchmark |
|--------|-----------|---------------|------------|-----------|
| Gini / AUC | | | | |
| KS | | | | |
| Accuracy / F1 | | | | |
| [Other] | | | | |

### 9.2 Stability Results

| Metric | Result | Assessment |
|--------|--------|-----------|
| PSI | | |
| CSI (key features) | | |

### 9.3 Calibration Results
<!-- Predicted vs. actual table and/or reliability diagram. -->

### 9.4 Stress / Sensitivity Testing
<!-- Results of sensitivity analysis; stress scenarios tested. -->

---

## Section 10 — Explainability [REQUIRED for Tier 1–2]

### 10.1 Global Explainability
<!-- Feature importance table; SHAP summary plot reference. -->

### 10.2 Local Explainability
<!-- Approach for explaining individual predictions. -->

### 10.3 Bias and Fairness Assessment
<!-- If applicable: protected characteristics assessed, fairness metrics, conclusions. -->

---

## Section 11 — Model Limitations [REQUIRED]

| # | Limitation | Potential Impact | Mitigant / Compensating Control |
|---|-----------|-----------------|--------------------------------|
| 1 | | | |

---

## Section 12 — Implementation Details [REQUIRED — at deployment]

### 12.1 Production Environment
<!-- System, technology stack, API / batch, frequency. -->

### 12.2 Input Data in Production
<!-- How production data is sourced; consistency with development data. -->

### 12.3 Output Format
<!-- What the model outputs in production; format; scale. -->

---

## Section 13 — Monitoring Plan Reference [REQUIRED — at deployment]

<!-- Reference to the active Monitoring Plan (TMPL-003). -->

Monitoring Plan ID / location: *[link or reference]*

---

## Section 14 — Change History [REQUIRED]

| Version | Date | Description | Type (M/NM) | Author | Approved by |
|---------|------|-------------|-------------|--------|-------------|
| 0.1 | | Initial draft | — | | |

---

## Section 15 — References

<!-- Data sources, academic papers, regulatory guidance, methodology references. -->

---

*Template: TMPL-001 | Standard: STD-002 | Version: DRAFT*
