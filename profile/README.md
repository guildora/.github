<div align="center">

# Guildora

**The platform for building powerful community applications.**

Extend your community hub with custom pages, bot integrations, API routes, and more — all in one framework.

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Built with Vue](https://img.shields.io/badge/Built%20with-Vue-42b883?logo=vue.js&logoColor=white)](https://vuejs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-Ready-3178c6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Powered by Nitro](https://img.shields.io/badge/API-Nitro-18181b?logo=nuxt.js&logoColor=white)](https://nitro.unjs.io/)

</div>

---

## What is Guildora?

Guildora is a developer platform for creating **community applications** that integrate deeply with your Hub. Think of it as an app marketplace for communities — where developers ship full-featured tools with their own pages, backend logic, bot commands, and configuration, all within a unified ecosystem.

Whether you're building a moderation dashboard, a leaderboard system, a custom onboarding flow, or an event manager — Guildora gives you the structure and infrastructure to ship it fast.

---

## Key Concepts

| Concept | Description |
|---|---|
| **Hub Pages** | Vue-powered frontend pages served inside the community Hub, supporting role-based access (user / moderator / admin) |
| **API Routes** | Server-side endpoints built on the [Nitro](https://nitro.unjs.io/) framework — fast, type-safe, and deployable anywhere |
| **Bot Hooks** | React to community events and slash commands directly from your app |
| **Config Fields** | Expose configurable settings for community admins without writing any UI |
| **i18n** | Built-in internationalization support — ship your app in multiple languages from day one |
| **Role Gating** | Fine-grained access control for pages and features based on community roles |

---

## Architecture Overview

```
guildora-app/
├── pages/            # Vue components — user, moderator, and admin views
├── api/              # Nitro API route handlers
├── bot/              # Event hooks and bot command definitions
├── locales/          # i18n translation files (e.g. en.json, de.json)
└── manifest.json     # App identity, config fields, permissions
```

Apps declare their capabilities in a `manifest.json` — the single source of truth for what your app exposes to the Hub: its pages, config schema, bot permissions, and marketplace metadata.

---

## Repositories

### [`guildora-app-template`](https://github.com/guildora/guildora-app-template)

> A ready-to-use starter for building Guildora apps.

The official template demonstrates all major integration points with working examples:

- Role-gated Hub pages (user / moderator / admin tiers)
- API routes with type-safe handlers
- Bot event hooks and command definitions
- Config field declarations
- English and German i18n out of the box

**Stack:** Vue · TypeScript · Nitro · MIT License

---

## Getting Started

```bash
# 1. Clone the template
git clone https://github.com/guildora/guildora-app-template my-app
cd my-app

# 2. Install dependencies
npm install

# 3. Customize manifest.json with your app identity and config

# 4. Implement your pages, API routes, and bot hooks

# 5. Sideload into your Guildora instance for local testing

# 6. Publish to the marketplace when ready
```

---

## Developer Experience

- **Opinionated structure** — clear separation of pages, API, bot logic, and translations
- **Type safety throughout** — TypeScript for all backend and integration code
- **Reactive frontend** — Vue components with full access to Hub context and community data
- **Zero-config i18n** — drop a JSON file per locale, the platform handles the rest
- **Role-aware navigation** — the Hub automatically adjusts sidebar entries based on member roles

---

## Contributing

Guildora is in active development. Contributions, feedback, and app submissions are welcome.

If you build something with Guildora, open an issue or discussion — we'd love to feature it.

---

<div align="center">

**[Explore the template →](https://github.com/guildora/guildora-app-template)**

</div>
