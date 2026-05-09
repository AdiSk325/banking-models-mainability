# Model Lifecycle Guide — Table of Contents and Authoring Instructions

> **Status: DRAFT**  
> **Document owner:** Model Risk Management  
> **Last updated:** see git log

---

## Table of Contents

This directory contains the core chapters of the **Model Lifecycle Guide**. The guide is organized as a numbered sequence of chapters that build on each other logically.

### Chapter Map

| # | Chapter File | Section Title | Priority |
|---|-------------|---------------|----------|
| 1 | [01_purpose_scope_audience.md](01_purpose_scope_audience.md) | Purpose, Scope and Applicability | 🔴 Critical |
| 2 | [02_definitions.md](02_definitions.md) | Key Definitions | 🔴 Critical |
| 3 | [03_guiding_principles.md](03_guiding_principles.md) | Guiding Principles | 🔴 Critical |
| 4 | [04_model_classification_tiering.md](04_model_classification_tiering.md) | Model Classification and Risk Tiering | 🔴 Critical |
| 5 | [05_lifecycle_overview.md](05_lifecycle_overview.md) | End-to-End Model Lifecycle Overview | 🔴 Critical |
| 6 | [06_stage_requirements/](06_stage_requirements/) | Stage-by-Stage Requirements | 🔴 Critical |
| 7 | [07_roles_responsibilities.md](07_roles_responsibilities.md) | Roles and Responsibilities | 🟠 High |
| 8 | [08_required_artifacts.md](08_required_artifacts.md) | Required Artifacts and Minimum Documentation | 🟠 High |
| 9 | [09_controls_exceptions_escalation.md](09_controls_exceptions_escalation.md) | Controls, Exceptions and Escalation | 🟠 High |
| 10 | [10_linked_documents.md](10_linked_documents.md) | Links to Supporting Standards, Procedures and Templates | 🟡 Medium |
| 11 | [11_review_cycle.md](11_review_cycle.md) | Review Cycle of This Guide | 🟡 Medium |
| 12 | [12_appendices/](12_appendices/) | Appendices | 🟡 Medium |

---

## Stage Requirements Detail (Chapter 6)

| Stage | File | Section |
|-------|------|---------|
| 6.1 | [06_stage_requirements/01_initiation.md](06_stage_requirements/01_initiation.md) | Initiation |
| 6.2 | [06_stage_requirements/02_data_sourcing_assessment.md](06_stage_requirements/02_data_sourcing_assessment.md) | Data Sourcing and Assessment |
| 6.3 | [06_stage_requirements/03_design_development.md](06_stage_requirements/03_design_development.md) | Design and Development |
| 6.4 | [06_stage_requirements/04_testing_documentation.md](06_stage_requirements/04_testing_documentation.md) | Testing and Documentation |
| 6.5 | [06_stage_requirements/05_independent_validation.md](06_stage_requirements/05_independent_validation.md) | Independent Validation |
| 6.6 | [06_stage_requirements/06_approval_governance.md](06_stage_requirements/06_approval_governance.md) | Approval and Governance Review |
| 6.7 | [06_stage_requirements/07_deployment_implementation.md](06_stage_requirements/07_deployment_implementation.md) | Deployment and Implementation Controls |
| 6.8 | [06_stage_requirements/08_monitoring_periodic_review.md](06_stage_requirements/08_monitoring_periodic_review.md) | Monitoring and Periodic Review |
| 6.9 | [06_stage_requirements/09_change_management.md](06_stage_requirements/09_change_management.md) | Change Management |
| 6.10 | [06_stage_requirements/10_retirement_archiving.md](06_stage_requirements/10_retirement_archiving.md) | Retirement and Archiving |

---

## Authoring Instructions

### What This Guide Is

The **Model Lifecycle Guide** is a **governance-grade, risk-based framework** document. Its role is to:

- Define the **principles** that govern model work in the bank.
- Describe the **mandatory stages** of the model lifecycle and what must happen at each stage.
- Define **roles** and assign **responsibilities**.
- Specify **minimum required artifacts** for each model tier.
- Establish **governance and control** requirements.
- Serve as the **navigation hub** for supporting standards, procedures, and templates.

### What This Guide Is NOT

- It is not a technical tutorial or how-to guide.
- It is not a step-by-step procedure (those belong in `02_procedures/`).
- It is not a template (those belong in `03_templates/`).
- It is not a research paper.

### Tone and Style

- Clear, direct, declarative: use "must", "shall", "is required", "is prohibited".
- Avoid excessive technical jargon; define technical terms in `02_definitions.md`.
- Use tables and bullet points over long prose paragraphs.
- Each stage section should follow the **standard stage template** below.

### Standard Stage Section Template

```markdown
## Stage N.M — [Stage Name]

### Purpose
[One paragraph on why this stage exists and what it achieves.]

### Entry Criteria
[What must be true / complete before this stage begins.]

### Key Activities
[Bulleted list of the main activities that occur in this stage.]

### Roles
[Who does what — reference full descriptions in Chapter 7.]

### Required Outputs / Artifacts
[Mandatory deliverables from this stage — reference Chapter 8 for full list.]

### Exit Criteria / Stage Gate
[What must be true before the model progresses to the next stage.]

### Linked Documents
[Standards, procedures, templates that apply to this stage.]
```

---

*See [ROADMAP.md](../ROADMAP.md) for completion tracking.*
