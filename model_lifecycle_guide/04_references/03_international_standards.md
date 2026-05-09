# International Standards — Reference Collection

> **Purpose:** International standards and frameworks that are directly relevant to model governance in banking.

---

## 1. ISO/IEC Standards

### ISO/IEC TR 24028:2020 — AI Trustworthiness
- **Source:** ISO/IEC, 2020
- **URL:** https://www.iso.org/standard/77608.html
- **Relevance:** AI model trustworthiness, explainability, fairness, and robustness
- **Key takeaways:**
  - Defines key dimensions of AI trustworthiness: accuracy, robustness, reliability, interpretability, explainability, fairness, privacy, safety
  - Useful framework for AI/ML model risk assessment in tiering and explainability requirements
  - Supports STD-008 content development
- **Guide sections informed:** Ch. 4 (classification of ML models), STD-008

---

### ISO 31000:2018 — Risk Management
- **Source:** ISO, 2018
- **URL:** https://www.iso.org/standard/65694.html
- **Relevance:** General risk management principles applicable to model risk governance
- **Key takeaways:**
  - Principles of risk identification, assessment, and treatment that underpin the model risk framework
  - Risk-based approach to governance
  - Aligns with Principle 1 (Risk-Based Approach) in the Guide
- **Guide sections informed:** Ch. 3 (Principles), Ch. 9 (Controls)

---

## 2. NIST (US National Institute of Standards and Technology)

### NIST AI Risk Management Framework (AI RMF 1.0)
- **Source:** NIST, January 2023
- **URL:** https://airc.nist.gov/RMF_Overview
- **Relevance:** AI-specific risk management framework; useful complement to SR 11-7 for ML models
- **Key takeaways:**
  - Four core functions: GOVERN, MAP, MEASURE, MANAGE
  - Addresses trustworthiness of AI systems across full lifecycle
  - Strong coverage of explainability, bias mitigation, accountability
  - Useful for structuring AI/ML-specific requirements within the Guide
- **Guide sections informed:** Ch. 3 (Principles), STD-008, Ch. 4 (tier classification for ML models)

---

## 3. Basel Committee on Banking Supervision (BCBS)

### BCBS 239 — Principles for Effective Risk Data Aggregation and Risk Reporting
- **Source:** BCBS, January 2013
- **URL:** https://www.bis.org/publ/bcbs239.pdf
- **Relevance:** Data governance, data quality, data lineage — critical for STD-007 and Ch. 6.2
- **Key takeaways:**
  - 11 principles: governance, data architecture, accuracy, completeness, timeliness, adaptability, reporting (4 principles)
  - Supervisory expectation for G-SIBs and many other institutions
  - Strong alignment with model data quality requirements
- **Guide sections informed:** Ch. 6.2, STD-007

---

### Basel III / CRR — IRB Model Requirements
- **Source:** Basel Committee / EU CRR (Capital Requirements Regulation)
- **URL:** https://www.bis.org/bcbs/publ/d424.pdf (IRB revisions)
- **Relevance:** Specific regulatory capital model requirements (Tier 1)
- **Key takeaways:**
  - Requirements for PD, LGD, EAD estimation methodology
  - Data requirements (observation periods, definitions of default)
  - Annual review and revalidation requirements
  - Regulatory approval process for model changes
- **Guide sections informed:** Ch. 4 (Tier 1 classification), Ch. 6.5 (validation), Ch. 6.9 (change)

---

## 4. European Union — AI Act

### EU Artificial Intelligence Act
- **Source:** European Parliament and Council, 2024 (final text — verify current status)
- **URL:** https://artificialintelligenceact.eu/
- **Relevance:** Emerging regulatory requirement for AI systems in banking; particularly relevant for high-risk AI systems (credit scoring, AML, fraud detection)
- **Key takeaways:**
  - Classification of AI systems by risk level (unacceptable / high / limited / minimal)
  - High-risk AI systems (including credit scoring) subject to: conformity assessment, documentation, logging, human oversight, accuracy requirements
  - Provides a parallel tiering framework to consider alongside internal model tiering
  - Explainability and human oversight requirements for high-risk systems
  - Overlap with GDPR Art. 22 (automated decision-making)
- **Guide sections informed:** Ch. 4 (AI/ML model classification), STD-008, Ch. 6.7 (deployment controls)
- **Note:** <!-- TODO: Confirm current applicability timeline and which model types in the bank's portfolio are classified as high-risk AI systems under the Act. -->

---

## 5. GDPR

### General Data Protection Regulation (GDPR)
- **Source:** EU Regulation 2016/679
- **URL:** https://gdpr-info.eu/
- **Relevance:** Data used in models; automated decision-making; right to explanation
- **Key takeaways:**
  - Article 22: Rights related to automated individual decision-making (right to human review, right to explanation)
  - Article 25: Data protection by design and by default (relevant to model development)
  - Data minimisation and purpose limitation (relevant to feature selection)
  - Retention and deletion obligations for training data
- **Guide sections informed:** Ch. 6.2 (Data), Ch. 6.10 (Retirement — data deletion), STD-007, STD-008

---

<!-- TODO: Add references to Polish-specific AI/ML regulation as it develops. Add any sector-specific fintech/banking regulations relevant to the bank's model types. -->
