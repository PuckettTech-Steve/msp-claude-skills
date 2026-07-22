# {{COMPANY_NAME}} Pricing: Support-Hour Estimates (benchmark research)

**Defaults you must review:** the per-block labor-hour estimates below are one working MSP's
numbers, tuned to its own automation maturity. See the "Setup Decisions" section of `../SKILL.md`
before treating any figure here as settled for your shop.

This file documents the monthly labor-hour estimate behind each building block: where the numbers came
from, whether they hold up against industry benchmarks, and the standing decisions. The hours are the
single biggest driver of cost, so getting them roughly right matters more than any other input.
Researched June 2026; revisit once you have your own ticket data.

These are all-in hours: reactive tickets plus proactive maintenance, patching, monitoring remediation,
and admin. They are not ticket-handle-time alone.

## Contents
1. The two benchmark lenses
2. Per-line assessment
3. Standing decisions
4. The per-user caveat

---

## 1. The Two Benchmark Lenses

Two independent methods converge on the same range for a workstation.

**Tickets times handle time.** An average, reactive MSP runs about 0.75 to 1.0 tickets per endpoint per
month; top performers run 0.2 to 0.5. Best-in-class handle time is about 30 minutes per ticket. So
reactive ticket work alone is roughly 0.4 to 0.5 hours per endpoint for an average shop, and proactive
and admin work roughly doubles it for the total.

**Technician-to-endpoint ratio.** The industry sweet spot is about 250 to 400 endpoints per technician
(below 250 is overstaffed, above 400 risks burnout without strong automation). The average MSP runs
200 to 300 per tech. A technician delivers roughly 140 productive hours a month, so:

| Maturity | Endpoints per tech | Hours per endpoint per month |
|----------|--------------------|------------------------------|
| Reactive / low automation / brand new | 125 to 200 | 0.7 to 1.1 |
| Balanced, good tools | 250 to 400 | 0.35 to 0.56 |
| Heavily automated (outlier) | 1,000+ | under 0.15 |

Bottom line: real all-in labor is about 1.0 hour per workstation for a reactive or brand-new MSP and
about 0.5 hour for a mature, automated one.

Sources: industry ticketing and PSA benchmark reports (tickets per endpoint), managed-services
efficiency research (handle time), workforce and staffing benchmark reports (endpoints per
technician), vendor pricing guides (server pricing). Figures are 2024 to 2026.

---

## 2. Per-Line Assessment

| Block | Hours | Verdict |
|-------|-------|---------|
| Workstation | 1.0 | Reasonable, deliberately conservative. Matches a reactive/new MSP; about double a mature one. Kept as-is. |
| Account-only user | 0.4 | New. No managed machine, so no maintenance and fewer tickets, just identity and account security. Lighter than a workstation by design. |
| Server | 1.5 | Raised from 1.0. Servers are higher-touch; 1.0 underpriced them. See decisions below. |
| Mobile | 0.5 | Slightly high for an MDM-managed phone, but minor and protective. Kept. |
| Firewall | 0.5 | Reasonable. Firmware, rule changes, and security monitoring justify it. |
| Switch / AP / Camera | 0.1 | Reasonable. Monitor-and-forget devices. Kept. |
| Printer | 0.3 | New. Business-class networked fleet only; the hardware gate keeps the nightmare population (consumer/inkjet/USB) out of the monthly, so load stays low. Most months zero-touch; occasional driver or scan-to-email work. Revisit with ticket data. |
| Special software | 1.0 | Placeholder; depends entirely on the app. Adjust per client. |

**Why keep workstation at 1.0 rather than drop to 0.5?** Because an early-stage shop without mature
automation carries real load near 1.0 today. And since price is always a fixed multiple of cost (~2.703x, 60% GM after the
payment fee), the conservative hour quietly builds in upside: as the stack standardizes and load drops
toward 0.5, real margin rises above the stated 60% if price holds. Revisit only with actual ticket data, roughly a year
in, then either keep the price and book the higher margin or trim to compete.

---

## 3. Standing Decisions

**Server raised from 1.0 to 1.5 hours.** The original sheet gave a server the same hour as a
workstation, which set the server anchor at only $140. Servers carry more load (patching with
maintenance windows, backup verification, tighter monitoring, higher-stakes troubleshooting) and the
market reflects it: server rates commonly run $100 to $500 per server per month, with about $200 a
typical midpoint. At 1.5 hours the loaded cost is $75 and the anchor is $210, squarely mid-market. At
2.0 hours it would be $260, the top end; 1.5 is the balanced choice. Bump it to 2.0 in the script for a
server-heavy or high-availability client.

---

## 4. The Per-User Caveat

The model bills per device, but reactive load is really driven per user: idle machines do not open
tickets, busy people do. This mostly washes out, but for a client with many low-use or shared machines,
per-device overstates labor, and for a few heavy power users it understates it. The power-user value
factor in the pricing logic exists to catch the second case. When a client's device count and headcount
diverge sharply, sanity-check the per-user figure against the $75 to 200 benchmark before quoting.
