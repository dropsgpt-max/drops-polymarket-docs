# Polymarket Quickstart

## ⚡ Start Tracking in 60 Seconds

You don't need to configure anything to start receiving Polymarket alerts. Open the market you care about, forward its link to the bot, and you're done — the next price move will arrive in your Telegram.

{% hint style="info" %}
**Prerequisites**
* You have an active EtherDrops Bot chat (`/start` already done).
* You haven't hit your plan's Polymarket Event limit — see [Plan Limits](./plan-limits.md).
{% endhint %}

## 🚀 The Four Steps

{% stepper %}

{% step %}
### Open a Polymarket event

Go to [polymarket.com](https://polymarket.com), find the market you want to follow, and open its dedicated page.

![Polymarket event page — copy the URL from the address bar at the top](../../../media/screenshots/polymarket/event-page.png)
{% endstep %}

{% step %}
### Copy the event link

Copy the URL from the browser address bar. The bot accepts URLs of the form `https://polymarket.com/event/<slug>` (with or without query parameters).

{% hint style="warning" %}
**Event URL only.** Category listings (`polymarket.com/markets`, `/sports`, etc.) and the Polymarket home page are rejected — make sure the URL contains `/event/` followed by a slug.
{% endhint %}
{% endstep %}

{% step %}
### Forward the link to the bot

Paste the URL into your Drops Bot chat and send it. The bot will recognise the Polymarket domain and prompt you to confirm.

<!-- screenshot: Telegram chat with a Polymarket URL pasted in -->
{% endstep %}

{% step %}
### Confirm tracking

Tap **Track Event** in the bot's reply. The market is added to your `🟦 Polymarket Events` list and starts producing alerts immediately.

{% hint style="success" %}
**Done!** You'll get a Telegram notification the next time activity on this market crosses your alert thresholds.
{% endhint %}
{% endstep %}

{% endstepper %}

## ➡️ Next Steps

Now that your first event is live, you may want to:

* 🔔 [Tune alert sensitivity](./alerts-and-filters.md) — global thresholds and per-event overrides.
* 🔁 [Track wallets that bet on Polymarket](./wallet-activity.md) — surface whale moves automatically.
* 🛠️ [Manage your event list](./event-management.md) — view, edit, or remove tracked events.

## 🔧 Troubleshooting

| Issue | Likely Cause | Fix |
|---|---|---|
| Bot doesn't recognise the link | URL is for a category page, not a specific event | Open the event itself and copy that URL |
| "Limit reached" reply | You've hit your plan's Polymarket Event quota | Remove an old event or [upgrade your plan](./plan-limits.md) |
| Link accepted but no alerts arrive | Market is already resolved or has no activity | Pick an active market with recent volume |

---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available on this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on this page's URL with the `ask` query parameter set to your question (URL-encoded). The response will contain context tailored to your query, drawn from the full EtherDrops Bot documentation.
