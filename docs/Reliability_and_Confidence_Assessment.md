# Reliability and Confidence Assessment — Kuala Lumpur STR Intelligence

Companion to the Market Intelligence Brief. Its purpose is to make every claim in that brief
auditable: what it rests on, how strong that foundation is, and what would overturn it.

This is the control against hallucinated intelligence. Each insight carries a confidence rating on four
criteria — source quality, consistency across sources, timeliness, and an overall rating — and the
ratings are deliberately heterogeneous. A brief where everything is High confidence is a brief that has
not been examined.

## 1. Confidence by insight

### Insight 1 — Kuala Lumpur is a value market and the gap is widening

- Source quality: High. The hotel rate of RM 393.4 comes from the Tourism Malaysia hotel survey for
  Q1 2026, a government statistical release; the STR rate of USD 45.15 is a full-sample median computed
  from 303 listings.
- Consistency: High. The two series are independent and diverge in the same direction — hotel rates up
  42%, STR rates flat.
- Timeliness: High. Q1 2026 against a trailing twelve-month window ending ~Q1 2026.
- Overall: High.

### Insight 2 — Demand converts on quality, not price

- Source quality: High. Computed on 298 observations with a populated superhost flag; the correlation
  uses the full 303-listing sample.
- Consistency: High. Two independent measurements agree: the ADR–occupancy correlation is −0.011, and
  the superhost comparison shows an 80% revenue premium at a 3% rate difference.
- Timeliness: High.
- Overall: High.

### Insight 3 — The next cost shock is regulatory and regressive by host size

- Source quality: Medium to High. MOTAC announcements, RMCD guidance and the KPMG tax analysis are
  primary or near-primary. The 0% licensing coverage figure, however, comes from a commercial tracker
  (Airbtics, March 2026) because Malaysia publishes no register of licensed STR operators.
- Consistency: Medium. The licensing figure is single-source, and the RM 2,850 per unit precedent is
  Penang's by-law, not a Kuala Lumpur rate. It is used as an order-of-magnitude precedent, not a
  KL-specific cost.
- Timeliness: High. Announcements span August 2025 to January 2026.
- Overall: Medium.

### Insight 4 — Supply is consolidating and the semi-professional middle is the casualty

- Source quality: Medium. The internal half is strong (full-sample medians by band). The external half —
  listings −29%, revenue per listing +110% — comes from commercial trackers without a named primary
  source.
- Consistency: Low to Medium. The internal sample is fixed at roughly 300 listings by construction and
  cannot confirm a market-wide decline; the two sources therefore cannot corroborate each other on the
  direction of supply.
- Timeliness: High. August 2025 to August 2026.
- Overall: Medium.

## 2. Source inventory and quality tiers

The Quick Research run returned 51 sources. They fall into four tiers.

Strong, primary or near-primary: Tourism Malaysia statistics and hotel surveys; the Malaysian and
Chinese governments; RMCD (customs) on service and tourism tax; KPMG and PwC on tax treatment; MIDA on
the Johor–Singapore Special Economic Zone; MOTAC as reported by The Star; JLL and CoStar on hotel
performance; the ADB on regional STR regulation.

Useful but interested: Airbnb's own guidance on Malaysian by-laws and tax obligations. Used only for
descriptive rule statements, never for market performance.

Aggregators and commercial trackers: AirDNA and Airbtics. These are the only sources for the 0%
licensing figure and for the −29% / +110% supply pair. They are credible enough to report and not
credible enough to treat as fact — which is exactly why Insights 3 and 4 carry Medium confidence rather
than High.

Weak or off-target: Wikipedia for KLIA passenger volumes that MAHB publishes directly, and — more
telling — Singapore's urban planning authority appearing in the first twelve sources before the regional
comparison had even been planned. That last one is a precision failure of the research tool, not a
content error: the source is used correctly for Singapore's ban, but its early appearance shows the
sweep was broad before it was sharp.

## 3. The measurement conflict, stated plainly

Occupancy is the largest single measurement risk in this work, and it is not resolved — it is disclosed.

The dataset computes 19.2% as reserved nights divided by 365 calendar days. AirDNA and Airbtics report
57–59% for the same city in the same period, dividing by nights actually available. The threefold gap is
definitional. It is not a data error, and it must not be averaged, blended, or presented as a range.

The rule applied throughout: the 19% figure is used for comparisons across the eighteen peer markets,
because all eighteen are computed identically. It is not used as an industry occupancy benchmark, and no
insight in the brief depends on it being one.

Two further data defects were found and excluded rather than repaired:

- `ttm_adjusted_occupancy` is corrupt in the source file — 281 reserved days is reported as 0.000 — and
  was dropped entirely.
- The available-days field counts unbooked rather than blocked days (it correlates −1.000 with
  reservations), so it cannot be used to reconstruct a true availability denominator.

## 4. Known gaps

- No public register of licensed short-term rental operators exists for Kuala Lumpur. Compliance cannot
  be measured, only estimated by a third party.
- The sample is capped at roughly 300 listings per city. Host concentration figures are floors, and
  per-listing revenue for professional hosts is systematically understated.
- The 2026 demand picture rests on a single quarter of arrivals data (Q1 2026, −2.5% year on year).
  One quarter is a signal, not a trend.
- No unit-level cost data exists in the dataset, so margin impact is taken from the external estimate
  (15–20%) rather than modelled.
- Hotel performance is used as a benchmark for STR demand, which assumes substitutability that is
  plausible but untested in this data.

## 5. What would change our mind

| Signal | Threshold that would overturn the reading |
|---|---|
| Hotel ADR | Two consecutive quarters of decline, which would compress the STR discount and remove the value-position argument |
| Licensing coverage | A published MOTAC register showing material licensed coverage, which would remove the first-mover compliance advantage |
| Listing counts | A second independent tracker showing stable or rising active listings, which would break the consolidation thesis |
| STR rate series | A rising STR rate while hotel rates stall, which would restore pricing power |
| ADR–occupancy correlation | A negative correlation on a larger sample, which would revive the price lever |
| Arrivals | A second consecutive quarter of declining arrivals, which would move demand from risk to fact |

## 6. Standing caveats for any reader of this work

- Every figure in the brief is either recomputed from the sample or attributed to a dated external
  source. Nothing is quoted from memory.
- Where internal and external evidence conflict, both are reported and the weighting is stated. No
  conflict is silently resolved in favour of the more convenient number.
- Where evidence is insufficient, the brief says so rather than estimating. Market size, market share
  and forward revenue are the three places this applies.
- The intelligence supports a decision; it does not make one.
- Nothing here should be described as fact on the strength of a single source. The two Medium-confidence
  insights each rest on a commercial tracker, and are labelled accordingly.
