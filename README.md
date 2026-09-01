# Resource Inbox — landing page

A single, static, responsive Astro landing page for the
**Resource Inbox** idea (Workshop 1 build). The page is sourced from five
approved answers — every claim is traceable to one of them.

> **Build status:** local build verified. Render deployment is pending authorization for Render to fetch the private GitHub repository. No backend, auth, or external runtime service has been added. The waitlist form does **not** submit anywhere yet (it is a static placeholder, confirmed below).

## Local development

```sh
npm install
npm run dev          # → http://localhost:4321
```

The dev server is the only place to preview changes. There is no remote
preview, no staging, no deployment configured.

## Production build

```sh
npm run build        # → ./dist/
npm run preview      # serve the built site locally on :4321
```

`npm run build` must pass with zero errors before reporting completion.

## Project structure

```
src/
  layouts/BaseLayout.astro    HTML scaffold, meta, OG tags
  styles/global.css           Design tokens + base styles (single file)
  components/
    Nav.astro                 Sticky identity bar
    Hero.astro                Title, lede, primary CTA, build-status strip
    Problem.astro             Section 01 — the problem
    HowItWorks.astro          Section 02 — three concrete actions
    Benefit.astro             Section 03 — what you get
    Sponsorship.astro         Section 04 — sponsorship-and-validation model
    Waitlist.astro            Section 05 — static placeholder form
    Footer.astro              Workshop tag + scope reminders
  pages/index.astro           All sections composed here
public/                       favicon
```

## Where each section comes from

| Page section     | Sourced from                                  |
| :--------------- | :-------------------------------------------- |
| Hero             | Q1 (audience) + Q4 (outcome)                  |
| Problem          | Q1                                           |
| How it works     | Q3                                            |
| What you get     | Q4                                            |
| Sponsorship      | Q5                                            |
| Waitlist         | Workshop constraint (no fake form submission) |

Q2 (the simplest solution) is the implicit product stance that connects
sections 01 → 02 → 03.

## Facts still requiring confirmation

These are deliberately **not** on the landing page. Do not add them to the
page until you have a dated, approved source for each.

- Sponsorship tiers and prices
- Exact review threshold before a paid listing surfaces
- Subscriber pricing
- Subscriber count, user count, or "X people found this useful" claims
- Testimonials or named endorsements
- Sponsor logos, partner credits, or organizer affiliations for Burning Token
  or any other event/program (see `../burning-token/AGENTS.md`)
- Product screenshots or dashboard mockups beyond the inline verdict card
- Release date or waitlist launch date
- Render deployment is pending authorization for Render to fetch the private GitHub repository. See `../../workstreams/pre-hack-workshops-september-2026/docs/render-deployment-record.md`.

## What this build deliberately excludes

- No Astro installed globally — `create-astro` was used to scaffold this
  project; install with `npm install` inside the directory.
- No Tailwind, no UI framework — vanilla CSS only.
- No fonts loaded over the network — system fonts only (editorial but
  offline-safe).
- No external image hosts, no analytics, no tracking pixels, no third-party
  scripts.
- No form submission wired. The `<form>` posts to `#` and the README states
  it is a stub.
- A private GitHub repository now contains the local landing page. Render CLI is authenticated and its workspace is set, but the Render GitHub integration has not yet been authorized to fetch that private repo. See `../../workstreams/pre-hack-workshops-september-2026/docs/render-deployment-record.md`.
- No modified files in `../agentic-coding-workshop-deck/` or
  `../tenki-pi-sandbox-launcher/`.

## Replaying the setup

A full prompt-and-output transcript is recorded in [`SETUP-LOG.md`](./SETUP-LOG.md).
That log + this project tree is everything you need to reproduce the build in
a live workshop.
