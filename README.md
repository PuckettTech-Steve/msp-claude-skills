# MSP Operations Kit

A complete Claude skill suite for running a small managed IT services business (MSP). Thirteen skills that work as one system: every client-visible number comes from one pricing skill, every piece of content follows one brand skill, and every legal-adjacent workflow carries an attorney escalation path.

Built and proven inside a working MSP, then white-labeled. The operational structure ships complete; the identity and the numbers are yours to fill in.

## Pay what you want

The kit is free and open to use. If it saves you time or wins you a client, [pay what you want via GitHub Sponsors](https://github.com/sponsors/RTFM-IT-Services-LLC). Any amount funds continued updates.

## What's inside

Setup:

- `msp-setup`: guided first-run setup. Interviews you for your facts, writes them into the other skills, tracks progress, and tells you when the kit is client-facing ready.

Foundation skills (the ones everything else defers to):

- `msp-brand`: your identity, colors, voice, and signature. A fill-in template; this is where you make the kit yours.
- `msp-sales`: outreach, call scripts, discovery, objection handling, pipeline, plus a 9-file reference library.
- `msp-pricing`: a pricing configurator with cost model references and a working quote script.
- `msp-legal`: your document stack (MSA, Orders, SOW, DPA, waivers) and negotiation playbook.
- `msp-website-setup`: a standard pipeline for client static websites with git-based dev/prod deployment.

Delivery skills (day-to-day operations):

- `msp-onboarding`: 30-day runbook from Closed Won to steady state.
- `msp-offboarding`: client exit runbook. Full service to the last day, never hold data hostage.
- `msp-helpdesk`: P1-P4 priority matrix, response targets, escalation, security incident track.
- `msp-maintenance`: patching, backup verification, monitoring triage, on-call, change management.
- `msp-client-comms`: operational message templates (maintenance, incidents, advisories, price changes, and more).
- `msp-qbr`: quarterly business review process and client scorecard.
- `msp-metrics`: monthly business review (MRR, margin per client, ticket load, SLA attainment) and the fire-or-fix framework.

## Install

As a plugin in Claude Code or Cowork (recommended, one step gets everything):

```
/plugin marketplace add RTFM-IT-Services-LLC/msp-claude-skills
/plugin install msp-ops-kit@msp-ops-kit
```

Or install skills individually in Cowork / claude.ai: zip a skill folder (the folder containing SKILL.md) and upload it under Settings, Capabilities.

## Setup

Ask Claude to "set up the kit". The `msp-setup` skill runs a guided, resumable interview that fills in your identity, rebuilds the pricing cost model with your numbers, walks every skill's Setup Decisions, routes `msp-legal` to your attorney, and finishes with a readiness check. It edits the kit source files in this folder, so keep this folder and reinstall the plugin after setup phases.

The skills work out of the box for internal drafting, but nothing should go client-facing until the readiness check passes. If you prefer manual setup, the five phases in `msp-setup/SKILL.md` are the checklist.

## Ground rules baked into the suite

Do not undo these; they are what makes the suite hold together.

- All client-visible numbers come from `msp-pricing`. No other skill states a price.
- Voice, naming, and formatting defer to `msp-brand`.
- Legal-adjacent content always carries the attorney escalation path.
- No em dashes in anything the suite produces.

## License

Copyright (c) 2026 RTFM IT Services LLC. Licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

In plain terms: use and customize it freely for running your own MSP, with credit. Don't sell the kit or repackage it into a commercial product, and share any adapted versions under the same license. Using it internally to run your business (including the client work you charge for) is fine; the restriction is on selling the kit itself. If you want to point another MSP at it, send them here. See the LICENSE file for the legal text.
