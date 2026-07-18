# Service Catalog: What We Sell and How to Talk About It

Source: the internal {{COMPANY_LEGAL_NAME}} Service Catalog (an internal document, "Internal
Use Only"). This file owns the sales-side view: the client-facing language, what is in and out
of scope, and the presentation rules. Every dollar figure except the public $1,000/month
engagement minimum lives in msp-pricing (the Internal Price Sheet and the configurator). Never
quote a number from memory; this file deliberately omits per-block rates.

---

## Managed Services: The Client-Facing Lineup

Clients hear services. We bill blocks. Use the left-column language in all customer-facing
content; the block names are internal vocabulary only.

| What the client hears | What we bill (internal) |
|---|---|
| Help desk & device care (staff with a company computer) | Workstation user block (the machine plus that person's support) |
| Account, email & security only (BYOD staff, 1099 contractors) | Account-only user block (identity, MFA, licensing; no managed machine) |
| Email & everyday apps (your email and productivity platform) | Included in the user blocks; licenses bill through {{COMPANY_NAME}} (margin policy in msp-pricing) |
| Servers & cloud | Server block |
| Backups & recovery | Included in workstation and server blocks (BDR stack) |
| Security (endpoint protection, secure access, Mac management) | Security agents folded into each device's loaded cost |
| Company phones & tablets | Mobile device block |
| Network care, per site | Network base fee plus firewall/router plus per switch, AP, or camera |
| Industry-specific software support | Special software block, per app |
| On-site presence ("about one visit a month") | Bundled on-site hours; extras bill at the managed on-site hourly rate (msp-pricing break-fix card) |
| Vendor wrangling, domains & DNS | Included in the engagement (vendor liaison) |

Per-user blocks carry the engagement; device blocks ride along. Anchors, the floor, START,
and the term ladder all come from msp-pricing.

## One-Time & Project Work

All one-time work quotes from Break-Fix rates and bills separately from the monthly. Never
absorb onboarding or migration into the recurring price. Categories:

- New PC and server setups, software installs, email account setups (scheduled Move / Add / Change)
- Onboarding and migration onto our stack (quoted up front at MAC rates)
- Equipment installs, upgrades, and cable runs (on-site field rates; subcontract structured
  cabling where low-voltage licensing requires)
- Emergencies and after-hours work (incident and priority rates)
- Training and consultation

Rates for all of the above live in msp-pricing.

## What We Do NOT Sell (and What to Say Instead)

| Service | Status | What to tell the prospect |
|---|---|---|
| SEO & site analytics | Cut | Marketing discipline, not IT. "We can refer you to people who do this all day." |
| Payment processing | Cut | Different industry with PCI liability. Refer to their bank or processor. |
| Website hosting | Folded | We don't sell hosting. Domains and DNS are covered under vendor liaison; the website itself goes to a web vendor we coordinate with. |
| Datacenter networking | Cut | Our sweet-spot clients don't have datacenters. Enterprise work breaks our delivery model. |
| Faxing | Folded | Secure e-fax lives under Business Phones. Healthcare clients still need it for HIPAA workflows; sell it there. |
| IVR / phone menus | Folded | A VoIP feature ("auto attendants and phone menus"), not a service line. |
| Cable runs | Folded | Project work at field rates, not a headline service. |

Saying no cleanly builds trust. Position cuts as focus: "we'd rather connect you with a
specialist than do a mediocre job outside our lane."

## VoIP: Setup Decision (Pricing Model)

The price sheet has no VoIP seat line yet, and you have not picked a model. Until you settle
this decision:

- Quote VoIP the project-plus-liaison way: set the client up directly with the carrier as a
  project at MAC rates, then support the system under vendor liaison and special software.
- NEVER invent a per-seat price on a call or in a proposal. If a prospect pushes for a seat
  price, take it back to whoever owns pricing decisions at your shop.

## Presentation Rules (Non-Negotiable in Sales Content)

1. Clients never see the price sheet or per-block rates. They see two or three assembled
   options: "here is what I put together for you."
2. The only public number is the $1,000/month engagement minimum (example default; set your
   own in msp-pricing). It qualifies leads and anchors expectations. Everything else comes out
   of the configurator per client.
3. Every quote shows the term ladder: 1-year on top as the minimum term and highest price,
   with 2, 3, and 5 years stepping down.
4. Response time never varies by option or price. Differentiate options on what's included,
   never on how fast we answer.
5. Quotes come from the configurator (price_quote.py), never from memory. Discovery feeds it:
   headcount split (workstation users vs. account-only), device counts, OS mix, server count,
   sites and network gear, special apps, and value factors.

## Discovery Implications

The catalog tells you what to count on a discovery call. Make sure discovery captures:

- Staff with company computers vs. BYOD/contractor staff (the workstation vs. account-only split)
- Servers, and whether the environment is server-heavy or high-availability
- Company-owned phones and tablets
- Sites, plus firewalls/routers, switches, APs, and cameras per site
- Industry-specific software (each app is its own block)
- Appetite for on-site presence
- Healthcare or other verticals that need e-fax under Business Phones
