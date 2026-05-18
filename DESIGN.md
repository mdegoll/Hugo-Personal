---
name: Michael DeGoll
description: Purpose-built software and AI agent work for operators, founders, and technically forward teams.
colors:
  paper: "#ffffff"
  surface: "#ffffff"
  ink: "#1e1e1e"
  body: "#1f1f1f"
  muted: "#6c6c6c"
  rule: "#eeeeee"
  code: "#f5f5f5"
  teal-wash: "#145c78"
  green-wash: "#467240"
  ochre-wash: "#a87026"
typography:
  display:
    fontFamily: "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif"
    fontSize: "clamp(2.5rem, 5vw, 5rem)"
    fontWeight: 700
    lineHeight: 0.96
    letterSpacing: "0"
  headline:
    fontFamily: "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif"
    fontSize: "clamp(2.25rem, 5vw, 4.75rem)"
    fontWeight: 700
    lineHeight: 0.98
    letterSpacing: "0"
  body:
    fontFamily: "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif"
    fontSize: "18px"
    fontWeight: 400
    lineHeight: 1.6
    letterSpacing: "0"
  label:
    fontFamily: "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif"
    fontSize: "0.78rem"
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: "0"
rounded:
  sm: "4px"
  md: "8px"
  pill: "999px"
spacing:
  xs: "8px"
  sm: "14px"
  md: "20px"
  lg: "24px"
  xl: "40px"
components:
  button-primary:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.paper}"
    rounded: "{rounded.md}"
    padding: "0.55rem 0.85rem"
    height: "42px"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
    padding: "0.55rem 0.85rem"
    height: "42px"
  chip:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.muted}"
    rounded: "{rounded.pill}"
    padding: "0.42rem 0.7rem"
---

# Design System: Michael DeGoll

## 1. Overview

**Creative North Star: "The Field Notebook"**

The site should feel like a practical notebook from someone who understands both business operations and software implementation. It is not trying to look like a venture-backed AI product, a Salesforce consultancy, or a polished agency portfolio. It should feel clear, useful, and edited.

The visual system is intentionally light: strong type, tight rhythm, restrained borders, and small moments of muted color. The site should look simple enough to publish quickly, but consistent enough that the ideas feel considered.

**Key Characteristics:**

- Plainspoken and technically credible
- Mostly text-led, with one real personal image and useful proof artifacts
- Restrained palette with muted teal, green, and ochre as quiet support
- Low decoration, no spectacle, no AI-template gestures

## 2. Colors

The palette is neutral-first with a muted operational accent set. Color supports structure instead of becoming the story.

### Primary

- **Ink** (#1e1e1e): primary text and filled buttons.
- **Paper** (#ffffff): main page background and button text on filled actions.

### Secondary

- **Muted Teal** (#145c78): used in low-opacity washes and top rules. It should feel like annotation, not branding wallpaper.
- **Field Green** (#467240): supports the gradient wash on proof sections.
- **Quiet Ochre** (#a87026): adds warmth to the same wash without becoming a startup gradient.

### Neutral

- **Body Ink** (#1f1f1f): long-form content text.
- **Muted Copy** (#6c6c6c): secondary paragraphs, metadata, and proof lists.
- **Rule** (#eeeeee): borders and dividers.
- **Code Surface** (#f5f5f5): code and low-emphasis surface backgrounds.

### Named Rules

**The Color Stays Useful Rule.** Use accent colors as structure, wash, or subtle emphasis. Do not make the site feel like an AI SaaS gradient.

## 3. Typography

**Display Font:** System sans stack  
**Body Font:** System sans stack  
**Label/Mono Font:** System sans stack

**Character:** The type should feel direct and native to the web. The system stack is acceptable here because the writing and spacing carry the identity; do not add a decorative font just to look designed.

### Hierarchy

- **Display** (700, `clamp(2.5rem, 5vw, 5rem)`, 0.96): homepage hero only.
- **Headline** (700, `clamp(2.25rem, 5vw, 4.75rem)`, 0.98): page titles and playbook heroes.
- **Title** (700, 1.2 to 1.5rem, 1.25): section and card headings.
- **Body** (400, 18px, 1.6): posts, playbooks, and page copy. Keep reading width near 65 to 75 characters.
- **Label** (700, 0.78rem, 0 letter-spacing): occasional kicker text only.

### Named Rules

**The Fewer Labels Rule.** Kicker labels are allowed, but they should not appear above every section. Repetition reads like AI scaffolding.

## 4. Elevation

The site is flat by default. Depth comes from spacing, borders, and tonal shifts rather than shadows. This fits the practical, notebook-like direction and keeps the page from feeling like generic SaaS.

### Named Rules

**The No Floating Deck Rule.** Do not introduce decorative shadows or floating card stacks. Use a border, a rule, or more whitespace first.

## 5. Components

### Buttons

- **Shape:** compact rectangles with 8px radius.
- **Primary:** ink background, paper text, 42px minimum height, small horizontal padding.
- **Secondary:** paper background, ink text, 1px rule border.
- **Hover / Focus:** preserve PaperMod focus behavior, but make custom buttons expose a visible outline or underline on focus.

### Chips

- **Style:** pill shape, border, white background, muted text.
- **Use:** metadata and compact qualifiers only. Do not use chips as decorative proof metrics.

### Cards / Containers

- **Corner Style:** 8px radius maximum.
- **Background:** white or a very light wash.
- **Shadow Strategy:** none.
- **Border:** 1px neutral rule. Avoid colored side stripes.
- **Internal Padding:** 1rem for compact content, 1.5 to 2.25rem for hero or feature blocks.

### Inputs / Fields

The current public site does not define custom input fields. If a contact form returns, use the same 8px radius, neutral border, visible label, and explicit focus outline.

### Navigation

Keep navigation simple and text-based. The current menu should stay small enough that Home, About, Playbooks, and Blog can coexist without feeling like a product nav.

### Signature Component

Playbook pages use a bordered hero with clear title, deck, metadata chips, and optional diagrams. Keep this format sober and document-like; it should feel like a proof artifact, not a lead magnet.

## 6. Do's and Don'ts

### Do:

- **Do** keep pages simple, consistent, and easy to publish.
- **Do** use direct copy that names the operating problem before the tool.
- **Do** preserve generous line-height and readable measure for long posts.
- **Do** use muted color washes sparingly to separate important proof sections.
- **Do** make the site credible to operators, founders, technical founders, and AI platform teams.

### Don't:

- **Don't** use generic AI consultant language, AI-demo theater, or "transformation" filler.
- **Don't** make the site Salesforce-first.
- **Don't** use corporate blue gradients, glassmorphism, gradient text, hero metric blocks, or repeated icon-card grids.
- **Don't** over-polish the site into an agency deck. It should be pretty and consistent, but still feel personal.
- **Don't** use em dashes or double-hyphen substitutes in public copy.
