---
version: 16.2.0
name: CTC-Playbook-design
description: The Chapter Launch Playbook's design system. Structure, type, shape and components follow Clay (DESIGN-clay.md); every colour is climatetechcities.com's own (DESIGN-climate-tech-cities.md). Warm paper canvas, filled olive primary buttons, Inter set at weight 500 with negative tracking for display, a 12/16/24px corner scale, and six saturated CTC colours cycled as feature cards. Flat, no shadows, warm cream footer.

colors:
  # Clay role: CTC colour (CTC token name)
  primary: "#25331a"            # olive ink, CTC's "black"
  primary-active: "#233b10"     # CTC's shape-block green, a step deeper than the ink
  on-primary: "#fefefd"         # paper
  ink: "#25331a"                # headlines in CTC olive, as on CTC's cream sections
  body: "#25331a"               # running text in olive
  muted: "#55554e"              # slate: sub-heads, captions, labels
  muted-soft: "#9b9b94"         # stone: decorative numerals only, fails AA as text
  hairline: "#e4e4dc"
  canvas: "#fefefd"             # paper, CTC's "white"
  panel: "#fcfcf9"              # hover wash
  surface-soft: "#f5f4e9"       # cream: footer, city field
  surface-card: "#f5f4e9"       # cream: callouts, badges, active nav item
  surface-strong: "#e4e4dc"
  surface-dark: "#25331a"       # prompt blocks, the featured card
  on-dark: "#fefefd"
  on-dark-muted: "rgba(254, 254, 253, 0.72)"
  # the six feature-card fills, in Clay's cycle order
  card-1: "#ef653a"             # coral    (Clay pink)
  card-2: "#25331a"             # olive    (Clay teal)
  card-3: "#e2bdff"             # lavender (Clay lavender)
  card-4: "#afd98f"             # meadow   (Clay peach)
  card-5: "#cfe3ec"             # water    (Clay ochre)
  card-6: "#f5f4e9"             # cream    (Clay cream)
  leaf: "#d1ecbc"               # spare accent (Clay mint)
  coral-deep: "#c24d1c"         # coral darkened for paper text: the Claude badge

typography:
  display-xl:  { fontFamily: Inter, fontSize: 72px, fontWeight: 500, lineHeight: 1,    letterSpacing: -2.5px }  # home h1
  display-lg:  { fontFamily: Inter, fontSize: 56px, fontWeight: 500, lineHeight: 1.05, letterSpacing: -2px }    # home section heads
  display-md:  { fontFamily: Inter, fontSize: 40px, fontWeight: 500, lineHeight: 1.1,  letterSpacing: -1px }    # page h1
  display-sm:  { fontFamily: Inter, fontSize: 32px, fontWeight: 500, lineHeight: 1.15, letterSpacing: -0.5px }  # page h2
  title-lg:    { fontFamily: Inter, fontSize: 24px, fontWeight: 600, lineHeight: 1.3,  letterSpacing: -0.3px }  # h3, step titles, feature-card titles
  title-md:    { fontFamily: Inter, fontSize: 18px, fontWeight: 600, lineHeight: 1.4,  letterSpacing: 0 }       # card titles, pager
  body-md:     { fontFamily: Inter, fontSize: 16px, fontWeight: 400, lineHeight: 1.55, letterSpacing: 0 }
  body-sm:     { fontFamily: Inter, fontSize: 14px, fontWeight: 400, lineHeight: 1.55, letterSpacing: 0 }
  caption:     { fontFamily: Inter, fontSize: 13px, fontWeight: 500, lineHeight: 1.4,  letterSpacing: 0 }       # badges
  label:       { fontFamily: Inter, fontSize: 13px to 14px, fontWeight: 500 to 600, lineHeight: 1.4, letterSpacing: 0, case: sentence }  # page labels, sidebar groups, table heads
  button:      { fontFamily: Inter, fontSize: 14px, fontWeight: 600, lineHeight: 1,    letterSpacing: 0 }
  nav-link:    { fontFamily: Inter, fontSize: 14px, fontWeight: 500, lineHeight: 1.4,  letterSpacing: 0 }
  mono:        { fontFamily: Geist Mono, fontSize: 13.5px, fontWeight: 400 }                                   # prompts, filenames

rounded: { xs: 6px, sm: 8px, md: 12px, lg: 16px, xl: 24px, pill: 9999px, full: 50% }
spacing: { xxs: 4px, xs: 8px, sm: 12px, md: 16px, lg: 24px, xl: 32px, xxl: 48px, section: 96px }

components:
  top-nav:            { backgroundColor: "{colors.canvas}", height: 64px, typography: "{typography.nav-link}", link: pill, active: "{colors.surface-card}" }
  button-primary:     { backgroundColor: "{colors.primary}", textColor: "{colors.on-primary}", rounded: "{rounded.md}", height: 44px, padding: 12px 20px }
  button-secondary:   { class: .btn.outline, backgroundColor: "{colors.canvas}", textColor: "{colors.ink}", border: "1px {colors.hairline}", rounded: "{rounded.md}" }
  button-small:       { class: .btn.sm, height: 34px, rounded: "{rounded.sm}" }
  button-on-color:    { class: .btn.lav, backgroundColor: "{colors.canvas}", textColor: "{colors.ink}", use: on the featured olive card }
  hero-band:          { backgroundColor: "{colors.canvas}", grid: 7/5, padding: 96px }
  hero-artifact:      { backgroundColor: "{colors.card-3}", rounded: "{rounded.xl}", holds: the sample-issue card on canvas, rounded lg }
  feature-card:       { class: .tiles a, backgroundColor: "card-1 .. card-6 by position", rounded: "{rounded.xl}", padding: 32px, title: "{typography.title-lg}" }
  featured-card:      { class: .band-wrap, backgroundColor: "{colors.surface-dark}", textColor: "{colors.on-dark}", rounded: "{rounded.xl}", padding: 64px, accent: "{colors.card-3}" }
  content-card:       { class: .card, backgroundColor: "{colors.canvas}", border: "1px {colors.hairline}", rounded: "{rounded.lg}", padding: 24px }
  callout:            { class: .note, backgroundColor: "{colors.surface-card}", rounded: "{rounded.lg}", padding: 16px 20px }
  prompt-block:       { class: .prompt-card, backgroundColor: "{colors.surface-dark}", rounded: "{rounded.lg}", copy: lavender fill, olive text }
  sidebar-item:       { rounded: "{rounded.md}", typography: "{typography.nav-link}", active: "{colors.surface-card} fill, ink, 600" }
  text-input:         { backgroundColor: "{colors.canvas}", border: "1px {colors.hairline}", rounded: "{rounded.md}", height: 44px, focused: ink border }
  badge-pill:         { class: .tag, backgroundColor: "{colors.surface-card}", typography: "{typography.caption}", rounded: "{rounded.pill}", padding: 4px 12px }
  footer:             { backgroundColor: "{colors.surface-soft}", textColor: "{colors.muted}", padding: 64px }
---

## Overview

Two sources, one rule each. **Clay decides how things are built**: type scale and weights, corner radii, spacing, button and card anatomy, the long-scroll rhythm of saturated feature cards, flat depth, a warm footer. **Climate Tech Cities decides every colour**: no Clay hex appears anywhere. Each Clay colour role is filled with the CTC colour that plays the same part on climatetechcities.com.

CTC's palette was extracted from the site's own stylesheets on 2026-09-26 and is recorded in `DESIGN-climate-tech-cities.md`. Clay's system is `DESIGN-clay.md`.

## How Clay's roles map to CTC's colours

| Clay role | Clay hex | CTC colour used | Why |
|---|---|---|---|
| primary (buttons) | `#0a0a0a` | olive `#25331a` | CTC's declared "black" |
| primary-active | `#1f1f1f` | `#233b10` | CTC's shape-block green |
| ink (headlines) | `#0a0a0a` | olive `#25331a` | CTC's cream sections set headings in olive (no pure black, per Hallmark) |
| body | `#3a3a3a` | olive `#25331a` | CTC sets prose in its ink |
| muted | `#6a6a6a` | slate `#55554e` | CTC's secondary text |
| canvas | `#fffaf0` | paper `#fefefd` | CTC's warm white; long reading pages |
| surface-soft / surface-card | `#faf5e8` / `#f5f0e0` | cream `#f5f4e9` | CTC's site background, almost exactly Clay's card cream |
| brand-pink | `#ff4d8b` | coral `#ef653a` | CTC's hot accent |
| brand-teal (featured) | `#1a3a3a` | olive `#25331a` | CTC's dark surface |
| brand-lavender | `#b8a4ed` | lavender `#e2bdff` | CTC's theme accent |
| brand-peach | `#ffb084` | meadow `#afd98f` | CTC's map green |
| brand-ochre | `#e8b94a` | water `#cfe3ec` | CTC's map water |
| brand-mint | `#a4d4c5` | leaf `#d1ecbc` | CTC's glyph green (spare) |

Contrast, checked: black on coral 6.6:1 (so coral cards take black text, never white); paper on olive 13.3:1; olive on lavender 8.3:1, on meadow 8.4:1, on water 10.1:1, on cream 12.1:1; slate on paper 7.4:1. Stone `#9b9b94` is 2.8:1 on paper, so it is kept for decorative step numerals only.

## Typography

Inter throughout. Clay's display face, Plain Black, is licensed to Clay; its own documentation names Inter at weight 500 with negative tracking as the substitute, and that is what is used. Display sizes are always weight 500, never bolder, with Clay's negative letter-spacing. Titles are 600, body 400, letter-spacing 0. Labels (page labels, sidebar groups, table heads) are a step smaller in sentence case with no letter-spacing; nothing is set in tracked capitals. A page label that is not a step sits under its title. Geist Mono stays for prompts and filenames.

The previous skin's Catamaran and Gantari files are still in `assets/fonts/` but no longer loaded.

## Shape and depth

Corners: 12px buttons, inputs and nav items; 16px content cards, prompt blocks, figures, callouts; 24px feature cards, the hero artifact, the featured card and the viewer; pills for badges, tags and top-nav links; circles for step markers. No shadows: depth comes from a saturated or cream fill against the paper canvas, or a 1px hairline.

## Components

- **Home hero.** Paper band, 7/5 grid, 96px padding. Display-xl headline left; right, a lavender 24px card holding the sample-issue card (the product fragment, standing in for Clay's illustration).
- **Feature cards.** The overview and five steps are six saturated cards, coloured by position in Clay's cycle: coral, olive, lavender, meadow, water, cream. No colour repeats next to itself in the 3-column, 2-column or 1-column layout. Icon top left, step number and title-lg title, short description.
- **Optional step.** A hairline card in the same 24px shape, deliberately not coloured, so Partners reads as outside the required six.
- **Featured card.** The "Claude does the lists" loop is an olive 24px card inside the page margin, Clay's featured surface, with lavender role labels and counts and a canvas button.
- **Docs pages.** Paper canvas, sticky sidebar with Clay's tab treatment (cream fill on the current page), display-md page titles, display-sm section heads. Callouts are cream cards; content cards are hairline cards; prompts are olive cards with a lavender Copy button.
- **Attribution colours are unchanged.** Coral marks Claude's work, olive marks the lead's, in badges, swatches and the sample issue. Spreadsheet colour keys keep the files' own fills.
- **Footer.** Cream, never dark, 64px padding.

## Do and don't

- Do take every colour from the table above. A new surface picks a CTC token, never a Clay hex.
- Do keep display type at weight 500 with negative tracking.
- Do cycle feature cards in order; never put two of the same colour side by side.
- Don't put white text on coral; use black.
- Don't add shadows, or a seventh card colour.
- Don't use a dark footer.

## Hallmark polish (16.1.0)

On 2026-11-02 the site was checked with Hallmark (github.com/nutlope/hallmark) and polished: the system and layouts stayed, and only what its checker flags changed. Headings went from pure black to olive; uppercase tracked labels became sentence case; every colour, including the spreadsheet colour keys, goes through a token; content is visible before the script runs; sideways overflow is clipped rather than hidden; pressed and disabled states exist; the home sample-issue card lost its emoji. Still open by choice: Inter as the display face (this system's face) and the emoji in the Weekly cycle sample issue (what the newsletter writes). The restyle and full-redesign samples it was compared with are on the `hallmark-samples` branch.

## Iconography (16.2.0)

Every icon comes from Regen Icons (github.com/kazdenc/regen-icons, MIT), the outline set: a 24px grid, round caps, stroke 2 at control size and Regen's 1.5 weight at the 44px tile size. The SVGs used live in `assets/icons/` with Regen's licence. Small marks are drawn as CSS masks from tokens (`--i-<name>`) so they take the text colour; larger drawings are inline SVG.

| Where | Icon |
|---|---|
| Home tiles | calendar (overview), pencil (logo), cube (install), clipboard-check (set up), mail (newsletter), refresh (weekly cycle) |
| Arrows on links, pager, the weekly flow | arrow-right |
| Done lists | check, on the lavender disc |
| Help accordion | chevron-down, turning over when open |
| Expanders | plus and minus |
| Copy, Preview, Download, mobile Steps | copy, eye, download, menu |
| File viewer | minus and plus (zoom), x (close) |

Adding one: copy its SVG from Regen's `svg/outline/` into `assets/icons/`, then either add a `--i-<name>` mask token or inline it. Do not draw icons by hand or mix in another set; emoji are not icons.

## Known gaps

- Clay's 3D claymation illustrations are commissioned assets; there are none here. The hero uses a real product fragment (the sample issue) inside a saturated card, as Clay's feature cards do.
- climatetechcities.com could not be re-fetched on 2026-11-02 (outside this session's network allowlist), so the palette is the 2026-09-26 extraction.
