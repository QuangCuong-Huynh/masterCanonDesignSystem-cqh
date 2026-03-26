# MASTER CANON DESIGN SPECIFICATION
## Personal Universal Design System — Cường.Q.Huỳnh

---

**Document ID:** DESIGN-CANON-2026-001
**Version:** 1.0.0
**Status:** DRAFT — Pending Author Approval
**Created:** 2026-03-23
**Author:** Cường.Q.Huỳnh
**Role:** Master Orchestrator · Virtual Librarian · IP Assets Professional · Solution Consultant
**Assisted by:** Claude (Anthropic) — Synthesis & Specification Drafting
**Classification:** Personal IP · Canon Reference · Evergreen

**Status: RATIFIED — Cường Q. Huỳnh · 2026-03-23

**Changelog:**
| Version | Date | Author | Summary |
|---------|------|--------|---------|
| 1.0.0 | 2026-03-23 | Cường.Q.Huỳnh + Claude | Initial synthesis from 5 source specs |
| 1.0.1 | 2026-03-23 | Agent-IP + Claude | Embed cryptographic signature block; status → REVIEW |

**Traceability:**
- Source A: `Universal Personal Theme YAML` — Soft Minimalism / Soft Morphism, 4 palettes
- Source B: `Elegant Academic & Professional YAML` — serif-first academic theme
- Source C: `Echelon YAML` — Monochromatic + 1 Exceptional color system
- Source D: `Morphism UI Spec` — Glassmorphism / Neumorphism / Claymorphism
- Source E: `Universal SCSS` — Implementation reference, CSS variables, responsive system

**Document Signature Block:**
```
Author Sign:    Cường.Q.Huỳnh
System Sign:    Claude-Sonnet-4.6 | 2026-03-23T08:25:31Z
Doc Hash:       SHA-256 → 118320ff480de68e1d99791661a72946b9f6def39f5c67a87323060a6d8f7825
UUID:           019d19cc-96f4-7-b64e-cbeaf11d5eef  [UUIDv7]
Context Hash:   cad81c19b349096e89c5337e068247a3b6209eb9ce8665d72713247d7d8a4fb6
Composite Sig:  26e223d51a78ab458ebe753905bcb4d329bbca701e73cbbc069b957b6beecd87
Context:        DESIGN-CANON-2026-001|v1.0.0|2026-03-23|author:Cuong.Q.Huynh|system:Claude-Sonnet-4.6
Authority:      [Pending PO ratification — Cường.Q.Huỳnh]
```

---

## PREAMBLE — Design Philosophy

> *"Clarity is not emptiness. Softness is not weakness. Every surface is a statement."*

This Canon is the single source of truth governing all visual output attributed to Cường.Q.Huỳnh — spanning web UI, academic documents, slide decks, data visualization, and creative works. It is not a style guide for a single project; it is a personal design language, a living IP asset.

**Three governing principles:**

1. **Soft Minimalism as Default** — Restrained use of color, generous whitespace, refined typography. Complexity lives in structure, not decoration.
2. **Contextual Morphism** — Surface style adapts to medium (Soft-Morphism for UI, flat-academic for documents, subtle depth for slides) but palette and type remain canonical.
3. **60 / 30 / 10 Color Law** — Non-negotiable across all contexts and all themes. Primary background dominates; secondary structures space; accent punctuates meaning.

---

## PART I — COLOR SYSTEM

### 1.1 Master Palette Registry

Four canonical palettes. One active at a time. All governed by the 60/30/10 Law.

#### Theme 1: CLARITY (Default)
> Neutral, clean, bright. For everyday work, technical writing, and light-mode UI.

| Role | Token | Hex | Usage |
|------|-------|-----|-------|
| Primary | `--primary` | `#FDFDFD` | 60% — backgrounds, canvas |
| Secondary | `--secondary` | `#F5F5F5` | 30% — panels, containers |
| Accent | `--accent` | `#A8D5BA` | 10% — links, CTAs, highlights |
| Accent Light | `--accent-light` | `#C7E7D1` | Hover states, gradient start |
| Accent Dark | `--accent-dark` | `#7BAE8C` | Active states, gradient end |
| Text Primary | `--text-primary` | `#111111` | Body, headings |
| Text Secondary | `--text-secondary` | `#444444` | Captions, sub-labels |
| Text Muted | `--text-muted` | `#888888` | Footnotes, placeholders |
| Border | `--border` | `#DDDDDD` | Dividers, input edges |

#### Theme 2: FOCUS
> High-contrast academic and business mode. Confident blue. For formal reports and presentations.

| Role | Token | Hex | Usage |
|------|-------|-----|-------|
| Primary | `--primary` | `#FFFFFF` | 60% — pure white canvas |
| Secondary | `--secondary` | `#EDEDED` | 30% — structural surfaces |
| Accent | `--accent` | `#3B82F6` | 10% — deep academic blue |
| Accent Light | `--accent-light` | `#93C5FD` | Hover, gradient start |
| Accent Dark | `--accent-dark` | `#1E40AF` | Emphasis, gradient end |
| Text Primary | `--text-primary` | `#0A0A0A` | Near-black for max contrast |
| Text Secondary | `--text-secondary` | `#333333` | Supporting copy |
| Text Muted | `--text-muted` | `#666666` | Metadata, footnotes |
| Border | `--border` | `#CCCCCC` | Clean neutral dividers |

*Note: FOCUS inherits the Echelon / Elegant Academic visual language. Serif body, sans heading.*

#### Theme 3: WARMTH
> Creative, inviting, earthy. Terracotta accent. For portfolios, creative briefs, and personal narratives.

| Role | Token | Hex | Usage |
|------|-------|-----|-------|
| Primary | `--primary` | `#FAFAFA` | 60% — soft warm white |
| Secondary | `--secondary` | `#F2F2F0` | 30% — warm gray surfaces |
| Accent | `--accent` | `#E07A5F` | 10% — terracotta |
| Accent Light | `--accent-light` | `#F2B8A4` | Warm hover states |
| Accent Dark | `--accent-dark` | `#9C4431` | Deep warm emphasis |
| Text Primary | `--text-primary` | `#1A1A1A` | Warm near-black |
| Text Muted | `--text-muted` | `#7A7A7A` | Subdued copy |
| Border | `--border` | `#E0E0E0` | Warm light border |

*Note: The terracotta (#E07A5F) is the "exceptional" color from the Echelon system — deployed here as primary accent. In FOCUS mode, it demotes to ≤1% emotional/alert-only use.*

#### Theme 4: NIGHTFALL
> Dark mode. Atmospheric, modern. Violet accent. For late-night work sessions and dark UI builds.

| Role | Token | Hex | Usage |
|------|-------|-----|-------|
| Primary | `--primary` | `#111111` | 60% — deep background |
| Secondary | `--secondary` | `#1E1E1E` | 30% — elevated surfaces |
| Accent | `--accent` | `#8B5CF6` | 10% — violet highlight |
| Accent Light | `--accent-light` | `#C4B5FD` | Soft violet hover |
| Accent Dark | `--accent-dark` | `#4C1D95` | Deep violet emphasis |
| Text Primary | `--text-primary` | `#FFFFFF` | Light text on dark |
| Text Muted | `--text-muted` | `#AAAAAA` | Subdued secondary copy |
| Border | `--border` | `#2C2C2C` | Dark subtle divider |

### 1.2 The 60/30/10 Law

```
Primary (60%)  → Base canvas: page backgrounds, slide backgrounds, document paper.
Secondary (30%) → Structure: panels, cards, sidebars, table rows, figure backgrounds.
Accent (10%)   → Signal: links, CTAs, callouts, highlights, data markers.
```

**Violations to avoid:**
- Accent used for large background blocks → forbidden
- Secondary used as text color for headings → forbidden
- Multiple competing accent colors in one composition → forbidden
- Accent exceeding 15% of visible area → flag for review

### 1.3 Exceptional Color Protocol (Echelon Rule)

In FOCUS theme only:
- `#E07A5F` (terracotta) is reserved for < 1% of composition
- Permitted uses: alert banners, critical callouts, personal signature marks, philosophical quote highlights
- Never as background; never as body text color

---

## PART II — TYPOGRAPHY SYSTEM

### 2.1 Font Stack

| Role | Font Stack | Context |
|------|-----------|---------|
| Sans (UI) | `"IBM Plex Sans", "Inter", "Helvetica Neue", Arial, sans-serif` | UI, headings, slides, captions |
| Serif (Academic) | `"Libre Baskerville", "Merriweather", Georgia, serif` | Body text, academic papers, long-form |
| Monospace | `"Fira Code", Consolas, monospace` | Code, algorithms, formulas, data tables |

**Rationale for hierarchy:**
- IBM Plex Sans leads sans stack: technical credibility + humanist warmth, avoids generic Inter-default aesthetic
- Libre Baskerville leads serif: traditional academic authority, strong at small sizes
- Fira Code: ligature support for code readability

### 2.2 Type Scale

| Token | Size | Usage |
|-------|------|-------|
| `--fs-xs` | 0.75rem (12px) | Footnotes, legal text, metadata |
| `--fs-sm` | 0.875rem (14px) | Captions, labels, secondary UI text |
| `--fs-base` | 1rem (16px) | Body text default |
| `--fs-md` | 1.125rem (18px) | Emphasized body, intro paragraphs |
| `--fs-lg` | 1.25rem (20px) | Subheadings, section intros |
| `--fs-xl` | 1.5rem (24px) | Level-3 headings, card titles |
| `--fs-2xl` | 2rem (32px) | Level-2 section headings |
| `--fs-3xl` | 2.5–3rem (40–48px) | Hero titles, slide covers, document title pages |

### 2.3 Typography Regulations by Medium

**Academic Documents:**
- Body: Serif, `--fs-base` to `--fs-md`, 1.5–1.7 line height, generous margins
- Headings: Sans-serif or Serif Bold at `--fs-xl` to `--fs-2xl`
- Citations & footnotes: Serif, `--fs-xs` to `--fs-sm`
- Code/formula: Monospace, `--fs-sm` to `--fs-base`
- Title page: Serif or Sans Bold, `--fs-3xl`, centered

**Presentations / Slides:**
- Titles: Sans-serif Bold, `--fs-2xl` to `--fs-3xl`
- Body/bullets: Sans-serif Regular, `--fs-base` to `--fs-lg`
- Max 30 words per slide for clarity
- Captions: `--fs-sm`, text-muted color

**Web UI:**
- Headings: Sans-serif (IBM Plex Sans / Inter)
- Body: Sans-serif
- Form labels: Sans-serif `--fs-sm`, weight 600
- Code/data: Monospace

**Long-form Writing / Narrative:**
- Body: Serif, `--fs-base`, 1.6 line height
- Pull quotes: Serif Italic, `--fs-lg` to `--fs-xl`, accent color

---

## PART III — LAYOUT & SPACING

### 3.1 Spacing Scale (4px Modular)

| Token | Value | Common use |
|-------|-------|-----------|
| `--space-xs` | 4px | Icon gaps, micro-padding |
| `--space-sm` | 8px | Inline padding, list item gaps |
| `--space-md` | 16px | Card padding, input padding, section gaps |
| `--space-lg` | 24px | Major block margins, card-to-card gaps |
| `--space-xl` | 32px | Section-to-section spacing |
| `--space-2xl` | 48px | Major section dividers |
| `--space-3xl` | 64px | Hero spacing, full-page section breaks |

**Rule:** Whitespace is structure, not emptiness. Minimum 16px padding on all major blocks.

### 3.2 Grid System

- Base: CSS Grid, 12-column where applicable; `auto-fit / minmax(280px, 1fr)` for fluid card grids
- Container max-width: `1200px` (documents); `1440px` (full-width UI)
- Academic: single-column center-aligned, max `720px` text block
- Slides: full-bleed, aspect-ratio `16:9` standard

### 3.3 Responsive Breakpoints

| Label | Width | Adaptation |
|-------|-------|-----------|
| Mobile | ≤ 480px | Single column, stacked nav, font-size 0.9rem |
| Tablet | 481–768px | 2-column max, collapsible panels |
| Desktop | 769–1200px | Full layout, standard padding |
| Wide Desktop | > 1200px | Extended grid, wider gutters |

**Touch targets:** Minimum 44px × 44px for all interactive elements.

---

## PART IV — SURFACE STYLES (MORPHISM SYSTEM)

This Canon recognizes four surface styles. Each is context-appropriate; none are mandatory in all contexts.

### 4.1 Soft-Morphism (Default — All Contexts)

The canonical surface treatment. Subtle depth, never harsh.

```css
border-radius: 16px;
border: 1px solid var(--border);
box-shadow: 0 4px 12px rgba(0,0,0,0.08);
background: var(--secondary);
transition: all 0.25s ease;

/* Hover lift */
transform: translateY(-4px);
box-shadow: 0 8px 20px rgba(0,0,0,0.12);

/* Inner gloss (optional for cards) */
box-shadow: inset 0 2px 6px rgba(255,255,255,0.6);
```

### 4.2 Glassmorphism (Dashboards, Modals, SaaS UI)

Translucency + blur. Use over rich background images or gradient backdrops.

```css
background: rgba(255,255,255,0.25);
backdrop-filter: blur(10px);
box-shadow: 0 8px 32px 0 rgba(31,38,135,0.37);
border-radius: 16px;
```

**Accessibility gate:** Text contrast ≥ 4.5:1 must be verified on blurred backgrounds. Never use small text (< 14px) over heavy blur.

### 4.3 Neumorphism (Inputs, Toggles, Tactile Controls)

Soft extrusions for interactive elements only. Do not apply to informational content.

```css
/* Raised */
background: #F0F0F0;
border-radius: 16px;
box-shadow: 6px 6px 12px #bebebe, -6px -6px 12px #ffffff;

/* Pressed */
box-shadow: inset 6px 6px 12px #bebebe, inset -6px -6px 12px #ffffff;
```

**Restriction:** Use only in CLARITY or FOCUS themes (light backgrounds). Incompatible with NIGHTFALL unless inverted carefully.

### 4.4 Claymorphism (Consumer Cards, Onboarding, Creative UI)

Rounded, friendly, layered. For warmth-oriented contexts.

```css
background: #FFFFFF;
border-radius: 24px;
box-shadow: 0 6px 16px rgba(0,0,0,0.15);
```

Best paired with WARMTH theme.

### 4.5 Academic / Document (Flat — Formal)

For academic papers, formal reports, and printed documents.

```css
border-radius: 4px;       /* minimal rounding */
border: 1px solid #D0D0D0;
box-shadow: none;          /* flat, no depth */
background: var(--secondary);
```

No hover effects; no transitions. Static and authoritative.

---

## PART V — COMPONENT SPECIFICATIONS

### 5.1 Buttons

```css
.btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 16px;
  font-size: var(--fs-base);
  border-radius: 12px;
  border: none;
  cursor: pointer;
  font-weight: 600;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

/* Primary CTA */
.btn--accent {
  background: linear-gradient(180deg, var(--accent-light), var(--accent));
  color: var(--accent-on-strong);
  box-shadow: 0 6px 18px rgba(0,0,0,0.08);
}
.btn--accent:hover { transform: translateY(-3px); }
.btn--accent:active { transform: translateY(0); }

/* Outline */
.btn--outline { background: transparent; border: 1px solid var(--border); }

/* Ghost */
.btn--ghost { background: transparent; color: var(--accent); }

/* Disabled */
.btn[disabled] { opacity: 0.5; cursor: not-allowed; }
```

### 5.2 Cards

Three elevation levels:

| Level | Shadow | Use |
|-------|--------|-----|
| Flat | none / 1px border | Document figures, tables |
| Soft | `0 4px 12px rgba(0,0,0,0.08)` | Standard UI cards |
| Lifted (hover) | `0 8px 20px rgba(0,0,0,0.12)` | Interactive cards |

### 5.3 Forms & Inputs

```css
input, textarea, select {
  padding: 12px 14px;
  border-radius: 12px;
  border: 1px solid var(--border);
  background: var(--primary);
  font-size: var(--fs-base);
  transition: box-shadow 0.18s ease, border-color 0.18s ease;
}
:focus-visible {
  box-shadow: 0 0 0 4px color-mix(in srgb, var(--accent) 18%, transparent);
  border-color: var(--accent-tone);
}
```

### 5.4 Tables

```css
table { width: 100%; border-collapse: collapse; }
th { background: var(--secondary); font-weight: 600; }
th, td { padding: var(--space-sm); border: 1px solid var(--border); }
tr:nth-child(even) { background: rgba(0,0,0,0.015); }
```

Academic tables: secondary background header, thin border, no shadows, serif caption below.

### 5.5 Alerts & Callouts

```css
.alert { padding: 8px 16px; border-radius: 8px; font-weight: 500; }
.alert-success  { background: rgba(168,213,186,0.3); color: #2F855A; }
.alert-error    { background: rgba(245,101,101,0.2); color: #C53030; }
.alert-info     { background: rgba(163,191,250,0.2); color: #2B6CB0; }
.alert-exceptional { background: rgba(224,122,95,0.15); color: #9C4431; }
/* exceptional — Echelon rule: ≤ 1% area, philosophical/critical use only */
```

### 5.6 Code Blocks

```css
pre, code {
  font-family: var(--font-mono);
  font-size: var(--fs-sm);
  background: var(--secondary);
  border-radius: 8px;
  padding: var(--space-sm) var(--space-md);
  border: 1px solid var(--border);
  overflow-x: auto;
}
```

---

## PART VI — MEDIUM-SPECIFIC APPLICATIONS

### 6.1 Academic Papers & Technical Reports

| Element | Specification |
|---------|-------------|
| Body font | Serif (Libre Baskerville), 11–12pt / 1rem |
| Body line height | 1.6–1.7 |
| Heading font | Sans or Serif Bold |
| Margins | Generous (≥ 25mm or 64px equivalent) |
| Figures | Secondary background box, thin border, flat style |
| Tables | Secondary header, border-collapse, serif caption |
| Citations | `--fs-xs`, footnote or endnote style |
| Title page | Centered, Serif Bold `--fs-3xl`, author block below |
| Accent use | Hyperlinks, footnote markers, key term emphasis only |
| Morphism style | Academic Flat (no shadows, minimal radius) |
| Theme | FOCUS (preferred) or CLARITY |

### 6.2 Presentations / Slide Decks

| Element | Specification |
|---------|-------------|
| Slide background | Primary color (always — no busy backgrounds) |
| Title font | Sans-serif Bold, `--fs-2xl` to `--fs-3xl` |
| Body font | Sans-serif Regular, `--fs-base` to `--fs-lg` |
| Word limit | ≤ 30 words per slide |
| Accent use | Diagrams, data highlights, key messages only |
| Secondary panels | For multi-part structure within one slide |
| Morphism style | Soft-Morphism for cards/callouts; Academic Flat for data tables |
| Figures | Center-aligned, secondary background |
| Theme | FOCUS or CLARITY for formal; WARMTH for creative; NIGHTFALL for tech/dark decks |
| Emotional slides | Exceptional terracotta accent, ≤ 5% area, conclusion/signature slides only |

### 6.3 Web UI & Applications

| Element | Specification |
|---------|-------------|
| Base grid | CSS Grid / Flexbox, 12-column, `max-width: 1440px` |
| Card style | Soft-Morphism default; Glassmorphism for modals |
| Navigation | Collapsible on mobile, 44px touch targets |
| Dark mode | Auto-detect via `prefers-color-scheme`, override with `.theme-nightfall` |
| Animations | Fade-in on load, hover-lift on cards, subtle button press. No continuous motion. |
| Accessibility | WCAG 2.1 AA minimum, ARIA labels on all non-text interactive elements |
| Theme switching | CSS class on `<html>`: `.theme-focus` / `.theme-warmth` / `.theme-nightfall` |

### 6.4 Data Visualization

| Element | Specification |
|---------|-------------|
| Gridlines | Secondary color or border color, low opacity |
| Data accent | Accent color for primary series / highlight |
| Secondary data | Secondary color for categories |
| Outliers / alerts | Exceptional terracotta (FOCUS), or accent-dark |
| Labels | Sans-serif `--fs-sm`, text-muted |
| Background | Primary color (transparent chart background preferred) |

---

## PART VII — INTERACTION & MOTION

### 7.1 Transition Standard

| Interaction | Duration | Easing |
|------------|----------|--------|
| Hover state | 0.2s | ease |
| Card lift | 0.25s | ease |
| Modal appear | 0.3s | ease-out |
| Page/section fade | 0.4s | ease |
| Theme switch | 0.25s | ease |

**Rule:** No looping, continuous, or autoplay animations in professional/academic contexts. Motion is purposeful — it confirms interaction or guides attention.

### 7.2 Animation Library

```css
.fade-in { animation: fadeIn 0.4s ease forwards; }
@keyframes fadeIn { from { opacity:0; } to { opacity:1; } }

.slide-up { animation: slideUp 0.4s ease forwards; }
@keyframes slideUp {
  from { opacity:0; transform: translateY(12px); }
  to   { opacity:1; transform: translateY(0); }
}
```

---

## PART VIII — ACCESSIBILITY REQUIREMENTS

| Requirement | Standard |
|------------|---------|
| Text contrast | WCAG 2.1 AA — minimum 4.5:1 for body; 3:1 for large text (24px+) |
| Interactive elements | Keyboard navigable; visible focus ring via `:focus-visible` |
| Focus ring style | 4px accent-hue outline, 2px offset |
| Touch targets | 44px × 44px minimum |
| Hover-only interactions | Must have touch alternative |
| ARIA labels | All icon buttons, non-text controls, modal triggers |
| Font zoom | Layout must not break at 200% browser zoom |
| Motion | Respect `prefers-reduced-motion` — suppress animations if set |

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { animation-duration: 0.01ms !important; transition-duration: 0.01ms !important; }
}
```

---

## PART IX — CSS VARIABLE IMPLEMENTATION REFERENCE

```css
:root {
  /* Active palette (Clarity default) */
  --primary: #FDFDFD;
  --secondary: #F5F5F5;
  --accent: #A8D5BA;
  --accent-light: #C7E7D1;
  --accent-tone: #95C4A9;
  --accent-dark: #7BAE8C;
  --accent-gradient: linear-gradient(135deg, #C7E7D1, #A8D5BA, #7BAE8C);
  --accent-on-strong: #0B2A18;

  --text-primary: #111111;
  --text-secondary: #444444;
  --text-muted: #888888;
  --border: #DDDDDD;

  /* Typography */
  --font-sans: "IBM Plex Sans", "Inter", "Helvetica Neue", Arial, sans-serif;
  --font-serif: "Libre Baskerville", "Merriweather", Georgia, serif;
  --font-mono: "Fira Code", Consolas, monospace;

  --fs-xs: 0.75rem;   --fs-sm: 0.875rem; --fs-base: 1rem;
  --fs-md: 1.125rem;  --fs-lg: 1.25rem;  --fs-xl: 1.5rem;
  --fs-2xl: 2rem;     --fs-3xl: 3rem;

  /* Spacing */
  --space-xs: 4px;  --space-sm: 8px;  --space-md: 16px;
  --space-lg: 24px; --space-xl: 32px; --space-2xl: 48px; --space-3xl: 64px;

  /* Surface */
  --radius: 16px;
  --border-width: 1px;
  --shadow: 0 4px 12px rgba(0,0,0,0.05);
  --shadow-soft: 0 4px 12px rgba(0,0,0,0.08);
  --shadow-inner: inset 0 2px 6px rgba(255,255,255,0.6);
  --transition: all 0.25s ease;

  /* Z-index layers */
  --z-base: 0; --z-card: 10; --z-modal: 1000; --z-tooltip: 2000;
}

/* Theme overrides — apply to <html> or <body> */
.theme-focus    { /* FOCUS palette — see Part I.1 */ }
.theme-warmth   { /* WARMTH palette — see Part I.1 */ }
.theme-nightfall { /* NIGHTFALL palette — see Part I.1 */ }
```

---

## PART X — QUALITY CHECKLIST

Before publishing any output governed by this Canon, verify:

**Color & Theme**
- [ ] 60/30/10 law observed
- [ ] Single accent color per composition
- [ ] Exceptional terracotta used < 1% (FOCUS) or as primary accent (WARMTH only)
- [ ] WCAG 2.1 AA contrast verified for all text/background pairs

**Typography**
- [ ] Maximum 3 typefaces per composition
- [ ] Scale hierarchy respected (body < subhead < heading)
- [ ] Serif for academic body; sans for UI/slides; mono for code

**Layout**
- [ ] 4px spacing modular scale observed
- [ ] Minimum 16px padding on major blocks
- [ ] Grid-based structure, not ad hoc positioning

**Surface & Morphism**
- [ ] Correct morphism style for context (Soft-Morphism default)
- [ ] No overly aggressive shadows or contrast
- [ ] Transition durations within spec (0.2–0.4s)

**Responsive / Accessible**
- [ ] Layout tested at all four breakpoints
- [ ] 44px touch targets confirmed
- [ ] ARIA labels present on all interactive non-text elements
- [ ] `prefers-reduced-motion` respected
- [ ] Keyboard navigation functional

**Documents & Slides**
- [ ] Author attribution block present
- [ ] Version and date recorded
- [ ] Traceability footnote included

---

## APPENDIX A — SURFACE STYLE QUICK REFERENCE

| Context | Morphism Style | Theme | Font Role |
|---------|---------------|-------|----------|
| Academic paper | Flat | FOCUS / CLARITY | Serif body |
| Technical report | Flat + Soft | FOCUS | Serif body, Sans heading |
| Web dashboard | Soft-Morphism | Any | Sans throughout |
| SaaS modal | Glassmorphism | Any | Sans |
| Creative portfolio | Claymorphism | WARMTH | Mixed |
| Slide deck (formal) | Soft-Morphism | FOCUS | Sans bold |
| Slide deck (creative) | Soft + Clay | WARMTH | Sans bold |
| Dark UI / night mode | Soft-Morphism | NIGHTFALL | Sans |
| Data viz | Flat | Any | Sans labels |

---

## APPENDIX B — ICON USAGE POLICY

**Strict limited use.** Icons are functional, never decorative.

- Use icons only where a label alone is insufficient for quick recognition
- Icon size: 16–24px for inline; 32px max for standalone
- Icon style: consistent line-weight, single color (text-primary or accent), no multi-color icons
- Never use icons as substitute for text in academic or formal document contexts
- Emoji: forbidden in formal documents and presentations; permitted in informal UI only

---

## APPENDIX C — DOCUMENT AUTHORSHIP & SIGNATURE TEMPLATE

Every ratified output governed by this Canon must include:

```
Document ID:   [PROJECT-YYYYMMDD-###]
Version:       [semver]
Author:        Cường.Q.Huỳnh
Assisted by:   [Claude / GPT / Perplexity / Gemini / NotebookLM — as applicable]
Date:          [ISO 8601]
Status: RATIFIED — Cường Q. Huỳnh · 2026-03-23

Doc Hash:      SHA-256([content])
Signed by:     Cường.Q.Huỳnh   → [signature]
Signed by:     System           → [Claude-Sonnet-4.6 | timestamp]
Signed by:     Authority        → [optional]
UUID:          [uuidv7 on ratification]
```

---

*End of MASTER CANON DESIGN SPECIFICATION v1.0.0*
*This document is personal IP. All rights reserved. Cường.Q.Huỳnh © 2026.*
