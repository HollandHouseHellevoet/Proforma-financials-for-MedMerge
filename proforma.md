# MedMerge Captive Insurance Program — Proforma Financial Model

**Prepared for:** MedMerge partners, investors, and physician group leadership
**Coverage scope:** Health benefits, Medical Malpractice (MedMal), Casualty, Property
**Structure:** 3 captive entities
**Population:** 2,500 surgeons + clinical staff + white-collar lives = **20,050 total covered lives**

> ⚠️ This proforma is a planning document. It is **not** an actuarial opinion, legal opinion, or tax opinion. Items requiring formal professional sign-off are flagged in §11 and §12. All figures derive from the CSV files in `data/`; tweak inputs there to re-run scenarios.

---

## 1. Executive Summary

| Metric | Year 1 | Year 3 | 3-Year Cumulative |
|---|---:|---:|---:|
| Gross Written Premium | **$262.9M** | $288.6M | $827.0M |
| Ceded Premium (reinsurance) | ($26.8M) | ($29.0M) | ($83.7M) |
| Net Earned Premium | $236.1M | $259.6M | $743.3M |
| Net Incurred Losses | ($172.1M) | ($189.5M) | ($542.2M) |
| Operating expenses + admin + tax | ($23.1M) | ($25.3M) | ($72.5M) |
| Investment Income | $3.5M | $11.5M | $22.1M |
| **Net Underwriting Result** | **$44.5M** | **$56.3M** | **$150.7M** |
| Captive Surplus (balance sheet) | $80.3M | $186.4M | — |

**Headline numbers:**
- **Initial capital injection:** $35.75M across all three captives
- **Year 1 underwriting profit retained on MedMerge balance sheet:** $44.5M
- **End-of-Year-3 captive surplus position:** $186.4M (~5.2× initial capital)
- **Estimated annual savings vs. fully-insured equivalent:** $45–90M depending on commercial market hardening (see §10)

The structural value driver is simple: **MedMerge today writes a $300M+ check every year for insurance and never sees that money again.** Under the captive structure, ~$45M of underwriting profit per year stops being someone else's revenue and becomes a MedMerge balance sheet asset, on top of investment income earned on accumulating reserves.

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
| 3 | **MedMerge Property Captive** | Property + Business Interruption on owned ASCs, clinics, equipment | **Cayman** | Short-tail, reinsurance-driven line. Cayman is cost-efficient for property/cat structures and offers fast licensing. |

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

### 4.3 Property Captive — $0.80M

| Component | Calc | Amount |
|---|---|---:|
| Property | TIV $300M × 0.20% | $0.60M |
| Business Interruption | 12-month BI on critical ASCs | $0.20M |
| **Subtotal** | | **$0.80M** |

**TIV is a placeholder.** A real Statement of Values for owned ASCs, clinics, and major equipment is required before binding. If MedMerge owns surgical centers in catastrophe-exposed regions (Florida, Texas Gulf, California earthquake zones), the rate on TIV doubles or triples and the property captive premium grows materially.

### 4.4 Program Total

**$262.91M** Year 1 GWP across all three captives.

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
| Property | $0.60M | 45% | $0.27M | $0.01M | Geographic concentration TBD |
| BI | $0.20M | 45% | $0.09M | $0.005M | Correlates with property |
| **TOTAL** | **$262.91M** | **68.9%** | **$181.02M** | **$9.30M** | |

### 5.1 Health — driver commentary

The 78% loss ratio assumes (a) claims continue to develop at 6.5% medical trend, (b) Rx specialty drugs (GLP-1s, autoimmune biologics, oncology) continue at ~10% trend, (c) the group's demographic profile is stable. Two large-claimant clusters in a single year (e.g., NICU + transplant + late-stage oncology in the same plan year) is the most common driver of an 88%+ year. The aggregate stop-loss at 125% caps the worst case.

### 5.2 MedMal — driver commentary

A 60% target loss ratio is **conservative on purpose.** MedMal IBNR develops over 7–10 years and severity is bimodal: most claims close under $250k, but the ~5% that go to verdict can break $5M. The mix here — Neuro, Spine, Ortho, General Surgery — is in the highest-severity quartile of physician practice. Captive math:

- Frequency: ~5 claims per 100 surgeons per year (250 reported claims/year for the group)
- Severity (closed-claim mean for this mix): ~$300k weighted average
- Frequency × severity ≈ $75M expected losses, matching the 60% LR ($74.9M)
- The $25M aggregate stop-loss caps a one-bad-year scenario; per-claim $500k retention caps individual severity

### 5.3 Property — driver commentary

Property captives the size of MedMerge's are dominated by **single-event risk**, not attritional losses. The 45% loss ratio assumption holds in any year without a cat event; a single ASC fire can blow through the entire annual premium. The reinsurance structure ($1M retention, $50M xs $1M cat tower) is what makes the captive viable at this premium scale.

### 5.4 Other Casualty — driver commentary

Cyber is the line to watch. Healthcare PHI breaches average $11M+ in total cost (incident response, regulatory, class action). The $700k cyber premium with $250k retention is appropriate for a group this size today, but cyber should be re-rated annually.

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
PROPERTY CAPTIVE — Per Risk + Cat
─────────────────────────────────────────────
                                 │ Reinsurer
              $50M xs $1M        │ cat / per-risk
              ──────────────────  ────────────
                                 │ CAPTIVE
              UP TO $1M / occ    │ retains primary

Property ceded: $0.20M (25.0% of GWP)
```

| Total ceded program | $26.77M | 10.2% of GWP |
|---|---:|---:|

⚠️ **All ceded premium ratios need a broker market check before bind.** The MedMal severity layer specifically may price meaningfully above the modeled $17.47M in today's market depending on reinsurer appetite for high-risk surgical specialty captives.

---

## 7. Capitalization

Source: `data/capitalization.csv`

| Captive | Domicile | Statutory Min | Y1 Working Capital | Y3 Target Surplus | Y1 P/S Ratio |
|---|---|---:|---:|---:|---:|
| Health Captive | Montana | $1.0M | $10.0M | $25.0M | 12.4 : 1 |
| Casualty Captive — MedMal pool | Vermont | (notional) | $22.5M | $67.5M | 4.8 : 1 |
| Casualty Captive — Other Casualty pool | Vermont | (notional) | $2.5M | $7.5M | 1.8 : 1 |
| Casualty Captive — total entity | Vermont | $1.0M | **$25.0M** | **$75.0M** | 4.5 : 1 |
| Property Captive | Cayman | $0.25M | $0.75M | $1.5M | 0.8 : 1 |
| **TOTAL INITIAL CAPITAL** | | **$2.25M** | **$35.75M** | **$101.5M** | |

### Sizing logic

- **Statutory minimums** are regulatory floors (MT, VT, Cayman). They are far below operating capital needs and are not the binding constraint.
- **Working capital Y1** is what MedMerge actually injects on day one. It needs to cover (a) reserves accumulating before claims pay out, (b) volatility around expected losses, and (c) regulatory comfort margin.
- **Target surplus by Y3** reflects underwriting profit accretion plus investment income. The captives largely **self-fund** their growth — initial capital is leveraged, not topped up annually.

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
| Gross Written Premium | $0.80M | $0.82M | $0.85M |
| Ceded Premium | ($0.20M) | ($0.21M) | ($0.21M) |
| Net Earned Premium | $0.60M | $0.62M | $0.64M |
| Net Incurred Losses | ($0.36M) | ($0.37M) | ($0.38M) |
| LAE | ($0.02M) | ($0.02M) | ($0.02M) |
| Captive Operating Expenses | ($0.20M) | ($0.21M) | ($0.21M) |
| Premium Tax (Cayman) | $0.00M | $0.00M | $0.00M |
| Investment Income | $0.04M | $0.05M | $0.06M |
| **Net Underwriting Result** | **$0.06M** | **$0.07M** | **$0.08M** |

The Property Captive runs thin by design — the strategic rationale is **control of the cat tower** and access to alternative reinsurance markets, not underwriting profit. If MedMerge's owned-property footprint grows, premium scales and the captive becomes more material.

### 8.4 Consolidated 3-Year Summary

| Line Item | Year 1 | Year 2 | Year 3 |
|---|---:|---:|---:|
| Gross Written Premium | $262.91M | $275.42M | $288.62M |
| Ceded Premium | ($26.77M) | ($27.87M) | ($29.03M) |
| Net Earned Premium | $236.14M | $247.55M | $259.59M |
| Net Incurred Losses | ($172.08M) | ($180.58M) | ($189.55M) |
| LAE + TPA + Opex + Tax | ($23.07M) | ($24.15M) | ($25.29M) |
| Investment Income | $3.54M | $7.05M | $11.54M |
| **Net Underwriting Result** | **$44.52M** | **$49.87M** | **$56.29M** |
| Cumulative NUR | $44.52M | $94.39M | **$150.69M** |
| Beginning Surplus | $35.75M | $80.27M | $130.14M |
| **Ending Surplus** | **$80.27M** | **$130.14M** | **$186.44M** |

**The 3-year story:** $35.75M of injected capital becomes ~$186M of MedMerge-controlled balance-sheet assets, with cumulative underwriting profit of $150.7M — before any commercial-market savings comparison.

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
| Property | Cayman | $0.60M | $0.00M |
| **TOTAL** | | $236.14M | **$0.73M** |

Total program premium tax of $0.73M is roughly **0.3% of net premium** — meaningfully lower than commercial-fronted alternatives that incur state premium tax on the full GWP in every state of risk.

---

## 10. The Investor Story — P&L Expense → Balance Sheet Asset

This section is the one to walk physician group leadership and investors through.

### 10.1 Today: Fully Insured (assumed current state)

| Line | Estimated Commercial Premium |
|---|---:|
| Health (fully-insured large-group medical + Rx) | ~$145M |
| MedMal (commercial mature claims-made, this specialty mix) | ~$156M |
| Property (commercial standalone) | ~$1.0M |
| Other Casualty (commercial program) | ~$6.25M |
| **Total annual fully-insured premium** | **~$308M** |

That $308M leaves MedMerge's books **permanently** every year. It's expense — gone. Whatever underwriting profit and investment income those carriers earn on the float, MedMerge does not see.

### 10.2 Tomorrow: Captive Structure

| Component | Year 1 |
|---|---:|
| Premium contributed by operating company | $262.91M |
| Of which: ceded to reinsurance (gone) | ($26.77M) |
| Of which: paid as losses (gone) | ($172.08M) |
| Of which: paid as admin/opex/tax (gone) | ($23.07M) |
| **Of which: retained as captive surplus + investment income** | **$44.52M** |

**Two simultaneous wins:**

1. **Premium spend drops** from $308M to $263M — a $45M reduction that flows straight to MedMerge operating margin (the captive prices ~15–20% below commercial)
2. **Of the $263M MedMerge does spend, $44.5M circles back** as captive underwriting profit + investment income — sitting on MedMerge's balance sheet rather than a carrier's

### 10.3 The Three-Year Picture

| | Y1 | Y2 | Y3 | 3-yr cumulative |
|---|---:|---:|---:|---:|
| Premium savings vs. fully insured | ~$45M | ~$48M | ~$51M | **~$144M** |
| Captive net underwriting result (added to surplus) | $44.5M | $49.9M | $56.3M | **$150.7M** |
| **Total annual value captured** | **~$90M** | **~$98M** | **~$107M** | **~$295M** |
| Captive surplus position (cumulative) | $80.3M | $130.1M | $186.4M | |

Over three years, MedMerge captures roughly **$295M of value** that would otherwise have been commercial carrier and reinsurer profit, and ends Year 3 with a **$186M balance-sheet position** built from $35.75M of initial capital — a 5.2× return on injected capital.

### 10.4 Strategic, non-financial benefits

- **Risk-management feedback loop** — paying your own claims sharpens patient-safety and clinical-quality programs in a way carrier programs never do
- **Coverage flexibility** — captive can add coverages that aren't commercially available (cyber sublimits, communicable disease, regulatory defense, integration costs)
- **Tail liability control** — MedMerge controls how MedMal tails are managed at retirement, practice change, or M&A
- **M&A enabler** — when MedMerge acquires another physician group, the captive can underwrite the new lives immediately, eliminating commercial broker re-marketing friction
- **Investor exit optionality** — captive surplus is a real asset that can be distributed, reinvested, or used as collateral

### 10.5 What can go wrong (honest answer)

| Risk | Probability | Impact | Mitigant |
|---|---|---|---|
| Adverse MedMal claim year (severity) | Medium | Aggregate stop-loss caps captive loss at $50M | RI tower; conservative 60% LR target |
| Health large-claimant cluster | Medium | Aggregate stop-loss caps at 125% of expected | $25M aggregate layer; specific stop-loss removes catastrophic claimant exposure |
| Reinsurance market hardening at renewal | Medium | Ceded premium ratios rise 20–40% | Multi-year RI placements where possible; build captive credibility for better terms |
| Pandemic / systemic medical event | Low–Medium | Potential aggregate trigger | Aggregate stop-loss; communicable disease exclusions reviewed annually |
| Specialty roster shift (more high-risk) | Low | MedMal premium under-priced | Annual re-rating; mid-year endorsement mechanism |
| Capital injection insufficient | Low | Regulator requires top-up | Conservative Y1 sizing; surplus accretes from underwriting profit |

The structure is built so a **single bad year is survivable** — the worst-case scenario in §13 (`data/scenarios.csv`) still produces positive consolidated NUR.

---

## 11. Sensitivity Analysis

Source: `data/scenarios.csv`

| Scenario | Y1 Net Underwriting Result | Δ vs Base | Commentary |
|---|---:|---:|---|
| **Base case** (target loss ratios) | **$44.5M** | — | Plan-of-record |
| Favorable (LRs −10pts each line) | $71.7M | +$27.2M | Strong claim emergence |
| Adverse (LRs +10pts each line) | $17.4M | ($27.2M) | **Still profitable** — margin holds |
| Severe MedMal shock (LR +20pts) | $29.6M | ($15.0M) | Single bad MedMal year; aggregate stop-loss caps further downside |
| Severe Health shock (LR +15pts) | $28.8M | ($15.7M) | Aggregate stop-loss caps worst case at 125% |
| Trend acceleration (+2pts medical) | $40.6M | ($4.0M) | One-year impact only; re-rate at renewal |
| Compound stress (all adverse + trend) | $13.4M | ($31.1M) | **Still positive** — investment income + structural margin |
| Property cat event (10× losses) | $41.3M | ($3.2M) | Per-occurrence RI caps captive at $1M retention |

**The key insight from the sensitivity grid:** the program is structurally profitable in every modeled scenario, including compound stress. The reinsurance towers do their job — they convert tail-severity exposure into a manageable, capped retention.

---

## 12. Areas Requiring Formal Sign-Off

The following items must be formally reviewed and certified by qualified professionals **before binding any coverage**:

| # | Area | Discipline | Why it matters |
|---|---|---|---|
| 1 | Health IBNR + reserve adequacy | Credentialed health actuary | Required by MT regulator and auditor; ensures captive holds enough reserves |
| 2 | MedMal loss reserves + premium adequacy + capital adequacy | Credentialed P&C actuary (FCAS) | Required by VT regulator; signed Statement of Actuarial Opinion (SAO) at year-end |
| 3 | Specialty roster verification | Captive manager + broker | Replace the placeholder distribution in `data/specialty_mix.csv` with the actual surgeon census; MedMal premium shifts materially |
| 4 | Property Statement of Values | Risk engineer / captive manager | Replace placeholder $300M TIV with verified asset-by-asset SOV |
| 5 | Existing MT cell starting surplus | Captive manager | Confirm whether $10M Y1 health working capital is incremental or replaces existing surplus |
| 6 | Workers Compensation inclusion | Risk manager + WC counsel | Decision: include in Casualty captive (state-by-state regulatory analysis required) or leave outside the program |
| 7 | IRC §831 risk-distribution analysis | Captive tax counsel | Required if seeking captive insurance company tax treatment under §831 |
| 8 | Cayman §953(d) election | Tax counsel | Determines U.S. tax treatment of Property Captive |
| 9 | Vermont feasibility study | Captive manager + actuary | Required by VT regulator before licensing the new Casualty captive (typically 6–10 weeks) |
| 10 | Cayman feasibility study | Cayman captive manager | Required by Cayman Monetary Authority before licensing the Property captive |
| 11 | Reinsurance broker market check | RI broker (Marsh, Aon, Lockton, etc.) | Every ceded-premium assumption needs real quotes; MedMal severity layer is most price-sensitive |
| 12 | RRG state registration | Specialty insurance counsel | If VT RRG path chosen, register in every state where physicians practice |
| 13 | TPA RFP and stop-loss broker placement | Benefits broker | Health captive admin and stop-loss layer pricing |
| 14 | Captive operating expense quotes | Captive manager candidates | $750k / $1.5M / $200k Y1 opex assumptions need RFP validation |
| 15 | Investment policy statement | Investment advisor | $4% yield assumption requires an actual investment mandate appropriate to reserve duration |

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
