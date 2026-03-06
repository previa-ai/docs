# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Product Context

**Previa** is an AI-powered prediction market intelligence platform that aggregates news, social media, and market data to generate confidence scores and insights for traders on Kalshi and Polymarket.

This repo (**previa-docs**) is the user-facing documentation site. It explains how to use the Previa web app: browsing markets, understanding AI scores, setting alerts, linking trading accounts, managing your account, and choosing a plan. Built with Mintlify and deployed automatically via the Mintlify GitHub app.

### Where this fits

```
previa-docs (this repo)
    │
    │  Documents the features of:
    ▼
previa-web-app (Next.js, user-facing app)
    │
    │  Calls /v1/* with Firebase auth
    ▼
previa-backend (Hono, Cloud Run)
    │
    │  Proxies market data via POLLER_API_URL
    ▼
previa-poller (Hono, Cloud Run)
    │
    ▼
Cloud SQL (PostgreSQL 17)
```

The marketing website (previa-website) links to these docs from its `/docs` page.

## Persona

The engineer working on this repo is a technical writer or product-minded engineer who:
- Writes clear, task-oriented documentation for prediction market traders
- Structures content by user intent: quickstart, how-to guides, reference, explanations
- Keeps docs in sync with web app features as they ship
- Uses Mintlify's MDX components (callouts, tabs, code blocks, cards)
- Maintains content fragments in `snippets/` for reuse across pages

## Commands

```bash
# Development
pnpm add -g mint        # Install Mintlify CLI (first time)
mint dev                # Preview at http://localhost:3000

# Validation
mint broken-links       # Check internal links
mint validate           # Validate build
```

There are no test commands or build steps — Mintlify handles the build on deploy.

## Structure

```
previa-docs/
├── docs.json               # Site config, navigation, theme
├── index.mdx               # Welcome / landing page
├── quickstart.mdx           # 5-minute quickstart
├── supported-platforms.mdx  # Kalshi, Polymarket
├── markets/                 # Market scanner, detail, watchlist
├── intelligence/            # AI scores, insights, scoring methodology
├── alerts/                  # Alert setup, types, notification prefs
├── portfolio/               # Account linking, position tracking
├── account/                 # Profile, security, orgs, data privacy
├── plans/                   # Pricing, upgrading, billing
├── api-reference/           # API docs (coming soon)
└── snippets/                # Reusable content fragments
```

## Documentation Sections

| Section | Covers |
|---|---|
| **Markets** | Browsing markets, filtering by platform/category/status, market detail view, watchlist |
| **Intelligence** | AI confidence scores (5-component breakdown), scoring methodology, insights feed |
| **Alerts** | Creating alert rules (price threshold, score shift, news catalyst, volume spike), notification channels |
| **Portfolio** | Connecting Kalshi/Polymarket accounts, position tracking, P&L summary |
| **Account** | Profile settings, MFA, organization management, linked OAuth accounts, GDPR data export/deletion |
| **Plans** | Free vs Pro vs Team tiers, billing, upgrading |

## Key conventions

- Navigation is defined in `docs.json` — update it when adding new pages
- Use Mintlify components (`<Card>`, `<CardGroup>`, `<Tabs>`, `<Callout>`, `<Steps>`) for structured content
- Every page should stand alone — don't use "see above" references
- Keep the quickstart under 5 minutes to first success
- When documenting features, focus on what the user can do, not internal implementation
- Reusable content goes in `snippets/` and is included via MDX imports

## Deployment

Changes pushed to the default branch deploy automatically via the Mintlify GitHub app. No CI/CD workflows to manage.
