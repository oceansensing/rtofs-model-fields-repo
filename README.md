# rtofs-model-fields-repo

The RTOFS **fields** — a data repository of the oceansensing ocean map system: its own
Pages site, its own schedule, its own gigabyte, holding no code of its own.

**Built, rehearsed and taken live 2026-09-27** — published to Pages and R2,
not drawn on the website's map. `PLAN.md` is the founding plan;
`CLAUDE.md` carries what must not be got wrong and the shared doc doctrine.

## What it publishes

NOAA's Global Real-Time Ocean Forecast System's **scalar** fields — sea
surface temperature, salinity and height, and sea ice where the model carries
it.

| root | quantity | grid |
| --- | --- | --- |
| `ssh-rtofs.json` | sea surface height | global, 0.25 degree |
| `sic-rtofs.json` | sea ice concentration | global, 0.25 degree |
| `sit-rtofs.json` | sea ice thickness | global, 0.25 degree |
| `sst-rtofs-useast.json` | surface temperature | US East, 0.08 degree, `regional: true` |
| `sss-rtofs-useast.json` | surface salinity | US East, 0.08 degree, `regional: true` |

23 MB a tree (measured 2026-09-27).

These products are published **operationally but not drawn on the website's
map** — the owner's call, 2026-09-27. The map's status line still reports
them when they fall behind, which is how their health stays visible.

## Where the data comes from

**Source**: NOAA's open-data bucket on AWS, registry entry
<https://registry.opendata.aws/noaa-rtofs/>. The study of its layout, grid
and latency is this repository's first PLAN entry, written when the fetcher
is.

## How it will run

The orchestrator (the site's private `pipeline/`), the fetchers and the
published-file contract all come from `oceansensing.github.io`, checked out at
run time. This repository will carry `pipeline/products.toml` and its publish
workflow, and nothing else executable. Each run publishes to GitHub Pages and
to Cloudflare R2 from one build. Sibling repositories of the same model:
`rtofs-model-currents-repo`.

**Which document gets what, and what "update docs" means across all
twenty repositories, is the doctrine block at the top of `CLAUDE.md`** —
the same text in all twenty, held equal by the site's `check:docs`.

## Structure

```
README.md       what this is
CLAUDE.md       what must not be got wrong, and the shared doc doctrine
PLAN.md         the founding plan and running record
DECISIONS.md    dated one-way decisions, D1 onward
```
