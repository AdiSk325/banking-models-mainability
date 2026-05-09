# Drafting Notes

> **Purpose:** Running log of decisions, choices, and notes made during the drafting of the Model Lifecycle Guide.  
> **Add entries in reverse chronological order (newest at top).**

---

## 2026-05-09 — Framework Initialisation

**Summary of work done:**
- Created full documentation framework structure: `model_lifecycle_guide/`
- Created all chapter placeholders for the main Guide (`00_guide/`)
- Created supporting standards (STD-001 through STD-008)
- Created procedures (PROC-001 through PROC-006)
- Created templates (TMPL-001 through TMPL-006)
- Created references area (`04_references/`) with seeded content from regulatory guidance, supervisory expectations, standards, industry practices, consulting materials
- Created working notes area
- Updated root README.md

**Key structural decisions made:**
1. Guide is structured as a 10-chapter document with stage requirements broken into individual files (one per lifecycle stage). This makes collaborative authoring easier — different people can work on different stages simultaneously.

2. The document hierarchy follows 5 levels: Policy → Guide → Standards → Procedures → Templates. The Guide is Level 2 — it sets principles and framework, but defers detail to subordinate documents.

3. Tiering uses 3 tiers (1=Critical, 2=Significant, 3=Lower Risk) aligned with EBA Guidelines and SR 11-7 proportionality principle.

4. English filenames and consistent naming convention (`CODE-NNN_descriptive_name.md`) for scalability.

5. Every section file includes `<!-- TODO: ... -->` markers for content that still needs to be written.

6. References area is seeded with real regulatory sources (SR 11-7, EBA, ECB, BCBS 239, ISO/IEC TR 24028, NIST AI RMF, EU AI Act, GDPR) — these provide the primary inspiration for content.

**Next actions for Monday:**
- [ ] Start filling in detailed content in the main guide chapters, starting with Ch. 3 (Guiding Principles) which is the normative heart
- [ ] Fill in STD-001 (Development Standard) with actual technical requirements
- [ ] Fill in STD-002 (Documentation Standard) with required sections
- [ ] Fill in STD-003 (Validation Standard) with validation methodology detail
- [ ] Conduct stakeholder interviews to populate `06_internal_inspiration.md`
- [ ] Confirm actual committee names, approval authority levels with governance
- [ ] Confirm materiality thresholds with Risk and Finance
- [ ] Review ROADMAP.md and update status as work progresses

---

## Drafting Priorities for Monday, 12 May 2026

Based on the problem statement, the team wants to have a **ready document** by Monday, 12 May 2026. Given the scope, the priority order for content completion is:

### HIGH PRIORITY (must have):
1. Chapter 1 — Purpose, Scope, Audience (finalise the TODO sections)
2. Chapter 3 — Guiding Principles (already substantive — review and enhance)
3. Chapter 4 — Model Classification (finalise tiering matrix and thresholds)
4. Chapter 5 — Lifecycle Overview (confirm stage map is correct)
5. Stages 6.1–6.5 (initiation through validation) — most frequently used

### MEDIUM PRIORITY:
6. Stages 6.6–6.10 (approval through retirement)
7. Chapter 7 — Roles and Responsibilities
8. Chapter 8 — Required Artifacts
9. TMPL-001 and TMPL-002 (most important templates)

### LOWER PRIORITY (framework is already useful with placeholders):
10. STD-001 and STD-003 (most important standards — detailed technical content)
11. All other standards, procedures, templates

---

## Key Alignment Points to Confirm Internally

Before finalising the Guide, the following must be confirmed with the appropriate internal parties:

| Item | Owner | Priority |
|------|-------|---------|
| Committee names (Model Risk Committee, etc.) | Governance | 🔴 High |
| Approval authority levels by tier | MRM / Governance | 🔴 High |
| Tiering thresholds (financial, regulatory) | Risk / Finance | 🔴 High |
| Definition of model — alignment with Policy | Legal / Compliance | 🔴 High |
| Retention periods | Legal / Compliance | 🟡 Medium |
| KNF-specific requirements | Compliance | 🟡 Medium |
| IT/MLOps tooling constraints | IT | 🟡 Medium |
| EU AI Act applicability | Legal | 🟡 Medium |

---

*Add new entries above this line.*
