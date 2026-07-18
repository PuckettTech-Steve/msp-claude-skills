---
name: msp-website-setup
description: Your MSP's standard process for setting up a new static client website hosted on
  your static hosting platform with a git-based dev/prod CI/CD pipeline, plus the
  client-practice rules around it. Use this skill whenever starting a new website project for a
  client, setting up a static site, initializing a website repo, connecting a site to your
  static hosting platform, or wiring up dev and prod deployments for a small business site, even
  if the user just says "let's build a site for this client" or "set up the repo for the new
  website". Also trigger for questions about who owns a client's site, domain, repo, or content,
  which agreement a website project needs and when in the sequence (drafting the document itself
  is msp-legal), website accessibility (WCAG, alt text, contrast),
  privacy policy or form-data questions on a client site, and handing a site back at
  offboarding. Load before writing any site code or running git init so the project starts on
  the standard structure.
---

# {{COMPANY_NAME}} Static Website Setup

Standard process for standing up a new static client website: paper first, then client info, then git repo with a two-branch pipeline, then hosting on your static hosting platform. The order matters: content and structure decisions are cheaper before any code exists.

## Phase 0: Paper Gate (before any site work)

No website work starts before a signed SOW under the client's MSA. See msp-legal, document-stack entry 3. The SOW carries scope, price, timeline, content responsibilities (who writes copy, who supplies photos, by when), and acceptance criteria for launch. For managed clients, a website build is project work outside their Order, so it gets its own SOW; it does not ride along on the managed agreement. If someone says "just start the site, we'll paper it later", stop and route to msp-legal.

## Ownership Model

The client owns their website. Specifically:

- The client owns their domain, their content, and their site code.
- The domain registrar account and the static hosting platform account are in the client's name, with {{COMPANY_NAME}} added as an administrator.
- The repo on your git hosting provider is transferred to the client (or their successor provider) at offboarding.
- {{COMPANY_NAME}} retains a license to reuse its generic tooling and pipeline configs (the deployment setup, build scripts, and boilerplate it uses across client sites), not the client's content or design.

State this ownership model in each project's SOW so it is contract, not just practice. The point: no client is ever hostage to {{COMPANY_NAME}} for their own website, and no dispute can turn the site into leverage. This is standing policy, not a one-time decision; apply it to every client site.

## Architecture Overview

- Static site (plain HTML/CSS/JS, no framework unless the project demands one)
- Code on your git hosting provider, one repo per client site
- Hosting on your static hosting platform via its git integration
- A host that auto-deploys from a git branch, with a separate preview/dev branch environment, arranged as a two-branch pipeline:
  - `dev` branch → dev/preview deployment (a preview URL or dev subdomain)
  - `main` branch → production deployment on the client's custom domain
- Workflow: build and review on `dev`, merge to `main` to ship

## Phase 1: Company Info Document (before any code)

Create `COMPANY-INFO.md` in the project root capturing everything about the client before building. Gather from the client and their existing online presence:

- Legal business name, website domain, industry, service area
- Services offered (this becomes the site's core content)
- Contact info: phone, email
- Online presence: social profiles, review sites, and business directory listings
- Key selling points and existing taglines/messaging (reuse their voice)

Also include a "Website Plan" section in the same file: stack, repo/branching model, CI/CD flow, and a to-do checklist. This file doubles as the project brief and the deployment runbook.

### Content and legal checklist (part of Phase 1, before build)

- **Content ownership confirmed in writing.** The client confirms, in writing, that they own or have licenses for all photos and copy they supply. Copyright demand letters routinely target small-business sites over one lifted image; a stock photo grabbed from a web image search is not licensed. Keep the confirmation with the project file.
- **Photo consent for people.** Verify consent for any image showing a recognizable person, and treat photos of children as a hard stop until consent is confirmed. Childcare and education clients carry photo-consent obligations, and a consent failure is an easy, avoidable liability.
- **Privacy policy if the site collects anything.** Any form that takes a name, email, phone, or message means the site collects personal data, and a privacy policy page is required before launch. See msp-legal document-stack entry 11 for the shape of one.
- **Accessibility baseline: WCAG 2.1 AA intent.** Alt text on meaningful images, logical heading order, sufficient color contrast, and keyboard-navigable menus and forms. Check these before launch, not after; accessibility demand letters are the other letter small businesses get.

## Phase 2: Git Repo

```bash
cd <project-folder>
git init -b main
```

Create `.gitignore` before anything else so secrets never get staged:

```gitignore
# Secrets - never commit
.env

# OS junk
.DS_Store

# Dependencies / build output (if ever added)
node_modules/
dist/
```

Commit the info doc and .gitignore, then create the dev branch:

```bash
git add COMPANY-INFO.md .gitignore
git commit -m "Add company info and website plan"
git branch dev
```

## Phase 3: Remote and Push

Repos live in your organization's account on your git hosting provider (name the repo after the site's domain, e.g. `example.com`).

```bash
git remote add origin <your-git-host-url>/<your-org>/<repo>.git
git push -u origin main dev
```

### Token handling (when no credential helper is available)

If pushing from an environment without stored credentials (e.g. a sandbox), use a fine-grained personal access token from your git hosting provider:

- Store it in `.env` as `GIT_HOST_PAT=...` (already gitignored)
- Never hardcode the token in commands that get logged; read it from `.env` and mask it in any output (adjust the token-based push URL syntax to match your git hosting provider):

```bash
PAT=$(grep GIT_HOST_PAT .env | cut -d= -f2)
git push -u "https://x-access-token:${PAT}@<your-git-host>/<your-org>/<repo>.git" main dev 2>&1 | sed "s/${PAT}/***/g"
```

- Recommend rotating the token when the project wraps

### Common push issues

- **Remote already has commits** (the host created a README on repo creation): `git fetch <url> main`, then `git rebase FETCH_HEAD main`, re-point `dev` at the rebased `main` (`git branch -f dev main`), and push. A force push (`+dev`) may be needed for branches pushed before the rebase.
- **`--force-with-lease` rejected with "stale info"**: remote-tracking refs are out of date because you pushed by URL instead of by remote name. Fetch with an explicit refspec first: `git fetch <url> "+refs/heads/*:refs/remotes/origin/*"`, or use `+branch` syntax for a plain force on just that branch.
- **Stale `.git/*.lock` files** (sandboxed environments may fail to unlink them): remove `HEAD.lock`, `index.lock`, and `objects/*/tmp_obj_*` before retrying. In Cowork, if `rm` returns "Operation not permitted", request delete permission with the `allow_cowork_file_delete` tool rather than giving up.

## Phase 4: Build the Site

Build from `COMPANY-INFO.md` content on the `dev` branch. Keep it simple:

- Single-page or small multi-page static HTML/CSS/JS
- Click-to-call phone links (`tel:`), `mailto:` links, and social links throughout
- Mobile-first: most local-service customers arrive on phones
- Include business name, service area, and services in titles/headings for local SEO

### Contact form standard (standing proposal, not yet settled)

When a site needs a contact form, the default is a serverless function on your static hosting platform that emails submissions to the client, with a hidden honeypot field for spam. No third-party form service (such as a hosted form backend) without the client's sign-off, because that puts their visitors' data in a vendor they never chose. Form submissions are the client's data, full stop; {{COMPANY_NAME}} handles them, it does not own them. Flag this as a standing proposal when applying it: it is the working default until you settle it.

## Phase 5: Static Hosting Platform

In your static hosting platform's dashboard, connect the project to your git repo:

1. Connect the repo on your git hosting provider. Framework preset: None; build command: empty; output directory: `/` (or wherever the HTML lives) for a plain static site
2. Set the production branch to `main` (production deploys on push to `main`)
3. Confirm pushes to `dev` automatically create a preview deployment at a preview URL or dev subdomain. Use these for client review
4. Add the custom domain to the production project and follow your host's DNS instructions (easiest when the domain's DNS is already managed by the same platform)

## Definition of Done

- [ ] Signed SOW under the MSA, stating scope, price, timeline, content responsibilities, acceptance criteria, and the ownership model
- [ ] `COMPANY-INFO.md` with client info and website plan
- [ ] Content ownership confirmed in writing; photo consent verified for any images of people
- [ ] Git repo with `main` + `dev`, `.gitignore` covering `.env`
- [ ] Repo in your organization's account on your git hosting provider, both branches pushed
- [ ] Site built and reviewed on dev preview URL
- [ ] Privacy policy page live if the site collects any form data
- [ ] Accessibility baseline checked (alt text, heading order, contrast, keyboard navigation)
- [ ] Static hosting platform project connected, custom domain live on `main`
- [ ] Registrar and hosting platform accounts in the client's name with {{COMPANY_NAME}} as administrator
- [ ] Client contact links (phone/email/social) verified on the live site

## At Offboarding

When a client exits, follow msp-offboarding. For their website that means: transfer the repo (on your git hosting provider) to the client or their successor provider, confirm the client controls their registrar, DNS, and static hosting platform account, and remove {{COMPANY_NAME}}'s administrator access last, only after everything else is confirmed in their hands.
