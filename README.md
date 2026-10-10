# HealthPulse

Free online health and fitness calculators. Sister site of [NetPulse](https://janvanhal.github.io/netpulse/) and [UnitPulse](https://janvanhal.github.io/unitpulse/).

Vanilla HTML, CSS and JavaScript. No build step and no account. Each calculator is one page, and the script for that calculator is in the page. The arithmetic stays in the browser.

## Run locally

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8080
```

Then open http://localhost:8080/

No network is required for a result. The pages may request Inter and Source Serif 4 from Google Fonts. If that request fails, the fallback fonts are used and the calculators still run.

Published site: https://janvanhal.github.io/healthpulse/

## Pages

| File | Page |
|------|------|
| `index.html` | Home: eight calculators, then the introduction, then the blog |
| `bmi.html` | BMI, WHO category and Asian cut-offs |
| `calories.html` | Daily calories, Mifflin-St Jeor |
| `macros.html` | Protein, carbohydrate and fat |
| `body-fat.html` | US Navy body fat |
| `ideal-weight.html` | Healthy BMI range, Devine, Robinson, Miller |
| `water.html` | Daily water |
| `pace.html` | Running and cycling pace, with splits |
| `heart-rate.html` | Tanaka max heart rate and five zones |
| `blog.html` | Blog index |
| `blog/*.html` | Articles. They link `../styles.css` |
| `about.html` | About |
| `contact.html` | Contact. Opens your email app |
| `privacy.html` | Privacy |
| `terms.html` | Terms |
| `disclaimer.html` | Health disclaimer |
| `dmca.html` | Copyright notices |
| `styles.css` | Notion warm-paper styles shared with UnitPulse and NetPulse, plus HealthPulse components at the end |
| `img/healthpulse-icon.svg` | Icon and favicon |
| `img/healthpulse-logo.svg` | Homepage logo |

The metric or imperial choice, and the last figures for each calculator, are stored in this browser only.

Ad slots use the placeholder publisher ID `ca-pub-1234567890`. The AdSense script is not loaded, so the placeholder does not throw in the console.

The contact address `contact@healthpulse.example` is a placeholder.
