# Assumptions Log

Every material assumption used in the MedMerge captive proforma. Each entry tells you the value used, the basis/benchmark, the file and column that controls it, and how to override.

---

## 1. Covered Population

| # | Assumption | Value | Basis | Controlled in |
|---|---|---|---|---|
| 1.1 | Surgeon count | 2,500 | User input | `data/covered_lives.csv` |
| 1.2 | Employees per surgeon | 3.0 | User-stated MedMerge convention (1 surgeon supports ~3 clinical & support staff) | `data/covered_lives.csv` |
| 1.3 | Lives multiplier (employees → covered lives) | 2.30 | User-stated MedMerge convention; consistent with mid-sized employer dependent ratios | `data/covered_lives.csv` |
| 1.4 | White collar lives | 2,800 (already total covered lives) | User direction confirmed in clarification | `data/covered_lives.csv` |
| 1.5 | **Total covered lives** | **20,050** | Derived: 7,500 × 2.30 + 2,800 | `data/covered_lives.csv` |

## 2. Specialty Mix (MedMal)

| # | Assumption | Value | Basis | Controlled in |
|---|---|---|---|---|
| 2.1 | ER share | 25% | Estimated; **PLACEHOLDER — replace with actual roster** | `data/specialty_mix.csv` |
| 2.2 | Orthopedic share | 20% | Estimated **placeholder** | `data/specialty_mix.csv` |
| 2.3 | General Surgery share | 15% | Estimated **placeholder** | `data/specialty_mix.csv` |
| 2.4 | Interventional Pain share | 10% | Estimated **placeholder** | `data/specialty_mix.csv` |
| 2.5 | Dermatology share | 10% | Estimated **placeholder** | `data/specialty_mix.csv` |
| 2.6 | Spine share | 8% | Estimated **placeholder** | `data/specialty_mix.csv` |
| 2.7 | ENT share | 7% | Estimated **placeholder** | `data/specialty_mix.csv` |
| 2.8 | Neurosurgery share | 5% | Estimated **placeholder** | `data/specialty_mix.csv` |

## 3. Premium Rates

| # | Assumption | Value | Basis | Controlled in |
|---|---|---|---|---|
| 3.1 | Health PMPM (group medical + Rx) | $550 | Large-group self-funded benchmark for healthcare worker population (range $525–$650 PMPM); medical workers tend to higher utilization | `data/premiums.csv` |
| 3.2 | MedMal mature claims-made rates per surgeon (captive) | $14k–$130k by specialty | Priced ~15–20% under commercial market consistent with MPL Association (MPLA) reported physician rates 2024–2026; captive efficiency comes from removing commercial profit/expense load | `data/specialty_mix.csv` |
| 3.3 | GL per physician | $800/year | Standard physician group GL benchmark | `data/premiums.csv` |
| 3.4 | EPLI rate | ~$117/employee | Allocated against ~10,300 employees | `data/premiums.csv` |
| 3.5 | D&O premium | $750k flat | Mid-market healthcare D&O placement | `data/premiums.csv` |
| 3.6 | Cyber rate | $35/life | PHI exposure; current market rates 2025–2026 | `data/premiums.csv` |
| 3.7 | Auto premium | $350k | Small commercial fleet | `data/premiums.csv` |
| 3.8 | Property TIV | ~$3.315B (87 facilities: 27 micro hospitals at ~$45M each, 50 ASCs at ~$22M each, 10 POSHs at ~$100M each) | Built from MedMerge-stated facility counts and build costs plus standard healthcare ratios (equipment ~25-35% of build, contents ~10-15% of build, 12-month BI scaled to facility revenue) | `data/premiums.csv` |
| 3.9 | Property rate on TIV | Blended 0.193% (0.20% micro hospitals; 0.18% ASCs and POSHs) | Healthcare property benchmark for portfolios at this scale; geographic concentration TBD will refine final rate | `data/premiums.csv` |

## 4. Loss Ratios

| # | Assumption | Value | Basis | Controlled in |
|---|---|---|---|---|
| 4.1 | Health target loss ratio | 78% | Large self-funded plans typically 75–82% | `data/losses.csv` |
| 4.2 | MedMal target loss ratio | 60% | Conservative for long-tail; allows for full IBNR development and prudent claim recognition | `data/losses.csv` |
| 4.3 | GL loss ratio | 55% | Industry mid-market benchmark | `data/losses.csv` |
| 4.4 | EPLI loss ratio | 50% | Defense-heavy line; loss ratio understates true cost | `data/losses.csv` |
| 4.5 | D&O loss ratio | 40% | Low frequency; severity-driven | `data/losses.csv` |
| 4.6 | Cyber loss ratio | 55% | Hardening market with rising trend | `data/losses.csv` |
| 4.7 | Auto loss ratio | 55% | Standard commercial auto | `data/losses.csv` |
| 4.8 | Property loss ratio | 45% | Pure premium target for non-cat exposure | `data/losses.csv` |
| 4.9 | LAE — MedMal | 12% of loss | Reflects defense-heavy nature | `data/losses.csv` |
| 4.10 | LAE — other casualty | 8–20% of loss by line | Standard industry loadings | `data/losses.csv` |

## 5. Reinsurance / Retention

| # | Assumption | Value | Basis | Controlled in |
|---|---|---|---|---|
| 5.1 | Health specific stop-loss | $500k per life, unlimited above | Standard for groups >5k lives | `data/reinsurance.csv` |
| 5.2 | Health aggregate stop-loss | 125% of expected, $25M limit | Thin layer due to group size and credibility | `data/reinsurance.csv` |
| 5.3 | MedMal specific XOL | $500k per claim, $25M xs $500k | Captive retains primary; reinsurance fronts the severity tower | `data/reinsurance.csv` |
| 5.4 | MedMal aggregate stop-loss | $50M annual aggregate, $25M limit | Provides annual ceiling on captive exposure; layers with specific tower | `data/reinsurance.csv` |
| 5.5 | Other casualty XOL | $250k per occurrence, $5M xs $250k | Standard mid-market casualty tower | `data/reinsurance.csv` |
| 5.6 | Property per-risk tower | $1M per occurrence, $24M xs $1M | Covers any single facility (ASC / micro hospital / most POSH exposure) at full insurable value | `data/reinsurance.csv` |
| 5.6a | Property cat / excess tower | $25M attachment, $200M xs $25M | Excess layer above per-risk; sized comfortably above largest POSH valuation | `data/reinsurance.csv` |
| 5.6b | Property aggregate stop-loss | $10M annual aggregate, $25M xs $10M | Hard ceiling on captive's annual property losses across all 87 facilities | `data/reinsurance.csv` |
| 5.7 | Ceded premium ratios | 6–25% of GWP by line | Reinsurance pricing benchmark; **needs broker market check before bind** | `data/reinsurance.csv` |

## 6. Operating Expenses

| # | Assumption | Value | Basis | Controlled in |
|---|---|---|---|---|
| 6.1 | Health TPA / claims admin | 8.0% of GWP | Negotiated TPA fees for >20k-life self-funded plan | `data/projection_3yr.csv` |
| 6.2 | Health captive operating expenses | $750k Y1 | Captive manager + actuary + audit + regulator (MT) | `data/projection_3yr.csv` |
| 6.3 | Casualty captive operating expenses | $1.5M Y1 | Higher fees for MedMal claims handling, actuarial reserving, audit | `data/projection_3yr.csv` |
| 6.4 | Property captive operating expenses | $400k Y1 | Cayman cell scaled for material 87-facility book; manager + audit + actuary + engineering survey | `data/projection_3yr.csv` |
| 6.5 | Captive opex trend | 3.0%/year | General inflation | `data/projection_3yr.csv` |
| 6.6 | Health TPA trend | 5.2%/year | TPA fees rise with claims volume + inflation | `data/projection_3yr.csv` |

## 7. Premium Tax / Regulatory

| # | Assumption | Value | Basis | Controlled in |
|---|---|---|---|---|
| 7.1 | Montana captive premium tax | 0.4% on net premium | MT statute; one of the lowest in U.S. | `data/projection_3yr.csv` |
| 7.2 | Vermont captive premium tax | 0.214% blended on net premium | VT sliding scale (0.38% on first $20M, 0.285% next $20M, 0.19% next $20M, 0.072% next $20M, 0.024% above $80M) | `data/projection_3yr.csv` |
| 7.3 | Cayman premium tax | 0% | No premium tax in Cayman | `data/projection_3yr.csv` |
| 7.4 | Federal Excise Tax (FET) on offshore RI | Not modeled | Cayman captive may incur 1% FET on direct premium from US risks unless 953(d) election filed | flag for tax counsel |

## 8. Investment Income

| # | Assumption | Value | Basis | Controlled in |
|---|---|---|---|---|
| 8.1 | Investment yield | 4.0% | Short-duration high-grade fixed income benchmark 2025–2026 | `data/projection_3yr.csv` |
| 8.2 | Avg invested assets — Health Captive | Y1 $25M → Y3 $67M | Surplus + reserves; reserves modest given short-tail nature of health | `data/projection_3yr.csv` |
| 8.3 | Avg invested assets — Casualty Captive | Y1 $63M → Y3 $220M | MedMal long-tail builds reserves materially over time | `data/projection_3yr.csv` |
| 8.4 | Avg invested assets — Property Captive | Y1 $1M → Y3 $1.5M | Small invested base | `data/projection_3yr.csv` |

## 9. Capitalization

| # | Assumption | Value | Basis | Controlled in |
|---|---|---|---|---|
| 9.1 | Health Captive working capital Y1 | $10M | ~8% of net retained premium for short-tail line; **incremental funding only** if existing MT captive already holds surplus | `data/capitalization.csv` |
| 9.2 | Casualty Captive working capital Y1 | $25M | Sized for long-tail MedMal: $22.5M MedMal pool + $2.5M short-tail casualty pool | `data/capitalization.csv` |
| 9.3 | Property Captive working capital Y1 | $5.0M | Sized for 87-facility / $3.3B TIV portfolio with $1M per-occurrence and $10M annual aggregate retentions; supports collateral capacity for facility capex | `data/capitalization.csv` |
| 9.4 | Total initial capital injection | $40.0M | Sum of working capital across all 3 captives | `data/capitalization.csv` |
| 9.5 | Premium-to-surplus target — short-tail | 5:1 maturing | Health and short-tail casualty | `data/capitalization.csv` |
| 9.6 | Premium-to-surplus target — long-tail (MedMal) | 1.5:1 maturing | MedMal requires substantially more capital backing | `data/capitalization.csv` |

## 10. Trend Assumptions (Year-over-Year)

| # | Assumption | Value | Basis | Controlled in |
|---|---|---|---|---|
| 10.1 | Medical / Rx trend | 6.5% | KFF / Mercer / industry benchmarks 2025–2026 (medical 6.0%, Rx 9–11% blended) | `data/projection_3yr.csv` |
| 10.2 | MedMal rate trend | 3.0% | Reflects modest hardening but captive setting limits trend pass-through | `data/projection_3yr.csv` |
| 10.3 | Other casualty trend | 3.0% | Blended | `data/projection_3yr.csv` |
| 10.4 | Property trend | 3.0% | Hard market moderating | `data/projection_3yr.csv` |
| 10.5 | Loss ratio trend | Held flat at target | Assumes pricing keeps pace with loss trend | `data/losses.csv` |

## 11. Inputs to Validate During Implementation

These are confirmed through standard professional workstreams during the typical 4–6 month implementation:

1. **Specialty roster** — confirm actual surgeon-by-specialty census; MedMal premium is most sensitive to this single input
2. **Property SOV** — formal asset-by-asset Statement of Values across the 87-facility portfolio refines the working TIV estimate
3. **Existing Montana cell starting surplus** — captive manager confirms whether existing surplus carries forward or Y1 funding is fully incremental
4. **Workers Compensation scope** — risk manager + WC counsel decide on inclusion in Casualty captive
5. **Actuarial opinions** — health IBNR certification and MedMal Statement of Actuarial Opinion are standard regulator requirements
6. **Feasibility studies** — standard Vermont and Cayman pre-licensing workstreams (6–10 weeks each)
7. **Tax opinion** — standard IRC §831 risk-distribution opinion for multi-line captive structures
8. **Reinsurance broker market check** — every ceded-premium ratio confirmed via real quotes from RI brokers
9. **State licensing for MedMal RRG** — Vermont RRG framework registers in every state where physicians practice
10. **§953(d) election** — tax counsel evaluates U.S. tax treatment election for the Cayman property captive

## 12. Out-of-Scope (not in this proforma)

- Reserve discounting / Schedule P–style payment patterns
- Tax expense (federal income tax) — proforma shows pre-tax NUR; assumes captive election or pass-through
- State-by-state premium tax allocation
- Detailed asset allocation / investment policy
- Implementation timeline / domicile licensing project plan
