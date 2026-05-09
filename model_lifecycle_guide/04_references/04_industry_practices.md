# Industry Practices — Reference Collection

> **Purpose:** Industry best practices, maturity models, and frameworks from academic, practitioner, and vendor sources that inform the operational aspects of the Guide.

---

## 1. MLOps and Model Operations

### Google — Practitioners Guide to MLOps
- **Source:** Google Cloud, 2021
- **URL:** https://services.google.com/fh/files/misc/practitioners_guide_to_mlops_whitepaper.pdf
- **Relevance:** MLOps practices for STD-006 (Deployment Standard) and monitoring infrastructure
- **Key takeaways:**
  - MLOps maturity levels: manual / ML pipeline / CI/CD pipeline
  - CI/CD for ML: continuous training, continuous delivery, continuous monitoring
  - Model registry, feature store, and serving infrastructure best practices
  - Monitoring approaches: data drift, concept drift, serving performance
- **Guide sections informed:** STD-006, STD-004, Ch. 6.7–6.8

---

### Microsoft — MLOps Maturity Model
- **Source:** Microsoft Azure, ongoing
- **URL:** https://docs.microsoft.com/en-us/azure/architecture/example-scenario/mlops/mlops-maturity-model
- **Relevance:** Useful for defining expected MLOps maturity by model tier in STD-006
- **Key takeaways:**
  - 5-level maturity model from no MLOps to full ML platform
  - Level 0: Manual; Level 1: ML workflow automation; Level 2: CI/CD pipeline automation; Level 3: Feature and model management; Level 4: Full automation with governance
  - Useful to set minimum tier-by-tier MLOps expectations
- **Guide sections informed:** STD-006, Ch. 4 (tier requirements)

---

### Databricks — Big Book of MLOps
- **Source:** Databricks, 2023
- **URL:** https://www.databricks.com/resources/ebook/the-big-book-of-mlops
- **Relevance:** Practical MLOps patterns; model registry; experiment tracking; deployment patterns
- **Key takeaways:**
  - Model registry for versioning and lifecycle management
  - Experiment tracking as foundation for reproducibility
  - Feature engineering at scale; feature stores
  - Model serving patterns (batch vs. real-time)
- **Guide sections informed:** STD-001, STD-006, Ch. 6.3–6.7

---

## 2. Model Risk Management Maturity Models

### Moody's Analytics — Model Risk Management Framework
- **Source:** Moody's Analytics / Various publications
- **URL:** https://www.moodysanalytics.com — search "model risk management"
- **Relevance:** Commercial maturity model framework useful for benchmarking
- **Key takeaways:**
  - Model risk maturity dimensions: governance, inventory, development, validation, monitoring
  - Useful for self-assessment and communicating gaps to management
  - Practical templates and frameworks for model tiering
- **Guide sections informed:** Ch. 4, Ch. 9

---

### SAS — Model Risk Management in Financial Services
- **Source:** SAS Institute
- **URL:** https://www.sas.com/en_us/solutions/risk/model-risk-management.html
- **Relevance:** Practical MRM implementation; model inventory tooling; workflow
- **Key takeaways:**
  - Integrated model lifecycle workflow covering development through retirement
  - Model inventory and documentation management
  - Automated testing and validation support
- **Guide sections informed:** All; particularly inventory and workflow sections

---

## 3. Credit Scoring Specific Practices

### Siddiqi — Credit Risk Scorecards: Developing and Implementing Intelligent Credit Scoring
- **Source:** Naeem Siddiqi, Wiley, 2006 / 2017 (updated)
- **Relevance:** Core reference for credit scorecard development methodology; informs STD-001 for credit models
- **Key takeaways:**
  - Scorecard development process: data, exploratory analysis, variable treatment, modelling, scorecard scaling, validation
  - Documentation and governance expectations for scorecards
  - PSI and CSI monitoring methodology in detail
- **Guide sections informed:** STD-001, STD-004, Ch. 6.3–6.4 for credit models

---

### Anderson — The Credit Scoring Toolkit
- **Source:** Raymond Anderson, Oxford University Press, 2007
- **Relevance:** Comprehensive reference on credit scoring in regulated environments
- **Key takeaways:**
  - Regulatory compliance considerations for credit scoring
  - Validation and backtesting methodologies
  - Monitoring and model review
- **Guide sections informed:** STD-001, STD-003 for credit models

---

## 4. Reproducibility and Version Control

### Papers With Code — The ML Reproducibility Challenge
- **Source:** Community initiative, ongoing
- **URL:** https://paperswithcode.com/rc2022
- **Relevance:** Understanding reproducibility challenges; motivates STD-001 reproducibility requirements
- **Key takeaways:**
  - Reproducibility is difficult; must be designed for, not assumed
  - Seed management, environment pinning, data versioning are all necessary
- **Guide sections informed:** STD-001, Ch. 3 (Principle 3 — Reproducibility)

---

### DVC (Data Version Control)
- **Source:** Iterative.ai
- **URL:** https://dvc.org
- **Relevance:** Tool-level reference for data and model versioning; informs STD-001 tooling guidance
- **Key takeaways:**
  - Data versioning alongside code versioning
  - Experiment tracking and pipeline management
  - Model registry and artifact management
- **Guide sections informed:** STD-001, STD-006 (tooling recommendations)

---

## 5. Bias, Fairness, and Explainability

### Ribeiro, Singh, Guestrin — "Why Should I Trust You?" (LIME paper)
- **Source:** Proceedings of the 22nd ACM SIGKDD, 2016
- **URL:** https://arxiv.org/abs/1602.04938
- **Relevance:** Foundation for local explainability methods referenced in STD-008
- **Key takeaways:**
  - Local interpretable model-agnostic explanations
  - Practical approach to explaining individual predictions from black-box models
- **Guide sections informed:** STD-008

---

### Lundberg & Lee — A Unified Approach to Interpreting Model Predictions (SHAP)
- **Source:** Advances in Neural Information Processing Systems, 2017
- **URL:** https://arxiv.org/abs/1705.07874
- **Relevance:** Foundation for SHAP-based explainability referenced in STD-008 and Guide
- **Key takeaways:**
  - SHAP values as theoretically consistent approach to feature attribution
  - Both global and local interpretability
  - Widely adopted in banking model explanations
- **Guide sections informed:** STD-008, TMPL-001 (explainability section)

---

<!-- TODO: Add practical references on PSI/CSI threshold calibration, model drift detection methods, and any bank-specific tooling decisions. -->
