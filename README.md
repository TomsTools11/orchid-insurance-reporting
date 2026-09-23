# orchid-insurance-reporting

GOAL reporting for **Orchid Agency Group**, deployed as a static site on Vercel.

## Contents

| Path | Page |
| --- | --- |
| `index.html` | Campaign Configuration |
| `reports/ia-auto-configuration.html` | IA Auto Campaign Configuration |
| `reports/ia-home-configuration.html` | IA Home Campaign Configuration |

The homepage is the campaign configuration overview. Each report is a single self-contained HTML file. The only
external request is the Inter webfont from Google Fonts. There is no build step and
there are no dependencies.

## Deploying on Vercel

`vercel.json` serves the repo root as a static site (`framework: null`,
`outputDirectory: "."`, `cleanUrls: true`), so `/reports/<name>` works without the
`.html` extension. Once a Vercel project is connected to this repo, every push to `main`
publishes to production, and every other branch or PR gets its own preview URL.

Search engines are blocked with an `X-Robots-Tag: noindex` header and `robots.txt`
because these are client reports.

## Adding another report

Put the new HTML file in `reports/` with a lowercase, hyphenated name, add a link
to it from `index.html`, then commit and push.

## Previewing locally

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```
