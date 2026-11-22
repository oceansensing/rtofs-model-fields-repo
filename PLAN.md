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

## 2026-11-14 — a step a product

Until today one step made all eight products, and a step's exit is the fate of
every product it makes. On 2026-11-14 one column of NOAA's US East file — at
65.50 N 83.89 W and 250 m, off Southampton Island, one of 618,972 — read
-4.091 C at the cycle's f012 and -3.052 at f018, under the fetcher's floor of
-3 for the near-bottom temperature. That one product's refusal ended the step
non-zero, and all eight were held for two runs (13:53 and 19:53 UTC), standing
at 07:56.

Two changes. The floor is -5 in the site's `scripts/fetch-rtofs.py`: a wide
bound refuses a wrong unit, not the model's own extreme. And **each product
has a step of its own** in `pipeline/products.toml`, named for it and scoped
to it with `--only=`, all in the one lane, so a product's refusal holds that
product alone.

Rehearsed through the orchestrator with the site's fetcher: eight steps, eight
`fresh`, every file matching the contract; and with the near-bottom
temperature's floor planted at -2, that step exit 1 and that product alone
`held`, the other seven steps ok. The eight took 3 min 11 s on a workstation,
against under half a minute for the one step on the runner — each step opens
the files again.

## 2026-11-22 — the times either side, declared, rehearsed and publishing (D3)

Every product but the near-bottom level's depth declares 48 hours ahead and 24 behind (`974f8e1`, pushed 16:33 UTC).
Rehearsed, nothing published: a new cycle 22 minutes and 1,353.3 MB to R2, the run six hours on 3 min 37 s and
144.4 MB. **The first run**, `45063224056` (19:52–20:22 UTC): seven roots fresh, each from 24 hours
behind to 48 ahead, none left out, 292 files on R2 and the branch moved after them. Sea surface height's hours took
up to 503 s of their 600 on the runner (407 in rehearsal); past 600 the hours not yet read are left out. Open: the
second run, where keeping is proven, and that margin.

**Found that day, older than the times either side, not fixed**: the global roots publish a quarter-degree cell
empty where no model point lands in it — 896 of the 1,440 cells at 89.75 N, 126 at 88 N, 10 at 85 N — so a polar
drawing shows streaks from the pole. Open: those cells from the model's nearest point, its land left empty.
