# Add Polymarket Event

## 📋 Contents

* [Tracking a Specific Event](#-tracking-a-specific-event)
* [Walkthrough](#-walkthrough)
* [Bulk Adding](#-bulk-adding)
* [What Counts as a Valid Link](#-what-counts-as-a-valid-link)
* [FAQ](#-faq)
* [Troubleshooting](#-troubleshooting)

## ➕ Tracking a Specific Event

Adding a Polymarket event tells the bot to watch **one specific market** and notify you when meaningful things happen on it — price shifts, large trades, volume bursts. This is the most direct way to follow markets you already care about.

> [!NOTE]
> **Two equivalent entry points.** You can either forward an event link directly to the bot chat, or navigate via `Main Menu → Tracking → Polymarket Events → ➕ Add Event`. Both end up in the same place.

## 🪜 Walkthrough

### 1. Pick the market

Open the Polymarket event you want to follow. It can be a single binary market, a multi-outcome market, or a derived market — what matters is that the URL points to one event.

![Polymarket multi-outcome event page in the browser](../../../media/screenshots/polymarket/event-page.png)

### 2. Copy the event link

From the browser address bar, copy the full URL. Mobile share-sheet "Copy Link" works equally well.

### 3. Send the link to Drops Bot

Open your Drops Bot chat in Telegram and paste the link. The bot detects the Polymarket domain and replies with the **odds-selection screen**:

* The event title in the message body
* `Expires:` line — resolution date
* `Select ✅ Odds to Track:` header
* One row per outcome in the form `🟦 Will <outcome>? <price>¢`
* Action buttons: **Select All Yes**, **Select All No**, **Back**
* For events with more than 10 outcomes, a pagination row appears: `⏪ ⬅️ 1 ➡️ ⏩` (10 odds per page)

<!-- screenshot: bot preview message for a Polymarket event -->

### 4. Confirm

Pick individual outcomes by tapping their rows, or tap **Select All Yes** / **Select All No** to track all outcomes at once. Each selected odd gets a ✅ marker. **Back** discards the selection.

> [!TIP]
> **Tracking active.** Alerts begin immediately based on your current [alert settings](./alerts-and-filters.md). Default thresholds are conservative — tune them later if you want more or fewer pings.

### 5. (Optional) Adjust per-event settings

Open the event in `Polymarket Events → Edit` and customise:

* Alert frequency for this event
* Minimum price movement for a price alert
* Minimum trade size for a whale alert
<!-- VERIFY: exact per-event setting names -->

See [Configuring Polymarket Alerts](./alerts-and-filters.md) for the full settings reference.

## 📦 Bulk Adding

<!-- VERIFY: confirm whether bulk-add via TXT/CSV is supported for Polymarket events (similar to wallets / coins bulk add) -->

If you have a list of events to track, the same bulk-add patterns that exist for coins and wallets are expected to apply — paste multiple links separated by newlines, or upload a TXT file containing one URL per line. Confirm the exact format in the bot's `➕ Add Event` flow before relying on it.

## 🔍 What Counts as a Valid Link

The bot accepts any direct **event URL** on `polymarket.com`. Examples that work:

```
https://polymarket.com/event/<event-slug>
https://polymarket.com/event/<event-slug>?<query-params>
```

Examples that **do not** work:

* Category or topic listings (`polymarket.com/markets`, `polymarket.com/sports`)
* The Polymarket home page
* Shortlinks or social-share previews that don't resolve to a canonical event URL

## ❓ FAQ

<details>
<summary>What happens when the event resolves?</summary>

Tracking stops automatically once the market resolves. The event remains in your list as a historical record but no longer counts against limits in the same way as active events. <!-- VERIFY: exact post-resolution behaviour -->

</details>

<details>
<summary>Can I track multiple outcomes of one event?</summary>

Yes. The odds-selection screen lets you pick individual outcomes one by one, or hit **Select All Yes** / **Select All No** to track every outcome at once. Each tracked **odd** appears as its own row in `/polymarket` and can be edited (✏️) or removed (🗑) independently.

> Each odd consumes **one slot** of your Polymarket Events quota. A 12-outcome event with `Select All Yes` will use 12 slots, not 1 — see [Plan Limits](./plan-limits.md).

</details>

<details>
<summary>Does adding an event cost gas or any on-chain action?</summary>

No. Tracking is purely off-chain on the bot's side. Your wallet is not touched and no transaction is signed.

</details>

<details>
<summary>How is this different from Wallet Polymarket Activity?</summary>

**Add Event** watches one specific market regardless of who trades on it.<br>**[Wallet Activity](./wallet-activity.md)** watches one specific wallet across all the Polymarket markets it touches. They are complementary, not alternatives.

</details>

## 🔧 Troubleshooting

| Issue | Likely Cause | Fix |
|---|---|---|
| "Invalid Polymarket link" | URL points to a listing page, not a specific event | Open the event itself and copy that URL |
| "Limit reached" | Plan quota for Polymarket Events exceeded | Remove unused events or [upgrade plan](./plan-limits.md) |
| Bot accepts link but says "event not found" | Polymarket has delisted or hidden the event | Pick a currently visible event |
| No alerts after adding | Thresholds too high, or market has no activity | Lower thresholds in [Alerts & Filters](./alerts-and-filters.md) |

## 📚 Related Pages

* [Quickstart](./quickstart.md) — the 4-step short version of this walkthrough
* [Event Management](./event-management.md) — view, edit, remove tracked odds
* [Configuring Polymarket Alerts](./alerts-and-filters.md) — tune thresholds per odd
* [Plan Limits](./plan-limits.md) — how many odds your tier supports

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
