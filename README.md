# ScaleFlux

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

ScaleFlux is a semiconductor and systems company (founded 2014, Milpitas / San Jose, California) that
designs enterprise NVMe SSD controllers, computational storage drives and CXL memory products. Its
FX-series SoC controllers (SFX 3016, FX 5016) embed transparent hardware compression, so drives such as
the CSD 2000, CSD 3000 and CSD 5000 series present substantially more logical than physical capacity
while offloading compression and data-shaping from the host CPU.

- Website: https://scaleflux.com/
- Products: https://scaleflux.com/products/
- Secondary-market listing: https://forgeglobal.com/scaleflux_stock/

## No web API

ScaleFlux is a hardware vendor, not an API provider. Contract discovery on 2026-08-02 found **no**
OpenAPI, Swagger, GraphQL, AsyncAPI, MCP server or A2A agent card, and no first-party API client SDK on
npm, PyPI or crates.io. Its programmable surface is the NVMe standard command set plus the
vendor-specific `sfx` extensions.

Note: `scaleflux.com` sits behind a SiteDistrict WAF that returns **HTTP 403 to every automated
request**, including `/robots.txt` and `/sitemap.xml`. The `/.well-known/` results recorded in
`well-known/scaleflux-well-known.yml` are therefore *inconclusive, not absent* — nothing could be
retrieved from the provider's own host on this pass. Re-probe on a later round.

## Artifacts

| Dir | File | What |
|---|---|---|
| `cli/` | `scaleflux-cli.yml` | The 10-command `nvme sfx` / `sfx-nvme` vendor command surface, verbatim from the upstream nvme-cli plugin |
| `packages/` | `scaleflux-packages.yml` | `sfx3xdriver` kernel driver packages on packagecloud + registry probe results |
| `conformance/` | `scaleflux-conformance.yml` | NVMe / PCIe / CXL device standards |
| `security/` | `scaleflux-domain-security.yml` | TLS/DNS probe: TLS 1.3, SPF, DMARC `p=reject`, no DNSSEC, no CAA, no HSTS |
| `well-known/` | `scaleflux-well-known.yml` | `/.well-known/` probe record (all 403, WAF) |
| `llms/` | `scaleflux-llms.txt` | Generated llms.txt for this repo |
