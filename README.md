# KiloClaw Workspace

KiloClaw is an AI agent workspace designed for autonomous software development, research, and business operations. This repository serves as the persistent home for KiloClaw's identity, memory, skill library, and tooling configuration.

## Overview

The KiloClaw workspace is the central hub for an AI agent (named **Echo KiloClaw**) that assists Jay Alexander — founder of Alexander AI Solutions and the Liberty-Emporium ecosystem — with coding, sales, marketing, market research, and product development tasks.

Unlike a chatbot, KiloClaw is a persistent agent with:

- A **curated skill library** of battle-tested playbooks (growth hacking, SEO, market research, content creation, etc.)
- **Long-term memory** that persists across sessions via `MEMORY.md` and daily memory files
- An **identity system** (`IDENTITY.md`, `SOUL.md`, `USER.md`) that defines the agent's persona and operating principles
- A **heartbeat mechanism** for proactive periodic checks (email, calendar, reminders, project status)
- **Tool discovery** and configuration documented in `TOOLS.md`

The workspace is organized around **skills** — each skill is a directory containing a `SKILL.md` file with detailed instructions, frameworks, and workflows. KiloClaw loads and executes these skills as needed.

## Features

- **Skill Library** — 9 built-in skills covering growth, SEO, market research, content, email, sales outreach, app launches, discovery calls, and Shopify/GMC auditing
- **Persistent Memory** — `MEMORY.md` for long-term memories, `memory/YYYY-MM-DD.md` for daily logs
- **Identity Framework** — `IDENTITY.md` (who the agent is), `SOUL.md` (personality and principles), `USER.md` (who Jay is)
- **Proactive Heartbeat** — `HEARTBEAT.md` configures periodic checks for emails, calendar, mentions, weather, and project status
- **Tool Configuration** — `TOOLS.md` documents the environment, security context, Kilo CLI usage, and process model
- **Agent Guidelines** — `AGENTS.md` defines workspace conventions, memory discipline, communication rules, and group-chat etiquette
- **Skill Metadata** — each skill directory contains `.clawhub/origin.json` (source tracking) and `_meta.json` (metadata)
- **Brain Backup** — the entire workspace is backed up to a private Git repository for restoration across sessions

## Available Skills

| Skill | Description |
|---|---|
| **growth-hacking** | B2B SaaS growth playbook: ICE scoring, viral loop design, acquisition channel stacking, activation optimization, retention engineering, AARRR metrics |
| **owl-seo-audit** | Full SEO audit: technical, content, backlinks, competitive analysis |
| **owl-market-research** | Comprehensive market research and competitor analysis |
| **owl-content-creator** | Blog, social media, and SEO content creation |
| **owl-email-campaign** | High-converting email marketing campaigns |
| **owl-sales-outreach** | Cold emails, LinkedIn messages, follow-up sequences |
| **app-launch** | Mobile app launch playbook: first 1000 users strategy |
| **discovery-call-debrief** | Structured extraction and action items after sales calls |
| **shopify-gmc-misrepresentation-auditor** | Audit Shopify stores for Google Merchant Center violations |

## Tech Stack

| Layer | Technology |
|---|---|
| **Agent Framework** | OpenClaw / KiloClaw |
| **CLI** | `kilo` — agentic coding assistant with interactive and autonomous modes |
| **Process Management** | Controller-supervised (no systemd) |
| **Storage** | Workspace files on disk + Git backup to private repo |
| **Environment** | Debian Bookworm (slim), Go + Python available |
| **Config** | `/root/.openclaw/` (agent config, extensions), `/root/.config/kilo/` (CLI config) |

### Workspace Structure

```
kiloclaw-workspace/
├── AGENTS.md                  # Workspace conventions, memory rules, communication
├── IDENTITY.md                # Agent identity: name (KiloClaw), vibe, emoji
├── SOUL.md                    # Personality and operating principles
├── USER.md                    # About the human (Jay Alexander)
├── TOOLS.md                   # Environment, security context, CLI usage
├── HEARTBEAT.md               # Periodic check configuration
├── MEMORY.md                  # Long-term curated memories
├── skills/                    # Skill library
│   ├── app-launch/
│   ├── discovery-call-debrief/
│   ├── growth-hacking/
│   ├── owl-content-creator/
│   ├── owl-email-campaign/
│   ├── owl-market-research/
│   ├── owl-sales-outreach/
│   ├── owl-seo-audit/
│   └── shopify-gmc-misrepresentation-auditor/
└── (memory/                   # Daily memory files, created at runtime)
```

## Quick Start

### Restoring the Workspace

On a fresh KiloClaw instance, restore this workspace from the backup repository:

```bash
cd /root/.openclaw/workspace
git pull origin main
```

This restores all skills, identity files, and memory.

### Creating a New Workspace

To initialize a fresh workspace from this repo:

```bash
# 1. Clone the repository
git clone https://github.com/Liberty-Emporium/kiloclaw-workspace.git
cd kiloclaw-workspace

# 2. Copy to the OpenClaw workspace directory
cp -r . /root/.openclaw/workspace/

# 3. (Optional) Set up the Kilo CLI
kilo --version    # verify installation
```

### Using Skills

Skills are loaded on demand. When a task matches a skill's trigger, KiloClaw reads the skill's `SKILL.md` and follows its instructions. Skills can be updated or extended by editing the `SKILL.md` file in the relevant skill directory.

### Running Periodic Checks (Heartbeat)

The heartbeat mechanism is configured in `HEARTBEAT.md`. KiloClaw uses this file to decide what to check during periodic heartbeat polls. To modify what gets checked, edit the file and add your own checklist items.

## License

MIT License — Copyright (c) 2026 Jay Alexander

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
