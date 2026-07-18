# {{COMPANY_NAME}} Contract Playbook: Standing Positions

{{COMPANY_NAME}}'s example positions on contested contract clauses, shipped as a working
starting point from a working MSP. This file is formatted the way legal:review-contract expects
an organization playbook: for each clause, the **standard position** (what this paper says), the
**acceptable range** (what can flex without escalation, and where the flex lives), and the
**escalation trigger** (what goes to an attorney licensed in {{STATE}}).

These are one MSP's negotiated positions, not legal advice. The whole template is pending
attorney review; do not represent any of this as attorney-approved until your own attorney has
reviewed it. Your attorney must approve your versions before you rely on them.

**Orientation:** these positions assume {{COMPANY_NAME}} is the **Provider** on its own outbound
template. When {{COMPANY_NAME}} is on the receiving side of someone else's paper, use these
positions as the mirror: the clauses {{COMPANY_NAME}} deliberately right-sized (no-hire breadth,
insurance burden, unilateral amendment, short claim windows) are exactly what to hunt for in
inbound contracts.

---

## Dispute resolution and venue

- **Standard:** Arbitration with the seat in [county], {{STATE}}. Litigation carve-out for
  unpaid fees and injunctive relief, pointing to a {{STATE}} court. Governing law: {{STATE}}.
- **Acceptable range:** None on governing law or venue for outbound paper. (Watch for boilerplate
  that lists an out-of-state venue left over from a template source; treat any venue outside
  {{STATE}} in your own paper as an error, full stop.)
- **Escalate:** A client large enough to demand their home-state venue. Do not concede in
  drafting; that is an attorney conversation.

## Limitation of liability

- **Standard:** A single controlling cap of **six months of fees**, applying regardless of
  insurance. A competing "limited to proceeds of applicable insurance" sentence is deliberately
  left out: tying the cap to insurance proceeds risks lifting the real ceiling from roughly six
  months of fees (about $9k on a $1,500/month client) to a much higher E&O policy limit.
- **Acceptable range:** None in drafting. Never reintroduce insurance-proceeds language. Never
  add carve-outs from the cap at a client's request without escalation.
- **Escalate:** Any client redline touching the cap; the attorney review should also sanity-check
  the single cap's overall enforceability (open item).

## Ransomware cost allocation ("the ransom clause")

- **Standard:** KEEP the protection. The clause allocates ransomware-event costs to the client,
  which is standard MSP risk allocation. Wording is framed as **cost allocation**, not a promise
  to pay criminals, with a hold-harmless and the negligence carveout (see next entry).
- **History worth remembering:** an earlier review pass flagged this clause for deletion and
  overstated an OFAC concern, then walked it back. The protection was never the problem, only
  the phrasing. Do not re-flag the clause's existence; only its wording was at issue and that is
  settled.
- **Escalate:** Client demands to delete it entirely.

## Hold-harmless carveouts

- **Standard:** Every hold-harmless clause (unsupported software, theft of service, password
  management, ransomware, malicious activities) carries "except to the extent caused by
  Provider's negligence or willful misconduct."
- **Rationale:** The carveout is what makes the clauses fair and defensible: the client owns
  their choices, {{COMPANY_NAME}} owns its mistakes. It pairs with the Risk Acceptance Waivers
  (see document-stack.md entry 6).
- **Acceptable range:** None; the carveout stays in all of them. New hold-harmless clauses added
  in the future get it by default.

## Non-solicitation (formerly "No-Hiring")

- **Standard:** A targeted, **mutual**, **12-month** non-solicit limited to personnel who
  worked on or were introduced through the engagement, with standard carveouts for general job
  postings and self-initiated applicants. (Narrowed from an absolute no-hire, which is both
  aggressive and an enforceability risk.)
- **Open and attorney-only:** The liquidated-damages paragraph (100% of one year's pay) is
  retained but flagged. **This figure is the single highest-priority attorney-review item.** Do
  not modify, defend, or negotiate it without counsel.
- **Inbound mirror:** an absolute no-hire in someone else's NDA or MSA is a YELLOW/RED triage
  flag.

## Insurance requirements

- **Standard:** Cyber liability covering ACH/wire fraud, with the **minimum set flexibly by
  Order**. Workers' comp "where required by applicable law." Client equipment insured at full
  replacement value with evidence on request (not "name Provider as an insured beneficiary,"
  which is overreach). Waiver of subrogation kept. Provider carries E&O. "Client's insurance
  primary over Provider's" is **in** the template.
- **Acceptable range:** The "primary over Provider's" line is the designated flex point for
  small accounts: genuinely protective, but it is the line brokers push on. Softening it, or
  making it flexible by Order, is allowed when the owner asks; do not soften it silently.
- **Escalate:** A client refusing cyber coverage outright (that is also a Risk Acceptance Waiver
  conversation, and possibly a no-deal signal).

## Claim period

- **Standard:** Claims must be brought within **one year** (lengthened from six months, which is
  aggressive enough to spook brokers and shaky on enforceability).
- **Acceptable range:** None shorter than one year. Longer only via attorney.

## Amendment mechanics

- **Standard:** Amendments require **30 days' notice**, and the client gets a **no-penalty
  off-ramp for material adverse changes**. (This replaces a unilateral-amendment posture; the
  off-ramp is what makes 30-day amendments defensible and small-client friendly.)
- **Acceptable range:** None; this balance is the point.

## Survival

- **Standard:** Survival explicitly includes Limitation of Liability, Indemnification, payment
  obligations, the claim period, and Dispute Resolution.

## Term and the MSA/Order boundary

- **Standard:** The MSA carries **no term**. It is the umbrella for managed, break-fix, and
  project clients alike. The one-year minimum term and the discount ladder live in the Service
  Order (see msp-pricing for the ladder itself).
- **Acceptable range:** None. Adding term language to the MSA is an architecture error, not a
  negotiation position.

## Payment and rates

- **Standard:** After-hours at 1.5x and holiday at 2x hourly rates, matching the msp-pricing
  sheet. $1,000/month engagement minimum (an Order-level commercial term).
- **Known minor issue to check when you adapt this template:** if the MSA has a dual
  payment-timing reference (for example, due on the 1st versus late after 30 days), reconcile it
  at your next attorney-review cycle. Confirm your msp-pricing sheet states both multipliers
  (1.5x after-hours, 2x holiday) as the owning source, and that the break-fix rate card they
  multiply against exists (msp-pricing references/break-fix-rates.md).

## Termination and suspension (Example position; attorney to review)

- **Standard:** Either party may terminate the MSA for the other's material breach that remains
  uncured 30 days after written notice describing the breach. Provider may suspend services when
  an invoice is 30 or more days past due, after giving 10 business days' written warning;
  suspension is not termination, and fees continue to accrue during it. The MSA itself carries
  **no termination for convenience**. The convenience exit lives in the Order's early-termination
  economics (50% of remaining-term fees as liquidated damages, already settled; see
  document-stack.md entry 2), which keeps the MSA/Order architecture clean: the umbrella has no
  term, so it needs no convenience exit.
- **Acceptable range:** Cure period can stretch to 60 days for a client that asks; suspension
  warning can stretch modestly. Nothing shorter than 30-day cure on outbound paper.
- **Escalate:** A client demanding termination for convenience in the MSA itself, or demanding
  removal or weakening of the suspension-for-nonpayment right.

## Subcontractors and assignment (Example position; attorney to review)

- **Standard:** Provider may use subcontractors, provided each is bound by confidentiality
  obligations at least as protective as the MSA's, and Provider remains responsible for
  subcontractors' acts and omissions as if they were Provider's own. Neither party may assign
  the MSA without the other's written consent, except that either party may assign without
  consent to a successor in a merger or sale of all or substantially all of its business or
  assets.
- **Acceptable range:** Advance notice of subcontractors with access to Client's environment, or
  a named-subcontractor list in the Order, can be offered to a cautious or regulated client.
  Provider's responsibility for subcontractor acts does not flex.
- **Escalate:** A client demanding a consent right over the sale-of-business exception, a
  blanket prohibition on subcontractors, or flow-down terms beyond confidentiality (audit
  rights, insurance requirements on subcontractors).

## IP license-back at exit (Example position; attorney to review)

- **Standard:** Provider owns its preexisting and independently developed tools, scripts,
  processes, and know-how, and everything it builds on them. Client receives a **perpetual,
  non-exclusive license** to the configurations, documentation, and scripts deployed in
  Client's environment, effective on full payment of all amounts due. This refines a pure
  provider-ownership posture: ownership stays with Provider, but a client who has paid in full
  can keep running what was built for them.
- **Rationale:** Pure provider ownership with no license-back reads as hostage-taking to a
  departing client and their next provider, and it conflicts with the offboarding posture
  (msp-offboarding promises clean data return and transition). The license-back costs Provider
  nothing it actually sells and removes the scariest exit-clause reading.
- **Acceptable range:** None on Provider's ownership of preexisting IP (that is in the
  provider-favorable core). The license can be narrowed to a specific deliverable list in a SOW,
  or extended to a client's successor, on the owner's ask.
- **Escalate:** A client demanding assignment of ownership of Provider tools or work product, a
  license effective before full payment, or an exclusive license.

## Insurance reality gate

If {{COMPANY_NAME}} does not carry insurance yet, the plan of record should be E&O plus cyber
liability before the first client signs. Hard gate: the MSA's "Provider carries E&O"
representation must be true before the first MSA is signed, so the policies get bound before or
at first signing, not after. The broker conversation should also set the cyber policy's
incident-response requirements (notice timing, panel firm mandates), which feed the
msp-helpdesk security track.

## Provider-favorable core (do not weaken)

The following are working as designed and are deliberately left intact in this playbook. Treat
client pushback on these as a conversation (msp-sales, plain-English translation), not a
drafting change: limitation of liability structure, warranty disclaimers, client
responsibilities, IP ownership, remote-access rights.

## Formatting and identity (binding on all legal documents)

- Signature block: "{{COMPANY_LEGAL_NAME}} (Provider)" with correct spacing.
- Full legal name in all formal documents; no em dashes anywhere.
- Your MSA template should carry your brand formatting: your accent color on section headings,
  page-numbered footer (see msp-brand).

---

## Setup Decisions

Settle these for your own shop, with your own attorney, before this playbook goes client-facing:

1. **Get attorney review before the MSA goes live.** Priorities: the non-solicit
   liquidated-damages figure, the single liability cap's enforceability, and an overall review by
   an attorney licensed in {{STATE}}.
2. **Build your Service Order template** carrying your own minimum term and discount ladder. An
   Order task, not an MSA edit.
3. **Build the DPA** your MSA's regulated-data clause already references, if you have or expect
   any regulated-data client (education, healthcare-adjacent, financial, or legal). Confirm with
   your attorney which regimes actually apply to each such client before attaching it.
4. **Keep a tracked-changes version** of your MSA if your attorney wants a redline against a
   prior draft.
5. **Reconcile minor drafting items** before first use: any hardcoded effective-date line left
   over from a template source, and any dual payment-timing reference (due date versus
   late-after language). Confirm your price sheet states both multipliers (1.5x after-hours, 2x
   holiday) and that msp-pricing owns them.
6. **Decide your "client's insurance primary over Provider's" flex policy.** This is the
   designated flex point for small accounts; decide whether to soften it by default or only on
   request, and document your choice.
