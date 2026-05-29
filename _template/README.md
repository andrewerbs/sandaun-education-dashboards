# Sandaun Education — Dashboard Design System

A reusable visual identity for all Sandaun (West Sepik) Province education
dashboards. Inspired by the Sandaun provincial flag — a black upper triangle
bearing white stars and a blue setting sun with gold rays, over a red lower
triangle carrying the gold Raggiana bird-of-paradise. "Sandaun" means "sun
down": this is PNG's westernmost province, the home of the sunset. The header
carries a sunset gradient; the stripe and footer use the flag's gold / red /
black. Anchored to the PNG national flag (red, black, gold) for the accents.

This package is the Sandaun counterpart to the AROB and Central Province design
systems already in use. Components, naming, and traffic-light conventions are
kept parallel so the three suites can sit side by side.

## Files

| File | Purpose |
| --- | --- |
| `sandaun_design_system.html` | Living style guide — open in a browser to see the header, palette, components, callouts, charts, and footer in one place. Also the source of truth for the CSS variables. |
| `dashboard_starter.html` | Blank skeleton. Duplicate this file, rename it, and fill in the title, KPIs, sections, and charts. |
| `../_assets/sandaun_flag.svg` | Original simplified Sandaun flag/crest used in the header. |

## How to make a new dashboard

1. Copy `dashboard_starter.html` to the parent `Sources/` folder and rename it
   `Sandaun_<Topic>.html` (e.g. `Sandaun_Executive_Dashboard.html`).
2. Update the `<title>`, the header `.sd-title` / `.sd-subtitle` / `.sd-meta`,
   and the footer text.
3. Replace the KPI strip values, add `<div class="section">…</div>` blocks for
   each theme, and add canvases for charts.
4. Use the `SD` palette object in the inline `<script>` for all Chart.js colours
   so every dashboard stays on-brand.

## Brand tokens

| Token | Hex | Use |
| --- | --- | --- |
| `--sd-gold` | `#F4A800` | Sunset gold (sun rays) — primary chart fill, KPI accent, header glow |
| `--sd-gold-dark` | `#B97400` | Deep gold — KPI numbers, readable on white |
| `--sd-orange` | `#E0651E` | Sunset orange — header gradient start, secondary emphasis |
| `--sd-red` | `#D62027` | Flag red (lower triangle) — emphasis, warnings, footer stripe |
| `--sd-red-dark` | `#8E1418` | Hover / darker red gradients, table headings |
| `--sd-blue` | `#1C8FD1` | Setting-sun blue disk — secondary chart series |
| `--sd-blue-dark` | `#0B5C8A` | Headings (`h2`), deep accent |
| `--sd-black` | `#1A1A1A` | Upper triangle / PNG flag black — high-contrast accent |
| `--png-gold` | `#FCD116` | PNG flag gold — sparingly, footer / bird-of-paradise |

Status colours (`--green`, `--amber`, `--red`) follow the existing PEIP
traffic-light convention used in the AROB and Central suites and are unchanged.

## Component cheat sheet

- `.sd-header` + `.sd-stripe` — page header with the crest badge and Sandaun
  flag stripe (gold / red / black) over a sunset gradient.
- `.big-cards` / `.big-card` — KPI strip that overlaps the header. Variants:
  `.accent`, `.good`, `.warn`, `.bad`, `.blue`, `.dark`.
- `.section` — main content card. Variants: `.bordered` (red left border),
  `.bordered-gold`, `.bordered-blue`, `.bordered-black`.
- `.traffic` + `.tl` — traffic-light callouts. Colour variants on the wrapper
  (`.tl-red`, `.tl-amber`, `.tl-green`, `.tl-blue`, `.tl-gold`) and matching
  `.dot` class.
- `.actions` + `.action-box.ops|res|perf` — three-column recommendation boxes.
- `.callout` / `.callout-gold` / `.callout-blue` — large-number headline
  callouts.
- `.simple-table` + `.pill.pill-red|amber|green|blue|gold` — data tables with
  status pills.

## Charts

All dashboards should declare the shared `SD` palette and `SD.series` array,
then use those colours rather than hard-coded hex values. This keeps every
chart in the suite visually consistent.

```js
const SD = { gold:'#F4A800', blue:'#1C8FD1', red:'#D62027', /* ... */ };
SD.series = [SD.gold, SD.blue, SD.red, SD.teal, SD.orange, SD.pink, SD.grey];
```

## The dashboard suite

Parallel to the AROB suite, the Sandaun set comprises:

- `Sandaun_Executive_Dashboard.html` — one-page leadership overview.
- `Sandaun_Enrollment_Analysis.html` — enrolment, grade flow, the G2→G3 cliff.
- `Sandaun_Teacher_Analysis.html` — PTR, qualifications, registration, housing.
- `Sandaun_Infrastructure_Analysis.html` — classrooms, condition, WASH, power.
- `Sandaun_Gender_Equity_Analysis.html` — GPI by grade and district, teacher gender.
- `Sandaun_Data_Quality_Report.html` — missing data, outliers, ghost schools.
- `Sandaun_Feeder_Mapping.html` — elementary→primary feeder relationships.
- `Sandaun_School_Risk_Index.html` — composite 0–6 risk score per school.
- `Sandaun_PEIP_Progress_Report.html` — progress against the PEIP indicator set.
- `Sandaun_<District>_Deep_Dive.html` — Aitape/Lumi, Nuku, Telefomin, Vanimo/Green River.
- `index.html` — landing page linking the whole suite.

## Reference

- Sandaun flag — simplified original artwork at `_assets/sandaun_flag.svg`.
  Inspired by the public symbolism of the flag (black field with stars, blue
  setting sun, red field, gold bird-of-paradise).
- Symbolism: the setting sun = "Sandaun" / sun-down, PNG's westernmost
  province; the stars = the province's districts; the Raggiana
  bird-of-paradise = PNG's national emblem in the provincial gold.
