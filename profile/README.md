<div align="center">

# Guildora

**The open platform for building and running powerful Discord communities.**

A modern, self-hostable community platform with an extensible app ecosystem — landing pages, a community hub, an app marketplace, and a Discord bot, all in one.

[![PolyForm Noncommercial](https://img.shields.io/badge/License-PolyForm%20Noncommercial%201.0.0-blue.svg)](https://polyformproject.org/licenses/noncommercial/1.0.0)
[![Built with Vue](https://img.shields.io/badge/Built%20with-Vue%203-42b883?logo=vue.js&logoColor=white)](https://vuejs.org/)
[![Nuxt 4](https://img.shields.io/badge/Nuxt-4-00DC82?logo=nuxt.js&logoColor=white)](https://nuxt.com/)
[![TypeScript](https://img.shields.io/badge/TypeScript-Ready-3178c6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)

</div>

---

## What is Guildora?

Guildora is a full-stack platform for Discord communities that goes beyond a simple bot. It provides a **public landing page**, an **internal community hub** with role-based access, a **marketplace** for community apps, and a **Discord bot** — all connected and working together.

Community developers can build custom apps (pages, API routes, bot hooks, slash commands) that integrate directly into the hub and distribute them through the marketplace.

---

## Platform Overview

| Component | Description | Tech |
|---|---|---|
| **[Web](https://github.com/guildora/guildora)** | Public landing page with Discord OAuth | Nuxt 4 |
| **[Hub](https://github.com/guildora/guildora)** | Internal community hub — members, moderation, admin, app sideloading | Nuxt 4 + Nitro |
| **[Bot](https://github.com/guildora/guildora)** | Discord bot — voice tracking, guild sync, slash commands, app integration | Discord.js |
| **Marketplace** | App store and developer portal at [guildora.app](https://guildora.app) | Nuxt 4 + Nitro |
| **[Docs](https://github.com/guildora/docs)** | Architecture, API contracts, guides for developers, hosters, and users | Markdown |

---

## Architecture

```
guildora/                          ← Core monorepo (Turbo + pnpm)
├── apps/
│   ├── web/                       ← Public landing (port 3000)
│   ├── hub/                       ← Community hub (port 3003)
│   └── bot/                       ← Discord bot (port 3050)
├── packages/
│   ├── shared/                    ← Drizzle schema, DB client, types, utilities
│   ├── app-sdk/                   ← TypeScript SDK for community apps
│   └── mcp-server/                ← MCP server for AI-assisted landing page management
│
apps/                              ← Community app examples & templates
├── guildora-app-template/         ← Starter template
├── ticket-system/                 ← Support ticketing with Discord chat sync
├── voice-rooms/                   ← Temporary voice channel management
├── guildai/                       ← AI-powered admin assistant with MCP support
└── events/                        ← Event management with calendar and analytics
```

---

## Key Features

- **Community Hub** — Role-based dashboards for users, moderators, and admins with customizable themes
- **App Ecosystem** — Sideload community-built Vue apps with their own pages, API routes, bot hooks, slash commands, and config
- **App Marketplace** — Developer portal for publishing apps, admin review pipeline with AI-powered code review via Claude
- **Discord Integration** — OAuth authentication, voice tracking, guild sync, slash commands, bidirectional chat sync
- **Landing Page Builder** — Template-based sections with an MCP server for AI-assisted content management
- **Application Workflows** — Visual flow editor for structured community processes
- **Internationalization** — Built-in i18n support (German + English) across all apps
- **Self-Hostable** — Docker Compose setup for running your own instance

---

## Tech Stack

| Layer | Technologies |
|---|---|
| **Frontend** | Vue 3, Nuxt 4, Tailwind CSS, GSAP |
| **Backend** | Nitro |
| **Database** | PostgreSQL, Drizzle ORM |
| **Bot** | Discord.js 14 |
| **Auth** | Discord OAuth |
| **AI** | Anthropic Claude API (code review, admin assistant), MCP |
| **Build** | TypeScript, Turbo, pnpm workspaces |
| **Visualization** | Vue Flow, Chart.js |
| **Integrations** | Linear (issue tracking), GitHub Webhooks, AWS S3 |

---

## Community Apps

Guildora apps are Vue-based extensions that plug into the community hub. Each app declares its capabilities in a `manifest.json`:

```
my-app/
├── src/
│   ├── pages/        # Vue components — user, moderator, and admin views
│   ├── api/          # Nitro API route handlers
│   ├── bot/          # Event hooks and slash command definitions
│   └── i18n/         # Translation files (EN + DE)
└── manifest.json     # App identity, config fields, permissions, navigation
```

### Available Apps

| App | Description |
|---|---|
| **[App Template](https://github.com/guildora/guildora-app-template)** | Reference starter with all integration patterns |
| **Ticket System** | Support tickets with Kanban board and Discord chat sync |
| **Voice Rooms** | Temporary voice channels with lobby creation and auto-cleanup |
| **GuildAI** | AI admin assistant with streaming chat, action confirmations, and MCP support |
| **Events** | Event lifecycle management with templates, calendar, sign-ups, and analytics |

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

# Run database migrations
pnpm db:migrate

# Start all services (Hub, Web, Bot)
pnpm dev
```

---

## Repositories

| Repository | Description |
|---|---|
| [`guildora`](https://github.com/guildora/guildora) | Core platform — landing, hub, bot |
| [`docs`](https://github.com/guildora/docs) | Platform documentation |
| [`guildora-app-template`](https://github.com/guildora/guildora-app-template) | Starter template for building apps |

---

## Contributing

Guildora is in active development. Contributions, feedback, and app submissions are welcome.

If you build something with Guildora, open an issue or discussion — we'd love to feature it.

---

<div align="center">

**[Documentation](https://github.com/guildora/docs)** · **[Marketplace](https://guildora.app)** · **[App Template](https://github.com/guildora/guildora-app-template)**

</div>
