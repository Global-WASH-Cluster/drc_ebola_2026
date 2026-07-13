# DRC Ebola 2026 — epidemiological dashboard

Interactive epidemiological monitoring and importation-risk dashboard for the 2026 Bundibugyo
Ebola virus outbreak in the Democratic Republic of the Congo.

**Live dashboard:** https://global-wash-cluster.github.io/drc_ebola_2026/

The dashboard has two views:

- **Carte des risques** — health-zone map of the Ministry of Health response categories (A/B/C)
  and a mobility-based importation-risk ranking, used to prioritise zones for surveillance.
- **Courbes épidémiologiques** — weekly incidence curves and a table of affected health zones.

## How it is published

The dashboard is a self-contained HTML file rendered from an R (`flexdashboard` + Leaflet)
pipeline held in a separate working repo, and published here by a one-command script.

The site is served from the `gh-pages` branch, which is **rebuilt from scratch and
force-pushed on every publish** and therefore always holds exactly one commit. The dashboard
HTML is ~29 MB and changes on every render, so committing it normally would grow this repo by
that much per update; the orphan-branch rebuild pins the repo at roughly one file's worth,
permanently.

There is deliberately **no history of past dashboard versions** here, and the dashboard is
never committed to `main`.

## Data sources

- **Cases, deaths and response categories:** MVE situation reports from the Institut National
  de Santé Publique (INSP) and the Institut National de Recherche Biomédicale (INRB),
  Democratic Republic of the Congo — published at
  [INRB-UMIE/BDBV2026-Data](https://github.com/INRB-UMIE/BDBV2026-Data).
- **Population mobility** (importation model): [Flowminder
  Foundation](https://www.flowminder.org/resources/publications-reports/drc-reports-publications)
  estimates derived from Vodacom RDC call-detail records.
- **Administrative boundaries:** the 519 DRC Ministry of Health health zones
  ([OCHA COD-AB DRC](https://data.humdata.org/dataset/cod-ab-cod), ADM3).

The upstream data repository
[INRB-UMIE/BDBV2026-Data](https://github.com/INRB-UMIE/BDBV2026-Data) carries full metadata,
citations and licences for every dataset used, including the vulnerability and context layers
not listed above.

## Note on the data

These are **preliminary operational outbreak data**, published to support the response. Figures
are provisional and subject to revision as surveillance is consolidated; contact INSP/INRB
before reusing them.
