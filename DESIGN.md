---
name: Michael DeGoll
description: Purpose-built software and AI agent work for operators, founders, and technically forward teams.
colors:
  paper: "#f4f6fa"
  panel: "#ffffff"
  ink: "#151923"
  muted: "#596273"
  rule: "#dde1e8"
  rule-strong: "#c5ccd8"
  code: "#eaeef4"
  lime: "#a3d500"
  lime-deep: "#426600"
  lime-wash: "#f1f8d9"
typography:
  display:
    fontFamily: "'Newsreader', Georgia, serif"
    fontSize: "clamp(2.9rem, 7.2vw, 5.4rem)"
    fontWeight: 500
    lineHeight: 0.95
    letterSpacing: "-0.04em"
  headline:
    fontFamily: "'Newsreader', Georgia, serif"
    fontSize: "clamp(2.3rem, 5vw, 3.4rem)"
    fontWeight: 500
    lineHeight: 1.02
    letterSpacing: "-0.03em"
  section:
    fontFamily: "'Newsreader', Georgia, serif"
    fontSize: "clamp(1.9rem, 3.4vw, 2.6rem)"
    fontWeight: 500
    lineHeight: 1.02
    letterSpacing: "-0.03em"
  title:
    fontFamily: "'Newsreader', Georgia, serif"
    fontSize: "1.5rem"
    fontWeight: 500
    lineHeight: 1.15
    letterSpacing: "-0.02em"
  lede:
    fontFamily: "'Geist', system-ui, sans-serif"
    fontSize: "1.12rem"
    fontWeight: 400
    lineHeight: 1.55
    letterSpacing: "0"
  body:
    fontFamily: "'Geist', system-ui, sans-serif"
    fontSize: "17px"
    fontWeight: 400
    lineHeight: 1.65
    letterSpacing: "0"
  prose:
    fontFamily: "'Geist', system-ui, sans-serif"
    fontSize: "1.05rem"
    fontWeight: 400
    lineHeight: 1.7
    letterSpacing: "0"
  button:
    fontFamily: "'Geist', system-ui, sans-serif"
    fontSize: "0.92rem"
    fontWeight: 600
    lineHeight: 1.3
    letterSpacing: "-0.01em"
  meta:
    fontFamily: "'Geist Mono', ui-monospace, monospace"
    fontSize: "0.74rem"
    fontWeight: 400
    lineHeight: 1.4
    letterSpacing: "0.08em"
rounded:
  sm: "4px"
  md: "6px"
  pill: "999px"
spacing:
  xs: "6px"
  sm: "12px"
  md: "20px"
  lg: "36px"
  xl: "48px"
  xxl: "56px"
components:
  button-primary:
    backgroundColor: "{colors.lime}"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
    padding: "0.6rem 1.3rem"
    height: "46px"
  button-secondary:
    backgroundColor: "{colors.panel}"
    textColor: "{colors.ink}"
    border: "1px solid {colors.rule-strong}"
    rounded: "{rounded.md}"
    padding: "0.6rem 1.3rem"
    height: "46px"
  chip:
    backgroundColor: "{colors.panel}"
    textColor: "{colors.muted}"
    border: "1px solid {colors.rule}"
    rounded: "{rounded.pill}"
    padding: "5px 11px"
  panel:
    backgroundColor: "{colors.panel}"
    border: "1px solid {colors.rule}"
    rounded: "{rounded.md}"
    padding: "20px 22px"
---

# Design System: Michael DeGoll

## 1. Overview

**Creative North Star: "The Field Notebook, printed on rebase paper"**

The site shares a visual family with rebase.team: cool-gray paper, white panels, near-black ink, one lime accent, serif headings over a plain sans body. It is still one person's notebook, not a company landing page. No photography, no section numbers, no eyebrow labels, no hero metrics. Headings carry their own weight.

**Key Characteristics:**

- Serif display (Newsreader, weight 500, tight tracking) against a quiet Geist body
- Cool-gray page with white panels for anything that is a list of real artifacts
- Lime appears in exactly four places: the primary button, link underlines, the active nav item, and the footer band
- Flat by default: borders and whitespace, never shadows

## 2. Colors

### Primary

- **Ink** (#151923): all text and the brand mark.
- **Paper** (#f4f6fa): page background.
- **Panel** (#ffffff): header, list entries, code blocks, table cells, the table of contents.

### Accent

- **Lime** (#a3d500): primary button fill, link underline, active nav underline, footer band. Text on lime is always ink.
- **Lime Deep** (#426600): focus rings, hover underline, blockquote rule. Passes AA on paper as text.
- **Lime Wash** (#f1f8d9): link hover background and chip hover.

### Neutral

- **Muted** (#596273): ledes, descriptions, metadata, secondary prose.
- **Rule** (#dde1e8): borders and dividers. **Rule Strong** (#c5ccd8): hovered panel borders and secondary button borders.
- **Code** (#eaeef4): inline code and table headers.

### Named Rules

**The One Accent Rule.** Lime is the only chroma on the site. Do not add teal, green, or ochre washes, and do not use lime as a text color.

## 3. Typography

**Display and headings:** Newsreader (Google Fonts, optical size axis, weight 500)
**Body and UI:** Geist (Google Fonts, 400 and 600)
**Metadata:** Geist Mono, uppercase, tracked 0.08em, 0.72 to 0.74rem

### Hierarchy

- **Display** (Newsreader 500, `clamp(2.9rem, 7.2vw, 5.4rem)`, 0.95, -0.04em): homepage hero only, max 15ch.
- **Headline** (Newsreader 500, `clamp(2.3rem, 5vw, 3.4rem)`, 1.02, -0.03em): page and playbook titles.
- **Section** (Newsreader 500, `clamp(1.9rem, 3.4vw, 2.6rem)`, 1.02, -0.03em): homepage section headings in the left column.
- **Content H2** (Newsreader 500, 1.85rem, 1.15, -0.025em): long-form section headings, no underline rule.
- **Title** (Newsreader 500, 1.5rem list entries, 1.3rem home cards, 1.35rem content H3).
- **Lede** (Geist 400, 1.12rem, 1.55, muted): page descriptions and playbook deks, max 62ch.
- **Prose** (Geist 400, 1.05rem, 1.7): posts and playbooks. Home prose runs at 1.08rem / 1.65.
- **Body** (Geist 400, 17px, 1.65): default.
- **Meta** (Geist Mono 400, 0.74rem, uppercase): dates, chips, table-of-contents label, footer.

### Named Rules

**The No Eyebrow Rule.** No kicker or label above a heading. If a page needs a stage or audience marker, it goes in a chip below the dek.

**The Serif Carries It Rule.** Headings are 500, never bold. Emphasis in prose is Geist 600.

## 4. Elevation

Flat. Depth comes from the panel-on-paper contrast and 1px rules. Panels darken their border on hover instead of lifting.

### Named Rules

**The No Floating Deck Rule.** No box shadows anywhere.

## 5. Components

### Buttons

- **Primary:** lime fill, ink text, 1px lime border, 6px radius, 46px minimum height, Geist 600 at 0.92rem. Hover brightens the fill and darkens the border to Lime Deep.
- **Secondary:** white fill, ink text, Rule Strong border. Hover darkens the border to ink.
- **Focus:** 2px Lime Deep outline, 3px offset, on every interactive element.
- On narrow screens, hero and closing buttons go full width and stack.

### Links

Ink text with a 2px lime underline at 0.2em offset. Hover adds a Lime Wash background and a Lime Deep underline. Nav links, footer links, and card title links drop the underline and use color or a plain underline on hover instead.

### Chips

Pill, white, Rule border, muted Geist Mono at 0.74rem. Used for playbook metadata and tags only.

### Panels

White, Rule border, 6px radius, 20 to 22px padding. Used for list entries, home playbook and writing cards, code blocks, the table of contents, and the Mermaid container. Nested panels are never used.

### Navigation

White header with a bottom rule. Brand in Geist 600 at 1.2rem with -0.03em tracking. Menu items muted Geist 500 at 0.92rem; the active item is ink with a 2px lime underline. Three items: Playbooks, Writing, About.

### Footer

Full-width lime band, Geist Mono uppercase at 0.72rem, ink text, centered: name, email, year. Items separated by a middle dot on desktop and stacked on mobile.

### Home sections

Two-column grid: serif section heading in a 0.42fr left column, content in the right column, 56px column gap, 48px vertical padding, bottom rule. Collapses to one column at 820px.

## 6. Do's and Don'ts

### Do:

- **Do** keep every page on the same paper, panel, ink, lime set.
- **Do** list real artifacts (playbooks, posts) in panels rather than describing capabilities in card grids.
- **Do** keep reading measure at 60 to 62ch.
- **Do** keep the Newsreader optical size axis on, so small headings do not look spindly.

### Don't:

- **Don't** add kickers, eyebrows, section numbers, icon grids, metric blocks, or gradients.
- **Don't** add a second accent color or use lime as text.
- **Don't** use bold serif. Headings are 500.
- **Don't** reintroduce "Powered by" footers, scroll-to-top buttons, breadcrumbs, or share buttons.
- **Don't** use em dashes or double-hyphen substitutes in public copy.
