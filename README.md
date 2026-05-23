# BGC Group

API Evangelist network profile for **BGC Group, Inc.** (NASDAQ: **BGC**) — global brokerage and financial technology firm, formerly **BGC Partners**. Headquartered in New York and London, BGC operates electronic and voice broking across foreign exchange, interest rate derivatives, fixed income, energy and commodities, equity derivatives, credit, and futures, alongside the Fenics market-data franchise, the FMX execution venues, Lucera trading infrastructure, Capitalab post-trade optimization, and the GFI Group subsidiary.

- **Provider site:** https://www.bgcg.com
- **Investor relations:** https://ir.bgcg.com
- **Ticker:** NASDAQ:BGC
- **Spin-off:** Newmark Group (NASDAQ:NMRK) — completed 2018-11-30
- **Repo type:** `company`
- **Profiled:** 2026-05
- **Fortune 1000:** rank 963

## Why this profile is brokerage-shaped, not REST-API-shaped

BGC is a regulated inter-dealer broker and venue operator. Its "APIs" are session-oriented institutional integrations — **FIX 4.4**, **ITCH/OUCH over SoupBinTCP**, proprietary **BOP/BIMP** binaries, **multicast** market data, **FTP/SFTP/Cloud** data drops — distributed to onboarded counterparties under license. There is no public developer portal, no self-service API key, and no public OpenAPI specification across the BGC, FMX, Fenics, Lucera, or Capitalab properties.

This repository documents what exists and is publicly verifiable, including the September 23, 2024 launch of the FMX Futures Exchange (initial SOFR futures, U.S. Treasury futures added Q1 2025) and the Fenics FX ITCH market data specification (publicly downloadable PDF).

## APIs documented

| # | Surface | Type | Connectivity |
|---|---|---|---|
| 1 | **FMX Futures Exchange** | Listed futures venue | FIX, binary feeds, drop copy; cleared via LCH Limited |
| 2 | **FMX UST** | U.S. Treasury CLOB | FIX 4.4 (+selected 5.0), BOP order entry, BIMP multicast MD, Drop Copy, STP |
| 3 | **FMX FX (Fenics FX)** | FX execution (Spot, Fwd, NDF, Options) | FIX, ITCH/OUCH over SoupBinTCP |
| 4 | **Fenics Market Data** | Multi-asset market data | Direct Feed/API, Desktop, Excel, Cloud, FTP/SFTP, On-prem |
| 5 | **Lucera (LumeMarkets / LumeFX / Connect / Compute)** | Single-API cross-asset trading + SDN connectivity | Lucera-managed API across FX, Rates, Futures, Crypto, Credit |
| 6 | **Capitalab** | Post-trade IM optimization and compression | Bespoke program runs |
| 7 | **GFI Group** | Subsidiary inter-dealer broker | Voice + electronic broking |

## FMX Futures Exchange (highlight)

- **Launched:** September 23, 2024 (SOFR futures)
- **Added:** U.S. Treasury futures, Q1 2025
- **Equity partners (10):** Bank of America, Barclays, Citadel Securities, Citi, Goldman Sachs, J.P. Morgan, Jump Trading Group, Morgan Stanley, Tower Research Capital, Wells Fargo
- **Clearing:** LCH Limited — enables cross-margining with cleared interest rate swaps
- **Technology investment cited at launch:** > $200 million

## Repository layout

```
bgc-partners/
├── apis.yml                              ← Network index of all BGC surfaces
├── README.md                             ← This file
├── vocabulary/
│   └── bgc-partners-vocabulary.yml       ← Domain terms across corporate, venues, protocols, data, post-trade
├── json-ld/
│   └── bgc-partners-context.jsonld       ← schema.org-aligned context for BGC, FMX, Fenics, Lucera, Capitalab
├── plans/
│   └── bgc-partners-plans-pricing.yml    ← Commercial plan surface (sales-onboarded; no public rate card)
├── rate-limits/
│   └── bgc-partners-rate-limits.yml      ← Session/throughput posture across FIX, ITCH, binary feeds
└── finops/
    └── bgc-partners-finops.yml           ← FOCUS-aligned billable surfaces and cost dimensions
```

## Artifacts NOT generated (and why)

- **`openapi/`** — No public OpenAPI specifications are published by BGC, FMX, Fenics, Lucera, or Capitalab. Per the run-pipeline skill, empty/placeholder specs must not be created. Native specs are FIX, ITCH, OUCH, BOP, BIMP — distributed under license rather than as OpenAPI.
- **`asyncapi/`** — Same rationale; market-data streams use ITCH/BIMP/multicast, not AsyncAPI.
- **`json-schema/` / `json-structure/`** — No public canonical schemas to extract; entity models live inside FIX dictionaries and proprietary binary specs under NDA.
- **`examples/`** — No public request/response examples; protocol examples are in the licensed FIX/ITCH specifications.
- **`rules/`** — No OpenAPI to govern.
- **`capabilities/`** — No OpenAPI to source Naftiko capability definitions from.
- **`crd/`** — Not a Kubernetes-native provider.

## Key public references

- BGC Group corporate site — https://www.bgcg.com
- BGC investor relations — https://ir.bgcg.com
- FMX division — https://www.fmx.com
- FMX Futures Exchange — https://www.fmxfutures.com
- FMX UST technology — https://www.fenicsust.com/technology/
- Fenics Market Data — https://www.fenicsmd.com
- Fenics Market Data products — https://www.fenicsmd.com/products/
- Fenics Market Data Direct Feed & API — https://www.fenicsmd.com/delivery/direct-feed-and-api/
- Fenics FX ITCH market data specification (PDF) — https://www.fenicsfx.com/wp-content/uploads/2019/09/FenicsFX_ITCH_MarketData_v7.pdf
- Lucera (LumeMarkets / Connect / Compute) — https://www.lucera.com
- Capitalab — https://www.capitalab.com
- GFI Group — https://www.gfigroup.com
- LCH (clearing partner for FMX Futures) — https://www.lch.com
- Newmark Group (2018 spin-off) — https://www.nmrk.com
- Fenics Market Data on LSEG Workspace — https://www.lseg.com/en/data-analytics/financial-data/pricing-and-market-data/fixed-income-pricing-data/fenics-market-data
- FMX Futures Exchange launch announcement — https://www.prnewswire.com/news-releases/bgc-group-launches-fmx-futures-exchange-302256660.html

## Maintainer

[API Evangelist](https://apievangelist.com) — Kin Lane.
