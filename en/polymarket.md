# Polymarket

## 🎯 What is Polymarket?

[Polymarket](https://polymarket.com) is a decentralized prediction market on the **Polygon** blockchain. Users buy and sell **shares** of binary outcomes — `YES` or `NO` — on real-world questions: elections, sports, crypto prices, weather, you name it.

Share prices are quoted in cents (`0¢–100¢`) and reflect the market's implied probability of the outcome. A `YES` share at `23.4¢` means the market is pricing the event at a ≈23.4 % chance of happening. When an event resolves, winning shares pay `$1` each; losing shares pay `$0`.

> [!NOTE]
> Drops Bot does **not** trade for you. It only monitors Polymarket activity and reports it via Telegram — what you do with that information is up to you.

## 📊 What Drops Bot adds

Drops Bot delivers **instant, real-time alerts** for Polymarket activity on Polygon — straight to your Telegram. You don't need a Polymarket account, you don't sign transactions, and your funds are never touched. The bot reads public on-chain data and surfaces it.

> [!NOTE]
> Polymarket Event Tracking launched on **March 10, 2026** and is available across all subscription plans. Limits scale with your plan tier — see [Plan Limits](./plan-limits.md).

<!-- screenshot: Polymarket section in the bot's Tracking menu -->

## 🔍 Two Ways to Track

| Mode | What it watches | How to set up |
|---|---|---|
| 🟦 **Event Tracking** | One specific market, regardless of who trades on it | Forward a `polymarket.com/event/<slug>` URL to the bot, or `/polymarket → Add Event/Wallet` |
| 🔁 **Wallet Polymarket Activity** | One wallet's Polymarket trades, across every market it touches | Toggle Polymarket in the wallet's `Filters → Events` ([details](./wallet-activity.md)) |

The two modes complement each other — track a few hot markets directly, and let wallet monitoring surface everything else.

## 🧭 Anatomy of `/polymarket`

`/polymarket` is the master command. Type it to open your watchlist. The reply takes one of three shapes:

| State | When it shows | Body |
|---|---|---|
| **Empty** | No odds tracked yet | `"You are not tracking any Polymarket events yet"` plus a 4-button keyboard: **Add Event/Wallet**, **Polymarket Wallets**, **Trending Events**, **Back**. |
| **Populated** | You have ≥ 1 tracked odd | `"Your Polymarket Events Watchlist"` listing rows like `🟦 Will <outcome>? <price>¢`, each with inline 🗑 (remove) and ✏️ (edit) deep-links. |
| **Upsell** | Plan limit hit | A card whose only CTA is **Build Custom Plan** — see [Plan Limits](./plan-limits.md). |

You can also reach the watchlist via `/menu → Tracking → Polymarket Events`, or add a new event by forwarding any `polymarket.com/event/<slug>` URL straight into the bot chat.

## 🌐 Network Coverage

Polymarket Events on Drops Bot operate exclusively on **Polygon**.

> [!WARNING]
> **Polygon only.** Polymarket runs on Polygon PoS, and all tracking happens there. Wallet activity on Ethereum, Base, Solana, or any other network will **not** produce Polymarket alerts — even if the same wallet also trades on Polymarket.

## 💼 Use Cases

* **Traders** — Catch sudden price moves on markets you care about before the rest of the market reacts.
* **Researchers & analysts** — Build a watchlist of resolution-driving events (elections, sports, crypto, macro) and follow them straight from Telegram.
* **Whale watchers** — Tag wallets known for large Polymarket positions and get pinged the moment they move size.
* **Community / channel admins** — Route Polymarket alerts to a Telegram group or channel via [Bot for Groups and Channels](https://etherdrops.gitbook.io/etherdrops-bot/advanced-tools/bot-for-groups-and-channels) and keep your audience updated automatically.

## 📖 Glossary

Terms used throughout these docs:

| Term | Meaning |
|---|---|
| **Event** | A parent market on Polymarket — one question with a single resolution date (e.g., *"2026 FIFA World Cup Winner"*). |
| **Outcome** | A specific possibility within an event (e.g., *"France wins YES"*). Multi-outcome events split a question into many `YES` / `NO` bets. |
| **Odd** | Drops Bot's UI label for a tracked outcome. Each row in `/polymarket` is one odd. You can edit / delete each odd independently. |
| **Share** | A position unit on Polymarket. A `YES` share pays `$1` if the outcome resolves true, `$0` otherwise. |
| **Price (¢)** | Per-share price in cents. Equivalent to the market's implied probability — e.g., `23.4¢` ≈ 23.4 % chance. |
| **Resolution** | The moment an event's outcome is finalized and shares pay out. Tracking stops automatically at resolution. |
| **Share-swap** | A trade where shares change hands directly between users on the order book — the data source for **♻️ Swaps Alert**. |
| **Volume** | Cumulative USD value of trades on a market. Used by **📊 Volume Target** alerts. |

## 🚀 Get Started

* 👉 [**Quickstart**](./quickstart.md) — Track your first event in under 60 seconds.
* 🔁 [**Wallet Polymarket Activity**](./wallet-activity.md) — Watch wallets that bet on Polymarket.
* ❓ [**FAQ & Troubleshooting**](./faq-and-troubleshooting.md) — Common questions answered.

For the full page list, see the [section index](../README.md).

## ❓ FAQ

<details>
<summary>Do I need a Polymarket account to use this?</summary>

No. You only need the **public event URL**. Tracking is read-only and never touches funds.

</details>

<details>
<summary>Does the bot trade on Polymarket for me?</summary>

No. Drops Bot is **observation-only** — it surfaces activity so you can react manually in your wallet or on Polymarket directly.

</details>

<details>
<summary>Is there an extra fee for Polymarket tracking?</summary>

No. Polymarket Events are included in every plan; only the per-plan **odd limit** differs. See [Plan Limits](./plan-limits.md).

</details>

<details>
<summary>What's the difference between an event, an outcome, and an odd?</summary>

The **event** is the parent market ("2026 FIFA World Cup Winner"). Each **outcome** is one possibility (France YES, Spain YES, …). When you track an outcome in the bot, that tracked row is called an **odd** — see the [Glossary](#-glossary) above.

</details>

---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on the current page URL with the `ask` query parameter:

```
GET https://etherdrops.gitbook.io/etherdrops-bot/<page-path>.md?ask=<question>
```

The question should be specific, self-contained, and written in natural language.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.

Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
