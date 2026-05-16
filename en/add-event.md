# Add Polymarket Event

## ➕ Tracking a Specific Event

Adding a Polymarket event tells the bot to watch **one specific market** and notify you when meaningful things happen on it — price shifts, large trades, volume bursts. This is the most direct way to follow markets you already care about.

{% hint style="info" %}
**Two equivalent entry points.** You can either forward an event link directly to the bot chat, or navigate via `Main Menu → Tracking → Polymarket Events → ➕ Add Event`. Both end up in the same place.
{% endhint %}

## 🪜 Walkthrough

{% stepper %}

{% step %}
### Pick the market

Open the Polymarket event you want to follow. It can be a single binary market, a multi-outcome market, or a derived market — what matters is that the URL points to one event.

<!-- screenshot: Polymarket event page in browser -->
{% endstep %}

{% step %}
### Copy the event link

From the browser address bar, copy the full URL. Mobile share-sheet "Copy Link" works equally well.
{% endstep %}

{% step %}
### Send the link to Drops Bot

Open your Drops Bot chat in Telegram and paste the link. The bot detects the Polymarket domain and replies with a preview of the event:

* Event title
* Current odds (Yes / No or per-outcome)
* 24h volume
* Resolution date (if available)

<!-- screenshot: bot preview message for a Polymarket event -->
{% endstep %}

{% step %}
### Confirm

Tap **Track Event** to add it to your watchlist. Tap **Cancel** to discard.

{% hint style="success" %}
**Tracking active.** Alerts begin immediately based on your current [alert settings](./alerts-and-filters.md). Default thresholds are conservative — tune them later if you want more or fewer pings.
{% endhint %}
{% endstep %}

{% step %}
### (Optional) Adjust per-event settings

Open the event in `Polymarket Events → Edit` and customise:

* Alert frequency for this event
* Minimum price movement for a price alert
* Minimum trade size for a whale alert
<!-- VERIFY: exact per-event setting names -->

See [Configuring Polymarket Alerts](./alerts-and-filters.md) for the full settings reference.
{% endstep %}

{% endstepper %}

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

Yes. Multi-outcome markets are tracked as a single event — alerts fire on movement in any outcome.

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

---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available on this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on this page's URL with the `ask` query parameter set to your question (URL-encoded). The response will contain context tailored to your query, drawn from the full EtherDrops Bot documentation.
