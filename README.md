# CTC Chapter Launch Playbook, companion site

Live: **https://climatetechcities.github.io/chapter-launch-playbook/**

This is the only live site. It replaces two earlier repositories,
`ctc-chapter-launch-workflow` and `ctc-chapter-launch-workflow-v2`, both
retired on 2026-08-17. Their URLs no longer serve.

Pages publishes from `.github/workflows/pages.yml` rather than the classic
branch builder, which removes the Jekyll build step this static site never
needed.

A static companion site for the Climate Tech Cities chapter toolkit: three
packages, nine skills, covering a new chapter lead's launch.

| Package | Kind | Contains |
|---|---|---|
| `ctc-chapter-setup` v1.6.0 | Plugin, 1 skill | Eight questions in one message, writes the settings file and launch plan |
| `ctc-newsletter` v2.5.1 | Plugin, 5 skills | `ctc-newsletter-cycle`, `ctc-source-map`, `ctc-harvest`, `ctc-opportunities`, `ctc-assemble` |
| `ctc-partner-map` v2.2.0 | Plugin, 3 skills | `ctc-city-resources`, `ctc-partner-list`, `ctc-partner-outreach` |

The logo phase runs in ChatGPT rather than Claude, and the site carries the
house prompt and the reference artwork for it.

**The skills do the work, inside the lead's own Claude account.** This site has
no backend, no account connection, and stores nothing.

## Pages

Ten static pages. The six steps are numbered in the order a lead works
through them and carry a previous and next pair. Partners and the two
reference pages are not numbered: the newsletter does not depend on the
partner map. The former step 1, Is this you?, was recruitment framing and
was cut in v13; its definition of done lives on the Two-week overview page.

| Page | Path | Holds |
|---|---|---|
| Home | `/` | The numbered map, the counts, one statement |
| Overview | `/two-weeks/` | The plan table and what done looks like |
| 1 Logo | `/logo/` | The ChatGPT prompt, the five reference files, the sign-off |
| 2 Install | `/install/` | The three packages, the extension, the verify prompt |
| 3 Set up | `/set-up/` | The eight questions, the two documents |
| 4 Newsletter | `/newsletter/` | Source list (`#sources`), opportunities queue (`#opportunities`) |
| 5 Weekly cycle | `/weekly-cycle/` | Collect, cut, write, send (`#collect` `#cut` `#write` `#sample` `#send`) |
| Partners | `/partners/` | City resources, partner map, outreach. Optional |
| Help | `/help/` | Troubleshooting |
| Downloads | `/downloads/` | Packages and the nine samples |

Every anchor from the old single page (`/#setup`, `/#cycle`, and so on) is
redirected by the home page to the matching new page; `/#apply` and the
retired `/apply/` address land on the Two-week overview.

## Design

Two sources, one rule each, written up in `DESIGN.md`. The structure is
Clay's (`DESIGN-clay.md`): filled primary buttons 44px tall with 12px
corners, display type at weight 500 with negative tracking, a 12/16/24px
corner scale, saturated single-colour feature cards cycled down the page,
flat depth with no shadows, a warm cream footer. Every colour is
climatetechcities.com's own (`DESIGN-climate-tech-cities.md`, extracted from
that site's stylesheets on 2026-09-26): each Clay colour role is filled with
the CTC colour that plays the same part, and no Clay hex is used.

Paper `#fefefd` canvas, cream `#f5f4e9` for callouts, the city field, the
active nav item and the footer. Headings pure black, prose olive `#25331a`,
primary buttons olive. The overview and five steps are six feature cards in
coral, olive, lavender, meadow, water and cream; the weekly loop is an olive
featured card. Coral still marks Claude's work (darkened to `#c24d1c` under
paper text); lavender is the accent on dark surfaces.

Type is Inter (Clay's documented substitute for its licensed Plain Black),
from Google Fonts like Geist Mono, which stays for prompts and filenames.
Display 500, titles 600, body 400 at 16px, letter-spacing 0 except the
display sizes. Headings are olive, and labels are sentence case with no
letter-spacing (a Hallmark polish, 16.1.0). Every icon is from Regen Icons
(github.com/kazdenc/regen-icons, MIT), kept in `assets/icons/` with its
licence (16.2.0). No middle dots and no em
dashes anywhere.

## Standing rules

- Nothing fake: every control either works in the browser or hands off a
  copy-ready prompt.
- Static: no backend, no accounts, no cookies, no localStorage, no analytics.
  The city typed in the sidebar travels in the URL between pages and is never
  written to the browser.
- Nothing invented: every claim about what a skill does traces to that skill's
  own `SKILL.md`. Gaps are marked TODO in the source rather than papered over.
- Required means required. A page only joins the numbered spine when a lead
  cannot send the newsletter without it. Partners is optional and is labelled
  that way in the sidebar, on the home page, in the plan, and on its own page.
- Only what helps someone run the process. Recruitment framing, slogans and
  illustrative asides come out; a line stays if a lead acts on it or checks
  against it.
- Every step that produces a file shows a What you get back card built from
  the real sample in `downloads/samples/`, with Preview and Download beside it.
  Preview renders the whole file, page by page, from the same document the
  Download button hands over.
- Less: say it once. Verified facts stay; restatement, reassurance and hedging
  do not. Longer reasoning goes in a collapsed details block, not in the way.
- US English, no em dashes, no time estimates, no day names in the weekly
  cycle. The one allowed framing is "two weeks of setup, then about one
  sitting a week".

## Contents

- `index.html` and one `index.html` per page directory, listed above. No
  framework, no build step: the shell (top bar, sidebar, footer, viewer) is
  written into each file, so a change to the navigation is a change to all
  ten
- `DESIGN.md`, the design system the skin follows: Clay's structure with
  CTC's colours. `DESIGN-clay.md` and `DESIGN-climate-tech-cities.md`
  (extracted from climatetechcities.com on 2026-09-26) are its two sources
- `assets/site.css`, `assets/site.js`, shared by every page. Each page sets
  `window.ROOT` (`""` at the root, `"../"` one level down) before loading the
  script so asset paths resolve
- `downloads/guide/`, five screenshots of claude.ai used on the Install and
  Set up pages, cropped to the panel and marked with what to click. Taken
  2026-09-11; Claude's settings screens move, so re-take these when a step
  stops matching what a lead sees
- `downloads/`, the three package zips, the five brand PNGs, and `samples/`
  with the nine sample files plus `samples/previews/`, one interactive preview
  per sample (`<key>.html`): spreadsheets as Excel-style grids with sheet tabs,
  Word files as Word's own HTML export. The file viewer loads them into a
  shadow root and zooms them. Rebuild with `python tools/build_previews.py`
  whenever a sample changes (Windows with Word for the .docx files)
- `version.json`, version and date
- `playbook/newsletter-chapter.md`, Chapter 8 draft for the CTC Operational Playbook
- `TODO.md`, open items
