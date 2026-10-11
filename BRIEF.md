# Build "HealthPulse" — free online health & fitness calculators (sister site of NetPulse & UnitPulse)

## Goal
Create a new static website **HealthPulse** in a NEW GitHub repo `JanVanHal/healthpulse`, built as a sister site so it looks like one suite with NetPulse and UnitPulse. Eight calculators plus the same supporting pages. Deploy-ready for GitHub Pages.

## Base: copy UnitPulse's look exactly
- Clone `https://github.com/JanVanHal/unitpulse` (branch `main`) as the template (it already follows NetPulse). Do NOT modify that repo or `JanVanHal/netpulse`.
- Reuse its `styles.css` as-is (Notion "warm paper" design system: `--nt-*` variables, Inter + Source Serif 4). Add only the new component styles you truly need at the end, using existing `--nt-*` tokens. No new colours or fonts.
- Mirror the UnitPulse page structure and class names: `site-header` / `site-nav` / `nav-toggle` mobile menu with the "More" dropdown, `tools-grid` of `tool-card`s (`tool-mark` colour chip, `tool-tag`, h3, text, `btn btn-primary tool-btn`), `hero hero-centered`, tool pages with `page-wrap`, `tool-header`, `tool-panel`, `input-group`, `result-section` / `result-item` / `result-label` / `result-value`, `field-error`, `caption tool-caption`, "Common values" table (`conv-table`), FAQ (`faq-list` with `<details>`), the AdSense placeholder `ad-section` / `ad-container`, and the same footer.
- Homepage order like UnitPulse: tools grid, then centered hero ("Free Online Health & Fitness Calculators"), "From the blog", ad slot.
- **Logo** (same style as the current UnitPulse logo, `img/unitpulse-logo.svg`): SVG `img/healthpulse-logo.svg`, viewBox `0 0 960 615`, dark `#010a27` background with rounded corners, a cyan `#00dcfa` line icon above (a heart with a small pulse line through it, stroke only, NO border box around the icon, no tagline), and a big white bold "HealthPulse" wordmark underneath (Inter, ~190px, letter-spacing -5, filling most of the width like NetPulse's). Also a 32×32 `img/healthpulse-icon.svg` (same icon on a dark rounded square) for the header and favicon.
- Footer: "Also from us: NetPulse · UnitPulse" links (https://janvanhal.github.io/netpulse/ and https://janvanhal.github.io/unitpulse/).

## Tech rules
- Vanilla HTML/CSS/JS only. No frameworks, no build step, no npm, no external JS libraries. One HTML file per page, JS inline per tool page.
- Mobile-first, responsive, accessible (labels, aria-live results, keyboard, focus rings, contrast). Works fully offline.
- Results update as you type (Enter also works). **Metric / Imperial toggle** on every tool (cm/kg vs ft-in/lb), remembered in `localStorage`, plus last inputs per tool. Accept `,` and `.` decimals. Clear button and copy-result button.
- Nothing is sent anywhere: all calculations run in the browser. Say so on every page ("Your numbers never leave your device").

## The 8 calculators (one page each)
| # | File | Mark / tag | Calculator |
|---|------|-----------|------------|
| 1 | `bmi.html` | BMI / Body | BMI = kg / m². Show the category (WHO: under 18.5, 18.5–24.9, 25–29.9, 30+) on a simple colour bar using tokens, and a note on the Asian cut-offs (23 / 27.5). |
| 2 | `calories.html` | KCAL / Energy | Daily calorie needs: BMR with **Mifflin-St Jeor** (male: 10·kg + 6.25·cm − 5·age + 5; female: … − 161) × activity factor (1.2 / 1.375 / 1.55 / 1.725 / 1.9). Show maintain, mild loss (−250), loss (−500), gain (+250/+500). |
| 3 | `macros.html` | MAC / Nutrition | Macro split from a calorie target: presets (balanced 30/40/30, high-protein, low-carb) or custom %, protein option by g/kg (1.6–2.2). Grams and kcal for protein (4), carbs (4), fat (9). |
| 4 | `body-fat.html` | BF% / Body | **US Navy method** body fat % (male: neck, waist, height; female: + hip), cm or inches. Show the category table (essential, athletes, fitness, average, obese). |
| 5 | `ideal-weight.html` | IBW / Body | Ideal / healthy weight: healthy BMI range for the height, plus Devine, Robinson and Miller formulas side by side. |
| 6 | `water.html` | H₂O / Hydration | Daily water intake: ~33 ml per kg body weight plus extra per 30 min of exercise and for hot climate (toggle "hot climate, e.g. Thailand"). Show litres and glasses (250 ml). |
| 7 | `pace.html` | PACE / Training | Running & cycling pace: enter any two of distance, time, pace/speed and get the third. min/km ↔ min/mi ↔ km/h ↔ mph. Presets 5K, 10K, half, marathon; a split table. |
| 8 | `heart-rate.html` | BPM / Training | Heart-rate zones: max HR (Tanaka 208 − 0.7·age, show 220 − age too) and optional resting HR (Karvonen). Five zones with bpm ranges and what each zone is for. |

Each calculator page: h1, one-line intro, the calculator panel, a "Common values" table, "How it's calculated" (the formula in plain words), a 3–5 question FAQ, the health disclaimer and the ad slot.

## Health disclaimer (important for trust and AdSense)
On every calculator page and in the footer: "HealthPulse gives estimates for general information only. It is not medical advice. Talk to a doctor before big changes to diet or exercise, especially with a health condition." Add a `disclaimer.html` page as well, and link it in the footer next to Privacy and Terms.

## Supporting pages (copy the UnitPulse structure, rewrite the text for HealthPulse)
`index.html`, `about.html`, `contact.html`, `privacy.html`, `terms.html`, `dmca.html`, `disclaimer.html`, `blog.html`, plus 3 short blog posts in `blog/`: "BMI explained: what it tells you and what it doesn't", "How many calories do you really need?", "Heart-rate zones for beginners". Same `post-card` style, read time and pills.

## Nav
Home · BMI · Calories · Macros · Body Fat · More ▾ (Ideal Weight, Water, Pace, Heart Rate) · Blog · About · Contact.

## Done when
- All pages open from `index.html` with no console errors and no broken links.
- Calculations are correct. Spot-check:
  - BMI for 90 kg and 187 cm = **25.7** (overweight).
  - Mifflin-St Jeor BMR for a 51-year-old male, 90 kg, 187 cm = **1,819 kcal**; × 1.375 = **2,501 kcal**.
  - Pace: 10 km in 50:00 = **5:00 min/km** = 12.0 km/h = 8:03 min/mi.
  - Tanaka max HR at age 51 = **172 bpm** (220 − age = 169).
  - Navy body fat for a male, height 187 cm, neck 40 cm, waist 95 cm ≈ **20.7%**.
  - Water for 90 kg = about **3.0 L** before the exercise and heat extras.
- Looks the same in style as UnitPulse and NetPulse (fonts, colours, cards, header, footer, logo style).
- `README.md` lists the pages and how to run them; repo `JanVanHal/healthpulse` pushed to `main` with GitHub Pages enabled from `main` / root.
- Report back: the repo link, the Pages URL, and anything left as a placeholder (AdSense IDs stay as the same `ca-pub-1234567890` placeholders).

## Workflow
- This file is the source of truth. Build from it, commit with clear messages, push to `main`.
- Fix requests are added below under "Fix list" over time; when asked to "apply the fix list", do every unchecked item, tick it (`- [x]`), and push.

## Fix list
- [x] `bmi.html`: add an FAQ item "Is BMI different for men and women?" Answer in plain words: the adult BMI formula and categories (18.5 / 25 / 30) are the same for men and women; at the same BMI women usually carry a bit more body fat, so for body composition use the Body Fat calculator (link to `body-fat.html`). Mention that children and teens use age- and sex-specific BMI charts instead. Do not add a male/female input.
- [x] `heart-rate.html`: add an FAQ item "Is max heart rate different for men and women?" Answer: the Tanaka (208 − 0.7 × age) and 220 − age formulas are used for everyone; some studies suggest a slightly different formula for women, but the gap is only a few bpm, smaller than normal person-to-person variation; entering your resting heart rate (Karvonen) personalises the zones far more. Do not add a male/female input.
