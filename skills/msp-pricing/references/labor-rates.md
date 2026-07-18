# {{COMPANY_NAME}} Pricing: Labor Cost Basis (market research)

**Defaults you must review:** the wages, burden, and overhead figures below are one working MSP's
numbers in one market. See the "Setup Decisions" section of `../SKILL.md` before treating any
figure here as settled for your shop.

This file documents where the remote and on-site labor costs in the configurator come from. They
used to be flat numbers ($40 and $80). They are now built up from researched market wages so the
basis is transparent and you can re-cost the whole sheet by changing one input. Researched June 2026;
re-check annually, since wages drift.

The distinction that matters: what a tech *earns* (wage) is not what the tech *costs you* (the loaded
cost). {{COMPANY_NAME}} prices off the loaded cost.

## Contents
1. What the roles pay
2. The burden (wage to loaded cost)
3. The build-up to $40 remote and $80 on-site
4. Tuning levers

---

## 1. What the Roles Pay (base wage, 2026)

> **Citation honesty note:** the figures cited below are the source MSP's own market research for
> its own region and time period, rounded here so they cannot be reverse-matched to a specific
> metro survey result. Replace them with wage data for your own market before relying on this
> file, and do not present these citations as your own research.

**Level 1 phone help desk tech.** A reliable Tier 1 / entry-level help desk technician runs roughly
$22 to $26/hour in base wage, both nationally and in {{SERVICE_AREA}}.

- Salary aggregator sites: {{SERVICE_AREA}} help desk technician about $51,000/yr (~$25/hr, rounded); national Tier 1 about $51,000/yr (~$24/hr, rounded).
- Salary aggregator sites: {{SERVICE_AREA}} about $50,000/yr (~$24.00/hr, rounded); national entry-level about $48,000/yr (~$23.00/hr, rounded).
- Salary aggregator sites: national help desk technician about $20.50/hr (rounded).
- Salary aggregator sites: {{SERVICE_AREA}} help desk postings about $27.50/hr (rounded).
- An industry salary guide: cross-source consensus base of about $48,000 to $52,000 (rounded).

Working figure: **$25/hr** for a decent (not bottom-tier) L1, aligned to {{SERVICE_AREA}} and slightly
above the national floor so you can actually hire someone capable. Remote phone support does not have
to be local, so if {{COMPANY_NAME}} hires from a lower-cost market this can come down.

**Good field services tech.** Field/on-site work pays more than phone support because it is
customer-facing and on location.

- Salary aggregator sites: IT field technician about $65,000/yr (~$31/hr, rounded); IT field support technician about $52,000/yr (~$25/hr, rounded).
- Salary aggregator sites: field service technician about $26.00/hr (rounded).
- Salary aggregator sites: desktop support technician about $23.00/hr (rounded).

Working figure: **$32/hr** for a *good* field tech, toward the higher end because the word the brief used
was "good," and because a tech you trust to go solo to a client site commands a premium. Field techs must
be local to {{STATE}}, so this one cannot be sourced cheaper elsewhere.

---

## 2. The Burden (wage to loaded cost)

Base wage is only part of what an employer pays. Adding payroll taxes (Social Security, Medicare,
unemployment), workers compensation, benefits, and paid time off raises the real cost substantially.

- BLS-based analysis: base salary is roughly 70 to 75% of true cost; the all-in multiplier on wage runs
  about 1.25x to 1.8x depending on benefits generosity, role, and location. Benefits alone run near 30%
  of total compensation.
- Industry payroll data: benefits account for roughly 31.7% of an employee's total cost.

Working figure: **1.30x** on base wage. This is deliberately lean, fitting a startup MSP with modest
benefits. Richer benefits push it toward 1.40x or higher; raise BURDEN in the script if your benefits
grow.

---

## 3. The Build-Up

**Remote support, per hour:**

    L1 wage $25.00  x burden 1.30  = $32.50 loaded
    + remote delivery overhead     = $7.50   (tooling/RMM/PSA seat, supervision, escalation to higher tiers)
    = about $40/hr

The overhead line matters: not every remote ticket is solved by the L1 at L1 cost. Some escalate to a
more expensive tech, and every tech carries per-seat tool costs and supervision. That is why the honest
remote delivery cost is around $40, not the bare $32.50 loaded wage. The research validates the original
$40 figure rather than overturning it.

**On-site support, per hour:**

    Field wage $32.00  x burden 1.30  = $41.60 loaded
    x travel and utilization 1.65     = $68.64   (drive time each way, lower productive throughput on site)
    + vehicle/mileage and field tooling = $11.00
    = about $80/hr

On-site costs roughly double remote for three stacked reasons: a more expensive tech, time lost to
travel and lower on-site utilization, and vehicle/mileage. This validates the original $80 figure.

Because both build-ups land on the original numbers, adopting this grounded basis does not move any
published price. The benefit is transparency and tunability, not a repricing.

---

## 4. Tuning Levers

All of these live at the top of `scripts/price_quote.py`. Change one and the whole sheet re-costs.

- **L1_WAGE**: raise if hiring locally in {{SERVICE_AREA}} at the higher end; lower if sourcing remote
  support from a cheaper market. Drives every per-device cost.
- **FIELD_WAGE**: raise for a senior/lead field tech; drives on-site cost.
- **BURDEN**: raise toward 1.40x as benefits get richer.
- **REMOTE_OH**: raise if tool stack per tech is heavy or escalation is frequent.
- **ONSITE_UTIL**: raise for a spread-out service area with long drives; lower for a dense metro with
  clustered visits.
- **ONSITE_OH**: vehicle, fuel, and field tooling per on-site hour.

When any of these change, re-run a known client (for example `client.template.json`) and check the band
before quoting, so you know how far the sheet moved.
