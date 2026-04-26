# MedMerge Captive Insurance Proforma

A multi-line captive insurance proforma for MedMerge's physician group, white-collar population, and 87-facility owned-property portfolio. Built to help MedMerge partners and investors evaluate moving from fully insured (P&L expense) to a captive structure (working balance-sheet asset) across health, MedMal, casualty, and property lines.

---

## Headlines

- **Covered population:** 20,050 lives (17,250 physician group + 2,800 white collar)
- **Owned property footprint:** 87 facilities — 27 micro hospitals, 50 ASCs, 10 physician-owned surgical hospitals — TIV ~$3.3B
- **Captive structure:** 3 entities — Health (Montana, existing), Casualty incl. MedMal (Vermont RRG), Property (Cayman)
- **Year 1 gross written premium:** $268.5M
- **Initial capital injection:** $40M (recycles into a permanent, growing balance-sheet asset)
- **Year 1 net underwriting result:** $45.4M
- **3-year cumulative underwriting profit retained:** $153.7M
- **End-Year-3 captive surplus:** $193.7M (~4.8× initial capital — collateralizable working capital)
- **Estimated Year 1 value vs. fully insured:** ~$93M (~$48M premium savings + $45M U/W profit retained)

The captive surplus is not idle reserve — it serves as collateral capacity for facility expansion, equipment financing, and operational liquidity, and the investment income earned on captive assets directly offsets MedMerge group operating expenses.

---

## How to read this repo

| Read this... | If you want to... |
|---|---|
| `README.md` (this file) | Get the one-page picture |
| `proforma.md` | Read the full investor-facing proforma — recommended for board / partner / physician leadership review |
| `assumptions.md` | See every input assumption, its basis, and where to override it |
| `data/*.csv` | Tweak inputs and re-run scenarios |

---

## Captive structure at a glance

| # | Captive | Lines | Domicile | Y1 GWP |
|---|---|---|---|---:|
| 1 | Health Captive | Group medical, Rx | Montana (existing) | $132.3M |
| 2 | Casualty Captive | MedMal, GL, EPLI, D&O, Cyber, Auto | Vermont (RRG) | $129.8M |
| 3 | Property Captive | Property, BI, Equipment Breakdown — 87 facilities / $3.3B TIV | Cayman | $6.4M |
| | **TOTAL** | | | **$268.5M** |

MedMal sits inside the Casualty captive (it is a casualty line). MedMal vs. short-tail casualty are tracked as separate notional pools inside the Casualty captive for actuarial discipline.

---

## 3-year financial summary

| | Year 1 | Year 2 | Year 3 |
|---|---:|---:|---:|
| Gross Written Premium | $268.5M | $281.2M | $294.6M |
| Net Earned Premium | $238.9M | $250.4M | $262.6M |
| Net Incurred Losses | ($173.8M) | ($182.4M) | ($191.4M) |
| Operating expenses | ($23.4M) | ($24.5M) | ($25.6M) |
| Investment Income | $3.7M | $7.3M | $11.8M |
| **Net Underwriting Result** | **$45.4M** | **$50.9M** | **$57.4M** |
| Ending Captive Surplus | $85.4M | $136.3M | $193.7M |

---

## How captive surplus supports MedMerge operations

The captive structure is built so insurance premium does double duty — covering risk *and* funding MedMerge's broader operating and capital needs:

- **Collateral for facility expansion** — Property captive surplus naturally aligns with the owned-facility footprint and supports construction financing for new ASCs and micro hospitals
- **Equipment financing** — surplus collateralizes medical equipment leases at favorable rates vs. third-party lessors
- **Operating liquidity** — captive can provide intercompany loans at arm's-length rates for working capital
- **Investment income offset** — $3.7M (Y1) → $11.8M (Y3) of recurring investment income directly offsets group operating expenses
- **Premium-tax savings** — ~$0.7M annual savings vs. fully insured stay inside MedMerge
- **M&A growth capital** — captive can underwrite new acquisitions immediately and provide transition capital

See `proforma.md` §10.4 for full detail.

---

## What this proforma is — and what it covers

**It is:**
- A planning document for partner, investor, and physician-leadership conversations
- A working financial model with editable inputs and traceable math
- A structural recommendation for entity design and domicile

**The standard professional workstreams that will validate it during implementation** (see `proforma.md` §12):
- Actuarial opinions (health IBNR, MedMal SAO)
- Captive feasibility studies (Vermont, Cayman)
- Tax opinions (IRC §831, Cayman §953(d))
- Reinsurance broker market check
- TPA and stop-loss broker placement
- Investment policy statement

These are routine workstreams handled in parallel during a typical 4–6 month implementation.

---

## Inputs to validate during implementation

1. **Specialty mix** in `data/specialty_mix.csv` — replace placeholder distribution with actual surgeon roster
2. **Property TIV per facility** in `data/premiums.csv` — the $3.3B program total is built from your stated facility counts and standard healthcare ratios; refine via formal SOV
3. **Existing MT captive starting surplus** — proforma shows incremental Y1 funding; confirm with captive manager
4. **Workers Compensation** — not included by default; flagged for inclusion decision
5. **Reinsurance pricing** — every ceded-premium ratio in `data/reinsurance.csv` will be confirmed via broker market check
