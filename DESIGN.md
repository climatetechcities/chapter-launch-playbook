---
version: 17.0.0
name: CTC-Playbook-design
description: The Chapter Launch Playbook's design system. The material is Hallmark's Editorial theme (square corners, a heavy ink rule over 1px hairlines, one ink band, cream wells, no shadows), set in Inter, and every colour is climatetechcities.com's own. Chosen on 2026-11-02 from three Hallmark samples (polish, restyle, full): the restyle, with Inter kept from the polish.

colors:
  paper: "#fefefd"        # CTC paper: the page
  paper-2: "#f5f4e9"      # CTC cream: wells, callouts, the city field, the footer
  paper-3: "#e4e4dc"
  ink: "#25331a"          # CTC olive: heads, body, the ink band, the primary button
  muted: "#55554e"        # CTC slate: captions, labels, every field edge (3:1 on paper)
  rule: "#e4e4dc"         # hairlines between rows
  rule-2: "#9b9b94"       # CTC stone: under table heads; decorative only (2.8:1)
  accent: "#afd98f"       # CTC meadow: the one green, under 5% of a screen (link hover, current step, progress)
  lavender: "#e2bdff"     # CTC accent: only on the ink band and prompt blocks (labels, Copy, focus on ink)
  coral: "#ef653a"        # Claude's work and nothing else
  coral-deep: "#c24d1c"   # coral under paper text: the Claude badge
  water: "#cfe3ec"        # spare
  leaf: "#d1ecbc"         # spare
  app-excel: "#1d6f42"    # file-type badge and the viewer's sheet tab
  app-word: "#2b579a"     # file-type badge
  key-*: "the plugins' own spreadsheet fills, for the colour keys under each sample"

typography:
  family: Inter for everything; Geist Mono for prompts and filenames only
  hero: { size: "clamp(2.25rem, 5.4vw, 4.5rem)", weight: 500, tracking: -0.035em, leading: 1 }
  home-section: { size: "clamp(2rem, 4vw, 3.5rem)", weight: 500, tracking: -0.035em }
  page-title: { size: "clamp(2rem, 3.4vw, 2.5rem)", weight: 500, tracking: -0.03em }
  section: { size: "clamp(1.75rem, 1.6vw + 1rem, 2.25rem)", weight: 500, tracking: -0.03em }
  title: { size: "1.25rem to 1.5rem", weight: 600, tracking: -0.01em }
  body: { size: 16px, weight: 400, leading: 1.55 }
  lead: { size: "1.0625rem to 1.25rem", weight: 400 }
  label: { size: 15px, weight: 500, case: sentence, tracking: 0 }

shape:
  radius: 0 everywhere
  rules: { heavy: "4px ink, opens a section, a table, the header, the pager", hair: "1px rule between rows" }
  shadows: none
  motion: state only (a link underline turns meadow, a block darkens); no scroll reveals
---

## How it came about

On 2026-11-02 the site was put through Hallmark (github.com/nutlope/hallmark), a design skill that checks a page against habits that read as machine-made. Three samples were built from the home and Install pages: **polish** (the Clay + CTC system kept, only the flagged habits fixed), **restyle** (layouts kept, Hallmark's Editorial theme in CTC colours) and **full** (pages recomposed in Editorial). The restyle was chosen, with Inter kept from the polish in place of Editorial's condensed Bricolage and serif Source Serif. The samples stay on the `hallmark-samples` branch.

`DESIGN-clay.md` (the previous structure) and `DESIGN-climate-tech-cities.md` (the palette's source, extracted from climatetechcities.com on 2026-09-26) remain as references.

## Rules

- **Colour:** CTC's palette only, through the tokens at the top of `assets/site.css`. Olive is the ink; cream is the only second paper; meadow is the one green and stays small; lavender lives only on olive; coral means Claude.
- **Attribution:** coral for Claude's work, olive for the lead's, a cream ground where the lead finishes. Badges, swatches and the sample issue all follow it.
- **Type:** Inter. Heads are weight 500 with negative tracking, titles 600, body 400 at 16px. Labels, nav, buttons, captions and table heads are a step smaller in sentence case with no letter-spacing. No uppercase labels and no eyebrows above headings: a page's place in the steps ("Step 02 of 05, once", with the progress segments) sits directly under its title.
- **Surfaces:** square corners, no shadows. A 4px olive rule opens the header, each home section, tables and the pager; 1px hairlines part rows. Cream wells hold callouts and the city field. One olive band per page at most (the home loop), plus the olive prompt blocks.
- **Controls:** an olive block for the primary action beside a 1px olive outline for the secondary, 48px tall. Inputs are square with a slate edge that turns olive on focus. Links carry a hairline underline that turns meadow on hover.
- **Pictures:** the product's own: claude.ai screenshots, the sample files, the sample issue. No stock photos, no emoji as icons (the full sample issue on the Weekly cycle page keeps the emoji the newsletter itself writes).

## Hallmark check

`node <hallmark>/skills/hallmark/scripts/sloplint.mjs index.html */index.html assets/site.css --genre editorial` reports 0 Floor findings apart from the eight emoji the Weekly cycle sample issue keeps on purpose. Inter as the display face is waived in the stylesheet's stamp (chosen by the owner).
