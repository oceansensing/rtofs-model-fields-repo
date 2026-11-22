# Decisions

Dated, irreversible-leaning decisions, one entry each, newest last. The
reasoning lives in `PLAN.md`.

**What counts as one-way in a data repository**: a decision that puts bytes in
readers' hands under a shape they will code against; a decision about which
repository owns a product, since moving one costs a migration in two places;
and a decision that forecloses an upstream.

## D1 — 2026-09-27 — Its own repository, published but not drawn

The RTOFS **fields**, in a repository of its own under the convention every model
follows: **a model splits along the axis that costs bytes** — currents,
fields and, where the model has them, biogeochemistry — and an atmospheric
model has one atmosphere repository. See `espc-model-repo`'s `DECISIONS.md`
D2 for the measurement behind the split.

**Published but not drawn** (the owner, 2026-09-27): the products go to Pages
and R2 on a schedule and the website's map carries no layer for them, while
its status line reports their health. Drawing one later is a change to the
map, not to this repository.

One-way in the ordinary data-repository sense: moving a product between
repositories is cheap in machinery and expensive in everything that points at
it — roots in the contract, origins in the site's config, and the union
`check:docs` holds across origins.

## D2 — 2026-09-27 — Option A: global height and ice, US East temperature, salinity and currents

The global NetCDF files carry no surface temperature, salinity or currents; the US East regional subset does. Option B — those fields globally, from the 437 MB HYCOM binary per step — is the owner's to choose. Published, not drawn.

## D3 — 2026-11-22 — Two days ahead and one behind; the dated files R2's alone, kept while a base lists them

**The window is 48 hours ahead and 24 behind** (`hours_ahead`,
`hours_behind`; the site pipeline's D16, the owner's call of 2026-11-21), at
the steps the model posts: hourly for the global roots to f072 and three-hourly past it, six-hourly for US East. Every hour is in
`moreFrames`, the base among them; no root lists `frames`, as none did.

**The near-bottom level's depth takes no hours**: the deepest wet level was the
same in all 618,972 wet columns at n006, f012, f072 and f096 of the cycle of
2026-11-22.

**The hours behind are the newest cycle's own**: its nowcast up to the cycle,
its forecast after. An hour the model has since run through is not left as
yesterday's forecast. Where one cannot be read, what the last base listed
stands.

**A file once behind is never written again**, since readers hold it for good.
An hour read ahead is `<root>.v<time>.json`; an hour read behind is
`<root>.v<time>.r<run>.json`, so a new cycle's hour behind is a new file.

**The dated files are R2's alone** (`memory = "r2-kept"`): none is on Pages or
the `published` branch, none existed before, and R2 keeps one while a root
lists it. What a cycle has given is read from the last base's listing and not
asked of NOAA again. **The branch moves only after R2 has the files it
lists** (the workflow's `remember` job).

**The hours never cost the base**: it is read first, and what is added is
asked for in a step's first ten minutes, left out and said where it fails.

**Measured in rehearsal, nothing published**, from the branch of 2026-11-22:
a new cycle 22 minutes and 1,353.3 MB to R2 (271 times over seven roots), the
run six hours on 3 min 37 s and 144.4 MB, 235 files kept by the listings,
none a base lists left out. By the chunks' stored sizes a new cycle reads at
least 6.3 GB from NOAA's open bucket.

One-way in the ordinary sense: readers will code against `moreFrames` and the
files' names.
