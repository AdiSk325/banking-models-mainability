# STD-006 — Deployment Standard

> **Status: PLACEHOLDER — content to be completed**  
> **Document type:** Standard (Level 3)  
> **Parent document:** [Model Lifecycle Guide](../00_guide/README.md)  
> **Applies to lifecycle stages:** 6.7 (Deployment and Implementation Controls)  
> **Owner:** Model Risk Management / IT / MLOps

---

## Purpose

This standard defines the **technical and governance requirements for deploying models into production**. It implements Principle 8 (Controlled Change) and Principle 7 (Segregation of Duties) in the context of model implementation.

---

## Contents to Be Developed

<!-- TODO: Draft detailed provisions. Co-develop with IT/MLOps function. -->

### 1. Environment Segregation Requirements
- Mandatory separation: development / testing / staging / production.
- Access control between environments.
- Prohibitions (e.g., direct production access by developers).

### 2. Version Control and Artefact Management
- Code repository requirements.
- Model artefact storage (model files, configuration, preprocessing pipeline).
- Hash / checksum verification before production deployment.
- Tagging and release labelling.

### 3. Testing Requirements before Deployment
- UAT: who conducts, what is tested, sign-off requirements.
- SIT: IT integration testing scope.
- Performance validation in production-equivalent environment.

### 4. Deployment Process Controls
- Deployment pipeline requirements (CI/CD where applicable).
- Change ticket / deployment record requirements.
- Approval workflow for production deployments.
- Rollback plan documentation and testing requirements.

### 5. Monitoring Infrastructure
- Requirements for monitoring data collection from production.
- Logging requirements (inputs, outputs, data quality signals).
- Alert infrastructure.

### 6. Access Management
- Who may read / write / execute the production model.
- Periodic access reviews.

### 7. MLOps Maturity Expectations
- Minimum MLOps maturity level by model tier.
<!-- TODO: Define maturity levels and map to tier requirements. -->

---

## Cross-References

| Document | Relationship |
|----------|-------------|
| [Model Lifecycle Guide — Stage 6.7](../00_guide/06_stage_requirements/07_deployment_implementation.md) | Parent framework |
| [TMPL-006 — Release Readiness Checklist](../03_templates/TMPL-006_release_readiness_checklist.md) | Template |
| [STD-001 — Development Standard](STD-001_model_development_standard.md) | Upstream standard |
| [STD-004 — Monitoring Standard](STD-004_monitoring_standard.md) | Downstream standard |

---

*Key references: MLOps practices (Google, Microsoft, Databricks), SR 11-7 (implementation controls), NIST AI RMF (deployment requirements).*
