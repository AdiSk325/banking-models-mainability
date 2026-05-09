# Chapter 1 — Purpose, Scope and Applicability

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 1  
> **Linked Policy:** Model Risk Management Policy

---

## 1.1 Purpose

<!-- TODO: Write 2–3 paragraphs covering:
- Why this guide exists (governance rationale)
- What problem it solves (fragmentation, inconsistency, regulatory expectation)
- Its role as a "constitution" for model work — setting principles and structure, not procedures
-->

This Guide establishes the **governing framework** for the complete lifecycle of models used within the bank. It defines the minimum standards, required governance touchpoints, and assigned responsibilities that apply from the moment a model is conceived through to its retirement.

The Guide is designed to:

- Provide **data scientists, model owners, and all model stakeholders** with a clear, shared understanding of what is required at every stage of model work.
- Ensure that model risk is **identified, assessed, and managed** proportionally throughout the lifecycle.
- Satisfy the bank's obligations under applicable **regulatory and supervisory expectations** (see [Chapter 10 — Linked Documents](10_linked_documents.md) and [References](../04_references/01_regulatory_guidance.md)).
- Serve as the **master reference point** from which supporting standards, procedures, and templates derive their authority.

<!-- TODO: Add formal statement of authority — e.g. "This Guide is issued under authority of the Model Risk Management Policy approved by [Board/Committee]." -->

---

## 1.2 Scope and Applicability

### 1.2.1 What Is a Model?

For the purposes of this Guide, a **model** is defined as:

> A quantitative or algorithmic method that applies statistical, mathematical, computational, or expert-based logic to transform input data into outputs (scores, ratings, estimates, recommendations, or decisions) that inform or directly drive business decisions.

This definition is intentionally broad and covers:

- **Traditional statistical models** (e.g., logistic regression, linear regression).
- **Machine learning and AI models** (including supervised, unsupervised, and reinforcement learning approaches).
- **Rule-based scoring systems** where the rules are materially derived from data analysis or judgment.
- **Vendor-supplied models** used by the bank, even where the bank does not control the underlying methodology.
- **Regulatory capital models** (IRB PD, LGD, EAD, CCR, market risk, operational risk models).
- **IFRS 9 models** (PD, LGD, EAD, staging, macro-economic scenario models).
- **Business/decisioning models** (credit scoring, pricing, behavioural, CRM, collections).
- **Risk models** (market risk, liquidity risk, credit concentration, stress testing).

<!-- TODO: Confirm with MRM and Legal which specific model types are in scope. -->

### 1.2.2 What Is NOT in Scope

The following are **excluded** from the scope of this Guide unless otherwise specified by the Model Risk Management function:

- Simple calculation tools or spreadsheets that do not apply statistical methodology or judgment.
- Deterministic rule-based systems (e.g., eligibility checks with no model-derived thresholds).
- Industry-standard benchmarks or indices used as inputs without modification.
- Exploratory analyses or one-off research outputs not intended to drive decisions.

> **Note:** If there is doubt about whether a tool or methodology meets the definition of a model, the Model Risk Management function should be consulted. In ambiguous cases, a lighter-touch model registration and review may be appropriate.

### 1.2.3 Geographic and Organisational Applicability

<!-- TODO: Define which legal entities, business lines, and geographies are covered. -->

This Guide applies to:

- All **model development and use** within [Bank Name] and its material subsidiaries.
- All **third-party / vendor models** used to support material decisions.
- All **employees and contractors** who develop, validate, own, use, or govern models.

### 1.2.4 Proportionality

Requirements within this Guide are applied **proportionally** based on a model's classification tier (see [Chapter 4 — Model Classification and Risk Tiering](04_model_classification_tiering.md)). Higher-risk and higher-materiality models are subject to more rigorous requirements; lower-risk models may follow a simplified track.

---

## 1.3 Audience

| Audience | Relevance |
|----------|-----------|
| **Data Scientists / Model Developers** | Primary audience — day-to-day users of this guide throughout model development work |
| **Model Owners** | Understand ownership obligations across the lifecycle |
| **Model Validators / Independent Review** | Understand validation trigger points and independence requirements |
| **Model Risk Management (MRM)** | Enforce and maintain this framework |
| **IT / MLOps / Engineering** | Understand deployment and implementation controls |
| **Business Sponsors** | Understand approval and oversight obligations |
| **Compliance** | Confirm alignment with regulatory requirements |
| **Internal Audit** | Use as basis for assurance assessments |
| **Senior Management / Committees** | Understand governance expectations |

---

## 1.4 Relationship to Other Documents

This Guide sits at **Level 2** of the bank's model governance document hierarchy:

| Level | Document Type | Example |
|-------|--------------|---------|
| 1 | **Policy** | Model Risk Management Policy |
| 2 | **Guide / Framework** | ← This document |
| 3 | **Standards** | Model Development Standard, Validation Standard |
| 4 | **Procedures / SOPs** | Validation Procedure, Change Request Procedure |
| 5 | **Templates / Checklists** | Model Development Document, Monitoring Plan |

Where there is a conflict between this Guide and a subordinate document (standards, procedures, templates), this Guide takes precedence. Where there is a conflict between this Guide and the Model Risk Management Policy, the Policy takes precedence.

---

## 1.5 Document Governance

| Attribute | Detail |
|-----------|--------|
| Document owner | Model Risk Management |
| Review frequency | Annual, or following material regulatory change |
| Approval authority | <!-- TODO: Insert committee name --> |
| Version | DRAFT |
| Effective date | <!-- TODO: Insert date --> |

---

*Next: [Chapter 2 — Key Definitions](02_definitions.md)*
