# Model Lifecycle Guide — Documentation Framework

> **Status:** In active drafting | **Target completion:** Monday, 12 May 2026  
> **Document type:** Governance-grade framework ("constitution")  
> **Audience:** Data Scientists, Model Owners, Model Risk Management, Validators, IT/MLOps, Compliance, Audit

---

## Purpose of This Repository Area

This folder contains the full authoring workspace for the **Model Lifecycle Guide** — the governing framework document ("constitution") that defines how models are developed, validated, deployed, monitored, changed, and retired within the bank.

The Guide itself is a **high-level framework document**: it sets principles, defines lifecycle stages, assigns responsibilities, and mandates minimum artifacts. It does **not** replace detailed standards, procedures, and templates — it links to them.

---

## Document Hierarchy

```
Level 1 — Policy
    └── Model Risk Management Policy (owned by Risk/Compliance)

Level 2 — Guide / Framework  ← THIS DOCUMENT
    └── Model Lifecycle Guide  (this workspace)

Level 3 — Supporting Standards
    └── model_lifecycle_guide/01_supporting_standards/

Level 4 — Procedures / SOPs
    └── model_lifecycle_guide/02_procedures/

Level 5 — Templates / Checklists / Examples
    └── model_lifecycle_guide/03_templates/
```

---

## Folder Structure

```
model_lifecycle_guide/
├── README.md                        ← You are here: navigation hub
├── ROADMAP.md                       ← Authoring completion tracker
│
├── 00_guide/                        ← Main guide chapters (the core document)
│   ├── README.md                    ← Table of contents and authoring instructions
│   ├── 01_purpose_scope_audience.md
│   ├── 02_definitions.md
│   ├── 03_guiding_principles.md
│   ├── 04_model_classification_tiering.md
│   ├── 05_lifecycle_overview.md
│   ├── 06_stage_requirements/       ← One file per lifecycle stage
│   │   ├── README.md
│   │   ├── 01_initiation.md
│   │   ├── 02_data_sourcing_assessment.md
│   │   ├── 03_design_development.md
│   │   ├── 04_testing_documentation.md
│   │   ├── 05_independent_validation.md
│   │   ├── 06_approval_governance.md
│   │   ├── 07_deployment_implementation.md
│   │   ├── 08_monitoring_periodic_review.md
│   │   ├── 09_change_management.md
│   │   └── 10_retirement_archiving.md
│   ├── 07_roles_responsibilities.md
│   ├── 08_required_artifacts.md
│   ├── 09_controls_exceptions_escalation.md
│   ├── 10_linked_documents.md
│   ├── 11_review_cycle.md
│   └── 12_appendices/
│       ├── README.md
│       ├── A_raci_matrix.md
│       ├── B_model_inventory_schema.md
│       └── C_glossary.md
│
├── 01_supporting_standards/         ← Level-3 standards (detailed rules)
│   ├── README.md
│   ├── STD-001_model_development_standard.md
│   ├── STD-002_model_documentation_standard.md
│   ├── STD-003_validation_standard.md
│   ├── STD-004_monitoring_standard.md
│   ├── STD-005_change_management_standard.md
│   ├── STD-006_deployment_standard.md
│   ├── STD-007_data_quality_standard.md
│   └── STD-008_ai_ml_explainability_standard.md
│
├── 02_procedures/                   ← Level-4 procedures / SOPs
│   ├── README.md
│   ├── PROC-001_model_initiation_procedure.md
│   ├── PROC-002_validation_procedure.md
│   ├── PROC-003_model_inventory_procedure.md
│   ├── PROC-004_change_request_procedure.md
│   ├── PROC-005_retirement_procedure.md
│   └── PROC-006_exception_management_procedure.md
│
├── 03_templates/                    ← Level-5 templates and checklists
│   ├── README.md
│   ├── TMPL-001_model_development_document.md
│   ├── TMPL-002_validation_report.md
│   ├── TMPL-003_monitoring_plan.md
│   ├── TMPL-004_change_request_form.md
│   ├── TMPL-005_retirement_form.md
│   └── TMPL-006_release_readiness_checklist.md
│
├── 04_references/                   ← Source material and inspiration
│   ├── README.md
│   ├── 01_regulatory_guidance.md
│   ├── 02_supervisory_expectations.md
│   ├── 03_international_standards.md
│   ├── 04_industry_practices.md
│   ├── 05_consulting_materials.md
│   └── 06_internal_inspiration.md
│
└── 05_working_notes/                ← Drafting scratchpad
    ├── README.md
    ├── drafting_notes.md
    └── open_questions.md
```

---

## Quick Navigation for Contributors

| I want to…                                   | Go to…                                             |
|----------------------------------------------|----------------------------------------------------|
| Draft the main guide content                 | `00_guide/`                                        |
| Write a specific lifecycle stage section     | `00_guide/06_stage_requirements/`                  |
| Check what's done / what's missing           | `ROADMAP.md`                                       |
| Write or refine a supporting standard        | `01_supporting_standards/`                         |
| Write or refine a procedure / SOP            | `02_procedures/`                                   |
| Create or update a template / checklist      | `03_templates/`                                    |
| Add a regulatory or industry reference       | `04_references/`                                   |
| Leave working notes or open questions        | `05_working_notes/`                                |

---

## Authoring Conventions

1. **Language:** English for all filenames and headings; body content may be bilingual (EN/PL) during drafting.
2. **Naming:** `SECTION-NUMBER_snake_case_name.md`
3. **Status tags:** Use `> **Status: DRAFT / IN REVIEW / APPROVED**` at the top of each file.
4. **Cross-links:** Use relative markdown links (e.g., `[Validation Standard](../01_supporting_standards/STD-003_validation_standard.md)`).
5. **Placeholders:** Mark incomplete sections with `<!-- TODO: ... -->` comments.
6. **Principles:** The guide should answer *what* and *why*, not *how step-by-step*.

---

## Relationship to Existing Repository Content

The `05_model_lifecycle/specialized_knowledge/` directory holds research and reference knowledge accumulated by agents. The **Model Lifecycle Guide** workspace here (`model_lifecycle_guide/`) is the **authoring workspace** — it is where the formal governance document is being written based on that research.

---

*Last updated: see git log | Maintainer: see CODEOWNERS*
