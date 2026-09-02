# Moovsoon Listings Engine

An interactive proposal for collecting US real-estate listing data across six
national sources, delivered into the MSTech Property Data schema.

**Live deck → https://scrapesync.github.io/moovsoon/**

Pick the sources and drag the ZIP coverage on any sheet; every figure reprices
live, from a 25-ZIP pilot to national.

## What is in it

1. **Brief** | scope and who is building it
2. **Targets** | the five layers a request is judged at, and how deep each source contests
3. **Method** | the four tiers of effort and what each costs
4. **Pipeline** | named tools, quality gates and the self-healing loop, on self-hosted or AWS
5. **Scalability** | coverage against cost, broken down by component
6. **Build vs buy** | priced per source, with the fair objections to building answered
7. **Supply chain** | the named vendor behind every line of the build cost, split into what we build and what we buy, with a live chart of where the month's money goes
8. **What moves the bill** | one listing fetched three ways, drawn to scale: 75 KB, 255 KB, 1,200 KB
9. **Next step** | the pilot, and what the infrastructure costs to run at four coverage steps

## Notes on the numbers

Every access figure comes from live collection against all six sources on
1 September 2026. Request volume is derived from the crawl design rather than
assumed: 2.80 requests per listing per month = a daily sweep at ~24 listings per
request (1.25), detail fetches on the ~4% that change daily (1.20), and first
fetches for new inventory (0.35). Rung-2 page weight is measured from our own
captures (0.97-1.45 MB). Deep sources are costed at 25% incremental coverage
because their inventory overlaps the lighter sources.

Both rungs are priced on the same basis, as metered bytes times the contracted
per-GB rate. Rung 1 is 75 KB metered against a 45 KB payload, covering TLS setup
and retries. Rung 2 carries each source's own weight: Compass and Homes.com at
255 KB, the average of one 1.2 MB session mint and nine 150 KB credentialed
follow-ups, and Zillow at full page weight because it scores every request. The
server tier is chosen on the browser pool's in-window peak at one quarter duty
with half-box headroom, rather than on raw request count, because 85% of requests
carry no browser. The 255 KB blend, the 75 KB metered figure and the duty cycle
are the three assumptions the pilot exists to confirm.

Indicative monthly cost, all six sources: 25 ZIPs $31, 500 ZIPs $67,
3,000 ZIPs $264, national $1,133.

The deck works on desktop and phone; every sheet is usable down to 320px.

Buy-side rates are an independent August 2026 benchmark, not a vendor claim.
Supply-side rates on sheet 7 are each vendor's published price at the tier the
model actually buys at, checked August 2026. Three of the seven layers are
open source and cost nothing.

Prepared by Asad Ikram | [web-scraping-guide.com](https://web-scraping-guide.com)
