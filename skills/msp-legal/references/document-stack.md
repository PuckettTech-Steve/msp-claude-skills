# {{COMPANY_NAME}} Legal Document Stack: Full Detail

Per-document guidance for everything {{COMPANY_NAME}} signs with clients or needs to operate.
Each entry covers what the document is for, when it is used, what belongs in it, what does NOT
belong in it, and its current status. This file ships with example content from a working MSP;
review and adapt every section before it goes client-facing.

The architectural rule repeated once here because every entry depends on it: **the MSA is the
umbrella. It carries no term, no pricing, no client-specific scope. Those live in the Order or
SOW.** Whenever a drafting instinct says "add this to the MSA," check whether it is really an
Order-level or SOW-level fact.

---

## 1. Master Services Agreement (MSA)

**What it is:** The umbrella contract every client signs exactly once, covering the legal
relationship regardless of engagement type: managed, break-fix, or project-only.

**When used:** At the start of every client relationship, before any work. New engagement types
with an existing client do not need a new MSA; they need a new Order or SOW under the existing
one.

**What it contains:** Limitation of liability, indemnification and hold-harmless clauses,
warranties and disclaimers, client responsibilities, IP ownership, remote-access rights,
confidentiality, insurance requirements, dispute resolution (arbitration seat and litigation
carve-out), the non-solicit, amendment mechanics, survival, payment terms and rate multipliers,
and the regulated-data clause that points to the DPA.

**What it must NOT contain:** Term commitments, pricing, discount ladders, seat or device
counts, SLA response targets, or anything specific to one client. This playbook deliberately
decided against adding term language to the MSA for exactly this reason.

**Status:** Example template; pending review by an attorney licensed in {{STATE}} before it goes
live (highest priority is the non-solicit liquidated-damages figure). Known minor items to check
when you adapt it: any hardcoded effective-date line left over from a template source, a dual
payment-timing reference if both a due-on-the-1st and a late-after-30-days line appear, and
confirming your price sheet's holiday multiplier matches what the MSA states. Keep your working
copy in whatever document management system you use, and keep it in sync if you maintain more
than one copy.

---

## 2. Service Order (managed services)

**What it is:** The per-client commercial document under the MSA for recurring managed
services. This is where the deal actually lives.

**When used:** Every managed-services client signs one (or more, as scope grows). Renewals and
expansions are new or amended Orders, not MSA edits.

**What it contains:** Scope of services (the building blocks from msp-pricing assembled for
this client), seat and device counts, monthly price, the **one-year minimum term and the 4% per
year discount ladder**, on-site allowance, SLA response targets (see entry 4), any
client-specific insurance minimums the MSA's flexible clauses defer to ("cyber liability minimum
set by Order"), and any client-specific softening of flexible MSA clauses (for example the
"client's insurance primary over Provider's" line for small accounts).

**Why it matters so much:** Several MSA clauses were deliberately written to defer to the Order
(cyber insurance minimum, term). Until the Order template exists, those clauses point at
nothing. This is the most important unbuilt document in the stack.

**Status:** Example template; pending review by an attorney licensed in {{STATE}} before first
use. An example draft ships in the kit at `templates/msp-service-order-template.docx`;
includes the SLA schedule (entry 4). Example positions baked in, review and replace with your
own: auto-renewal in successive one-year terms at the then-current one-year rate, 60-day
non-renewal notice, early termination at 50% of remaining term fees as liquidated damages, and
service credits (5% of the monthly fee per documented P1/P2 first-response miss month, capped at
15%, sole and exclusive remedy inside the MSA cap). Monthly count reconciliation with a [10]%
amendment threshold is a standing proposal in the example draft.

---

## 3. Statement of Work (SOW)

**What it is:** The per-project document under the MSA for one-time, defined-scope work: cloud
migrations, network installs, office moves, server projects.

**When used:** Any fixed-scope engagement, for managed clients (project work outside their
Order) and for project-only clients (who sign the MSA plus a SOW, no Order).

**What it contains:** Deliverables, assumptions and exclusions (the scope fence), price or
estimate with the billing basis (fixed fee versus time and materials), timeline and milestones,
client dependencies ("client will provide access to the server room by..."), acceptance
criteria, and what happens to out-of-scope requests (pointer to the Change Order process).

**Drafting note:** Scope creep is the classic MSP project killer. The assumptions/exclusions
section and a working Change Order process are what make a SOW protective rather than
decorative. Be concrete: name what is excluded, not just what is included.

**Status:** Example template; pending review by an attorney licensed in {{STATE}} before first
use. An example draft ships in the kit at `templates/msp-sow-template.docx`.
Carries the scope-fence structure (assumptions and exclusions with drafter prompts), both
billing bases (fixed fee, and time and materials at an example rate card: $110/hr remote,
$220/hr on-site, after-hours 1.5x, holiday 2x), milestone timeline, client dependencies,
acceptance criteria with a [5]-business-day deemed acceptance, Change Order pointer, and a
website-project ownership rider placeholder (client owns domain, content, and site code;
registrar and hosting accounts in client's name).

---

## 4. Service Level Agreement (SLA)

**What it is:** The response-time and resolution-target commitments: how fast {{COMPANY_NAME}}
picks up, triages, and resolves by severity.

**Standing decision: not a standalone signed document.** For an MSP at this stage, SLA targets
belong as a schedule inside the Service Order, for three reasons: (1) targets may differ by
client and price point, which is Order-level information; (2) a standalone SLA invites
negotiation as if it were a separate contract; (3) the MSA's limitation-of-liability and remedy
structure should govern SLA misses, which is automatic when the SLA is a schedule under the
MSA/Order rather than its own paper. If a larger client's procurement insists on a standalone
SLA document, that is a flag to handle deliberately, not a default.

**What the SLA schedule contains:** Severity definitions in plain English (P1 "everyone is
down" through P4 "question or nice-to-have"), response targets per severity, business-hours
definition (with after-hours and holiday work pointing to the MSA's 1.5x/2x multipliers),
escalation path, and the remedy for a miss (typically service credits, never uncapped damages;
remedies must stay inside the MSA liability cap).

**Status:** Built as Schedule A of the Service Order template, pending the same attorney review.
Carries example targets (8am-6pm local business hours; P1 30 minutes through P4 next business
day), the capped service-credit remedy, and exclusions. These are shipped defaults; set your own
targets and hours to match msp-helpdesk.

---

## 5. Non-Disclosure Agreement (NDA)

**What it is:** Mutual confidentiality before deep discovery, when a prospect will show
{{COMPANY_NAME}} their environment, credentials posture, or business information before signing
the MSA.

**When used:** Pre-sale, selectively. Most small prospects will not ask; some (and any with
compliance exposure) will. Also used inbound: prospects and vendors send their own NDAs, which
get triaged with legal:triage-nda against the playbook.

**What it contains (outbound template):** Mutual obligations, standard carveouts (already
known, independently developed, publicly available, legally compelled), a 2 to 3 year
confidentiality term, no embedded non-solicit or no-hire (those belong in the MSA, already
right-sized there), {{STATE}} law and venue.

**Note:** Once the MSA is signed its confidentiality clause governs, so the NDA is a pre-sale
bridge, not a permanent layer.

**Status:** Not built. Low effort, worth having on the shelf before the next discovery call
with a compliance-sensitive prospect.

---

## 6. Risk Acceptance Waivers (cybersecurity, backup, and recommendations generally)

**What it is:** A short signed form for when a client declines a recommendation
{{COMPANY_NAME}} has made: declines backup or DR coverage, declines MFA, insists on running
end-of-life software, refuses a security control, or declines cyber insurance alignment.

**Why it exists:** The MSA's hold-harmless clauses (unsupported software, theft of service,
password management, ransomware cost allocation) do the heavy lifting, but a clause a client
signed long ago is weaker in practice than a one-page form they signed last Tuesday that says
"{{COMPANY_NAME}} recommended X on [date], we declined, we accept the risk." The waiver makes
the MSA's protections concrete and contemporaneous, and it changes the client conversation from
adversarial to documented.

**What it contains:** The specific recommendation, in plain English; the date it was made; the
risk of declining, stated plainly without fear-mongering (msp-brand voice applies even here);
the client's acknowledgment that declining is their decision and that the MSA's hold-harmless
and liability terms apply; signature and date. One page, one risk per form.

**When used:** Every time a documented recommendation is declined. Make issuing these a
standard part of the QBR-alternative / account review rhythm, not a special occasion.

**Status:** Example template; pending review by an attorney licensed in {{STATE}} before first
use. An example draft ships in the kit at `templates/msp-risk-acceptance-waiver-template.docx`. Two
pages, plain English throughout: recommendation and date, the risk of declining, the client's
decision, what the client accepts (MSA ransomware/security cost allocations apply as written;
the negligence carveout preserved; insurance-impact flag), a revisit date, and both signature
blocks. Pairs naturally with the negligence carveouts added to the MSA hold-harmless clauses (the
waiver covers the client's choice, the carveout preserves their recourse if {{COMPANY_NAME}}
itself is negligent, and the two together are fair and defensible).

---

## 7. Data Processing Agreement (DPA)

**What it is:** The addendum governing how {{COMPANY_NAME}} handles regulated or sensitive
personal data on a client's behalf: what data, what {{COMPANY_NAME}} may do with it, safeguards,
breach notification, subprocessors, return/deletion at offboarding.

**When used:** Attached to the MSA for any client clearly handling regulated data: schools and
childcare providers (student and children's records), healthcare-adjacent businesses, financial
services, and legal clients. Frame the applicable regimes carefully for each client type. For
example, an education client may or may not be FERPA-covered (FERPA reaches schools that receive
federal funding), and COPPA governs online services directed at children, not an MSP's record
handling; state childcare-licensing rules and a state privacy act, where one exists, are often
the more plausible frameworks for a childcare client. An attorney licensed in {{STATE}} confirms
which regimes actually apply before the DPA is drafted to a given client. Scope the DPA question
up front for any education, healthcare-adjacent, financial, or legal client: **regulated-data
clients need a DPA or BAA before onboarding.**

**Urgency note:** The MSA's regulated-data clause already points to a DPA **that does not
exist yet** until you build one. A contract referencing a missing addendum is a gap a client's
broker or auditor can catch. This and the Service Order are the two build-next documents.

**What it contains:** Categories of data covered; permitted processing (only as needed to
deliver the services); security measures in plain English; breach notification commitment
(timing and channel); subprocessor disclosure (the RMM, backup, email-security, and any other
vendors who technically touch client data); data return and deletion at termination; and
alignment with the MSA's liability cap (the DPA must not silently create uncapped data
liability).

**Status:** Example template; pending review by an attorney licensed in {{STATE}} before first
use; the attorney also confirms which regulatory regimes actually apply to each client before
the DPA is attached for that client. An example draft ships in the kit at `templates/msp-dpa-template.docx`. Carries the client-specific regime placeholder, the covered-data
checklist, permitted-processing limits (no sale or secondary use), plain-English security
measures, the subprocessor table (your RMM, backup, email security, endpoint protection,
password vault, and any AI-assisted tooling you use) with a change-notice commitment, breach
notification within [72] hours of confirming an incident (bracketed as a proposal for attorney
review) plus a note on your state's breach-notification statutory clock, data return and
deletion per the offboarding standard (60-day retention, then deletion with written
confirmation, unless Schedule 1 states a regulatory retention override), the no-expanded-
liability alignment with the MSA cap, and a BAA pointer for HIPAA clients.

---

## 8. Business Associate Agreement (BAA)

**What it is:** The HIPAA-specific addendum required when a client is a covered entity (medical,
dental, behavioral health, some wellness) and {{COMPANY_NAME}}'s services touch systems
containing PHI. Where it applies it is legally required, not optional, and a standard DPA does
not satisfy it.

**When used:** Any healthcare client, before {{COMPANY_NAME}} touches their systems. Note the
chain consequence: {{COMPANY_NAME}}'s own vendors that touch PHI-bearing systems (backup, RMM)
must offer BAAs to {{COMPANY_NAME}} in turn; verify this in vendor selection for healthcare
deals.

**Status:** Not built. Build when the first healthcare prospect reaches discovery, not before;
but treat "do you handle patient data?" as a standard discovery question now (feed this to
msp-sales discovery).

---

## 9. Change Order

**What it is:** A short amendment form for changing an existing Order or SOW: scope additions,
seat-count true-ups, mid-term service additions, project scope changes.

**Why it matters:** It is the pressure valve that keeps the MSA and Order stable. Without it,
changes get handled by email (unenforceable ambiguity) or by reopening the Order (renegotiation
risk). With it, scope creep on projects becomes billable rather than absorbed.

**What it contains:** Reference to the governing Order/SOW, the change in plain English, price
impact (from msp-pricing; seat changes follow the price sheet), effect on term (standing
default: additions co-terminate with the existing Order term), signatures.

**Status:** Not built. Build alongside the Service Order template.

---

## 10. Third-Party Terms Flow-Through

**What it is:** A short schedule or MSA exhibit stating that services resold or administered by
{{COMPANY_NAME}} (an email and productivity platform, an endpoint protection platform, a device
management platform, a static hosting platform, a VoIP carrier, a backup vendor) are subject to
those vendors' own terms, and that the vendors' uptime and data commitments are theirs, not
{{COMPANY_NAME}}'s.

**Why it matters:** Without it, {{COMPANY_NAME}} implicitly warrants its platform vendors'
uptime. The MSA's disclaimers help, but an explicit flow-through is cleaner and is standard MSP
practice.

**What it contains:** The list of third-party services with pointers to their terms, a
statement that {{COMPANY_NAME}} passes through but does not expand those vendors' warranties,
and a note that vendor price changes can be passed through per the MSA's amendment mechanics.

**Status:** Not built. Low effort; reasonable to fold into the MSA as an exhibit at the next
attorney-review cycle rather than maintaining standalone.

---

## 11. Website Privacy Policy and Terms of Use

**What it is:** Compliance pages for {{DOMAIN}}: what the site collects (forms, analytics), how
it is used, and the terms governing site use.

**Why it matters:** Baseline credibility and compliance hygiene. An IT services company whose
own website lacks a privacy policy hands skeptical prospects an easy objection, and contact
forms collect personal data that your state's privacy law can reach as the business grows.

**Status:** Not built. Low urgency, low effort; a templated policy reviewed by the attorney
during the same review cycle as the MSA is sufficient at this stage.

---

## 12. Staff Confidentiality and IP Assignment Agreement

**What it is:** The internal agreement every employee or subcontractor signs: confidentiality
covering client data and credentials, IP assignment to the company for work product, and
acceptable handling of client systems.

**Why it matters now, not later:** {{COMPANY_NAME}}'s people hold the keys to client
environments; the MSA promises clients confidentiality and security that {{COMPANY_NAME}} can
only deliver if its own staff are bound. Equity or partnership arrangements are handled in your
operating agreement and its amendments (a separate corporate-docs track, with its own
attorney-review needs around vesting and valuation), but a working-role confidentiality and IP
agreement is a different document from an equity grant, and future hires or 1099 contractors
will need it from day one.

**Status:** Not built. Build before the first non-owner hire or subcontracted tech.

---

## Quick selector: "What does client X need to sign?"

1. **Every client:** MSA. Always, once, first.
2. **Managed services:** + Service Order (which carries term, pricing, SLA schedule).
3. **Project work:** + SOW (managed clients too, for work outside their Order).
4. **Regulated data (school, finance, legal):** + DPA addendum, scoped at discovery.
5. **Healthcare / PHI:** + BAA instead of (or alongside) the DPA. Legally required.
6. **They decline a recommendation:** Risk Acceptance Waiver, each time, dated.
7. **Pre-sale deep discovery with a cautious prospect:** NDA first.
8. **Anything changes mid-flight:** Change Order, never a side email.
