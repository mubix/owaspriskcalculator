# OWASP Risk Rating Calculator

A client-side implementation of the [OWASP Risk Rating Methodology](https://owasp.org/www-community/OWASP_Risk_Rating_Methodology) originally authored by Jeff Williams.

The original community-maintained calculator at owasp-risk-rating.com went offline. This project rebuilds it as a single-file, zero-dependency tool designed for static hosting on GitHub Pages.

## Overview

The OWASP Risk Rating Methodology estimates risk severity by combining **Likelihood** and **Impact** factors:

```
Risk = Likelihood × Impact
```

**Likelihood** is derived from:
- **Threat Agent Factors** — Skill Level, Motive, Opportunity, Size
- **Vulnerability Factors** — Ease of Discovery, Ease of Exploit, Awareness, Intrusion Detection

**Impact** is derived from:
- **Technical Impact Factors** — Loss of Confidentiality, Integrity, Availability, Accountability
- **Business Impact Factors** — Financial Damage, Reputation Damage, Non-compliance, Privacy Violation

Each factor is scored 0–9. Factors within each group are averaged, then combined through the severity matrix:

| | LOW Likelihood | MEDIUM Likelihood | HIGH Likelihood |
|---|---|---|---|
| **HIGH Impact** | Medium | High | Critical |
| **MEDIUM Impact** | Low | Medium | High |
| **LOW Impact** | Note | Low | Medium |

Levels: 0 to <3 = LOW | 3 to <6 = MEDIUM | 6 to 9 = HIGH

## Features

- **Exact OWASP methodology** — All factor names, descriptions, options, and score values match the official specification word-for-word.
- **100% client-side** — No backend, no dependencies, no build step. One HTML file.
- **Shareable URLs** — Selections are encoded in the URL hash. Share a link to reproduce any rating.
- **Score vector** — Standard format `(SL:x/M:x/O:x/S:x/ED:x/EE:x/A:x/ID:x/LC:x/LI:x/LAV:x/LAC:x/FD:x/RD:x/NC:x/PV:x)` with one-click copy.
- **Impact mode toggle** — Choose between Technical Impact, Business Impact, or Worst Case (max of both) for the final severity calculation.
- **Severity matrix reference** — Collapsible matrix table with the active cell highlighted.

## Deployment

### GitHub Pages

1. Fork or clone this repo.
2. Rename `owasp-calculator.html` to `index.html` (or keep it and configure Pages accordingly).
3. Enable GitHub Pages in repo settings (Settings → Pages → Source: main branch).
4. Access at `https://<username>.github.io/<repo-name>/`.

### Any Static Host

Drop the HTML file on any web server or static hosting provider (Netlify, Cloudflare Pages, S3, etc.). No server-side processing required.

### Local

Open `owasp-calculator.html` directly in a browser. Everything works offline.

## Usage

1. Select the appropriate value for each factor using the dropdowns.
2. The calculator updates all scores and the overall severity in real time.
3. Use the **Impact mode toggle** to switch between Technical Impact (default), Business Impact, or Worst Case.
4. Copy the **score vector** or **shareable URL** to include in reports, tickets, or documentation.

## Attribution

This calculator is based on the [OWASP Risk Rating Methodology](https://owasp.org/www-community/OWASP_Risk_Rating_Methodology) by Jeff Williams, published under [Creative Commons Attribution-ShareAlike v4.0](https://creativecommons.org/licenses/by-sa/4.0/).

This project is not affiliated with or endorsed by the OWASP Foundation.

## License

[BSD 3-Clause](LICENSE)
