# STD-001 — Model Development Standard

> **Status: PLACEHOLDER — content to be completed**  
> **Document type:** Standard (Level 3)  
> **Parent document:** [Model Lifecycle Guide](../00_guide/README.md)  
> **Applies to lifecycle stages:** 6.3 (Design and Development), 6.4 (Testing)  
> **Owner:** Model Risk Management

---

## Purpose

This standard defines the **minimum technical requirements** for model development within the bank. It implements Principles 3 (Reproducibility), 4 (Traceability), and 5 (Documentation by Design) from the Model Lifecycle Guide.

---

## Scope

Applies to all models subject to the Model Lifecycle Guide. Specific provisions are tiered — see each section for tier-specific requirements.

---

## Contents to Be Developed

<!-- TODO: Draft the following sections: -->

### 1. Environment and Tooling Standards
- Approved tools, languages, and libraries.
- Environment management (virtual environments, containers, package pinning).
- Code repository requirements (branching strategy, commit conventions).

### 2. Code Quality Requirements
- Code style standards (e.g., PEP 8 for Python).
- Mandatory code review process.
- Static analysis / linting requirements.
- Unit testing requirements.

### 3. Reproducibility Requirements
- Random seed management.
- Environment documentation (requirements.txt, conda.yml, Dockerfile).
- Data snapshot / data version reference.
- Pipeline execution documentation.

### 4. Feature Engineering Standards
- Documentation requirements for transformations.
- Treatment of missing values.
- Encoding standards.
- Feature selection documentation and justification.

### 5. Model Training Standards
- Train/validation/test split requirements.
- Cross-validation approach documentation.
- Hyperparameter tuning documentation.
- Calibration requirements.

### 6. Testing Criteria
- Minimum performance thresholds by model type and tier.
- Required test types (in-sample, out-of-sample, out-of-time, stability, stress).
- Benchmark comparison requirements.

### 7. Versioning and Artefact Management
- Version numbering convention.
- What must be versioned (code, data references, configuration, model artefacts).
- Artefact storage and naming.

---

## Cross-References

| Document | Relationship |
|----------|-------------|
| [Model Lifecycle Guide — Stage 6.3](../00_guide/06_stage_requirements/03_design_development.md) | Parent framework |
| [Model Lifecycle Guide — Stage 6.4](../00_guide/06_stage_requirements/04_testing_documentation.md) | Parent framework |
| [STD-002 — Documentation Standard](STD-002_model_documentation_standard.md) | Companion standard |
| [STD-006 — Deployment Standard](STD-006_deployment_standard.md) | Downstream standard |
| [TMPL-001 — Model Development Document](../03_templates/TMPL-001_model_development_document.md) | Template |

---

*See [04_references/04_industry_practices.md](../04_references/04_industry_practices.md) for MLOps and reproducibility best practices inspiration.*
