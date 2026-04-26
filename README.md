# MedMerge Captive Insurance Proforma

A multi-line captive insurance proforma for MedMerge's physician group and white-collar population. Built to help MedMerge partners and investors evaluate moving from fully insured (P&L expense) to a captive structure (balance sheet asset) across health, MedMal, casualty, and property lines.

---

## Headlines

- **Covered population:** 20,050 lives (17,250 physician group + 2,800 white collar)
- **Captive structure:** 3 entities — Health (Montana, existing), Casualty incl. MedMal (Vermont RRG), Property (Cayman)
- **Year 1 gross written premium:** $262.9M
- **Initial capital injection:** $35.75M
- **Year 1 net underwriting result:** $44.5M
- **3-year cumulative underwriting profit retained:** $150.7M
- **End-Year-3 captive surplus:** $186.4M (~5.2× initial capital)
- **Estimated annual savings vs. fully insured:** ~$45M premium reduction + $44.5M U/W profit retained = ~$90M Year 1

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
| 3 | Property Captive | Property, BI | Cayman | $0.8M |
| | **TOTAL** | | | **$262.9M** |

MedMal sits inside the Casualty captive (it is a casualty line). MedMal vs. short-tail casualty are tracked as separate notional pools inside the Casualty captive for actuarial discipline.

---

## 3-year financial summary

| | Year 1 | Year 2 | Year 3 |
|---|---:|---:|---:|
| Gross Written Premium | $262.9M | $275.4M | $288.6M |
| Net Earned Premium | $236.1M | $247.5M | $259.6M |
| Net Incurred Losses | ($172.1M) | ($180.6M) | ($189.5M) |
| Operating expenses | ($23.1M) | ($24.2M) | ($25.3M) |
| Investment Income | $3.5M | $7.1M | $11.5M |
| **Net Underwriting Result** | **$44.5M** | **$49.9M** | **$56.3M** |
| Ending Captive Surplus | $80.3M | $130.1M | $186.4M |

---

## What this proforma is — and what it isn't

**It is:**
- A planning document for partner / investor / physician-leadership conversations
- A working financial model with editable inputs and traceable math
- A structural recommendation for entity design and domicile

**It is not:**
- An actuarial opinion (required from credentialed actuary before bind)
- A legal or tax opinion (required from captive counsel)
- A replacement for a feasibility study (required by VT and Cayman regulators)
- Bindable insurance — every ceded-premium assumption needs broker market quotes

See `proforma.md` §12 for the full list of items requiring formal professional sign-off.

---

## Key flagged assumptions to validate

1. **Specialty mix** in `data/specialty_mix.csv` is a placeholder distribution — replace with actual surgeon roster
2. **Property TIV** of $300M in `data/premiums.csv` is a placeholder — replace with actual Statement of Values
3. **Existing MT captive starting surplus** — proforma shows incremental Y1 funding; confirm with captive manager
4. **Workers Compensation** — not included by default; flagged for inclusion decision
5. **Reinsurance pricing** — every ceded-premium ratio in `data/reinsurance.csv` needs broker market check
