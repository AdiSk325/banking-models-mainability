# Stage 6.3 — Design and Development

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 6.3

---

## Purpose

The Design and Development stage is where the model is conceptually designed, built, and subjected to initial quality checks. It encompasses methodology selection, feature engineering, model training, and internal code review. The outputs of this stage must be of sufficient quality to support rigorous testing and independent validation.

---

## Entry Criteria

- Data Readiness Sign-off obtained (Stage 6.2 complete).
- Development environment is set up and version-controlled.
- Development team and Model Owner are confirmed.

---

## Key Activities

### Design

1. **Select and justify methodology** — choose the modelling approach (e.g., logistic regression, gradient boosting, neural network) with documented rationale aligned to the business use case and regulatory requirements.
2. **Define target variable and performance criteria** — establish what the model predicts and the criteria by which its performance will be judged.
3. **Design feature engineering approach** — document proposed transformations, encodings, and derived variables.
4. **Document assumptions and limitations** — explicitly identify and document key assumptions made in the design phase.

### Development

5. **Implement in version-controlled code** — all model code must be under version control (e.g., Git) from day one.
6. **Feature engineering and selection** — implement and document variable transformations; apply selection criteria (statistical, business, regulatory).
7. **Model training and calibration** — develop the model using the approved training dataset; calibrate outputs appropriately.
8. **Hyperparameter tuning** — document the approach to hyperparameter search and selection.
9. **Set random seeds and ensure reproducibility** — all stochastic processes must use fixed seeds; environment must be documented.
10. **Peer / internal code review** — at least one developer other than the author must review the code.
11. **Develop initial performance analysis** — produce preliminary performance metrics (to be formalized in Stage 6.4).

---

## Roles

| Role | Responsibility |
|------|---------------|
| Data Scientist / Developer | Designs and builds the model; produces documentation |
| Senior Data Scientist / Tech Lead | Reviews methodology and code |
| Model Owner | Confirms business logic and assumptions are correct |
| MRM | May provide guidance on methodology requirements for Tier 1 models |

---

## Required Outputs / Artifacts

| Artifact | Tier 1 | Tier 2 | Tier 3 |
|----------|--------|--------|--------|
| Methodology design document | ✅ Full | ✅ Full | 🟡 Summary |
| Assumptions and limitations register | ✅ Required | ✅ Required | ✅ Required |
| Version-controlled code repository | ✅ Required | ✅ Required | ✅ Required |
| Feature engineering documentation | ✅ Full | ✅ Full | 🟡 Key features |
| Peer code review record | ✅ Required | ✅ Required | 🟡 Recommended |
| Reproducibility documentation (env, seeds) | ✅ Required | ✅ Required | ✅ Required |

---

## Exit Criteria / Stage Gate

✅ **Development Complete Sign-off** before proceeding to Stage 6.4.

Confirms:
- Methodology is selected and documented with rationale.
- Code is version-controlled and peer-reviewed.
- Reproducibility is ensured.
- Assumptions and limitations are explicitly documented.
- Model is ready for structured testing.

---

## Key Principles Applied

- **Reproducibility (Principle 3):** Fixed seeds, pinned environments, documented code.
- **Documentation by Design (Principle 5):** Documentation maintained in parallel with development.
- **Traceability (Principle 4):** All design decisions are recorded with rationale.

---

## Linked Documents

| Document | Type | Reference |
|----------|------|-----------|
| Model Development Standard | Standard | [STD-001](../../01_supporting_standards/STD-001_model_development_standard.md) |
| Model Documentation Standard | Standard | [STD-002](../../01_supporting_standards/STD-002_model_documentation_standard.md) |
| AI/ML Explainability Standard | Standard | [STD-008](../../01_supporting_standards/STD-008_ai_ml_explainability_standard.md) |
| Model Development Document template | Template | [TMPL-001](../../03_templates/TMPL-001_model_development_document.md) |

---

*Previous: [Stage 6.2 — Data Sourcing and Assessment](02_data_sourcing_assessment.md)*  
*Next: [Stage 6.4 — Testing and Documentation](04_testing_documentation.md)*
