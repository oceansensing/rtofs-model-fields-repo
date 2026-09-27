# rtofs-model-fields-repo — the founding plan and running record

The RTOFS **fields**. Created on GitHub by the owner and given its documents on
2026-09-27, the day the owner asked for ECCOFS, CBEFS, Mercator's
biogeochemistry, RTOFS and GFS to be published without the map drawing them.
**Built 2026-09-27.**

## What it is for

NOAA's Global Real-Time Ocean Forecast System's **scalar** fields — sea
surface temperature, salinity and height, and sea ice where the model carries
it.

## Where the data comes from

**Source**: NOAA's open-data bucket on AWS, registry entry
<https://registry.opendata.aws/noaa-rtofs/>. The study of its layout, grid
and latency is this repository's first PLAN entry, written when the fetcher
is.

## Open, as founded

*Answered 2026-09-27 — the entry below.*

## 2026-09-27 — built and rehearsed

The fetcher is the site's `scripts/fetch-rtofs.py`; "What must not be got wrong" in
CLAUDE has its traps, each found on the first live run. Rehearsed through
the orchestrator in a throwaway copy of the site with the roots in its
contract: every file matched and every fate was `fresh`.

## 2026-09-27 — live

The site's commit `f872402` put the roots in the contract and the origin in
`MAP_ORIGINS`; the dispatched run 36297612223 went green on its first try (build,
Pages and R2), and `status/status.json` read at 2026-09-27T05:36:22Z: every
product `fresh` (5 of 5), the nearest frame 0.39 h
from the reader. The schedule `51 1,7,13,19 * * *` was then turned on (longest gap
6 h, so the watchdog's silence budget is 10 h).

## The workflow's packages come from the site — 2026-09-27

The publish workflow installs `site/scripts/requirements-rtofs.txt`, one file
per fetcher family, instead of naming packages in its own `pip install`
line. Dependabot reads requirements files and never a workflow line: an
inline pin elsewhere had carried `requests` 2.32.3, a version with two
advisories, unflagged. The site's `check:docs` now refuses an inline package
here. Confirmed by a dispatched run, green on build, Pages and R2.
