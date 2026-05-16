# Polymarket Quickstart

## ⚡ Track your first event in under 60 seconds

1. Open [polymarket.com](https://polymarket.com) and click into the event you want to follow.
2. Copy the URL from the address bar — it should look like `https://polymarket.com/event/<slug>`.
3. Paste the URL into your Drops Bot chat and send it.
4. On the **odds-selection screen** that pops up, tap **Select All Yes** (or hand-pick specific outcomes), then **Back** to finish.

> [!TIP]
> **Done.** Each outcome you selected is now in your watchlist as an **odd**. The bot will ping you in Telegram on price moves and volume bursts according to its default thresholds. Type `/polymarket` any time to see the watchlist.

![Polymarket event page — copy the URL from the address bar at the top](../../../media/screenshots/polymarket/event-page.png)

> [!NOTE]
> **Prerequisites**
> * You have an active Drops Bot chat (`/start` already done).
> * You haven't hit your plan's Polymarket Event limit — see [Plan Limits](./plan-limits.md).

## ➡️ Next Steps

* ➕ [**Add Polymarket Event** — full walkthrough](./add-event.md), including the odds-selection screen, multi-outcome events, and pagination.
* 🔔 [Configure alert thresholds](./alerts-and-filters.md) — `Price Change`, `Price Target`, `Swaps Alert`, `Volume Target`.
* 🔁 [Track wallets that bet on Polymarket](./wallet-activity.md) — surface whale moves automatically.
* 🛠️ [Manage your watchlist](./event-management.md) — view, edit, remove.

Stuck on something? See the [combined FAQ + Troubleshooting](./faq-and-troubleshooting.md).

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
