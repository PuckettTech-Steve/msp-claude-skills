# Rewrite Playbook: Making Outside Material Sound Like {{COMPANY_NAME}}

How to digest a licensed MSP marketing pack, an industry article, a vendor blog post, or any
other source and turn it into content the company can publish proudly.

---

## Step 1: Classify the Source (Rights First)

**Licensed marketing packs (from a paid MSP marketing content membership).** If the company is
a paying member and the membership licenses its content for adaptation and reuse in members'
own marketing, you may keep the structure, the ideas, and even reuse phrasing. The output
should still pass the transformation checklist, because many other MSPs receive the same pack.
Identical content published by hundreds of MSPs helps nobody's search ranking and sounds like
nobody in particular. Confirm which memberships the company actually holds (see SKILL.md Setup
Decisions) before treating any source as licensed.

**Third-party articles, vendor blogs, news pieces, anything the company doesn't have a license
to.** Inspiration only. Extract the underlying facts and the topic; write the piece from
scratch. Never close-paraphrase (same structure, same points in the same order, swapped
synonyms). If a specific statistic, quote, or original finding is used, name and link the
source in the piece. Never republish or lightly spin someone else's article.

**When rights are unclear, treat the source as third-party.**

## Step 2: Extract the Core

Read the whole source, then answer in one sentence: *what is the one thing a local business
owner should do or know after reading this?* That sentence becomes the spine of the rewrite.
Everything that doesn't serve it gets cut. Most source material is 40-60% filler; the rewrite
should be shorter and sharper than the original.

Discard on sight:

- Generic MSP boilerplate ("as a leading provider of managed services...")
- Anything pitching services the company deliberately does not sell (see the exclusions rule
  in SKILL.md; the current list lives in msp-sales `references/service-catalog.md`)
- Fear-based framing (rewrite the facts with an equipping tone)
- Claims and statistics you cannot verify. Verify or delete; never launder a stat you can't trace
- Placeholder names, "[Your MSP Name]" fields, and any other tell that this came from a pack

## Step 3: De-Pack and Localize

Many marketing-pack vendors write for an international audience, often Australian or UK based.
Sweep for:

- Spelling: organisation → organization, utilise → use, centre → center, licence → license
  (adjust for your own market if you are not US based)
- Currency: foreign currency symbols → remove or restate in general terms (no invented dollar
  figures)
- Idiom and season: "end of financial year" (June in Australia) → your market's tax season or
  year-end as fits; flip any opposite-hemisphere seasonal references
- Regulation: foreign privacy-law references → keep only what applies to your market's SMBs,
  or generalize to "privacy laws"

Then localize to the company: {{SERVICE_AREA}}, local weather and power blips, the kinds of
businesses the company serves (see msp-sales' ICP). One natural local touch per piece; forced
local color reads worse than none.

## Step 4: Re-Voice

Load msp-brand and apply its voice section in full. The compressed version: friendly expert,
plain English, outcomes over specs, empathy over fear, no em dashes, no hype words, jargon
translated per the brand's plain-English list. Speak to the business owner personally ("you,"
"your team," "your files").

## Step 5: Transformation Checklist

The rewrite passes when ALL are true:

1. **Blind test:** someone reading the source and the rewrite side by side would call them two
   different articles on the same topic, not two versions of one article.
2. **Structure moved:** the rewrite's outline is not the source's outline.
3. **Opening is original:** the first two sentences appear nowhere in the source in any form.
4. **Company fingerprint:** at least one point, example, or angle the source doesn't have (a
   local angle, a service-stack detail, a client-situation example with no real names).
5. **Facts survive, phrasing doesn't:** no sentence longer than a few words survives verbatim
   (licensed pack content excepted on rights, but still aim for it).
6. **Sources credited** where a third-party stat, quote, or finding is used.

If any item fails, revise before delivering. If the user pushes to publish a close paraphrase of
unlicensed material, decline and explain the rights problem plainly.

## Step 6: Finish

Apply the CTA (cta-library.md), run the SKILL.md pre-publish checklist, produce the repurposing
chain unless told otherwise, and log the piece in content-log.md.
