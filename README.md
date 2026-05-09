# Banking Models — Knowledge Repository & Model Lifecycle Guide

> **Primary focus:** Authoring workspace for the **Model Lifecycle Guide** — the governance-grade framework document ("constitution") for working with models in banking.  
> **Secondary:** Research and knowledge base on banking model types, methodologies, and regulatory requirements.

---

## 🎯 Repository Purpose

This repository serves two complementary purposes:

1. **Model Lifecycle Guide Workspace** (`model_lifecycle_guide/`) — The active authoring area for the bank's Model Lifecycle Guide and its supporting standards, procedures, and templates.

2. **Specialised Knowledge Base** (`01_classic_models/` through `05_model_lifecycle/`) — Research and knowledge documentation on banking model types, methodologies, governance, and regulatory requirements.

---

## 📚 Model Lifecycle Guide — Quick Start

> **If you are working on the Model Lifecycle Guide, start here.**

The `model_lifecycle_guide/` folder is the complete authoring workspace. It contains:

```
model_lifecycle_guide/
├── README.md              ← Navigation hub — START HERE
├── ROADMAP.md             ← Completion tracker
├── 00_guide/              ← Main guide chapters (the core document)
├── 01_supporting_standards/   ← Detailed standards (STD-001 to STD-008)
├── 02_procedures/         ← Step-by-step procedures (PROC-001 to PROC-006)
├── 03_templates/          ← Document templates (TMPL-001 to TMPL-006)
├── 04_references/         ← Regulatory guidance and inspiration sources
└── 05_working_notes/      ← Active drafting notes and open questions
```

**→ [Open Model Lifecycle Guide Workspace](model_lifecycle_guide/README.md)**

---

## 🗂️ Full Repository Structure

```
banking-models-mainability/
│
├── model_lifecycle_guide/          ← Model Lifecycle Guide authoring workspace
│   ├── README.md                   ← Navigation hub
│   ├── ROADMAP.md                  ← Completion status tracker
│   ├── 00_guide/                   ← Main guide (10 chapters + appendices)
│   │   ├── 01_purpose_scope_audience.md
│   │   ├── 02_definitions.md
│   │   ├── 03_guiding_principles.md
│   │   ├── 04_model_classification_tiering.md
│   │   ├── 05_lifecycle_overview.md
│   │   ├── 06_stage_requirements/  ← One file per lifecycle stage (10 stages)
│   │   ├── 07_roles_responsibilities.md
│   │   ├── 08_required_artifacts.md
│   │   ├── 09_controls_exceptions_escalation.md
│   │   ├── 10_linked_documents.md
│   │   ├── 11_review_cycle.md
│   │   └── 12_appendices/          ← RACI, Inventory Schema, Glossary
│   ├── 01_supporting_standards/    ← STD-001 to STD-008
│   ├── 02_procedures/              ← PROC-001 to PROC-006
│   ├── 03_templates/               ← TMPL-001 to TMPL-006
│   ├── 04_references/              ← Regulatory, standards, industry, internal
│   └── 05_working_notes/           ← Active drafting notes
│
├── 01_classic_models/              ← PD, LGD, regulatory capital, IFRS 9
├── 02_ml_models/                   ← Supervised and unsupervised ML
├── 03_decision_support/            ← Decision support systems and scoring
├── 04_CRM/                         ← CRM and customer analytics models
└── 05_model_lifecycle/             ← Model lifecycle research and knowledge
    ├── specialized_knowledge/      ← Deep-dive research knowledge base
    └── templates/                  ← Research templates
```

---

## 📋 Document Hierarchy

The Model Lifecycle Guide is a **Level 2 governance document** in the following hierarchy:

| Level | Type | Location |
|-------|------|----------|
| **1** | **Policy** — Model Risk Management Policy | External / Compliance |
| **2** | **Guide / Framework** ← this document | `model_lifecycle_guide/00_guide/` |
| **3** | **Standards** | `model_lifecycle_guide/01_supporting_standards/` |
| **4** | **Procedures / SOPs** | `model_lifecycle_guide/02_procedures/` |
| **5** | **Templates / Checklists** | `model_lifecycle_guide/03_templates/` |

---

## 👥 Who Is This Repository For?

| Role | What to use |
|------|-------------|
| **Data Scientists / Model Developers** | Model Lifecycle Guide (primary audience) |
| **Model Owners** | Guide — especially Roles (Ch. 7), Stage requirements (Ch. 6) |
| **Model Risk Management** | Guide + Standards + Procedures |
| **Independent Validators** | STD-003, PROC-002, TMPL-002 |
| **IT / MLOps** | STD-006, Ch. 6.7 |
| **Compliance / Audit** | Guide — all chapters; References |
| **Governance Committees** | Guide — Ch. 9; Stage gates in Ch. 6 |

---

## 🚀 Next Steps

1. **Read the [Model Lifecycle Guide README](model_lifecycle_guide/README.md)** to understand the workspace.
2. **Check the [ROADMAP](model_lifecycle_guide/ROADMAP.md)** for current completion status and priorities.
3. **Review [Open Questions](model_lifecycle_guide/05_working_notes/open_questions.md)** for items needing resolution before finalisation.
4. **Check [References](model_lifecycle_guide/04_references/)** for source material to draw on when writing guide content.

---

## 📖 Scope of Banking Knowledge (Research Base)

The `01_classic_models/` through `05_model_lifecycle/` directories contain research knowledge on:

- **Classic Models:** PD (Probability of Default), LGD (Loss Given Default), Regulatory Capital, IFRS 9
- **Machine Learning Models:** Supervised learning for credit risk, unsupervised learning
- **Decision Support:** Scoring systems, application scorecards, decisioning models
- **CRM Models:** Customer segmentation, retention, propensity models
- **Model Lifecycle Knowledge:** Governance frameworks, validation methodologies, monitoring, MLOps

---

## 🤝 Contributing

- See `CONTRIBUTING.md` for contribution guidelines.
- English filenames; consistent `SECTION-NNN_descriptive_name.md` naming.
- Mark incomplete sections with `<!-- TODO: ... -->`.
- All documentation changes should be reviewed before merging to main.

---

*This repository is an internal knowledge and documentation workspace. Contents are not intended for external distribution.*