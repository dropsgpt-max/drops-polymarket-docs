# Polymarket

## 📊 Real-Time Prediction Market Monitoring

EtherDrops Bot delivers **instant, real-time alerts** for Polymarket prediction market activity on the **Polygon network** — straight to your Telegram. Whether you are tracking a single event or watching whale wallets that bet on Polymarket, the bot keeps you in the loop without you ever leaving the chat.

{% hint style="info" %}
Polymarket Event Tracking launched on **March 10, 2026** and is available across all subscription plans. Limits scale with your plan tier — see [Plan Limits](./plan-limits.md).
{% endhint %}

<!-- screenshot: Polymarket section in the bot's Tracking menu -->

## 🔍 What You Can Track

Drops Bot supports **two tracking modes**, each suited to a different use case:

* 🟦 **Polymarket Events** — Track a specific market by forwarding its event link to the bot. You receive alerts whenever odds shift, large positions enter or exit, or volume spikes on that market.
* 🔁 **Wallet Polymarket Activity** — Watch a wallet, and the bot will surface every Polymarket trade it makes on Polygon — buys, sells, position adjustments — in real time.

The two modes complement each other: track a few hot markets directly, and let wallet monitoring surface everything else.

## 🌐 Network Coverage

Polymarket Events on Drops Bot operate exclusively on **Polygon**.

{% hint style="warning" %}
**Polygon only.** Polymarket runs on Polygon PoS, and all tracking happens there. Wallet activity on Ethereum, Base, Solana, or any other network will **not** produce Polymarket alerts — even if the same wallet also trades on Polymarket.
{% endhint %}

## 💼 Use Cases

* **Traders** — Catch sudden price moves on markets you care about before the rest of the market reacts.
* **Researchers & analysts** — Build a watchlist of resolution-driving events (elections, sports, crypto, macro) and follow them straight from Telegram.
* **Whale watchers** — Tag wallets known for large Polymarket positions and get pinged the moment they move size.
* **Community / channel admins** — Route Polymarket alerts to a Telegram group or channel via [Bot for Groups and Channels](https://etherdrops.gitbook.io/etherdrops-bot/advanced-tools/bot-for-groups-and-channels) and keep your audience updated automatically.

## 🚀 Get Started

* 👉 [**Polymarket Quickstart**](./quickstart.md) — Track your first event in under 60 seconds.
* ➕ [Add Polymarket Event](./add-event.md) — Full walkthrough of event link tracking.
* 🔁 [Wallet Polymarket Activity](./wallet-activity.md) — Enable Polymarket alerts for watched wallets.
* 🛠️ [Event Management](./event-management.md) — View, edit, and remove tracked events.
* 🔔 [Configuring Polymarket Alerts](./alerts-and-filters.md) — Tune notification frequency and filters.
* 💳 [Plan Limits](./plan-limits.md) — How many events your tier supports.
* ❓ [FAQ & Troubleshooting](./faq-and-troubleshooting.md) — Common questions answered.

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

No. Polymarket Events are included in every plan; only the per-plan **event limit** differs. See [Plan Limits](./plan-limits.md).

</details>

<details>
<summary>Where do I find Polymarket in the bot menu?</summary>

`Main Menu → Tracking → Polymarket Events`. New events can also be added by forwarding an event link to the bot directly from Polymarket.

</details>

---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available on this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on this page's URL with the `ask` query parameter set to your question (URL-encoded). The response will contain context tailored to your query, drawn from the full EtherDrops Bot documentation.
