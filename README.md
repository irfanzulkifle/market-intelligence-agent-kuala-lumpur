# Market Intelligence Agent — Kuala Lumpur

Market research on the Kuala Lumpur short-term rental market, built end-to-end inside **Amazon Quick Suite** (Quick Spaces, Quick Research, Quick Chat Agents) for the capstone of Udacity's *Future AWS Agentic AI Business Professional* programme. **Passed on first submission, 21 October 2026.**

---

## Bottom line

Regulation, not price, is the binding constraint on a Kuala Lumpur short-term rental operator over the next four quarters. Price is already the market's clearing mechanism — listing price and occupancy are statistically unrelated (r = −0.011) — while operational quality pays (superhosts earn 80% more revenue per listing at almost identical nightly rates) and the next material cost shock is regulatory rather than competitive. The recommendation is therefore to compete on operational quality and regulatory readiness, hold rate discipline rather than discount, and treat the semi-professional portfolio band as the segment at risk. Confidence is **High** for the pricing and quality findings, **Medium** for the regulatory and supply-consolidation findings.

---

## The question

> Should a Kuala Lumpur short-term rental operator compete on **price**, on **operational quality**, or on **regulatory readiness** over the next four quarters — and which of those three levers does the evidence actually support?

Deliberately framed as a choice between levers rather than a market-sizing question. A ~300-listing sample cannot size a market, and a market-size number would not change anyone's behaviour. A lever decision can be acted on this quarter and can be falsified by the evidence — which is what makes it worth researching.

## Approach

| Step | What was done |
|---|---|
| **Data** | Public Kaggle dataset (AirROI APAC short-term rental data), downloaded in its original format and loaded unchanged into a Quick Space — 303 Kuala Lumpur listings, 202 hosts, 3,557 monthly observations, February 2025 to January 2026 |
| **Knowledge** | Six precomputed CSVs plus the source dataset, loaded as the agent's internal knowledge source (seven files, all indexed before the agent went live) |
| **Agent** | `Market Intelligence Agent – Kuala Lumpur` — a seven-part output contract in its instructions (objective and scope, 3–5 insights, per-insight confidence, ≥2 limitations, strategic implications, ≥2 non-conclusions, 5–7 sentence leadership summary) |
| **Research** | Quick Research across four workstreams — competitor landscape, pricing, market growth, regional dynamics — 51 sources retained, research plan revised twice before execution |
| **Analysis** | Dataset findings and external findings compared side by side, with agreement, disagreement and definitional gaps recorded explicitly |
| **Reliability** | Per-insight scoring on source quality, cross-source consistency and timeliness, plus a limitations register |
| **Brief** | 3,409-word research brief: 9 sections, 5 appendices, 4 tables, 11 images, every figure traceable to `data/` |

The division of labour was deliberate: **the agent synthesised, it did not calculate.** Every aggregate was computed in Python before the agent saw it, so no number in the brief originates from a language model. Each one can be recomputed from the CSVs in `data/`.

## What the evidence shows

| # | Insight | Evidence | Confidence |
|---|---|---|---|
| 1 | **Kuala Lumpur is a value market, and the gap is widening** — ADR of USD 45.15 against a peer median of USD 56.80, tenth of eighteen regional markets | Dataset ADR flat at USD 45.15 while KL hotel ADR rose 42% to MYR 393.4 in Q1 2026 | High |
| 2 | **Demand converts on quality, not on price** — ADR and occupancy are uncorrelated (r = −0.011) | Superhosts: 24% occupancy and USD 4,639 revenue per listing versus 14% and USD 2,575 for non-superhosts, on ADRs of 45.80 and 44.40 | High |
| 3 | **The next cost shock is regulatory, and it is regressive by host size** | 6% rental service tax applies only above an RM 1 million registration threshold, while Penang-style per-unit licensing at RM 2,850/unit/year equals ~20% of the median KL listing's gross revenue — a fixed cost that hits small operators hardest | Medium |
| 4 | **Supply is consolidating and the casualty is the semi-professional middle** | Market-wide active units fell ~29% year on year while revenue rose ~110%; in the sample the mid band (35 listings) earns 21% less per listing than the other three bands combined | Medium |

Full argument, evidence and "why it matters" for each: [`BRIEF.md`](BRIEF.md).

## Where the sources disagree — and why that is the finding

The most decision-relevant output was not a number both sources agreed on, but the places they contradicted each other:

- **Occupancy: 19% in the dataset versus 57–59% market-wide.** A three-fold gap is a measurement-definition problem, not a market signal. The brief reports both, names the likely cause (occupied nights over available nights versus over calendared nights) and refuses to average them.
- **Price direction: dataset ADR flat for twelve months while hotel ADR rose 42%.** Reported as a relative-position finding rather than a price-trend finding.
- **Supply: 303 listings in the sample against roughly 20,000–24,000 active market-wide.** Absolute market share is therefore not computable, and no attempt was made.

## What this analysis does not establish

These are boundary conditions on the conclusions, not caveats attached to them:

- **It does not size the market or estimate market share.** The sample supports within-sample comparison and relative peer position only; the confidence intervals on absolute levels are too wide to act on.
- **It does not rank Kuala Lumpur against the eighteen peers in absolute terms.** The benchmark holds inside that peer set, for the observation window February 2025 to January 2026. A different peer set or a longer window could reorder the middle of the table.
- **It does not establish causality.** Quality correlates with occupancy; the dataset cannot separate quality from location, listing age or host marketing spend, so "improve quality and occupancy follows" is a hypothesis, not a measured effect.
- **It does not forecast the regulatory outcome.** The direction of travel (licensing, per-unit fees, tax thresholds) is well sourced; the timing and the final fee schedule are not.

## Repository map

```
BRIEF.md                    The research brief (Markdown, reads well on GitHub; 9 sections, 5 appendices)
docs/
  Market_Intelligence_Brief_Kuala_Lumpur.docx   Same brief, formatted (11 images, 4 tables)
  Market_Analysis_Kuala_Lumpur.md / .docx       Comparative analysis: dataset vs external evidence
  Reliability_and_Confidence_Assessment.md/.docx Confidence scoring and limitations register
  PROJECT_REVIEW.md                             Grading outcome and the improvements it suggested
data/
  KL_listings_303.csv            Listing-level extract, 303 rows x 24 columns
  KL_segment_summary.csv         Metrics by host-portfolio band
  KL_peer_benchmark_18_markets.csv  ADR, occupancy and RevPAR across 18 APAC markets
  KL_monthly_market_series.csv   Monthly ADR, occupancy and revenue
  KL_correlations.csv            Pairwise correlations, including ADR vs occupancy
charts/                      Three figures (matplotlib), computed from data/
screenshots/                 Thirteen evidence screenshots: dataset download, Space setup, agent configuration,
                             Quick Research plan and sources, knowledge binding, share state
```

## How the figures were produced

Every number in the brief is computed from the tables in `data/`, which are published here so each figure can
be re-derived independently rather than taken on trust. The three charts were regenerated from that extract and
compared against the versions in the brief before publication; the comparison was identical, figure by figure.

Analysis and document assembly were done with Python locally. That code is not published — the repository is
kept to the research itself: the brief, the underlying tables, the charts and the console evidence. The Quick
Suite steps (Space upload, agent instructions, Quick Research plan) are console work, not scripted, and are
documented with screenshots in `BRIEF.md` section 3 and Appendix D.

## Data, licence and attribution

- **Written analysis and documents**: MIT, see [`LICENSE`](LICENSE).
- **Market data**: derived from the AirROI APAC short-term rental dataset published on Kaggle under **CC BY-NC 4.0** — attribution required, **non-commercial use only**. The CSVs in `data/` inherit that licence. See [`data/README.md`](data/README.md).
- **External signals** (tourism arrivals, hotel performance, licensing rules, tax thresholds) are cited in the brief with their sources and are reproduced as short quotation, not as redistributed data.
- **Screenshots** show a shared Udacity lab environment for Amazon Quick Suite; the lab does not persist after the programme, so the console is not reproducible, but the recorded state is.

## Review outcome

Graded **Passed** on attempt 1 (21 October 2026). The reviewer endorsed the objective, scope, approach, insights, confidence assessment, limitations, strategic implications and leadership summary, and asked for two framing changes for future work: state non-conclusions as **explicit boundary conditions** rather than disclaimers, and put the **leadership summary at the top** of the brief. Both are implemented in this README — the Bottom line section above, and the boundary-conditions section rather than a list of caveats. Notes and the full refinement list: [`docs/PROJECT_REVIEW.md`](docs/PROJECT_REVIEW.md).
