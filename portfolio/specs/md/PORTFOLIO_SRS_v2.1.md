# PORTFOLIO SYSTEM REQUIREMENTS SPECIFICATION

**Document ID:** PORTFOLIO-SRS-2026-001
**Version:** 2.1.0
**Status:** ACTIVE
**Date:** 2026-03-23
**Author:** Cường Q. Huỳnh
**Assisted By:** Claude-Sonnet-4.6 (Anthropic)
**Canon Ref:** DESIGN-CANON-2026-001 v2.1.0
**Classification:** Personal IP · Technical Specification

---

**Changelog:**

| Version | Date | Author | Summary |
|---------|------|--------|---------|
| 1.0.0 | 2026-03-23 | Cường.Q.Huỳnh + Claude | Initial SRS from SPA + PWA-DSD-001 |
| 2.0.0 | 2026-03-23 | Cường.Q.Huỳnh + Claude | Integration of 5 source docs; SFIA, morphism, theme systems |
| 2.1.0 | 2026-03-23 | Cường.Q.Huỳnh + Claude | Post-QA fixes; dropdown design menu; portfolio.json integrity pass |

**Signature Block:**

```
Author:        Cường Q. Huỳnh → [Pending ratification]
System:        Claude-Sonnet-4.6 | 2026-03-23
Canon Ref:     DESIGN-CANON-2026-001
```

---

## 1. Purpose & Scope

This document defines all requirements for the **Master Canon Design System CQH** — a personal portfolio web application and its governing Canon design system. It serves as the single technical reference for frontend architecture, data, design, accessibility, and governance.

**Target audiences:** Job recruiters, collaborators, technical reviewers, the author.

**In scope:** Portfolio SPA, Canon HTML specification, `portfolio.json` data contract, repo structure.

**Out of scope:** Backend CMS, server infrastructure, analytics.

---

## 2. System Overview

| Attribute | Value |
|-----------|-------|
| Type | Single Page Application (SPA) |
| Architecture | Static HTML + vanilla JS + embedded JSON |
| Deployment | Static hosting (GitHub Pages, Netlify, Vercel) |
| Dependencies | Google Fonts CDN only — zero runtime JS libraries |
| Data Source | `portfolio.json` (external) or inline `PORTFOLIO_DATA` (embedded) |
| Design System | DESIGN-CANON-2026-001 |
| Versioning | Semantic versioning (MAJOR.MINOR.PATCH) |

---

## 3. Functional Requirements

### 3.1 Core SPA

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-01 | Single-file HTML, zero runtime dependencies | MUST |
| FR-02 | All content loaded from `PORTFOLIO_DATA` (inline JSON or fetch) | MUST |
| FR-03 | Skeleton loaders visible during data render delay | MUST |
| FR-04 | Sections: Hero · About · Skills · Experience · Projects · Certs · Blog · Contact | MUST |
| FR-05 | Scroll-triggered section reveal animations | SHOULD |
| FR-06 | Reading progress bar | SHOULD |
| FR-07 | Footer: dynamic year, Canon ref, version | MUST |

### 3.2 Theme & Design Controls

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-08 | Binary Light/Dark toggle (☀️/🌙) | MUST |
| FR-09 | 4-palette selector: Focus · Clarity · Warmth · Nightfall | MUST |
| FR-10 | 5 surface style selector: Soft · Glass · Clay · Neu · Flat | MUST |
| FR-11 | Theme and morph selection persisted via localStorage | MUST |
| FR-12 | `prefers-color-scheme: dark` auto-applies Nightfall if no saved preference | SHOULD |
| FR-13 | Theme/morph controls in single dropdown menu in nav | MUST |
| FR-14 | Dropdown closes on outside click, Escape key, item selection | MUST |

### 3.3 Skills — SFIA v8

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-15 | Skills displayed with SFIA v8 level (L1–L7) | MUST |
| FR-16 | Visual 7-dot bar indicating level | MUST |
| FR-17 | Each skill links to evidence anchor (#projects, #certs, #experience) | MUST |
| FR-18 | SFIA legend (L1 Awareness → L7 Distinguished) displayed below skills | SHOULD |

### 3.4 Experience Timeline

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-19 | Vertical timeline layout with dot markers and period badges | MUST |
| FR-20 | Role, company, location, date range, bullet points per entry | MUST |

### 3.5 Projects — STAR

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-21 | Project cards with title, summary, tags, icon, badge | MUST |
| FR-22 | Expandable STAR accordion (Situation · Task · Action · Result) | MUST |
| FR-23 | STAR accordion keyboard accessible (aria-expanded) | MUST |

### 3.6 Certifications

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-24 | Certification cards: title, issuer, issue date, expiry | MUST |
| FR-25 | Evidence link per certificate | MUST |
| FR-26 | SHA-256 hash displayed for cryptographically signed certs | SHOULD |

### 3.7 Blog / Publications

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-27 | Series → Posts nested structure | MUST |
| FR-28 | Post card: date, title, summary, tags | MUST |

### 3.8 Contact

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-29 | Email, location, LinkedIn, GitHub from JSON data | MUST |
| FR-30 | Contact form with name, email, engagement type, message | MUST |
| FR-31 | Client-side validation: required fields, email regex | MUST |
| FR-32 | `role="alert"` `aria-live="polite"` error/success feedback | MUST |
| FR-33 | Social links: GitHub, LinkedIn, website in hero | MUST |

---

## 4. Non-Functional Requirements

### 4.1 Performance

| ID | Requirement |
|----|-------------|
| NFR-01 | First Contentful Paint < 2s on standard broadband |
| NFR-02 | Zero render-blocking JavaScript |
| NFR-03 | Font preload hints for critical fonts |
| NFR-04 | `font-display: swap` on Google Fonts |
| NFR-05 | No external CSS dependencies (fonts excepted) |

### 4.2 Accessibility — WCAG 2.1 AA

| ID | Requirement |
|----|-------------|
| NFR-06 | Text contrast ≥ 4.5:1 for body; ≥ 3:1 for large text |
| NFR-07 | `:focus-visible` keyboard ring on all interactive elements |
| NFR-08 | Skip-to-main-content link |
| NFR-09 | HTML5 landmark roles: `nav`, `main`, `contentinfo` |
| NFR-10 | `aria-label` on all non-text interactive elements |
| NFR-11 | 44×44px minimum touch targets |
| NFR-12 | `prefers-reduced-motion` suppresses all animations |
| NFR-13 | Mobile menu keyboard focus trap (Tab/Shift-Tab cycling, Escape to close) |
| NFR-14 | `required` + `aria-required` on mandatory form fields |
| NFR-15 | Layout stable at 200% browser zoom |

### 4.3 SEO

| ID | Requirement |
|----|-------------|
| NFR-16 | `<meta name="description">`, `<meta name="author">` |
| NFR-17 | Open Graph: `og:title`, `og:description`, `og:url`, `og:image` |
| NFR-18 | Twitter Card meta tags |
| NFR-19 | JSON-LD `Person` schema |
| NFR-20 | `<link rel="canonical">` |
| NFR-21 | Single `<h1>` per page |

### 4.4 Print

| ID | Requirement |
|----|-------------|
| NFR-22 | `@media print` hides nav, animations, decorative elements |
| NFR-23 | Link URLs rendered via CSS `::after` in print |

---

## 5. Design System Requirements

All visual output governed by **DESIGN-CANON-2026-001**.

### 5.1 Color — 60/30/10 Law

```
Primary   60%  → backgrounds, canvas
Secondary 30%  → panels, containers, structure
Accent    10%  → links, CTAs, highlights
Exceptional <1% → alerts, signature marks only
```

### 5.2 Four Canonical Themes

| Theme | Accent | Context |
|-------|--------|---------|
| Focus | `#2B6CB0` Deep Blue | Academic, formal, default |
| Clarity | `#3B9E6B` Mint Green | Everyday, light-mode |
| Warmth | `#E07A5F` Terracotta | Creative, personal |
| Nightfall | `#8B5CF6` Violet | Dark mode, technical |

### 5.3 Five Surface Styles

| Style | Context |
|-------|---------|
| Soft-Morphism | Default — all general UI |
| Glassmorphism | Modals, dashboards, nav |
| Claymorphism | Consumer cards, creative UI |
| Neumorphism | Inputs, toggles, controls |
| Academic Flat | Formal documents, print |

### 5.4 Typography

| Role | Stack |
|------|-------|
| Sans (UI) | IBM Plex Sans, Helvetica Neue, Arial |
| Serif (Academic) | Libre Baskerville, Georgia |
| Monospace | Fira Code, Consolas |

### 5.5 Spacing — 4px Modular Scale

`xs:4px` · `sm:8px` · `md:16px` · `lg:24px` · `xl:32px` · `2xl:48px` · `3xl:64px`

---

## 6. Data Contract — portfolio.json

### 6.1 Schema

```
portfolio.json
├── _meta          (doc_id, version, integrity_note, changelog)
├── site           (title, contact{email, location, socials})
├── profile        (name, title, summary, about, avatar, resume)
├── skills[]       (area, icon, skills[]{name, sfia:1-7, sfia_label, evidence})
├── experience[]   (company, role, start, end, location, bullets[])
├── projects[]     (title, summary, tags[], icon, badge, star{S,T,A,R}, link)
├── certs[]        (title, issuer, date, expiry, evidence, hash?)
└── blogs.series[] (title, posts[]{title, summary, date, tags[], status})
```

### 6.2 Integrity Rules

- `[OWNER: ...]` markers indicate content requiring owner substitution before publishing
- SFIA levels must be honest self-assessment (L1–L7 per SFIA v8 framework)
- No fabricated company names, dates, or certifications
- Blog posts with `"status": "draft"` must not be treated as published

---

## 7. File & Repo Structure

```
Master Canon Design System CQH/
├── README.md
├── CHANGELOG.md
├── HISTORY.md
├── REQUIREMENTS.md
│
├── docs/
│   ├── html/   MASTER_CANON_DESIGN_SPEC_v*.html
│   ├── docx/   MASTER_CANON_DESIGN_SPEC_v*.docx
│   └── md/     MASTER_CANON_DESIGN_SPEC_v*.md
│
├── portfolio/
│   ├── specs/
│   │   ├── html/  PORTFOLIO_SRS_v*.html
│   │   ├── docx/  PORTFOLIO_SRS_v*.docx
│   │   └── md/    PORTFOLIO_SRS_v*.md
│   ├── data/
│   │   └── portfolio.json
│   ├── v1.0.0/  portfolio_v1.0.0.html
│   ├── v1.0.1/  portfolio_v1.0.1.html
│   ├── v1.0.2/  portfolio_v1.0.2.html
│   ├── v2.0.0/  portfolio_v2.0.html
│   ├── v2.1.0/  portfolio_v2.1.html  ← CURRENT
│   └── latest → v2.1.0/portfolio_v2.1.html  (symlink or copy)
│
├── sprint-records/
└── .meta/
    └── SIGNATURES.md
```

---

## 8. Quality Gate — v2.1.0 Acceptance Criteria

All items checked in SPRINT-05 QA:

- [x] Script tag balance: 2 open / 2 close
- [x] Zero dead `href="#"` links
- [x] PORTFOLIO_DATA valid JSON, no placeholder hallucinations
- [x] 4 theme palette buttons functional
- [x] 5 morphism style buttons functional, `data-morph` on `<body>`, CSS selectors apply
- [x] Binary LD toggle: ☀️/🌙 state correct, localStorage persist
- [x] Dropdown: closes on Escape, outside click, item select
- [x] SFIA v8 7-dot bar renders correctly
- [x] Experience timeline renders from JSON
- [x] STAR accordion keyboard accessible
- [x] Contact form: validation + `role="alert"` feedback
- [x] WCAG 2.1 AA: skip link, landmarks, focus-visible, reduced-motion
- [x] Print stylesheet present
- [x] Version refs: v2.1.0 throughout

---

*PORTFOLIO-SRS-2026-001 · v2.1.0*
*Author: Cường Q. Huỳnh · Assisted: Claude-Sonnet-4.6 · 2026-03-23*
*Personal IP · All rights reserved · Cường Q. Huỳnh © 2026*
