# REQUIREMENTS SPECIFICATION

> **Project:** Master Canon Design System CQH
> **Document ID:** REQ-CANON-PORTFOLIO-2026-001
> **Version:** 1.0.0
> **Status:** RATIFIED
> **Author:** Cường Q. Huỳnh
> **Assisted By:** Claude-Sonnet-4.6
> **Date:** 2026-03-23
> **Classification:** Personal IP · Governance Document

---

## 1. Project Overview

This document defines the technical, design, governance, and accessibility requirements for the Master Canon Design System CQH project — comprising the personal portfolio site and the Master Canon Design Specification for Cường Q. Huỳnh.

---

## 2. Functional Requirements

### 2.1 Portfolio Site

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-01 | Single-file HTML with zero runtime dependencies | MUST |
| FR-02 | All 4 Canon themes switchable via UI control | MUST |
| FR-03 | Theme selection persisted across sessions (localStorage) | MUST |
| FR-04 | Sections: Hero, About, Expertise, Projects, Skills, Philosophy, Contact | MUST |
| FR-05 | Contact form with field validation and user feedback | MUST |
| FR-06 | Scroll-triggered section reveal animations | SHOULD |
| FR-07 | Skill bar animations triggered on scroll entry | SHOULD |
| FR-08 | Reading progress indicator | SHOULD |
| FR-09 | Mobile navigation with hamburger menu | MUST |
| FR-10 | All project cards link to a valid destination | MUST |

### 2.2 Canon Design Specification

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-11 | Specification delivered in HTML, DOCX, and Markdown formats | MUST |
| FR-12 | HTML version: interactive sidebar navigation, theme switcher | MUST |
| FR-13 | DOCX version: A4 format, header/footer, page numbers, all styles | MUST |
| FR-14 | MD version: version-controlled source with embedded signature block | MUST |
| FR-15 | All formats version-consistent and content-equivalent | MUST |

---

## 3. Design Requirements

| ID | Requirement | Standard |
|----|-------------|----------|
| DR-01 | 60/30/10 color law enforced in all compositions | Canon Part I |
| DR-02 | Four canonical themes implemented: Focus / Clarity / Warmth / Nightfall | Canon Part I |
| DR-03 | Exceptional color (#E07A5F) limited to <1% area outside WARMTH theme | Canon Part I §1.3 |
| DR-04 | Font stack: IBM Plex Sans (sans) + Libre Baskerville (serif) + Fira Code (mono) | Canon Part II |
| DR-05 | Type scale: 9 tokens from --fs-xs (0.75rem) to --fs-3xl (3rem) | Canon Part II §2.2 |
| DR-06 | Spacing: 4px modular scale, 7 tokens --space-xs through --space-3xl | Canon Part III |
| DR-07 | Soft-Morphism as default surface style | Canon Part IV §4.1 |
| DR-08 | Surface style matched to medium context | Canon Appendix A |
| DR-09 | Maximum 3 typefaces per composition | Canon Part II §2.3 |
| DR-10 | Maximum 1 accent color per composition | Canon Part I §1.2 |

---

## 4. Accessibility Requirements

All requirements per **WCAG 2.1 AA**.

| ID | Requirement | Standard |
|----|-------------|----------|
| AR-01 | Text contrast ratio ≥ 4.5:1 for body text | WCAG 1.4.3 AA |
| AR-02 | Text contrast ratio ≥ 3:1 for large text (≥24px) | WCAG 1.4.3 AA |
| AR-03 | All interactive elements keyboard-accessible | WCAG 2.1.1 |
| AR-04 | Visible focus indicator via `:focus-visible` (3px accent outline) | WCAG 2.4.7 |
| AR-05 | Skip-to-main-content link present above navigation | WCAG 2.4.1 |
| AR-06 | HTML5 landmark roles: `nav`, `main`, `footer` | WCAG 1.3.1 |
| AR-07 | All non-text interactive elements have `aria-label` | WCAG 4.1.2 |
| AR-08 | `aria-labelledby` on all sections with visible heading | WCAG 1.3.1 |
| AR-09 | Decorative elements marked `aria-hidden="true"` | WCAG 1.1.1 |
| AR-10 | Touch targets minimum 44×44px | WCAG 2.5.8 |
| AR-11 | All animations respect `prefers-reduced-motion` | WCAG 2.3.3 |
| AR-12 | Modal/overlay (mobile menu) implements keyboard focus trap | WCAG 2.1.2 |
| AR-13 | Focus returns to trigger element when overlay closes | WCAG 2.1.2 |
| AR-14 | Form inputs carry `required` and `aria-required` | WCAG 1.3.5 |
| AR-15 | Form errors surfaced via `role="alert"` `aria-live="polite"` | WCAG 4.1.3 |
| AR-16 | Layout does not break at 200% zoom | WCAG 1.4.10 |
| AR-17 | All buttons have explicit `type=` attribute | HTML spec |
| AR-18 | `autocomplete` attribute on standard form fields | WCAG 1.3.5 |
| AR-19 | `lang` attribute on `<html>` element | WCAG 3.1.1 |

---

## 5. SEO Requirements

| ID | Requirement |
|----|-------------|
| SR-01 | Single `<title>` tag, descriptive and unique |
| SR-02 | `<meta name="description">` present |
| SR-03 | `<meta name="author">` present |
| SR-04 | `<meta name="robots" content="index, follow">` |
| SR-05 | Open Graph: `og:title`, `og:description`, `og:type`, `og:url`, `og:image`, `og:locale` |
| SR-06 | Twitter Card: `twitter:card`, `twitter:title`, `twitter:description`, `twitter:image` |
| SR-07 | `<link rel="canonical">` present |
| SR-08 | JSON-LD `Person` schema with `name`, `jobTitle`, `description`, `url`, `knowsAbout` |
| SR-09 | Single `<h1>` element per page |
| SR-10 | Logical heading hierarchy (h1 → h2 → h3) |
| SR-11 | `lang="en"` on `<html>` |

---

## 6. Performance Requirements

| ID | Requirement | Target |
|----|-------------|--------|
| PR-01 | Zero external JavaScript dependencies | Hard requirement |
| PR-02 | Zero external CSS dependencies (fonts excepted) | Hard requirement |
| PR-03 | Font preload hint for critical fonts | SHOULD |
| PR-04 | `rel="preconnect"` for font CDN domains | SHOULD |
| PR-05 | `display=swap` on Google Fonts URL | MUST |
| PR-06 | CSS transitions only where purposeful (Canon Part VII) | MUST |
| PR-07 | IntersectionObserver for scroll-triggered effects (no scroll listeners for animation) | SHOULD |

---

## 7. Governance Requirements

| ID | Requirement |
|----|-------------|
| GR-01 | Every ratified document carries a Canon Signature Block (Doc Hash, UUID v7, Author Sign, System Sign) |
| GR-02 | All documents use semantic versioning (MAJOR.MINOR.PATCH) |
| GR-03 | A CHANGELOG.md entry exists for every version release |
| GR-04 | Source traceability: every synthesised document declares its input sources |
| GR-05 | Author attribution: `Author: Cường Q. Huỳnh` on all documents |
| GR-06 | AI assistant attribution: Claude / GPT / Perplexity / Gemini / NotebookLM declared where used |
| GR-07 | Document status declared: DRAFT → REVIEW → RATIFIED |
| GR-08 | All sprint review records retained in `sprint-records/` |
| GR-09 | All version history retained (no files deleted, only superseded) |
| GR-10 | IP declaration: "Personal IP · All rights reserved · Cường Q. Huỳnh © 2026" |

---

## 8. Technical Stack

| Layer | Technology | Rationale |
|-------|-----------|-----------|
| Portfolio | Vanilla HTML5 + CSS3 + ES6 JS | Zero dependency; maximum portability |
| Fonts | Google Fonts CDN (IBM Plex Sans, Libre Baskerville, Fira Code) | Canon-specified font stack |
| Theme switching | CSS custom properties + JS `data-theme` attribute | Clean, performant, progressive enhancement |
| Animations | CSS keyframes + IntersectionObserver API | No JS animation library; Canon motion spec |
| Form validation | Vanilla JS (regex + DOM API) | No library dependency |
| Canon DOCX | `docx` npm package v9.5.3 | Programmatic Word generation |
| Version control | Semantic versioning (semver) | Industry standard |
| Signing | SHA-256 + UUIDv7 + composite signature | Canon Appendix C protocol |

---

## 9. File Naming Conventions

```
portfolio_v{MAJOR}.{MINOR}.{PATCH}.html
MASTER_CANON_DESIGN_SPEC_v{MAJOR}.{MINOR}.{PATCH}.{ext}
SPRINT-{N}-{SUBJECT}.md
```

---

## 10. Acceptance Criteria — Current Version (v1.0.2)

All requirements in sections 2–7 must be satisfied for a version to be marked production-ready.

- [x] FR-01 through FR-10: All functional requirements met
- [x] FR-11 through FR-15: Canon multi-format export complete
- [x] DR-01 through DR-10: All design requirements met
- [x] AR-01 through AR-19: All accessibility requirements met
- [x] SR-01 through SR-11: All SEO requirements met
- [x] PR-01 through PR-07: All performance requirements met
- [x] GR-01 through GR-10: All governance requirements met

**QA verification: SPRINT-03 post-fix audit 16/16 PASS**

---

*REQ-CANON-PORTFOLIO-2026-001 · v1.0.0*
*Author: Cường Q. Huỳnh · Assisted: Claude-Sonnet-4.6 · 2026-03-23*
*Personal IP · All rights reserved · Cường Q. Huỳnh © 2026*
