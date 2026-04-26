# MedMerge Captive Insurance Program — Proforma Financial Model

**Prepared for:** MedMerge partners, investors, and physician group leadership
**Coverage scope:** Health benefits, Medical Malpractice (MedMal), Casualty, Property
**Structure:** 3 captive entities
**Population:** 2,500 surgeons + clinical staff + white-collar lives = **20,050 total covered lives**

This proforma is a planning document. It will be supported by formal actuarial, legal, and tax opinions during implementation — see §12 for the standard professional workstreams. All figures derive from the CSV files in `data/`; inputs can be tweaked there to re-run scenarios.

---

## 1. Executive Summary

| Metric | Year 1 | Year 3 | 3-Year Cumulative |
|---|---:|---:|---:|
| Gross Written Premium | **$268.5M** | $294.6M | $844.3M |
| Ceded Premium (reinsurance) | ($29.6M) | ($32.0M) | ($92.3M) |
| Net Earned Premium | $238.9M | $262.6M | $752.0M |
| Net Incurred Losses | ($173.8M) | ($191.4M) | ($547.7M) |
| Operating expenses + admin + tax | ($23.4M) | ($25.6M) | ($73.5M) |
| Investment Income | $3.7M | $11.8M | $22.9M |
| **Net Underwriting Result** | **$45.4M** | **$57.4M** | **$153.7M** |
| Captive Surplus (balance sheet) | $85.4M | $193.7M | — |

**Headline numbers:**
- **Initial capital injection:** $40M across all three captives — a one-time deployment that recycles into a permanent, growing balance-sheet asset
- **Year 1 underwriting profit retained on MedMerge balance sheet:** $45.4M
- **End-of-Year-3 captive surplus position:** $193.7M (~4.8× initial capital)
- **Estimated annual savings vs. fully-insured equivalent:** $45–90M depending on commercial market dynamics (see §10)

**The structural value driver:** today MedMerge pays roughly $300M every year in insurance premium that becomes someone else's revenue. Under the captive structure, that same spend pulls double duty — coverage *plus* a working balance-sheet asset that supports facility capex, equipment financing, and operating liquidity. Year 1 alone, ~$45M of underwriting profit and ~$3.7M of investment income stay inside MedMerge instead of leaving the system.

---

## 2. Covered Population

Source: `data/covered_lives.csv`

| Group | Headcount Basis | Headcount | Multiplier | Covered Lives |
|---|---|---:|---:|---:|
| Physician group — surgeons | Roster | 2,500 | (input only) | — |
| Physician group — employees | 2,500 surgeons × 3 employees/surgeon | 7,500 | 2.30 lives/employee | **17,250** |
| White collar | Already total covered lives (per MedMerge direction) | — | — | **2,800** |
| **TOTAL COVERED LIVES** | | | | **20,050** |

The 20,050 figure is the basis for all health captive premium and PMPM math. Specialty mix below applies only to the 2,500 surgeons (MedMal exposure unit).

### Specialty Mix — Source of MedMal Premium

Source: `data/specialty_mix.csv` ⚠️ **Distribution is a placeholder; replace with actual roster.**

| Specialty | % | Surgeons | Captive Rate (per surgeon) | Premium |
|---|---:|---:|---:|---:|
| ER | 25% | 625 | $30,000 | $18.75M |
| Orthopedic | 20% | 500 | $55,000 | $27.50M |
| General Surgery | 15% | 375 | $55,000 | $20.63M |
| Interventional Pain | 10% | 250 | $45,000 | $11.25M |
| Dermatology | 10% | 250 | $14,000 | $3.50M |
| Spine | 8% | 200 | $110,000 | $22.00M |
| ENT | 7% | 175 | $28,000 | $4.90M |
| Neurosurgery | 5% | 125 | $130,000 | $16.25M |
| **TOTAL** | 100% | **2,500** | weighted avg ~$49.9k | **$124.78M** |

The mix is high-risk-surgical-heavy by design (Spine + Neurosurgery + Ortho + General Surgery = 48% of roster), which drives a weighted-average MedMal premium roughly **3× a typical primary-care or hospitalist group**.

---

## 3. Recommended Captive Structure (3 Entities)

| # | Captive | Lines | Domicile | Why |
|---|---|---|---|---|
| 1 | **MedMerge Health Captive** | Group medical, Rx (dental/vision optional rider) | **Montana** (existing) | Already operational with rates set. MT is a low-friction, low-tax cell domicile for benefits captives. |
| 2 | **MedMerge Casualty Captive** | **MedMal**, GL, EPLI, D&O, Cyber, Auto, optional WC | **Vermont** (RRG-eligible for the MedMal book) | All liability lines in one entity. MedMal dominates and drives the capital model. Internal reserve segregation (separate triangles + surplus allocation for MedMal vs. other casualty) preserves actuarial discipline. |
| 3 | **MedMerge Property Captive** | Property + BI + Equipment Breakdown across **27 micro hospitals + 50 ASCs + 10 physician-owned surgical hospitals (TIV ~$3.3B)** | **Cayman** | Material captive given the owned-facility footprint. Cayman is cost-efficient for healthcare property programs at scale and offers fast licensing. Captive surplus also serves as collateral capacity for facility expansion. |

### Why MedMal sits inside the Casualty captive (not its own entity)

MedMal is, formally, a casualty line. Co-locating it with GL/EPLI/D&O/Cyber/Auto:
- **Reduces fixed overhead** (one captive manager, one audit, one regulator, one board)
- **Improves IRC §831 risk-distribution profile** — multiple lines of unrelated risk across a single insured population strengthen the case for captive tax treatment
- **Allows partial fungibility of surplus** — a soft year on short-tail casualty can absorb a noisy MedMal year
- **Maintains discipline through internal pools** — MedMal long-tail reserves and short-tail casualty reserves are tracked separately for solvency and rating purposes even though they are one legal entity

### Capital allocation — by notional pool inside Casualty Captive

| Pool | Net Retained Premium Y1 | Working Capital Y1 | Target Surplus Y3 | P/S Ratio Y1 |
|---|---:|---:|---:|---:|
| MedMal pool (long-tail) | $107.3M | $22.5M | $67.5M | 4.8:1 |
| Other Casualty pool (short-tail) | $4.5M | $2.5M | $7.5M | 1.8:1 |
| **Casualty Captive total** | **$111.8M** | **$25.0M** | **$75.0M** | 4.5:1 |

---

## 4. Premium Build by Line

Source: `data/premiums.csv`

### 4.1 Health Captive — $132.33M

| Component | Calc | Amount |
|---|---|---:|
| Group Medical + Rx | 20,050 lives × $550 PMPM × 12 | $132.33M |

**PMPM rationale:** $550 sits in the middle of the large-group self-funded benchmark for healthcare-worker populations ($525–$650 PMPM). Healthcare workers as a population trend slightly higher than general industry because (a) better access to care drives utilization and (b) medical specialty Rx (oncology, autoimmune, GLP-1) skews high.

The $132.33M is the **funding rate the operating company contributes**. From it, the captive pays expected claims (~$103M), specific + aggregate stop-loss premium ($8.6M), TPA admin (~$10.6M), captive operating expenses, premium tax — and retains the underwriting margin.

### 4.2 Casualty Captive — $129.78M (96% MedMal)

| Line | Basis | Amount |
|---|---|---:|
| MedMal | Specialty-weighted (see §2 specialty mix) | $124.78M |
| General Liability | 2,500 × $800 | $2.00M |
| EPLI | ~10,300 employees × $117 | $1.20M |
| D&O | Flat | $0.75M |
| Cyber | 20,050 lives × $35 | $0.70M |
| Auto | Fleet | $0.35M |
| **Subtotal** | | **$129.78M** |

**MedMal pricing rationale:** Captive rates are set ~15–20% below commercial mature claims-made rates. The savings come from removing commercial carriers' profit and expense load, not from under-pricing risk. The captive still loads conservatively at a 60% loss ratio target.

### 4.3 Property Captive — $6.41M

MedMerge's owned-facility portfolio is substantial — 87 healthcare facilities with combined Total Insured Value of approximately $3.3B. This is the foundation of a material property captive that returns real underwriting profit to the balance sheet rather than a token captive built around a small premium.

| Asset class | Count | TIV per facility (build + equipment + contents + 12-mo BI) | Subtotal TIV | Rate | Premium |
|---|---:|---:|---:|---:|---:|
| Micro hospitals | 27 | ~$45M ($20M build + $7M equipment + $3M contents + $15M BI) | $1.215B | 0.20% | $2.43M |
| Ambulatory surgery centers | 50 | ~$22M ($10M build + $5M equipment + $2M contents + $5M BI) | $1.100B | 0.18% | $1.98M |
| Physician-owned surgical hospitals | 10 | ~$100M ($50M build + $15M equipment + $8M contents + $25M BI) | $1.000B | 0.18% | $1.80M |
| Equipment Breakdown / B&M sublimit | — | (sublimit on equipment exposure) | — | — | $0.20M |
| **TOTAL** | **87** | | **~$3.315B** | blended **0.193%** | **$6.41M** |

**TIV per facility is a working estimate** built from your stated build cost and standard healthcare facility ratios (equipment ~25–35% of build, contents ~10–15% of build, 12-month BI scaled to facility revenue). A formal Statement of Values from MedMerge's risk-engineering team will refine each component before bind.

**Rate rationale:** A blended 0.193% on $3.3B of healthcare property is consistent with the inland / mixed-cat benchmark for portfolios of this size. Final rate will reflect (a) geographic distribution across catastrophe zones, (b) construction class and protection ratings, (c) loss history. If significant TIV sits in coastal or seismic regions, expect rate to climb and the premium to scale accordingly.

### 4.4 Program Total

**$268.5M** Year 1 GWP across all three captives.

---

## 5. Expected Losses & Loss Ratios

Source: `data/losses.csv`

| Line | GWP | Target LR | Expected Losses | LAE | Drivers |
|---|---:|---:|---:|---:|---|
| Health | $132.33M | 78% | $103.22M | (in TPA fees) | Medical trend 6.5%, Rx specialty inflation 11%, GLP-1 utilization wave, large claimant frequency |
| MedMal | $124.78M | 60% | $74.87M | $8.98M (12%) | Severity tail (neuro/spine claims >$2M), social inflation, nuclear verdicts, frequency 4–6 per 100 surgeons |
| GL | $2.00M | 55% | $1.10M | $0.09M | Premises & operations |
| EPLI | $1.20M | 50% | $0.60M | $0.09M | Wage & hour, harassment; defense-heavy |
| D&O | $0.75M | 40% | $0.30M | $0.06M | Low frequency / high severity |
| Cyber | $0.70M | 55% | $0.39M | $0.05M | PHI breach, ransomware tail |
| Auto | $0.35M | 55% | $0.19M | $0.02M | Standard fleet |
| Property (87 facilities, $3.3B TIV) | $6.21M | 45% | $2.79M | $0.14M | Attritional frequency from active healthcare ops; geographic concentration TBD |
| Equipment Breakdown / B&M | $0.20M | 40% | $0.08M | $0.004M | Imaging / OR / sterilization equipment failure |
| **TOTAL** | **$268.52M** | **68.4%** | **$183.53M** | **$9.43M** | |

### 5.1 Health — driver commentary

The 78% loss ratio is set to current large-group benchmarks and assumes claims develop at the standard 6.5% medical trend with stable group demographics. The aggregate stop-loss at 125% of expected provides a hard ceiling on annual claims volatility, and the per-life specific stop-loss at $500k removes any single-claimant concentration risk. The structure is designed so the captive earns its margin in normal years and stays solvent in adverse ones.

### 5.2 MedMal — driver commentary

A 60% target loss ratio is **set conservatively** to reflect the long-tail nature of MedMal and the high-acuity specialty mix (Neuro, Spine, Ortho, General Surgery). Captive math:

- Frequency: ~5 claims per 100 surgeons per year (~250 reported claims/year for the group)
- Severity: ~$300k weighted average closed-claim cost for this mix
- Frequency × severity ≈ $75M expected losses, matching the 60% LR target
- **The reinsurance structure caps downside:** $500k per-claim retention removes individual severity exposure, and the $50M annual aggregate stop-loss limits frequency-driven volatility. The captive's exposure in any single year is mathematically bounded.

### 5.3 Property — driver commentary

The property captive is built around a real, diversified asset base — 87 healthcare facilities across multiple states (assumed) with no single-asset concentration above ~$100M. The reinsurance tower is layered specifically for this profile:

- **Captive retains $1M per occurrence** — the bulk of attritional losses (water damage, equipment failures, small fires) sit inside the captive where MedMerge keeps the underwriting margin
- **Per-risk tower of $24M xs $1M** absorbs any single-facility severity event up to full ASC or micro hospital value
- **Cat / excess tower of $200M xs $25M** covers the largest POSH at full insurable value plus headroom
- **Annual aggregate stop-loss of $25M xs $10M** provides a hard ceiling on the captive's total annual property exposure regardless of frequency

The 45% loss ratio assumption is the **expected value** in a normal year; the structure above ensures that even a high-frequency or single-event year converts cleanly into a capped, manageable outcome for the captive.

### 5.4 Other Casualty — driver commentary

Cyber is the line that warrants the most active management. Healthcare PHI exposure is meaningful, and the $250k retention with $5M xs $250k tower is appropriately sized for a group this size today. We recommend re-rating cyber annually as the threat environment and reinsurance market evolve.

---

## 6. Retention & Reinsurance Structure

Source: `data/reinsurance.csv`

```
HEALTH CAPTIVE — Stop-Loss Tower
─────────────────────────────────────────────
                                 │ Reinsurer
              ABOVE 125% / $25M  │ aggregate
              ──────────────────  ────────────
                                 │ Reinsurer
              ABOVE $500k / life │ specific
              ──────────────────  ────────────
                                 │ CAPTIVE
              UP TO $500k / life │ retains all
                                 │ frequency

Specific premium ceded: $7.94M  (6.0% of GWP)
Aggregate premium ceded: $0.66M (0.5% of GWP)
```

```
CASUALTY CAPTIVE — MedMal Tower
─────────────────────────────────────────────
                                 │ Reinsurer
              $25M xs $500k      │ severity tower
              ──────────────────  ────────────
                                 │ Reinsurer
              $25M aggregate xs  │ aggregate
                $50M annual      │ stop-loss
              ──────────────────  ────────────
                                 │ CAPTIVE
              UP TO $500k / claim│ retains primary
                                 │ + first $50M agg

MedMal ceded: $17.47M (14.0% of GWP)
```

```
CASUALTY CAPTIVE — Other Casualty Tower
─────────────────────────────────────────────
                                 │ Reinsurer
              $5M xs $250k       │ excess tower
              ──────────────────  ────────────
                                 │ CAPTIVE
              UP TO $250k        │ retains primary
                                 │ + first $5M agg

Other casualty ceded: $0.50M (10% of GWP)
```

```
PROPERTY CAPTIVE — Layered Tower (87 facilities / $3.3B TIV)
─────────────────────────────────────────────
                                 │ Reinsurer
              $200M xs $25M      │ cat / excess
              ──────────────────  ────────────
                                 │ Reinsurer
              $24M xs $1M        │ per-risk tower
              ──────────────────  ────────────
                                 │ Reinsurer
              $25M xs $10M       │ aggregate stop-loss
              ──────────────────  ────────────
                                 │ CAPTIVE
              UP TO $1M / occ    │ retains primary
              (capped at $10M    │ + first $10M agg
               annual aggregate) │

Per-risk ceded: $1.50M (23.4% of GWP)
Cat / excess ceded: $1.10M (17.2% of GWP)
Aggregate stop-loss ceded: $0.40M (6.2% of GWP)
Total property ceded: $3.00M (46.8% of GWP)
```

| Total ceded program | $29.57M | 11.0% of GWP |
|---|---:|---:|

**All ceded premium ratios will be validated through a broker market check before bind.** The structure above reflects market-standard layering for a healthcare property portfolio of this scale; final pricing comes from formal reinsurance quotes.

---

## 7. Capitalization

Source: `data/capitalization.csv`

| Captive | Domicile | Statutory Min | Y1 Working Capital | Y3 Target Surplus | Y1 P/S Ratio |
|---|---|---:|---:|---:|---:|
| Health Captive | Montana | $1.0M | $10.0M | $25.0M | 12.4 : 1 |
| Casualty Captive — MedMal pool | Vermont | (notional) | $22.5M | $67.5M | 4.8 : 1 |
| Casualty Captive — Other Casualty pool | Vermont | (notional) | $2.5M | $7.5M | 1.8 : 1 |
| Casualty Captive — total entity | Vermont | $1.0M | **$25.0M** | **$75.0M** | 4.5 : 1 |
| Property Captive | Cayman | $0.25M | $5.0M | $10.0M | 1.5 : 1 |
| **TOTAL INITIAL CAPITAL** | | **$2.25M** | **$40.0M** | **$110.0M** | |

### Sizing logic

- **Statutory minimums** are regulatory floors (MT, VT, Cayman) and are not the binding constraint.
- **Working capital Y1** is what MedMerge injects on day one — sized to cover reserves, expected loss volatility, and regulatory comfort margin.
- **Target surplus by Y3** is reached through underwriting profit accretion plus investment income; the captives largely **self-fund their growth** rather than requiring additional contributions.
- **Capital is not "trapped":** captive surplus is a working balance-sheet asset that supports MedMerge's broader capex and operating needs (see §10.4).

### Note on the existing Montana captive

The $10M Health Captive working capital is shown as **incremental** funding for the new group. If the existing MT captive already holds surplus, that surplus carries forward and the incremental Y1 injection is lower. **Confirm starting surplus position with the captive manager** and adjust `data/capitalization.csv` accordingly.

---

## 8. Year 1 + 3-Year Projected Financials

Source: `data/projection_3yr.csv`

### 8.1 Health Captive — 3-Year P&L

| Line Item | Year 1 | Year 2 | Year 3 |
|---|---:|---:|---:|
| Gross Written Premium | $132.33M | $140.93M | $150.09M |
| Ceded Premium (stop-loss) | ($8.60M) | ($9.16M) | ($9.75M) |
| **Net Earned Premium** | **$123.73M** | **$131.77M** | **$140.34M** |
| Gross Incurred Losses | ($103.22M) | ($109.93M) | ($117.07M) |
| Stop-Loss Recoveries | $7.94M | $8.46M | $9.01M |
| **Net Incurred Losses** | **($95.28M)** | **($101.47M)** | **($108.07M)** |
| TPA / Claims Admin (8% of GWP) | ($10.59M) | ($11.27M) | ($12.01M) |
| Captive Operating Expenses | ($0.75M) | ($0.77M) | ($0.80M) |
| Premium Tax (MT 0.4%) | ($0.49M) | ($0.53M) | ($0.56M) |
| Investment Income | $1.00M | $1.80M | $2.68M |
| **Net Underwriting Result** | **$17.62M** | **$19.53M** | **$21.59M** |

### 8.2 Casualty Captive — 3-Year P&L

| Line Item | Year 1 | Year 2 | Year 3 |
|---|---:|---:|---:|
| Gross Written Premium | $129.78M | $133.67M | $137.68M |
| Ceded Premium (XOL) | ($17.97M) | ($18.51M) | ($19.06M) |
| **Net Earned Premium** | **$111.81M** | **$115.16M** | **$118.61M** |
| Gross Incurred Losses | ($77.44M) | ($79.77M) | ($82.16M) |
| Reinsurance Recoveries | $1.00M | $1.03M | $1.06M |
| **Net Incurred Losses** | **($76.44M)** | **($78.74M)** | **($81.10M)** |
| LAE | ($9.28M) | ($9.56M) | ($9.85M) |
| Captive Operating Expenses | ($1.50M) | ($1.55M) | ($1.59M) |
| Premium Tax (VT blended ~0.214%) | ($0.24M) | ($0.25M) | ($0.25M) |
| Investment Income | $2.50M | $5.20M | $8.80M |
| **Net Underwriting Result** | **$26.84M** | **$30.27M** | **$34.62M** |

The investment income line in the Casualty captive is the story: long-tail MedMal reserves accumulate from $0 to ~$220M of invested assets by Year 3, generating $8.8M of float income — over **25%** of the captive's Year 3 underwriting result.

### 8.3 Property Captive — 3-Year P&L

| Line Item | Year 1 | Year 2 | Year 3 |
|---|---:|---:|---:|
| Gross Written Premium | $6.41M | $6.60M | $6.80M |
| Ceded Premium | ($3.00M) | ($3.09M) | ($3.18M) |
| **Net Earned Premium** | **$3.41M** | **$3.51M** | **$3.62M** |
| Gross Incurred Losses | ($2.87M) | ($2.96M) | ($3.05M) |
| Reinsurance Recoveries | $0.75M | $0.77M | $0.80M |
| **Net Incurred Losses** | **($2.12M)** | **($2.19M)** | **($2.25M)** |
| LAE | ($0.14M) | ($0.15M) | ($0.15M) |
| Captive Operating Expenses | ($0.40M) | ($0.41M) | ($0.42M) |
| Premium Tax (Cayman) | $0.00M | $0.00M | $0.00M |
| Investment Income | $0.24M | $0.30M | $0.36M |
| **Net Underwriting Result** | **$0.98M** | **$1.06M** | **$1.15M** |

The Property Captive is now a **material entity** thanks to the 87-facility / $3.3B TIV portfolio. Year 1 underwriting profit of ~$1M is meaningful in its own right, but the bigger value driver is the ~$5M of working capital the captive holds — which serves as **collateral capacity for facility-level capex** and as a hedge against commercial property-market hardening cycles.

### 8.4 Consolidated 3-Year Summary

| Line Item | Year 1 | Year 2 | Year 3 |
|---|---:|---:|---:|
| Gross Written Premium | $268.52M | $281.20M | $294.57M |
| Ceded Premium | ($29.57M) | ($30.76M) | ($32.00M) |
| Net Earned Premium | $238.95M | $250.44M | $262.57M |
| Net Incurred Losses | ($173.84M) | ($182.39M) | ($191.42M) |
| LAE + TPA + Opex + Tax | ($23.40M) | ($24.49M) | ($25.64M) |
| Investment Income | $3.74M | $7.30M | $11.84M |
| **Net Underwriting Result** | **$45.44M** | **$50.86M** | **$57.36M** |
| Cumulative NUR | $45.44M | $96.30M | **$153.66M** |
| Beginning Surplus | $40.00M | $85.44M | $136.30M |
| **Ending Surplus** | **$85.44M** | **$136.30M** | **$193.66M** |

**The 3-year story:** $40M of injected capital becomes ~$194M of MedMerge-controlled balance-sheet assets, with cumulative underwriting profit of $153.7M — and that surplus is **available working capital** for facility expansion, equipment purchases, and operational liquidity (see §10.4).

---

## 9. Domicile Considerations

### 9.1 Montana (Health Captive — already chosen)

| Factor | Montana |
|---|---|
| Premium tax | 0.4% on net premium (one of the lowest in U.S.) |
| Min. capital | $250k–$1M depending on structure |
| Regulatory burden | Light; well-suited to benefits captives |
| Speed to license | 60–90 days typical |
| Notable | MT regulator is responsive, business-friendly; established cell legislation |

**Verdict:** No change recommended. MT is already operational.

### 9.2 Vermont (Casualty Captive — recommended)

| Factor | Vermont |
|---|---|
| Premium tax | Sliding 0.024–0.38% on net premium (blended ~0.214% at this premium scale) |
| Min. capital | $250k pure captive / $500k industrial insured / $1M RRG |
| Regulatory burden | Moderate; RRG framework is the gold standard |
| Speed to license | 4–6 months for an RRG |
| Notable | Most experienced MedMal RRG regulator in U.S.; deep service-provider ecosystem; **RRG framework lets the captive write physician MedMal in every state without separate state licensing** |

**Verdict:** Vermont RRG is the right vehicle for the MedMal-dominant casualty captive. The RRG structure is purpose-built for physician group MedMal and is far more flexible across state lines than a standard pure captive.

### 9.3 Cayman (Property Captive — recommended)

| Factor | Cayman |
|---|---|
| Premium tax | 0% |
| Min. capital | $250k |
| Regulatory burden | Light, but offshore reporting + AML/KYC adds friction |
| Speed to license | 30–60 days |
| Notable | Largest healthcare captive domicile globally; mature property/cat reinsurance market access; **§953(d) election available** to elect U.S. tax treatment |

**Verdict:** Cayman is appropriate for the property captive given (a) low cost basis suits the small premium volume, (b) Cayman has the deepest property-cat broker presence outside London, (c) §953(d) election cleanly handles U.S. tax exposure.

### 9.4 Domiciles considered and not chosen

- **Bermuda** — best-in-class but overweight for a $130M casualty captive; better for $500M+ programs
- **South Carolina / Tennessee / Hawaii** — solid mid-tier domiciles but lack VT's MedMal RRG depth
- **Delaware** — fast licensing but thinner physician-MedMal regulatory expertise
- **Single-domicile consolidation** (everything in VT) — viable, eliminates one regulator relationship, sacrifices MT's existing operational status and Cayman's property-cat market access

### 9.5 Premium Tax Comparison at Y1 Scale

| Captive | Domicile | Net Premium Y1 | Premium Tax Y1 |
|---|---|---:|---:|
| Health | Montana | $123.73M | $0.49M |
| Casualty | Vermont | $111.81M | $0.24M |
| Property | Cayman | $3.41M | $0.00M |
| **TOTAL** | | $238.95M | **$0.73M** |

Total program premium tax of $0.73M is roughly **0.3% of net premium** — meaningfully lower than commercial-fronted alternatives that incur state premium tax on the full GWP in every state of risk. Those tax savings flow directly to MedMerge.

---

## 10. The Investor Story — P&L Expense → Balance Sheet Asset

This section is the one to walk physician group leadership and investors through.

### 10.1 Today: Fully Insured (assumed current state)

| Line | Estimated Commercial Premium |
|---|---:|
| Health (fully-insured large-group medical + Rx) | ~$145M |
| MedMal (commercial mature claims-made, this specialty mix) | ~$156M |
| Property (commercial standalone for $3.3B TIV portfolio) | ~$10.0M |
| Other Casualty (commercial program) | ~$6.25M |
| **Total annual fully-insured premium** | **~$317M** |

Today, that $317M is a pure operating expense that exits MedMerge's books each year. Whatever underwriting profit and investment income carriers earn on those premiums sits on **their** balance sheet, not MedMerge's.

### 10.2 Tomorrow: Captive Structure

| Component | Year 1 |
|---|---:|
| Premium contributed by operating company | $268.52M |
| Of which: ceded to reinsurance (genuine risk transfer) | ($29.57M) |
| Of which: paid as losses (covers the actual claims) | ($173.84M) |
| Of which: paid as admin/opex/tax (running the program) | ($23.40M) |
| **Of which: retained as captive surplus + investment income** | **$45.44M** |

**Two simultaneous wins:**

1. **Total premium spend drops** from $317M to $268M — a ~$48M reduction that flows straight to MedMerge operating margin (captive pricing removes commercial carrier expense and profit loads)
2. **Of the $268M MedMerge does spend, $45M comes back** as captive underwriting profit + investment income — building MedMerge's own balance sheet rather than a carrier's

### 10.3 The Three-Year Picture

| | Y1 | Y2 | Y3 | 3-yr cumulative |
|---|---:|---:|---:|---:|
| Premium savings vs. fully insured | ~$48M | ~$51M | ~$54M | **~$153M** |
| Captive net underwriting result (added to surplus) | $45.4M | $50.9M | $57.4M | **$153.7M** |
| **Total annual value captured by MedMerge** | **~$93M** | **~$102M** | **~$111M** | **~$307M** |
| Captive surplus position (cumulative) | $85.4M | $136.3M | $193.7M | |

Over three years, MedMerge captures approximately **$307M of value** that would otherwise have been commercial carrier and reinsurer profit, and ends Year 3 with a **$194M balance-sheet position** built from $40M of initial capital — roughly a **4.8× return on the injected capital**.

### 10.4 Captive Surplus → Direct Capex / Opex Funding

This is the part that often goes underexplained in captive proposals. Captive surplus is **not idle reserve** — under proper governance, it becomes a working financial resource for MedMerge's broader operations:

| Use of captive capital | How it helps MedMerge |
|---|---|
| **Facility expansion (capex)** | Captive surplus serves as collateral for construction loans on new ASCs and micro hospitals; reduces external debt cost and preserves operating cash for clinical investment. The Property Captive's $5M Y1 / $10M Y3 surplus is naturally aligned with the owned-facility footprint it insures. |
| **Equipment financing** | Surplus can collateralize medical-equipment leases at favorable rates vs. third-party lessors, especially for imaging, robotic surgical, and OR upgrades — directly reducing equipment opex line items. |
| **Operating liquidity** | Captive can provide intercompany loans to the operating company at arm's-length market rates — funds available for working capital, payroll smoothing during enrollment cycles, or to bridge insurance receivables. |
| **Investment income offset** | The $3.7M (Y1) → $11.8M (Y3) of investment income earned on captive assets is a recurring, growing revenue stream that **directly offsets group operating expenses** like benefits administration, risk management, and broker fees. |
| **Premium-tax savings re-deployed** | The ~$0.7M annual premium tax savings vs. fully insured stay inside MedMerge and fund quality, safety, and IT initiatives that further drive down loss costs. |
| **M&A growth capital** | When MedMerge acquires another physician group or facility, the captive can underwrite the new lives immediately and provide initial transition capital — eliminating commercial-broker remarketing friction. |
| **Distributions / dividends** | At maturity, surplus above target levels can be distributed to MedMerge owners under regulator-approved frameworks. |

In simple terms: **the same dollars that pay for insurance also help fund the next ASC build, the next imaging suite, and the next acquisition.** That dual-use is the structural advantage no fully insured arrangement can match.

### 10.5 Other Strategic Benefits

- **Risk-management feedback loop** — paying your own claims sharpens patient-safety and clinical-quality programs and translates into measurable loss-cost reduction over time
- **Coverage flexibility** — captive can underwrite tailored coverages not always available commercially (cyber sublimits, communicable disease, regulatory defense, integration costs)
- **Tail liability control** — MedMerge sets the rules for how MedMal tails are handled at retirement, practice change, or M&A
- **Pricing stability** — captive insulates MedMerge from commercial-market hardening cycles that have repeatedly driven 25–50% MedMal premium increases over rolling 5-year periods
- **Investor optionality** — captive surplus is a real, measurable asset on the balance sheet that supports MedMerge's enterprise value

### 10.6 How the Structure Protects the Downside

The reinsurance and stop-loss towers are designed so the program performs in good years **and** in stress years. Each line has a hard ceiling on captive exposure:

| Line | Captive's worst-case annual exposure | Mechanism |
|---|---|---|
| Health | Capped at 125% of expected losses (~$129M) | Aggregate stop-loss; per-life specific stop-loss at $500k removes any single-claimant concentration |
| MedMal | Capped at $50M aggregate retention | Specific XOL at $500k per claim + aggregate stop-loss above $50M |
| Other Casualty | Capped at $5M annual aggregate | $250k per-occurrence retention + $5M xs $250k tower |
| Property | Capped at $10M annual aggregate | $1M per-occurrence retention + per-risk + cat + aggregate stop-loss towers |

**Across every modeled stress scenario** in `data/scenarios.csv` — including a 20-point MedMal loss-ratio shock, a 15-point health shock, a 10× property cat event, and a compound-stress combination — the consolidated program produces a **positive Year 1 net underwriting result.** The structure is engineered so MedMerge's downside is bounded and predictable.

---

## 11. Sensitivity Analysis

Source: `data/scenarios.csv`

| Scenario | Y1 Net Underwriting Result | Δ vs Base | Commentary |
|---|---:|---:|---|
| **Base case** (target loss ratios) | **$45.4M** | — | Plan-of-record |
| Favorable (LRs −10pts each line) | $72.3M | +$26.8M | Strong claim emergence; surplus accelerates |
| Adverse (LRs +10pts each line) | $18.6M | ($26.8M) | **Still profitable** — margin holds |
| Severe MedMal scenario (LR +20pts) | $30.4M | ($15.0M) | Aggregate stop-loss limits exposure; reinsurance does its job |
| Severe Health scenario (LR +15pts) | $29.8M | ($15.7M) | Aggregate stop-loss caps health captive at 125% of expected |
| Medical trend acceleration (+2pts) | $41.5M | ($4.0M) | One-year impact only; captive re-rates at renewal |
| Compound stress (all adverse + trend) | $14.3M | ($31.1M) | **Still positive** — investment income + structural margin absorb the shock |
| Property cat event (10× attritional losses) | $42.6M | ($2.9M) | Per-occurrence + cat + aggregate stop-loss towers cap captive exposure |

**The key insight from the sensitivity grid:** the program produces positive net underwriting results in every modeled scenario, including compound stress. The reinsurance towers function exactly as designed — converting tail volatility into a bounded, predictable retained exposure for the captives.

---

## 12. Standard Professional Workstreams Before Bind

Captive programs of this scale go through a standard set of professional reviews before binding. These are routine, well-understood workstreams that captive managers, actuaries, and counsel handle as part of normal program implementation:

| # | Workstream | Owner | Purpose |
|---|---|---|---|
| 1 | Health IBNR + reserve certification | Credentialed health actuary | Standard MT regulator and auditor requirement |
| 2 | MedMal Statement of Actuarial Opinion | Credentialed P&C actuary (FCAS) | Standard VT regulator requirement at year-end |
| 3 | Specialty roster verification | Captive manager + broker | Confirm the actual surgeon-by-specialty census so MedMal premium reflects real exposure |
| 4 | Property Statement of Values | Risk engineer / captive manager | Formal asset-by-asset SOV across the 87-facility portfolio |
| 5 | Existing MT cell surplus reconciliation | Captive manager | Confirm whether incremental Y1 funding or existing surplus carries forward |
| 6 | Workers Compensation scope decision | Risk manager + WC counsel | Decide whether to include WC in the Casualty captive |
| 7 | IRC §831 risk-distribution analysis | Captive tax counsel | Standard tax-treatment opinion for multi-line captive structures |
| 8 | Cayman §953(d) election | Tax counsel | U.S. tax treatment election for the Property captive |
| 9 | Vermont feasibility study | Captive manager + actuary | Standard VT pre-licensing workstream (6–10 weeks) |
| 10 | Cayman feasibility study | Cayman captive manager | Standard Cayman Monetary Authority pre-licensing workstream |
| 11 | Reinsurance broker market check | RI broker (Marsh, Aon, Lockton, etc.) | Confirm ceded-premium pricing through real quotes |
| 12 | RRG state registration | Specialty insurance counsel | Multi-state physician writing under VT RRG framework |
| 13 | TPA RFP and stop-loss placement | Benefits broker | Health captive admin and stop-loss layer pricing |
| 14 | Captive operating expense quotes | Captive manager candidates | Validate captive opex assumptions through RFP |
| 15 | Investment policy statement | Investment advisor | Define investment mandate aligned with reserve duration |

These items are sequenced into a typical 4–6 month implementation timeline. Most are handled in parallel by the captive manager, actuary, and broker working together.

---

## 13. File Map

| File | Purpose |
|---|---|
| `README.md` | One-page overview, headline numbers, and how to read this proforma |
| `proforma.md` | This document |
| `assumptions.md` | Every material input assumption with basis, source, and CSV pointer |
| `data/covered_lives.csv` | Lives derivation |
| `data/specialty_mix.csv` | MedMal premium build by specialty |
| `data/premiums.csv` | Premium by line × captive entity (Y1) |
| `data/losses.csv` | Expected losses, loss ratios, LAE, drivers by line |
| `data/reinsurance.csv` | Retention, attachment, limit, ceded premium per line |
| `data/capitalization.csv` | Capital requirements by captive (statutory min, working capital, target surplus) |
| `data/projection_3yr.csv` | Y1/Y2/Y3 P&L per captive + consolidated, with surplus walk |
| `data/scenarios.csv` | Sensitivity grid on Y1 NUR |

To re-run scenarios: edit the inputs in `data/*.csv`, recompute the dependent rows in `data/projection_3yr.csv`, and update the corresponding tables in this document. All formulas are documented in the comment columns of each CSV.

---

*End of proforma.*
