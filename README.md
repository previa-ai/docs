# Previa Documentation

User-facing documentation for [Previa](https://useprevia.com) — AI-powered prediction market intelligence.

Built with [Mintlify](https://mintlify.com).

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

## Development

```bash
pnpm add -g mint
mint dev
```

Preview at `http://localhost:3000`.

## Deploying

Changes pushed to the default branch are deployed automatically via the Mintlify GitHub app.

## Validation

```bash
mint broken-links   # Check internal links
mint validate       # Validate build
```
