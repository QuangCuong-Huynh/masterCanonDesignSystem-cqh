# Master Canon Design System CQH

> **Personal Portfolio & Master Canon Design System**
> Single-page portfolio and governing design specification for all visual output attributed to Cường Q. Huỳnh.

---

## Project Identity

| Field | Value |
|-------|-------|
| **Project Name** | Master Canon Design System CQH |
| **Canon Ref** | DESIGN-CANON-2026-001 |
| **Author** | Cường Q. Huỳnh |
| **Role** | Master Orchestrator · Virtual Librarian · IP Assets Professional · Infra & Data Architect · Solution Consultant |
| **Assisted By** | Claude-Sonnet-4.6 (Anthropic) |
| **Current Portfolio** | `v2.1.0` — QA cleared, 40/40 PASS |
| **Canon Status** | RATIFIED v1.0.0 → active, spec at v2.1.0 |
| **SRS Version** | `PORTFOLIO-SRS-2026-001 v2.1.0` |
| **License** | Personal IP · All rights reserved · Cường Q. Huỳnh © 2026 |

---

## Repository Structure

```
Master Canon Design System CQH/
│
├── README.md                          ← You are here
├── CHANGELOG.md                       ← Full version history
├── HISTORY.md                         ← Sprint & decision narrative
├── REQUIREMENTS.md                    ← Technical & governance requirements
│
├── docs/                              ← Master Canon Design Specification
│   ├── html/
│   │   ├── MASTER_CANON_DESIGN_SPEC_v1.0.1.html
│   │   └── MASTER_CANON_DESIGN_SPEC_v2.1.html    ← CURRENT (interactive, reactive)
│   ├── docx/
│   │   └── MASTER_CANON_DESIGN_SPEC_v1.0.1.docx
│   ├── md/
│   │   └── MASTER_CANON_DESIGN_SPEC_v1.0.1.md
│   └── governance/                      ← Enterprise Governance Framework & Git Strategy
│       ├── DATA_GOV_STANDARD.md         ← Universal Artifact Signature definitions
│       ├── GOVERNANCE_AND_STANDARDS.md  ← Prompt/AI lifecycle & ISO compliance
│       └── GIT_STRATEGY_POLICY.md       ← Repository Git and Semantic Versioning rules
│
├── portfolio/
│   ├── specs/                         ← Portfolio System Requirements Specification
│   │   ├── html/  PORTFOLIO_SRS_v2.1.html
│   │   ├── docx/  PORTFOLIO_SRS_v2.1.docx
│   │   └── md/    PORTFOLIO_SRS_v2.1.md
│   ├── data/
│   │   └── portfolio_data_v2.1.json   ← Content source of truth
│   ├── v1.0.0/  portfolio_v1.0.0.html  (pre-QA)
│   ├── v1.0.1/  portfolio_v1.0.1.html  (first QA-cleared)
│   ├── v1.0.2/  portfolio_v1.0.2.html  (a11y fixes)
│   ├── v2.0.0/  portfolio_v2.0.html    (SPA + JSON + 5 sections)
│   └── v2.1.0/  portfolio_v2.1.html    ← CURRENT (dropdown menu + fixes)
│
├── sprint-records/
│   └── SPRINT-01-06.md
└── .meta/
    └── SIGNATURES.md
```

---

## Quick Start

```bash
# Open current portfolio
open portfolio/v2.1.0/portfolio_v2.1.html

# Or serve locally
python3 -m http.server 8080
# → http://localhost:8080/portfolio/v2.1.0/portfolio_v2.1.html
```

The portfolio is **zero-dependency** — one HTML file, Google Fonts CDN only.

---

## Portfolio v2.1.0 — Feature Matrix

| Feature | Status |
|---------|--------|
| JSON-driven SPA (data from `PORTFOLIO_DATA`) | ✅ |
| Skeleton loaders during render | ✅ |
| **Dropdown design menu: 4 themes + 5 morphism styles** | ✅ |
| Binary Light/Dark toggle (☀️/🌙) | ✅ |
| `prefers-color-scheme` auto dark fallback | ✅ |
| Theme + morph persisted via `localStorage` | ✅ |
| Glassmorphism nav (backdrop-filter blur) | ✅ |
| Claymorphism project cards | ✅ |
| `data-morph` CSS drives all card surfaces | ✅ |
| SFIA v8 skills (L1–L7 dot bar + evidence links) | ✅ |
| Experience timeline | ✅ |
| Projects with STAR breakdown accordion | ✅ |
| Certifications with SHA-256 hash display | ✅ |
| Blog — Series → Posts nested | ✅ |
| Social links (GitHub, LinkedIn, website) | ✅ |
| Contact form: validation + `role="alert"` feedback | ✅ |
| Skip-to-content, ARIA landmarks, focus-visible | ✅ |
| Focus trap on mobile menu | ✅ |
| `prefers-reduced-motion` | ✅ |
| Font preload hints | ✅ |
| Print stylesheet | ✅ |
| JSON-LD Person schema, OG tags, canonical | ✅ |
| **QA Score (Sprint-06)** | **40/40 PASS** |

---

## Canon Design Specification

`DESIGN-CANON-2026-001` governs all visual output. Available in three formats:

| Format | File | Use |
|--------|------|-----|
| **HTML** | `docs/html/MASTER_CANON_DESIGN_SPEC_v2.1.html` | Interactive reference — live theme switcher, morphism demo |
| **DOCX** | `docs/docx/MASTER_CANON_DESIGN_SPEC_v1.0.1.docx` | Annotation, printing, formal distribution |
| **MD** | `docs/md/MASTER_CANON_DESIGN_SPEC_v1.0.1.md` | Version control, plain text reference |

### Canon Summary

**60/30/10 Color Law** — Primary (60%) canvas · Secondary (30%) structure · Accent (10%) signal · Exceptional (<1%) alerts.

**4 Themes** — Focus (blue) · Clarity (mint) · Warmth (terracotta) · Nightfall (violet/dark).

**5 Surface Styles** — Soft-Morphism · Glassmorphism · Claymorphism · Neumorphism · Academic Flat.

**Font Stack** — IBM Plex Sans (UI) · Libre Baskerville (academic) · Fira Code (mono).

---

## portfolio_data_v2.1.json — Integrity Policy

The data file follows a strict **no-hallucination** rule:

- All unknown/personal fields are marked `[OWNER: ...]` — must be replaced before publishing
- SFIA levels are honest self-assessment per SFIA v8 framework
- No fabricated company names, certifications, or dates
- Blog posts carry `"status": "draft"` until published
- `_meta.integrity_note` documents this policy in the file itself

---

## Governance & Signatures

Every ratified document carries a Canon Signature Block:

```
Doc Hash:   SHA-256([content])
UUID:       [uuidv7 on ratification]
Signed by:  Cường.Q.Huỳnh  → [signature]
Signed by:  System (Claude-Sonnet-4.6 | timestamp)
Signed by:  Authority (optional)
```

See `.meta/SIGNATURES.md` for all ratified document signatures.

**Canon DESIGN-CANON-2026-001 v1.0.0 — RATIFIED** ✓ — 2026-03-23, Cường Q. Huỳnh.

---

## Sprint History Summary

| Sprint | Subject | Output |
|--------|---------|--------|
| 01 | Portfolio MVP build | `portfolio_v1.0.1.html` |
| 02 | Canon ratification | Canon DOCX + HTML + MD · Canon RATIFIED |
| 03 | Portfolio QA fix + repo pack | `portfolio_v1.0.2.html` + repo zip |
| 04 | Doc integration (SRS, PWA-DSD, Morphism, SFIA) | `portfolio_v2.0.html` |
| 05 | Interactive theme/morphism switchers | `portfolio_v2.1.html` · Canon HTML reactive |
| 06 | JSON integrity + bug fixes + Portfolio SRS | `portfolio_v2.1.html` (fixed) · SRS 3-format · repo v2.1.0 |

---

*Master Canon Design System CQH · Author: Cường Q. Huỳnh · Assisted: Claude-Sonnet-4.6*
*Personal IP · All rights reserved · Cường Q. Huỳnh © 2026*
