# Polymarket — Documentation Section

This folder contains the **foundational documentation** for the Polymarket tracking feature of [EtherDrops Bot](https://etherdrops.gitbook.io/etherdrops-bot/), written in the same GitBook-friendly style as the rest of the public docs and enhanced with FAQ + troubleshooting patterns from [docs.onfomo.com](https://docs.onfomo.com/).

> **Status:** drafts ready for review and screenshot insertion. Items marked `<!-- VERIFY -->` require confirmation against the live bot UI before publishing.

## 🌍 Languages

| | Path |
|---|---|
| 🇬🇧 English | [`./en/`](./en/) |
| 🇷🇺 Русский | [`./ru/`](./ru/) |

## 📑 Pages

| # | Page (EN) | Page (RU) | Purpose |
|---|---|---|---|
| 1 | [polymarket.md](./en/polymarket.md) | [polymarket.md](./ru/polymarket.md) | Overview / hub page |
| 2 | [quickstart.md](./en/quickstart.md) | [quickstart.md](./ru/quickstart.md) | First event in 60 seconds |
| 3 | [add-event.md](./en/add-event.md) | [add-event.md](./ru/add-event.md) | Full how-to for event link tracking |
| 4 | [wallet-activity.md](./en/wallet-activity.md) | [wallet-activity.md](./ru/wallet-activity.md) | Polymarket activity on watched wallets |
| 5 | [event-management.md](./en/event-management.md) | [event-management.md](./ru/event-management.md) | View / edit / remove tracked events |
| 6 | [alerts-and-filters.md](./en/alerts-and-filters.md) | [alerts-and-filters.md](./ru/alerts-and-filters.md) | Notification tuning & filters |
| 7 | [plan-limits.md](./en/plan-limits.md) | [plan-limits.md](./ru/plan-limits.md) | Plan tiers & event limits |
| 8 | [faq-and-troubleshooting.md](./en/faq-and-troubleshooting.md) | [faq-and-troubleshooting.md](./ru/faq-and-troubleshooting.md) | FAQ + problem/cause/fix table |

## 🎨 Style conventions

- **`# H1`** — one per page, no emoji
- **`## H2`** — section headings, emoji prefix for visual scanning (📊 🔍 🌐 💼 🚀 ❓ 🔧)
- **`{% hint style="info|warning|success" %}`** — GitBook callouts
- **`{% stepper %}`** — numbered walkthroughs
- **`{% tabs %}`** — parallel UI options
- **Tables** for plan limits and troubleshooting
- **`<details><summary>`** for FAQ entries (collapsible)
- **Footer** — every page ends with the standard `Agent Instructions: Querying This Documentation` block (matches the rest of EtherDrops GitBook)

## 🧱 Source of truth for facts

All factual claims (limits, dates, menu paths) are derived from the local mirror of the official docs:

```
/Users/kwlad1ck/Projects/DropsBotTests/docs/_external/drops-bot-gitbook.md
```

Spots where the mirror does not provide a clear answer are tagged `<!-- VERIFY: <description> -->` inline so reviewers can either confirm or replace before publishing.

## 🖼️ Screenshots

Screenshot placeholders look like `<!-- screenshot: short description -->`. Drop matching images into `media/screenshots/polymarket/` and replace each placeholder with the markdown image reference at publish time.
