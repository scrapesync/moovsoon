# Moovsoon Listings Engine

An interactive proposal for collecting US real-estate listing data across six
national sources, delivered into the MSTech Property Data schema.

**Live deck → https://scrapesync.github.io/moovsoon/**

Pick the sources and drag the ZIP coverage on any sheet; every figure reprices
live, from a 25-ZIP pilot to national.

## What is in it

1. **Brief** — scope and who is building it
2. **Targets** — the five layers a request is judged at, and how deep each source contests
3. **Method** — the four tiers of effort and what each costs
4. **Pipeline** — named tools, quality gates and the self-healing loop, on self-hosted or AWS
5. **Scalability** — coverage against cost, broken down by component
6. **Build vs buy** — priced per source, with the fair objections to building answered
7. **What moves the bill** — page weight, and the tier mix that controls it
8. **Next step** — the pilot

## Notes on the numbers

Every access figure comes from live collection against all six sources on
1 September 2026. Request volume is derived from the crawl design rather than
assumed: 2.80 requests per listing per month = a daily sweep at ~24 listings per
request (1.25), detail fetches on the ~4% that change daily (1.20), and first
fetches for new inventory (0.35). Rung-2 page weight is measured from our own
captures (0.97–1.45 MB). Deep sources are costed at 25% incremental coverage
because their inventory overlaps the lighter sources.

Buy-side rates are an independent August 2026 benchmark, not a vendor claim.

Prepared by Asad Ikram — [web-scraping-guide.com](https://web-scraping-guide.com)
