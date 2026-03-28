<div align="center">

# Guildora

**The open platform for building and running powerful Discord communities.**

A modern, self-hostable community platform with an extensible app ecosystem — landing pages, a community hub, a marketplace for extensions, and a Discord bot, all in one.

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Built with Vue](https://img.shields.io/badge/Built%20with-Vue%203-42b883?logo=vue.js&logoColor=white)](https://vuejs.org/)
[![Nuxt 4](https://img.shields.io/badge/Nuxt-4-00DC82?logo=nuxt.js&logoColor=white)](https://nuxt.com/)
[![TypeScript](https://img.shields.io/badge/TypeScript-Ready-3178c6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)

</div>

---

## What is Guildora?

Guildora is a full-stack platform for Discord communities that goes beyond a simple bot. It provides a **public landing page**, an **internal community hub** with role-based access, a **marketplace** for community extensions, and a **Discord bot** — all connected and working together.

Community developers can build custom apps (pages, API routes, bot hooks, configurations) that integrate directly into the hub and are distributed through the marketplace.

---

## Platform Overview

| Component | Description | Tech |
|---|---|---|
| **[Web](https://github.com/guildora/guildora)** | Public landing page with Discord OAuth | Nuxt 4 |
| **[Hub](https://github.com/guildora/guildora)** | Internal community hub — members, moderation, admin, app sideloading | Nuxt 4 + Nitro |
| **[Marketplace](https://github.com/guildora/marketplace)** | App marketplace, developer portal, admin review panel | Nuxt 4 |
| **[CMS](https://github.com/guildora/guildora)** | Editorial content management | Payload CMS 3 + Next.js |
| **[Bot](https://github.com/guildora/guildora)** | Discord bot — voice tracking, guild sync, slash commands, app integration | Discord.js |
| **[Docs](https://github.com/guildora/docs)** | Architecture, API contracts, guides for developers, hosters, and users | Markdown |

---

## Architecture

```
guildora/                          ← Core monorepo (Turbo + pnpm)
├── apps/
│   ├── web/                       ← Public landing (port 3000)
│   ├── hub/                       ← Community hub (port 3003)
│   ├── cms/                       ← Payload CMS (port 3002)
│   └── bot/                       ← Discord bot (port 3050)
├── packages/
│   ├── shared/                    ← Drizzle schema, DB client, utilities
│   └── app-sdk/                   ← TypeScript SDK for community apps
│
marketplace/                       ← Standalone Nuxt 4 app (port 3004)
├── app/                           ← Pages, components, composables
└── server/                        ← API routes, GitHub OAuth, AI reviews
│
apps/                              ← Community app examples & templates
├── guildora-app-template/         ← Starter template
├── ticket-system/                 ← Ticket management with Kanban board
├── voice-rooms/                   ← Temporary voice room creation
├── guildai/                       ← AI-powered admin assistant
└── events/                        ← Event management
```

---

## Key Features

- **Community Hub** — Role-based dashboards for users, moderators, and admins with customizable themes
- **App Ecosystem** — Sideload community-built Vue apps with their own pages, API routes, bot hooks, and config
- **Marketplace** — Browse, submit, and review community extensions with AI-powered code review
- **Discord Integration** — OAuth authentication, voice tracking, guild sync, slash commands
- **Internationalization** — Built-in i18n support (German + English) across the platform
- **Self-Hostable** — Docker Compose setup for running your own instance

---

## Tech Stack

| Layer | Technologies |
|---|---|
| **Frontend** | Vue 3, Nuxt 4, Tailwind CSS |
| **Backend** | Nitro, Payload CMS 3, Next.js 15 |
| **Database** | PostgreSQL, Drizzle ORM |
| **Bot** | Discord.js |
| **Auth** | Discord OAuth (Hub), GitHub OAuth (Marketplace) |
| **Build** | TypeScript, Turbo, pnpm workspaces |
| **AI** | Anthropic Claude API (code reviews) |
| **Integrations** | Linear (issue tracking), GitHub Webhooks, AWS S3 |

---

## Getting Started

```bash
# Clone the repository
git clone https://github.com/guildora/guildora.git
cd guildora

# Install dependencies
pnpm install

# Set up environment variables
cp guildora/.env.example guildora/.env
cp marketplace/.env.example marketplace/.env

# Run database migrations
pnpm db:migrate

# Start all services (Hub, Web, CMS, Bot, Marketplace)
pnpm dev
```

---

## Building Apps

Guildora apps are Vue-based extensions that plug into the community hub. Each app declares its capabilities in a `manifest.json`:

```
my-app/
├── pages/            # Vue components — user, moderator, and admin views
├── api/              # Nitro API route handlers
├── bot/              # Event hooks and bot command definitions
├── locales/          # i18n translation files
└── manifest.json     # App identity, config fields, permissions
```

Start with the **[App Template](https://github.com/guildora/guildora-app-template)** for working examples of all integration points.

---

## Repositories

| Repository | Description |
|---|---|
| [`guildora`](https://github.com/guildora/guildora) | Core platform — landing, hub, CMS, bot |
| [`marketplace`](https://github.com/guildora/marketplace) | App marketplace & developer portal |
| [`docs`](https://github.com/guildora/docs) | Platform documentation |
| [`guildora-app-template`](https://github.com/guildora/guildora-app-template) | Starter template for building apps |

---

## Contributing

Guildora is in active development. Contributions, feedback, and app submissions are welcome.

If you build something with Guildora, open an issue or discussion — we'd love to feature it.

---

<div align="center">

**[Documentation](https://github.com/guildora/docs)** · **[App Template](https://github.com/guildora/guildora-app-template)** · **[Marketplace](https://github.com/guildora/marketplace)**

</div>
