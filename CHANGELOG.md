# CHANGELOG

> **Project:** Master Canon Design System CQH
> **Format:** [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) — Semantic Versioning
> **Author:** Cường Q. Huỳnh
> **Maintained by:** Cường Q. Huỳnh + Claude-Sonnet-4.6

---

## [Unreleased]

_Backlog items pending next sprint:_
- `BACKLOG-DL-001` — Add icon stroke-width spec (1.5px default / 2px emphasis) to Canon Appendix B
- `BACKLOG-FE-001` — Document `data-theme` attribute method alongside class-based switching in Canon Part IX
- `BACKLOG-FE-002` — Expand all 4 theme override blocks in Canon Part IX CSS reference
- `BACKLOG-DI-001` — Add `governs:` and `derived_from:` fields to Canon metadata header
- `BACKLOG-002` — Connect portfolio contact form to backend / email service
- `BACKLOG-003` — Replace project card "Enquire →" links with real project URLs when published

---

## [1.0.2] — 2026-03-23 — Portfolio · Sprint-03 QA Fix

**Scope:** Portfolio site only (`portfolio_v1.0.2.html`)
**Sprint:** SPRINT-03-QA-FIX
**QA Score:** 16/16 PASS (up from 6 defects)

### Fixed
- **LINK-001 [HIGH]** — 4 dead `href="#"` placeholder links on project cards replaced with `href="#contact"` + descriptive `aria-label` per project
- **FORM-001 [MED]** — Contact form inputs now carry `required` + `aria-required="true"`; email validated against RFC-compatible regex; live `role="alert"` `aria-live="polite"` feedback div shows field-level errors with accent border; focus moves to first invalid field on submit attempt
- **SEO-001 [MED]** — `og:image` meta added (`https://cuongqhuynh.com/og-cover.png`) with `og:image:width=1200`, `og:image:height=630`; `twitter:image` added
- **SEO-002 [LOW]** — `og:url` meta added
- **A11Y-001 [MED]** — All 5 buttons (4 theme pills + hamburger) given explicit `type="button"` attribute
- **A11Y-002 [MED]** — Mobile menu overlay now has full keyboard focus trap: Tab/Shift+Tab cycle within menu, Escape key closes menu and returns focus to hamburger trigger, first focusable element receives focus on open
- **A11Y-005 [LOW]** — Submit button given `aria-label="Submit contact form"`
- **PERF-001 [MED]** — Font `rel="preload"` hint added for critical Google Fonts stylesheet URL (FOUT prevention)
- **CSS-001 [LOW]** — Full `@media print` stylesheet added: hides nav/animations/decorative elements, exposes link URLs via `::after`, sets print-safe typography

### Changed
- All Canon version references updated from `v1.0.1` → `v1.0.2` throughout (CSS comment, hero card, projects section, philosophy section, footer)
- `DESIGN-CANON-2026-001 · v1.0.2 · Assisted by Claude-Sonnet-4.6` in footer

---

## [1.0.1] — 2026-03-23 — Portfolio + Canon HTML/DOCX

**Scope:** Portfolio rebuild + Canon multi-format export
**Sprint:** SPRINT-02-CANON-RATIFICATION (post-ratification delivery)

### Added — Portfolio (`portfolio_v1.0.1.html`)
- Full rebuild of portfolio from v1.0.0 with all SPRINT-01 defects resolved
- `role="main"` landmark wrapping full content area — **DEF-001 closed**
- `:focus-visible` rule with `:focus{outline:none}` pair — **DEF-002 closed**
- `skip-link` above nav for keyboard users
- `data-theme` attribute switching (canonical) + `.theme-*` class fallback (legacy)
- Dynamic `<meta name="theme-color">` update on theme switch
- `aria-expanded` + `aria-controls` on hamburger button
- `aria-valuenow` live update on reading progress bar
- `data-w` attribute on skill bar elements (separation of data/style)
- 4 responsive breakpoints: 960px / 640px / 480px
- `type="button"` on all nav buttons (partial — completed in v1.0.2)
- Font stack: IBM Plex Sans + Libre Baskerville + Fira Code
- All 4 Canon themes: Focus / Clarity / Warmth / Nightfall
- localStorage theme persistence
- JSON-LD `Person` schema
- `og:title`, `og:description`, `twitter:card`, `twitter:description`
- Canonical URL, `lang="en"`
- Scroll-triggered reveal (IntersectionObserver)
- Skill bar animation triggered on section scroll
- Reading progress bar
- Hero blob animation, staggered hero text reveals
- Print stylesheet (partial)

### Added — Canon Documents
- `MASTER_CANON_DESIGN_SPEC_v1.0.1.html` — Interactive HTML reference with sticky sidebar, 4-theme switcher, type scale demo, spacing visualizer, morphism demos, reading progress
- `MASTER_CANON_DESIGN_SPEC_v1.0.1.docx` — Professional Word document: A4 format, custom header/footer with page numbers, IBM Plex Sans + Libre Baskerville + Fira Code, all tables with DXA dual-width, full signature block, Appendices A–C
- `MASTER_CANON_DESIGN_SPEC_v1.0.1.md` — Source markdown with cryptographic signature block embedded

### Changed
- Canon document status: `DRAFT` → `REVIEW` (SPRINT-02 Sprint Review complete)
- Changelog entry added: v1.0.1 (Agent-IP + Claude: embed signature block)
- Signature block populated with: SHA-256 hash, UUIDv7, context hash, composite signature, system timestamp

---

## [1.0.0] — 2026-03-23 — Initial Release

**Scope:** Master Canon Design Specification synthesis + initial Portfolio MVP
**Sprint:** SPRINT-01-MVP

### Added — Canon Specification (`MASTER_CANON_DESIGN_SPEC_v1.0.0`)
- Synthesized from 5 source documents:
  - Source A: Universal Personal Theme YAML (Soft Minimalism / Soft Morphism, 4 palettes)
  - Source B: Elegant Academic & Professional YAML (serif-first academic theme)
  - Source C: Echelon YAML (Monochromatic + 1 Exceptional color system)
  - Source D: Morphism UI Spec (Glassmorphism / Neumorphism / Claymorphism)
  - Source E: Universal SCSS (CSS variables and responsive implementation)
- Parts I–X: Color System, Typography, Layout & Spacing, Surface Styles, Components, Applications, Motion, Accessibility, CSS Variables, Quality Checklist
- Appendices A (Surface Quick Reference), B (Icon Policy), C (Signature Template)
- Document ID: `DESIGN-CANON-2026-001`
- Status at release: `DRAFT`

### Added — Portfolio MVP (`portfolio_v1.0.0.html` → `portfolio_v1.0.1.html`)
- Single-page portfolio site: Hero, About, Expertise (6 domains), Projects (4 cards), Skills, Philosophy, Contact
- 4-theme switcher: Focus / Clarity / Warmth / Nightfall
- Canon 60/30/10 color law
- IBM Plex Sans + Libre Baskerville + Fira Code
- Soft-Morphism surface system
- Scroll-triggered animations
- JSON-LD Person schema, og: / twitter: meta tags

### Known Issues at v1.0.0 (resolved in v1.0.1 / v1.0.2)
- DEF-001: Missing `role="main"` landmark
- DEF-002: `:focus-visible` rule absent
- DEF-003: 30% token comment absent (false positive — resolved in audit)
- LINK-001: Dead `href="#"` on project cards
- FORM-001: No contact form validation
- SEO-001: `og:image` missing
- A11Y-001: Buttons missing `type=`
- A11Y-002: Mobile menu no focus trap
- PERF-001: No font preload

---

_Master Canon Design System CQH · Cường Q. Huỳnh © 2026_
