# Regulatory Guidance — Reference Collection

> **Purpose:** Key regulatory guidance documents that should inform the content of the Model Lifecycle Guide.  
> **Priority reading for:** All sections of the Guide, especially Principles, Validation, Governance.

---

## 1. United States — Federal Reserve / OCC

### SR 11-7 — Guidance on Model Risk Management
- **Source:** Board of Governors of the Federal Reserve System / OCC, April 2011
- **URL:** https://www.federalreserve.gov/supervisionreg/srletters/sr1107.htm
- **OCC companion:** OCC Bulletin 2011-12 — https://www.occ.gov/news-issuances/bulletins/2011/bulletin-2011-12a.pdf
- **Relevance:** Entire Guide — this is the foundational MRM framework
- **Key takeaways:**
  - Defines model, model risk, and the expectation for bank-wide model risk management
  - Three elements of sound model risk management: development/implementation, validation, governance/controls
  - Strong emphasis on validation independence, scope, and documentation
  - Defines monitoring and periodic review obligations
  - Discusses governance and organisational responsibilities
  - Widely accepted international benchmark even outside the US
- **Guide sections informed:** Chapters 1, 2, 3, 5, 6.3–6.8, 7, 9

---

### OCC Bulletin 2011-12
- **Source:** Office of the Comptroller of the Currency, April 2011
- **URL:** https://www.occ.gov/news-issuances/bulletins/2011/bulletin-2011-12a.pdf
- **Relevance:** Complementary to SR 11-7; issued simultaneously for national banks
- **Key takeaways:**
  - Applies the same principles as SR 11-7 to OCC-supervised institutions
  - Useful reference for US regulatory capital context
- **Guide sections informed:** All

---

## 2. European Banking Authority (EBA)

### EBA Guidelines on Model Risk Management
- **Source:** European Banking Authority, 2023 (EBA/GL/2023/01 or latest version — verify current reference)
- **URL:** https://www.eba.europa.eu/regulation-and-policy/model-risk-management
- **Relevance:** EU-specific regulatory expectations; directly applicable to EU banks
- **Key takeaways:**
  - Defines model risk management framework for all EU institutions
  - Covers governance, validation, model inventory, risk identification, and model risk appetite
  - Introduces proportionality principle aligned with institution size and complexity
  - Addresses data governance, explainability, and AI/ML-specific considerations
  - Requires documentation of model risk management in policies and procedures
- **Guide sections informed:** All chapters; particularly strong on governance (Ch. 9), classification (Ch. 4), inventory
- **Note:** Check EBA website for most current version; guidelines are periodically updated

---

### EBA/GL/2019/05 — Guidelines on ICT and Security Risk Management
- **Source:** EBA, 2019
- **URL:** https://www.eba.europa.eu/regulation-and-policy/internal-governance/guidelines-ict-and-security-risk-management
- **Relevance:** MLOps, deployment controls, IT governance aspects
- **Key takeaways:**
  - Security and operational risk aspects of model deployment
  - Change management requirements from IT governance perspective
- **Guide sections informed:** Chapter 6.7 (Deployment), STD-006

---

## 3. European Central Bank (ECB)

### ECB Guide to Internal Models
- **Source:** European Central Bank, 2018 (updated versions available)
- **URL:** https://www.bankingsupervision.europa.eu/ecb/pub/pdf/ssm.imiguideline201807.en.pdf
- **Relevance:** IRB and internal model governance; directly relevant for regulatory capital models (Tier 1)
- **Key takeaways:**
  - ECB supervisory expectations for internal model development, validation, and governance
  - Detailed requirements for PD, LGD, EAD models under CRR/Basel
  - Strong requirements for validation independence and scope
  - Documentation requirements for regulatory models
  - Covers initial approval, ongoing monitoring, and change processes
- **Guide sections informed:** Ch. 4 (Tier 1 classification), Ch. 6.3–6.5, Ch. 6.8, Ch. 6.9
- **Note:** Check ECB SSM website for current version; subject to ongoing review

---

## 4. Polish Financial Supervision Authority (KNF)

### KNF — Recommendations on Internal Rating Systems
- **Source:** Komisja Nadzoru Finansowego (KNF)
- **URL:** https://www.knf.gov.pl — search for "rekomendacje modele"
- **Relevance:** Polish-specific regulatory expectations for model governance
- **Key takeaways:**
  - Polish supervisory expectations on credit scoring and IRB models
  - Documentation and validation requirements
  - Governance obligations for Polish-licensed banks
- **Guide sections informed:** All; especially Tier 1 credit models
- **Note:** <!-- TODO: Identify current active KNF recommendations on model risk management. Check with Compliance for current list. -->

---

## 5. Basel Committee on Banking Supervision (BCBS)

### BCBS 239 — Principles for Effective Risk Data Aggregation and Risk Reporting
- **Source:** Basel Committee on Banking Supervision, January 2013 (revised)
- **URL:** https://www.bis.org/publ/bcbs239.pdf
- **Relevance:** Data governance aspects — particularly relevant to STD-007 (Data Quality Standard)
- **Key takeaways:**
  - 11 principles covering data accuracy, completeness, timeliness, and governance
  - Strong alignment with model data requirements
  - Regulatory expectation for systemically important banks
- **Guide sections informed:** Ch. 6.2 (Data), STD-007

---

## Quick Reference: Which Guide Chapter Does Each Source Inform?

| Chapter | Primary Reference(s) |
|---------|---------------------|
| Ch. 1 — Purpose & Scope | SR 11-7, EBA Guidelines |
| Ch. 2 — Definitions | SR 11-7, EBA Guidelines |
| Ch. 3 — Guiding Principles | SR 11-7, EBA Guidelines, ECB Guide |
| Ch. 4 — Classification | EBA Guidelines, SR 11-7, ECB Guide |
| Ch. 5 — Lifecycle Overview | SR 11-7, EBA Guidelines |
| Ch. 6.2 — Data | BCBS 239, STD-007, SR 11-7 |
| Ch. 6.3–6.4 — Development | SR 11-7, EBA Guidelines |
| Ch. 6.5 — Validation | SR 11-7 Section V, EBA Guidelines, ECB Guide |
| Ch. 6.6 — Governance | EBA Guidelines, SR 11-7 |
| Ch. 6.7 — Deployment | EBA ICT Guidelines, SR 11-7 |
| Ch. 6.8 — Monitoring | SR 11-7, EBA Guidelines |
| Ch. 6.9 — Change | SR 11-7, ECB Guide |
| Ch. 6.10 — Retirement | SR 11-7, EBA Guidelines |
| Ch. 7 — Roles | SR 11-7, EBA Guidelines |
| Ch. 9 — Governance/Exceptions | SR 11-7, EBA Guidelines |
