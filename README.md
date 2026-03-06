# previa-docs

User-facing documentation for the [Previa](https://useprevia.com) platform — AI-powered prediction market intelligence. Covers onboarding, market scanning, AI scoring methodology, alerts, portfolio tracking, account management, and billing.

Built with [Mintlify](https://mintlify.com). Deployed automatically on push to the default branch via the Mintlify GitHub app.

## Structure

```
previa-docs/
├── docs.json               # Site config, navigation, theme
├── index.mdx               # Welcome / landing page
├── quickstart.mdx           # 5-minute quickstart
├── supported-platforms.mdx  # Kalshi, Polymarket, and upcoming platforms
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

## Development

```bash
pnpm add -g mint
mint dev
```

Preview at `http://localhost:3000`.

## Validation

```bash
mint broken-links   # Check internal links
mint validate       # Validate build
```

## Related Services

| Service | Relationship |
|---|---|
| `previa-web-app` | The app this documentation describes |
| `previa-website` | Marketing site links to docs from `/docs` page |
| `previa-backend` | API behavior documented in API reference section |
