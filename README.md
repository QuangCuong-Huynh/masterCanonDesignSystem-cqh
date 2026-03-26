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
| **Assisted By** | Claude-Sonnet-4.6 (Anthropic) · GPT · Perplexity · Gemini · NotebookLM |
| **Current Version** | `1.0.2` |
| **Canon Status** | RATIFIED v1.0.0 → active |
| **Portfolio Status** | v1.0.2 — QA cleared, Canon compliant |
| **License** | Personal IP · All rights reserved · Cường Q. Huỳnh © 2026 |

---

## What This Repository Contains

```
Master Canon Design System CQH/
│
├── README.md                    ← You are here
├── CHANGELOG.md                 ← Detailed version history per file
├── HISTORY.md                   ← Narrative sprint & decision history
├── REQUIREMENTS.md              ← Technical & governance requirements spec
│
├── docs/                        ← Master Canon Design Specification (3 formats)
│   ├── html/  MASTER_CANON_DESIGN_SPEC_v1.0.1.html
│   ├── docx/  MASTER_CANON_DESIGN_SPEC_v1.0.1.docx
│   └── md/    MASTER_CANON_DESIGN_SPEC_v1.0.1.md
│
├── portfolio/                   ← Portfolio site — all version history
│   ├── v1.0.0/  portfolio_v1.0.0.html   (pre-QA internal build)
│   ├── v1.0.1/  portfolio_v1.0.1.html   (first QA-cleared release)
│   └── v1.0.2/  portfolio_v1.0.2.html   ← CURRENT — all defects resolved
│
├── canon/                       ← Canon source version archive
│   ├── v1.0.0/
│   └── v1.0.1/
│
├── sprint-records/              ← Agile ceremony records (Sprint Reviews, CAP logs)
│
└── .meta/                       ← Cryptographic signatures, UUIDs, hashes
    └── SIGNATURES.md
```

---

## Quick Start

The portfolio is a **single-file, zero-dependency HTML** page.

```bash
# Open latest version directly in browser
open portfolio/v1.0.2/portfolio_v1.0.2.html

# Or serve locally
python3 -m http.server 8080
# → http://localhost:8080/portfolio/v1.0.2/portfolio_v1.0.2.html
```

The Canon specification is available in three formats:

```bash
# Interactive HTML reference (recommended for navigation)
open docs/html/MASTER_CANON_DESIGN_SPEC_v1.0.1.html

# Word document (for annotation, printing, formal distribution)
open docs/docx/MASTER_CANON_DESIGN_SPEC_v1.0.1.docx

# Markdown source (for version control diffs, plain text reference)
cat docs/md/MASTER_CANON_DESIGN_SPEC_v1.0.1.md
```

---

## Design System — Canon Summary

The **Master Canon Design Specification** (`DESIGN-CANON-2026-001`) governs all visual output from this project. Key rules:

### Four Canonical Themes
| Theme | Accent | Use Context |
|-------|--------|-------------|
| **Focus** | `#2B6CB0` Deep Blue | Academic, formal, default |
| **Clarity** | `#3B9E6B` Mint Green | Everyday, light-mode, neutral |
| **Warmth** | `#E07A5F` Terracotta | Creative, portfolio, personal |
| **Nightfall** | `#8B5CF6` Violet | Dark mode, technical, night |

### 60/30/10 Color Law
```
Primary   60% → backgrounds, canvas
Secondary 30% → panels, containers, structure
Accent    10% → links, CTAs, highlights
Exceptional <1% → alerts, signature marks only
```

### Font Stack
```css
--font-sans:  "IBM Plex Sans", "Helvetica Neue", Arial, sans-serif;
--font-serif: "Libre Baskerville", Georgia, serif;
--font-mono:  "Fira Code", Consolas, monospace;
```

### Five Surface Styles
`Soft-Morphism` (default) · `Glassmorphism` · `Neumorphism` · `Claymorphism` · `Academic Flat`

---

## Portfolio Feature Matrix (v1.0.2)

| Feature | Status |
|---------|--------|
| 4-theme live switcher (persistent via localStorage) | ✅ |
| Canon 60/30/10 color law enforced | ✅ |
| IBM Plex Sans + Libre Baskerville + Fira Code | ✅ |
| Soft-Morphism surface system | ✅ |
| Skip-to-content link | ✅ |
| `role="main"` / `nav` / `contentinfo` landmarks | ✅ |
| `:focus-visible` keyboard ring | ✅ |
| `prefers-reduced-motion` | ✅ |
| Mobile hamburger menu + focus trap | ✅ |
| Escape key closes mobile menu | ✅ |
| Contact form validation + error feedback | ✅ |
| `required` + email regex validation | ✅ |
| `aria-required`, `aria-label`, `aria-live` alerts | ✅ |
| `og:title`, `og:description`, `og:image`, `og:url` | ✅ |
| `twitter:card`, `twitter:image` | ✅ |
| JSON-LD `Person` schema | ✅ |
| Canonical URL | ✅ |
| Font preload hints (FOUT prevention) | ✅ |
| Print stylesheet | ✅ |
| Scroll-triggered reveal animations | ✅ |
| Skill bar animations (IntersectionObserver) | ✅ |
| Reading progress bar | ✅ |
| Responsive: 480 / 640 / 960px breakpoints | ✅ |

**QA Score: 16/16 PASS (Sprint-03 post-fix)**

---

## Governance & Traceability

Every ratified document in this project carries a **Canon Signature Block**:

```
Doc Hash:      SHA-256([content])
UUID:          [uuidv7 on ratification]
Signed by:     Cường.Q.Huỳnh
Signed by:     System (Claude-Sonnet-4.6 | timestamp)
Signed by:     Authority (optional)
```

See `.meta/SIGNATURES.md` for all ratified document signatures.

---

## Author

**Cường Q. Huỳnh**
Master Orchestrator · Virtual Librarian · IP Assets Professional
Infra & Data Architect · Solution Consultant

*Assisted by: Claude-Sonnet-4.6 (Anthropic)*
*Master Canon Design System CQH © 2026 · Personal IP · All rights reserved*
