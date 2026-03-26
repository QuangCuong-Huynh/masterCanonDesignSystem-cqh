# Universal Git Strategy & Release Policy

**ID:** GOV-GIT-STD-001 | **Version:** 1.0.0 | **Status:** Active
**Owner:** Cường Q. Huỳnh (Master Orchestrator / Authority Official)
**Scope:** `masterCanonDesignSystem-cqh`

This document defines the strict version control, branching, and commit semantics required to operate within the Master Canon Design System. It aligns Git operations with the enterprise Data Governance Standard and the ISO-compliant System Prompt Framework.

---

## 1. Branching Architecture

The repository adheres to a stringent, simplified multi-agent flow:

- **`main` (Production/Ratified):**
  - Immutable history. No direct pushes permitted without PO (Product Owner) ratification.
  - Every commit on `main` MUST represent a complete, functional, and verified state.
  - Represents the single source of truth for all compliant IP assets.

- **`sprint/*` (Agile Iteration Branches):**
  - Used for encapsulating all work within a defined Agile sprint (e.g., `sprint/09-data-governance`).
  - Merged into `main` only after the full **Agile Simulation Loop** (Phase 2 & 3) is completed and simulated QA agents (QA Director, Creative Products Director, PM/BA, Multirole Engineer) provide sign-off.

- **`feature/*` / `fix/*` (Atomic Changes):**
  - Short-lived branches for isolated development tasks.
  - Must be merged into their parent `sprint/*` branch or documented thoroughly before reaching `main`.

---

## 2. Commit Semantics & Verification

Commits must follow the **Conventional Commits** standard to maintain an automated, machine-readable history that AI agents can parse for Changelog generation.

### Allowed Prefixes
- `feat:` — New capabilities, artifacts, or design tokens.
- `fix:` — Defect resolution (must map to a QA trace or bug report).
- `docs:` — Updates to documentation, SRS, or Governance frameworks.
- `chore:` — Maintenance, tooling, or dependency updates.
- `refactor:` — Code changes that neither fix a bug nor add a feature.

### Commit Body Rules
1. **Context:** If the commit resolves a specific Backlog Item, it must be mentioned (e.g., `Resolves BACKLOG-DL-001`).
2. **Signature Adherence:** For commits that introduce or modify Ratified IP Assets or Canonical documents, the commit body SHOULD explicitly state that a cryptographic signature (UUIDv7 + SHA256) was applied in `.meta/SIGNATURES.md` or within the file itself.

**Example Commit:**
```text
docs: migrate enterprise data governance standards

- Imported DATA_GOV_STANDARD.md
- Imported GOVERNANCE_AND_STANDARDS.md
- Synchronized compliance matrices with the Prompt Governance Framework.

Ratified Signature applied inside documents.
```

---

## 3. Versioning & Tagging

This repository strictly implements **Semantic Versioning 2.0.0** (`MAJOR.MINOR.PATCH`).

- **Version Bump Triggers:**
  - `MAJOR`: Breaking changes to the Master Canon, architectural shifts, or major framework overhauls.
  - `MINOR`: New features, agile sprints completed seamlessly, or significant documentation expansions (e.g., a new Persona added).
  - `PATCH`: Hotfixes, typo corrections, or minor JSON data updates.

- **Tagging Mandatory:**
  Every release milestone merged into `main` MUST be accompanied by an annotated Git Tag (e.g., `git tag -a v2.3.0 -m "Release v2.3.0"`).

---

## 4. Pull Requests & Ratification Gates

As managed by the `.agents/workflows/agile_simulation.md` framework:
1. Code and documentation are prepared by the executing AI/Engineer.
2. The simulation loop processes feedback from all Stakeholder Personas.
3. A formal `SPRINT-XX` document is generated in `sprint-records/`.
4. The **Authority Official (Cường Q. Huỳnh)** reviews the output.
5. If Approved, the execution agent commits the code, tags the release, and generates the explicit Ratification Signature in the payload. 

*No artifact attains RATIFIED status without the execution of these gates.*

---
```yaml
---
# ── UNIVERSAL ARTIFACT SIGNATURE ──────────────────────────────
artifact_id:   "019f7a52-c3f2-7489-8d1e-2abf12c8a011"
doc_id:        "GOV-GIT-STD-001"
title:         "Universal Git Strategy & Release Policy"
version:       "1.0.0"
status:        "ratified"
dc:
  creator:     "Antigravity Agent"
  date:        "2026-03-27T03:00:00+07:00"
  type:        "policy"
  format:      "text/markdown"
---
```
