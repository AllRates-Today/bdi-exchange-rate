# Banca d'Italia Exchange Rates API — bdi-exchange-rate

[![npm version](https://img.shields.io/npm/v/bdi-exchange-rate.svg)](https://www.npmjs.com/package/bdi-exchange-rate)
[![license](https://img.shields.io/npm/l/bdi-exchange-rate.svg)](https://github.com/AllRates-Today/bdi-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/bdi-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![EUR/USD today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbdi%3Fsource%3DEUR%26target%3DUSD&query=%24.rate&label=EUR%2FUSD%20published%20by%20Banca%20d'Italia&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bdi/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbdi%3Fsource%3DEUR%26target%3DUSD&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bdi/)

**Official Banca d'Italia (Italy) daily exchange rates for Node.js and TypeScript. The published central bank rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Banca d'Italia itself prints, every business day.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — Banca d'Italia's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2016** — point-in-time tables and daily series for any past date
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Banca d'Italia itself published, fixed once printed and carrying the central bank's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## ⚡ Try it without a key

The latest Banca d'Italia table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/bdi?source=USD&target=EUR"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/bdi').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the central bank's latest published table, no key
```

The open endpoint serves the *latest* table only (JSON by default; add `?format=csv`, `xml` or `xlsx` for a file) and is free to use with a visible, followable link where the rates are shown: `<a href="https://allratestoday.com">Exchange rates by AllRatesToday</a>` (terms: <https://allratestoday.com/terms/#attribution>). The client below uses the keyed API, which adds point-in-time tables and history; with a key the link is appreciated, not required.

## 📈 Latest published table

[![Latest Banca d'Italia table](https://allratestoday.com/api/open/central-bank/bdi/table.svg)](https://allratestoday.com/central-bank-rates-api/bdi/)

The image is rendered live from the keyless endpoint above, so it follows the central bank's publications on npm and on GitHub alike without a new release. The same table as text is folded below for search and copy-paste: on GitHub [a daily Action](.github/workflows/daily-table.yml) refreshes it whenever the central bank publishes a new table; on npm it is as of the package's publish date.

<!-- daily-table:start -->
<details>
<summary>Table as text: published 2026-10-27 by Banca d'Italia — 150 rates, first 60 shown. Updated 2026-10-27.</summary>

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| EUR | AED | reference | 4.0948 |
| EUR | AFN | reference | 72.5168 |
| EUR | ALL | reference | 90.75 |
| EUR | AMD | reference | 402.64 |
| EUR | AOA | reference | 1028.792 |
| EUR | ARS | reference | 1717.4395 |
| EUR | AUD | reference | 1.5856 |
| EUR | AWG | reference | 1.9959 |
| EUR | AZN | reference | 1.8955 |
| EUR | BAM | reference | 1.95583 |
| EUR | BBD | reference | 2.23 |
| EUR | BDT | reference | 138.0928 |
| EUR | BHD | reference | 0.419 |
| EUR | BIF | reference | 3358.938 |
| EUR | BMD | reference | 1.115 |
| EUR | BND | reference | 1.4285 |
| EUR | BOB | reference | 13.4023 |
| EUR | BRL | reference | 5.9624 |
| EUR | BSD | reference | 1.115 |
| EUR | BTN | reference | 106.0635 |
| EUR | BWP | reference | 15.6821 |
| EUR | BZD | reference | 2.23 |
| EUR | CAD | reference | 1.5636 |
| EUR | CDF | reference | 2518.038 |
| EUR | CHF | reference | 0.9239 |
| EUR | CLP | reference | 1103.1 |
| EUR | CNY | reference | 7.4343 |
| EUR | COP | reference | 3503.37 |
| EUR | CRC | reference | 505.541 |
| EUR | CUP | reference | 26.76 |
| EUR | CVE | reference | 110.265 |
| EUR | CZK | reference | 24.348 |
| EUR | DJF | reference | 198.159 |
| EUR | DKK | reference | 7.4742 |
| EUR | DOP | reference | 66.9709 |
| EUR | DZD | reference | 150.598 |
| EUR | EGP | reference | 62.7004 |
| EUR | ERN | reference | 17.1487 |
| EUR | ETB | reference | 180.9336 |
| EUR | FJD | reference | 2.5118 |
| EUR | FKP | reference | 0.83658 |
| EUR | GBP | reference | 0.83658 |
| EUR | GEL | reference | 2.8943 |
| EUR | GHS | reference | 12.9573 |
| EUR | GIP | reference | 0.83658 |
| EUR | GMD | reference | 80.84 |
| EUR | GNF | reference | 9818.5396 |
| EUR | GTQ | reference | 8.521 |
| EUR | GYD | reference | 233.2803 |
| EUR | HKD | reference | 8.7466 |
| EUR | HNL | reference | 29.9922 |
| EUR | HTG | reference | 145.6719 |
| EUR | HUF | reference | 367.48 |
| EUR | IDR | reference | 20224.54 |
| EUR | ILS | reference | 3.4003 |
| EUR | INR | reference | 106.0635 |
| EUR | IQD | reference | 1690.34 |
| EUR | ISK | reference | 136.4 |
| EUR | JMD | reference | 176.9072 |
| EUR | JOD | reference | 0.7905 |

</details>

[Full table on the Banca d'Italia rates page](https://allratestoday.com/central-bank-rates-api/bdi/) · Source: [Official rates published by BDI, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/bdi/). Rates are as printed by the central bank; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 📦 Installation

```bash
npm install bdi-exchange-rate
```

```bash
yarn add bdi-exchange-rate
```

```bash
pnpm add bdi-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/bdi-exchange-rate`](https://www.npmjs.com/package/@allratestoday/bdi-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'bdi-exchange-rate';

const pair = await getRate('USD', 'EUR', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Banca d'Italia rate, on the central bank's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the central bank printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the central bank does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('USD', 'EUR', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'bdi',
  name: 'Banca d\'Italia',
  rate_date: '2026-10-13',   // Banca d'Italia's own publication date
  source: 'USD',
  target: 'EUR',
  rate: 0.893815,
  rate_type: 'reference',
  derived: true,
  method: 'inverse',  // computed from the published EUR/USD print
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'bdi-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'bdi',
  name: 'Banca d\'Italia',
  rate_date: '2026-10-13',
  rates: [
    { "base": "EUR", "quote": "USD", "type": "reference", "value": 1.1188 },
    // … the rest of the published table (150 currencies vs EUR)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2016 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'bdi-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'EUR' });
```

**Response:**

```javascript
{
  bank: 'bdi',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'bdi-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'EUR', from: '2026-01-01', to: '2026-10-13' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'bdi',
  source: 'USD',
  target: 'EUR',
  from: '2026-01-01',
  to: '2026-10-13',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-13', rate: 0.893815, rate_type: 'reference', derived: true, method: 'inverse' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Banca d'Italia currently publishes rates covering **150 currencies** against the EUR (as of the latest table):

🇦🇪 `AED` · 🇦🇫 `AFN` · 🇦🇱 `ALL` · 🇦🇲 `AMD` · 🇦🇴 `AOA` · 🇦🇷 `ARS` · 🇦🇺 `AUD` · 🇦🇼 `AWG` · 🇦🇿 `AZN` · 🇧🇦 `BAM` · 🇧🇧 `BBD` · 🇧🇩 `BDT` · 🇧🇭 `BHD` · 🇧🇮 `BIF` · 🇧🇲 `BMD` · 🇧🇳 `BND` · 🇧🇴 `BOB` · 🇧🇷 `BRL` · 🇧🇸 `BSD` · 🇧🇹 `BTN` · 🇧🇼 `BWP` · 🇧🇿 `BZD` · 🇨🇦 `CAD` · 🇨🇩 `CDF` · 🇨🇭 `CHF` · 🇨🇱 `CLP` · 🇨🇳 `CNY` · 🇨🇴 `COP` · 🇨🇷 `CRC` · 🇨🇺 `CUP` · 🇨🇻 `CVE` · 🇨🇿 `CZK` · 🇩🇯 `DJF` · 🇩🇰 `DKK` · 🇩🇴 `DOP` · 🇩🇿 `DZD` · 🇪🇬 `EGP` · 🇪🇷 `ERN` · 🇪🇹 `ETB` · 🇫🇯 `FJD` · 🇫🇰 `FKP` · 🇬🇧 `GBP` · 🇬🇪 `GEL` · 🇬🇭 `GHS` · 🇬🇮 `GIP` · 🇬🇲 `GMD` · 🇬🇳 `GNF` · 🇬🇹 `GTQ` · 🇬🇾 `GYD` · 🇭🇰 `HKD` · 🇭🇳 `HNL` · 🇭🇹 `HTG` · 🇭🇺 `HUF` · 🇮🇩 `IDR` · 🇮🇱 `ILS` · 🇮🇳 `INR` · 🇮🇶 `IQD` · 🇮🇸 `ISK` · 🇯🇲 `JMD` · 🇯🇴 `JOD` · 🇯🇵 `JPY` · 🇰🇪 `KES` · 🇰🇬 `KGS` · 🇰🇭 `KHR` · 🇰🇲 `KMF` · 🇰🇷 `KRW` · 🇰🇼 `KWD` · 🇰🇾 `KYD` · 🇰🇿 `KZT` · 🇱🇦 `LAK` · 🇱🇧 `LBP` · 🇱🇰 `LKR` · 🇱🇷 `LRD` · 🇱🇸 `LSL` · 🇱🇾 `LYD` · 🇲🇦 `MAD` · 🇲🇩 `MDL` · 🇲🇬 `MGA` · 🇲🇰 `MKD` · 🇲🇲 `MMK` · 🇲🇳 `MNT` · 🇲🇴 `MOP` · 🇲🇷 `MRU` · 🇲🇺 `MUR` · 🇲🇻 `MVR` · 🇲🇼 `MWK` · 🇲🇽 `MXN` · 🇲🇾 `MYR` · 🇲🇿 `MZN` · 🇳🇦 `NAD` · 🇳🇬 `NGN` · 🇳🇮 `NIO` · 🇳🇴 `NOK` · 🇳🇵 `NPR` · 🇳🇿 `NZD` · 🇴🇲 `OMR` · 🇵🇦 `PAB` · 🇵🇪 `PEN` · 🇵🇬 `PGK` · 🇵🇭 `PHP` · 🇵🇰 `PKR` · 🇵🇱 `PLN` · 🇵🇾 `PYG` · 🇶🇦 `QAR` · 🇷🇴 `RON` · 🇷🇸 `RSD` · 🇷🇼 `RWF` · 🇸🇦 `SAR` · 🇸🇧 `SBD` · 🇸🇨 `SCR` · 🇸🇩 `SDG` · 🇸🇪 `SEK` · 🇸🇬 `SGD` · 🇸🇭 `SHP` · 🇸🇱 `SLE` · 🇸🇴 `SOS` · 🇸🇷 `SRD` · 🇸🇸 `SSP` · 🇸🇹 `STN` · 🇸🇻 `SVC` · 🇸🇾 `SYP` · 🇸🇿 `SZL` · 🇹🇭 `THB` · 🇹🇯 `TJS` · 🇹🇲 `TMT` · 🇹🇳 `TND` · 🇹🇴 `TOP` · 🇹🇷 `TRY` · 🇹🇹 `TTD` · 🇹🇼 `TWD` · 🇹🇿 `TZS` · 🇺🇦 `UAH` · 🇺🇬 `UGX` · 🇺🇸 `USD` · 🇺🇾 `UYU` · 🇺🇿 `UZS` · 🇻🇪 `VES` · 🇻🇳 `VND` · 🇻🇺 `VUV` · 🇼🇸 `WST` · `XAF` · `XCD` · `XCG` · `XDR` · `XOF` · `XPF` · 🇾🇪 `YER` · 🇿🇦 `ZAR` · 🇿🇲 `ZMW` · 🇿🇼 `ZWG`

## 🏛️ Source

Banca d'Italia is Italy's central bank and part of the Eurosystem. Its exchange-rate portal publishes daily reference rates for around 170 currencies against the euro, compiled through the daily concertation procedure with the other ESCB central banks — the series Italian tax and accounting practice refers to.

- Publisher's own page: [Exchange rates portal (Cambi)](https://tassidicambio.bancaditalia.it/terzevalute-wf-ui-web/converter) · [www.bancaditalia.it](https://www.bancaditalia.it)
- Publication: every business day; the exact schedule, freshness status and any current delay are on the [Banca d'Italia rates page](https://allratestoday.com/central-bank-rates-api/bdi/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Banca d'Italia quotes **foreign currency per 1 EUR** (e.g. `base: "EUR", quote: "USD"` means USD per one EUR).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the central bank's series a row belongs to (`reference` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Banca d'Italia rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/bdi/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('bdi')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate bdi ...` command
- Evaluating? Agents can self-issue a trial key with no signup: `POST https://allratestoday.com/api/agent/keys` (send `Content-Type: application/json`) returns a 100-call key valid 7 days that covers the free-plan methods (latest table, pairs); dated tables and history need a [paid plan](https://allratestoday.com/pricing/). The MCP servers expose it as `request_trial_key`
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If Banca d'Italia does not print a pair directly, the API resolves it from the central bank's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The central bank printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via EUR from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Banca d'Italia |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'bdi-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('bdi-exchange-rate');

getRate('USD', 'EUR', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once per business day — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The central bank's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2016 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRatesToday/central-bank-exchange-rates](https://huggingface.co/datasets/AllRatesToday/central-bank-exchange-rates) — one CSV per institution (`rates/bdi.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- Raw JSON on GitHub: `https://raw.githubusercontent.com/AllRates-Today/central-bank-exchange-rates/main/data/bdi/latest.json`

## 🔗 Links

- [Banca d'Italia rates page](https://allratestoday.com/central-bank-rates-api/bdi/) — live table, publication cadence, FAQ
- [All central bank sources](https://allratestoday.com/central-bank-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/bdi-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (Free)](https://allratestoday.com/register) · [Dashboard](https://allratestoday.com/profile) · [Pricing](https://allratestoday.com/pricing/)
- [Status](https://allratestoday.com/status)
- [Postman collection](https://allratestoday.com/postman/)
- [GitHub](https://github.com/AllRates-Today/bdi-exchange-rate)

## 📜 License

MIT
