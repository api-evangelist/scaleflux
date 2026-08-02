# ScaleFlux

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
