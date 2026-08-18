# Engineering Portfolio — Aatiesh

A single-page portfolio built around a technical blueprint aesthetic: drafting-navy ground, cyan
linework, one amber accent used sparingly, and the whole page framed as a numbered drawing set
("SHEET 01 / 04" ... a title-block footer) rather than a generic template layout.

## Design System

Everything is driven by CSS custom properties defined once in `:root`, so the whole page reads as
one system rather than a pile of one-off styles.

**Colour**
| Token | Value | Use |
|---|---|---|
| `--bg` | `#0a1420` | Base drafting-navy background |
| `--bg-2` / `--bg-3` | `#0d1c2c` / `#11253a` | Panel and hover fills |
| `--cyan` / `--cyan-bright` | `#8ecfe8` / `#c3e8f7` | Primary linework, headings, accents |
| `--amber` / `--amber-bright` | `#ffab4d` / `#ffc57a` | The one bold accent — CTA fill, stamps, endorsement tags |
| `--paper` | `#eef6fb` | Primary text |
| `--ink` / `--ink-dim` | `#a9c1d1` / `#5f7b8f` | Body copy / tertiary labels |

**Type** — three families, each with a job: `Space Grotesk` (display headings), `IBM Plex Mono`
(labels, nav, data, tags — anything reading as a technical annotation), `Inter` (body copy).

**Spacing** — a `--sp-1` … `--sp-20` scale (0.25rem → 9rem) used throughout instead of ad hoc values.

**Motifs** — a live grid-paper background (`body` background-image, two layered grid sizes), drawn
dimension-line rules under section headers (SVG-free, CSS `scaleX` transform triggered on scroll),
corner registration marks, a rotated dashed "stamp" badge on the flagship project, and a footer
styled as an engineering title block (Title / Sheet / Scale / Rev / Date).

## Interactions

- Scroll-triggered reveals (`IntersectionObserver`) with a shared easing curve
- Count-up animation on stat numbers when they enter the viewport
- A scroll-progress ruler pinned under the nav, plus active-section highlighting in the nav links
- A cursor coordinate readout in the hero (desktop + fine-pointer only — hidden on touch)
- A full-screen mobile nav panel below 960px
- `prefers-reduced-motion: reduce` disables the scroll/count/line-draw animations and the smooth-scroll behaviour

## Sections

1. **Hero** — name, tagline, key stats, contact links
2. **Sheet 01 — Academic Profile** — NCEA history, current subjects, ambassadorships
3. **Sheet 02 — Engineering Projects** — flagship build (Tago RFID attendance system) plus four
   supporting projects
4. **Sheet 03 — Leadership & Service** — a role/organisation/impact table, plus service metrics
5. **Sheet 04 — Honours & Recognition** — competitions, university challenges, school awards
6. **Contact / footer** — CTA and a title-block-style footer

## Setup

Single static HTML file, no build step, no dependencies.

1. Open `index.html` directly in a browser, or serve the folder with any static file server
2. Deploys as-is to Vercel (or any static host) — no build command needed

### Customisation

- **Personal info** — update the `mailto:` and GitHub links (appear in the hero and the closing CTA)
- **Content** — each section is a `.sheet` block with an `id`; edit the markup directly
- **Colours / spacing / type** — change the tokens in the `:root` block at the top of the `<style>` tag
- **Stat counters** — add `class="count" data-target="123" data-suffix="+"` to any number; the
  script animates it from 0 on scroll

## Browser support

Modern evergreen browsers (Chrome/Edge, Firefox, Safari, mobile). Uses `IntersectionObserver`,
`backdrop-filter`, and CSS custom properties — no polyfills included.

## Contact

- **GitHub**: [thelonMusk](https://github.com/thelonMusk)
- **Email**: aatiesh99@gmail.com

---
*Last updated: August 2026*
