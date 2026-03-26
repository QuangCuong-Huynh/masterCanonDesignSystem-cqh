# CHANGELOG

> **Project:** Master Canon Design System CQH
> **Format:** Keep a Changelog · Semantic Versioning
> **Author:** Cường Q. Huỳnh · **Maintained by:** Cường Q. Huỳnh + Claude-Sonnet-4.6

---

## [Unreleased]

_Backlog items pending next sprint:_

- `BACKLOG-DL-001` — Add icon stroke-width spec (1.5px / 2px) to Canon Appendix B
- `BACKLOG-FE-001` — Document `data-theme` attribute alongside class-based switching in Canon Part IX
- `BACKLOG-FE-002` — Expand all 4 theme override blocks in Canon Part IX CSS reference
- `BACKLOG-DI-001` — Add `governs:` and `derived_from:` fields to Canon metadata header
- `BACKLOG-002` — Connect contact form to backend / email service
- `BACKLOG-003` — Replace `[OWNER: ...]` placeholders in `portfolio.json` with real personal data

---

## [2.3.0] — 2026-03-27 — Sprint-08: Full Professional Agent Team Expansion

**Scope:** `.agents/personas/*` · `.agents/workflows/agile_simulation.md` · `sprint-records/SPRINT-08-ENHANCED-AGENT-TEAM.md`
**Simulation QA:** Agile Feedback Loop — PASS (portfolio validated by new extended setup)

### Added

- **AGENT-PERSONAS [MAJOR]** — Imported enterprise-grade stakeholder personas from external `prompt-library`: `qa_director.md`, `creative_products_director.md`, `pm_ba.md`, and `engineer_multirole.md`.
- **AGENT-WORKFLOW [HIGH]** — Enhanced `.agents/workflows/agile_simulation.md` Phase 2 feedback loops to mandate reviews from all new QA and Stakeholder agents before PO approval.
- **SPRINT-DOC [INFO]** — Generated `sprint-records/SPRINT-08-ENHANCED-AGENT-TEAM.md` documenting the simulated internal QA loop performed by the extended team on `portfolio_latest.html`.

---

## [2.2.0] — 2026-03-27 — Sprint-07: Dynamic Data Load + QA Sign-off

**Scope:** `portfolio_latest.html` · `portfolio/data/portfolio.json` · `CHANGELOG.md` · `sprint-records/SPRINT-07-QA-REVIEW.md`
**QA Score:** Agile QA Loop — PASS (see `sprint-records/SPRINT-07-QA-REVIEW.md`)

### Changed

- **DATA-SEP [CRITICAL]** — Removed hardcoded `PORTFOLIO_DATA` object (was inline ~6KB JSON blob in `<script>` tag). Replaced with `async loadPortfolioData()` using `fetch('data/portfolio.json')`.
- **ERROR-HANDLE [HIGH]** — Added `try...catch` with graceful UI fallback: hero section displays styled error and console log on fetch failure.
- **VERSION-BUMP [INFO]** — All version references bumped from `v2.1.0` → `v2.2.0` across CSS header, hero card badge, footer meta, JS comment, and dynamic footer renderer fallback.
- **JSON-META [INFO]** — `portfolio.json` `_meta.version` updated to `2.2.0` with new changelog entry for the dynamic load feature.

### Added

- `portfolio/v2.2.0/portfolio_v2.2.html` — Version archive snapshot.
- `sprint-records/SPRINT-07-QA-REVIEW.md` — Full Agile QA Loop sign-off document.

```text
Version: v2.2.0
Author: Cường.Q.Hùynh
Virtual Librarian Notebooklm, Assistances: Claude GPT Perplexity Gemini
Ratified Signature Context: v2.2.0 Release & QA Sign-off
UUIDv7: 019f7a3c-2d44-7b8e-a1c0-4e7f3b9d5a12
Timestamp: 2026-03-27T02:45:25+07:00
Signed by Contributor: System Agent
Signed by System: Antigravity
```

---

## [2.1.0] — 2026-03-23 — Sprint-06: JSON Integrity + Bug Fixes + Portfolio SRS

**Scope:** `portfolio_v2.1.html` (fixes) · `portfolio_data_v2.1.json` · Portfolio SRS (3 formats) · Repo repack
**QA Score:** 40/40 PASS

### Fixed

- **SCRIPT-BAL [HIGH]** — Unclosed `<script>` tag left by previous sprint's duplicate-block removal. Orphaned JS comment `// ── EMBEDDED DATA...` was sitting outside the script tag, causing the parser to treat it as HTML text. Added `</script>` closure and removed orphan.
- **DEAD-LINKS [HIGH]** — 4 dead `href="#"` links:
  - Hero resume button → `assets/resume.pdf` (JS overrides at runtime from JSON)
  - About resume link → `assets/resume.pdf`
  - Contact LinkedIn link → `https://linkedin.com` (JS overrides with real data from JSON)
  - Contact GitHub link → `https://github.com` (JS overrides with real data from JSON)
- **VERSION [INFO]** — Stale `v1.0.2` reference in CSS comment block → updated to `v2.1.0`

### Added

- `portfolio_data_v2.1.json` — Standalone JSON data file:
  - `_meta` block with `doc_id`, `version`, `integrity_note`, `changelog`
  - All personal/unknown fields marked `[OWNER: ...]` — zero hallucination
  - `"status": "draft"` on all blog posts
  - SHA-256 note on canon cert hash
  - Clean schema matching SPA data contract
- `PORTFOLIO_SRS_v2.1.html` — Interactive Portfolio System Requirements Specification:
  - Canon-styled, sidebar nav, 4-theme switcher, reading progress bar
  - Sections: Purpose, Functional Req, Non-Functional Req, Design System, Data Contract, Quality Gate
- `PORTFOLIO_SRS_v2.1.docx` — Word document version of Portfolio SRS (A4, header/footer, page numbers)
- `PORTFOLIO_SRS_v2.1.md` — Markdown source of Portfolio SRS

### Changed

- `portfolio.json` inline data updated to clean v2.1 dataset (no hallucinated company names or certs)
- Repo structure extended with `portfolio/specs/` and `portfolio/data/` directories
- `README.md` updated with full v2.1.0 feature matrix and integrity policy
- `CHANGELOG.md` updated with Sprint-06 record

---

## [2.1.0-pre] — 2026-03-23 — Sprint-05: Interactive Theme & Morphism Switchers

**Scope:** `portfolio_v2.1.html` · `MASTER_CANON_DESIGN_SPEC_v2.1.html`

### Added — Portfolio (`portfolio_v2.1.html`)

- **Dropdown design menu** in nav replacing pill buttons:
  - Section 1: 4-theme grid (Focus · Clarity · Warmth · Nightfall) with swatch previews
  - Section 2: 5-morphism list (Soft · Glass · Clay · Neu · Flat) with live mini-preview tiles
  - Dropdown label shows current selection e.g. `Focus · Soft`
  - Closes on: outside click, Escape key, item selection
  - `aria-haspopup`, `aria-expanded`, `role="menu"`, `role="menuitem"` — full ARIA
- `data-morph` attribute on `<body>` — 5 sets of CSS attribute selectors restyle all card surfaces
- Binary Light/Dark toggle retained alongside dropdown

### Added — Canon HTML (`MASTER_CANON_DESIGN_SPEC_v2.1.html`)

- Theme Preview section (Part I §1.2): 4 static info strips → **clickable switcher cards**
  - Each card: live mini-UI preview, 60/30/10 swatch row, "Active" badge, fires `setTheme()`
  - `syncThemeCards()` keeps all 4 in sync regardless of which control sets theme
- Part IV Morphism section: static demos → **interactive 5-button selector + live preview card**
  - Preview card updates `background`, `border-radius`, `border`, `box-shadow`, button styles in real time
  - Spec table row highlights for active style
  - Selection persists to `localStorage`

---

## [2.0.0] — 2026-03-23 — Sprint-04: Full Integration (5 Source Docs)

**Scope:** `portfolio_v2.0.html` · `MASTER_CANON_DESIGN_SPEC_v2.0.html`

### Integration Map — All 15 Gaps Resolved

| Gap | Source | Status |
|-----|--------|--------|
| JSON-driven content | SRS §4 | ✅ `PORTFOLIO_DATA` with 250ms skeleton |
| Dark/Light toggle | SRS §7 | ✅ Binary ☀️/🌙 toggle |
| SFIA v8 skills | PWA-DSD-001 §3.1 | ✅ 7-dot bar L1–L7, evidence links |
| Experience timeline | SRS §7 | ✅ Vertical timeline with period badges |
| Certifications | PWA-DSD-001 §3.4 | ✅ Issuer, date, expiry, hash |
| Blog / Publications | SRS + PWA §3.2 | ✅ Series → Posts nested |
| Skeleton loaders | SRS §3 | ✅ Shimmer animation |
| STAR expandable cards | SRS §7 | ✅ Accordion per project |
| Glassmorphism nav | Morphism Spec §1 | ✅ backdrop-filter blur |
| Claymorphism cards | Morphism Spec §3 | ✅ 24px radius clay surface |
| Evidence links on skills | PWA-DSD-001 §3.1 | ✅ Per skill |
| Social links | PWA-DSD-001 §3.1 | ✅ GitHub, LinkedIn, website |
| Canon HTML reactive | PO requirement | ✅ All 4 themes + prefers-color-scheme |
| prefers-color-scheme | Universal Theme | ✅ Auto-Nightfall |
| Scroll animations | SRS §7 | ✅ IntersectionObserver |

---

## [1.0.2] — 2026-03-23 — Sprint-03: Portfolio QA Fix & Repo Pack

**Scope:** `portfolio_v1.0.2.html` · Initial repo structure

### Fixed (all from CAP)

- **LINK-001 [HIGH]** — 4 dead `href="#"` project card links → `href="#contact"` with aria-labels
- **FORM-001 [MED]** — Contact form: added `required`, email regex, `role="alert"` feedback, field error borders
- **SEO-001 [MED]** — `og:image` added with width/height; `twitter:image` added
- **SEO-002 [LOW]** — `og:url` added
- **A11Y-001 [MED]** — All 5 buttons given `type="button"`
- **A11Y-002 [MED]** — Mobile menu: full keyboard focus trap (Tab/Shift-Tab, Escape, auto-focus on open)
- **A11Y-005 [LOW]** — Submit button `aria-label="Submit contact form"` added
- **PERF-001 [MED]** — Font `rel="preload"` hint added
- **CSS-001 [LOW]** — `@media print` stylesheet added

### Added

- Complete professional repo: `README.md`, `CHANGELOG.md`, `HISTORY.md`, `REQUIREMENTS.md`
- `.meta/SIGNATURES.md` — cryptographic signature registry
- `sprint-records/` directory
- Portfolio version archive: v1.0.0 / v1.0.1 / v1.0.2

---

## [1.0.1] — 2026-03-23 — Sprint-02: Canon Ratification

**Scope:** Canon multi-format export · Canon RATIFIED

### Added

- `MASTER_CANON_DESIGN_SPEC_v1.0.1.html` — Interactive HTML spec (sidebar nav, live themes, morphism demos, type scale, spacing vis)
- `MASTER_CANON_DESIGN_SPEC_v1.0.1.docx` — Word document (A4, custom header/footer, all tables DXA dual-width)
- `MASTER_CANON_DESIGN_SPEC_v1.0.1.md` — Markdown source with cryptographic signature block embedded

### Changed

- Canon status: `DRAFT` → `REVIEW` → **`RATIFIED`** (PO: Cường Q. Huỳnh, 2026-03-23)
- Signature block populated: SHA-256 `118320ff…`, UUIDv7 `019d19cc-…`, composite sig `26e223d5…`

### Fixed

- **DEF-001** — `role="main"` landmark missing → added
- **DEF-002** — `:focus-visible` rule absent → added
- **DEF-003** — 30% token comment (false positive, resolved in audit)

---

## [1.0.0] — 2026-03-23 — Sprint-01: Initial Release

**Scope:** Canon synthesis from 5 source docs · Portfolio MVP

### Added — Canon Specification (DESIGN-CANON-2026-001)

Synthesised from five source documents:
- Source A: Universal Personal Theme YAML (Soft Minimalism / Soft Morphism, 4 palettes)
- Source B: Elegant Academic & Professional YAML (serif-first academic theme)
- Source C: Echelon YAML (Monochromatic + 1 Exceptional color system)
- Source D: Morphism UI Spec (Glassmorphism / Neumorphism / Claymorphism)
- Source E: Universal SCSS (CSS variables and responsive implementation)

Parts I–X + Appendices A–C. Document ID: `DESIGN-CANON-2026-001`. Status at release: `DRAFT`.

**Key synthesis decisions:**
- IBM Plex Sans → primary sans (over Inter: avoids generic AI-aesthetic)
- Terracotta `#E07A5F` — primary accent in WARMTH; <1% exceptional in other themes
- `data-theme` attribute as canonical switching pattern (alongside `.theme-*` class fallback)
- 16px as Soft-Morphism default border-radius (resolved 8/12/16px conflict across sources)

### Known Issues at v1.0.0 (resolved in subsequent versions)

- DEF-001: Missing `role="main"` → fixed v1.0.1
- LINK-001: Dead `href="#"` on project cards → fixed v1.0.2
- FORM-001: No form validation → fixed v1.0.2
- GAP-01..15: JSON data, SFIA, Experience, Certs, Blog → fixed v2.0.0
- SCRIPT-BAL, DEAD-LINKS → fixed v2.1.0

---

_Master Canon Design System CQH · Cường Q. Huỳnh © 2026 · Personal IP_
