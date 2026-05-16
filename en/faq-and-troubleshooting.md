# Polymarket FAQ & Troubleshooting

A consolidated reference for the most common questions and the failure modes worth knowing in advance. Page-specific FAQs are also available inside each individual page.

## ❓ Frequently Asked Questions

### General

<details>
<summary>What networks does Polymarket tracking support?</summary>

**Polygon only.** Polymarket itself runs on Polygon PoS, so all event tracking and wallet Polymarket activity is scoped to Polygon. Wallet activity on Ethereum, Base, Solana, or any other chain — even on the same wallet address — does not produce Polymarket-flavoured alerts.

</details>

<details>
<summary>Do I need a Polymarket account or to connect a wallet?</summary>

No. Tracking is read-only. You provide the bot with public event URLs and/or watched wallet addresses; nothing in your own funds is ever touched.

</details>

<details>
<summary>When was Polymarket Event Tracking launched?</summary>

**March 10, 2026.** Subsequent fixes (notably the April 9, 2026 cleanup fix) refined data hygiene around account deletion.

</details>

<details>
<summary>Is there a shortcut command for Polymarket?</summary>

Yes — **`/polymarket`** opens your watchlist directly. The reply has three shapes (empty / populated / upsell) — see [Anatomy of `/polymarket`](./polymarket.md#-anatomy-of-polymarket) for the full breakdown.

You can also add events by forwarding a `polymarket.com/event/<slug>` URL into the chat, or reach the watchlist via `/menu → Tracking → Polymarket Events`.

</details>

### Tracking & Limits

<details>
<summary>What's the difference between event tracking and wallet activity tracking?</summary>

**Event tracking** watches one specific Polymarket market regardless of which wallet trades on it. You add it by forwarding a Polymarket URL.<br>
**Wallet activity tracking** watches one wallet across all the Polymarket markets it touches. You enable it via `Wallet → Filters → Events → Polymarket`.

The two are complementary and use **independent quotas** — events count against your Polymarket Events limit; wallet activity counts against your Wallets limit.

</details>

<details>
<summary>Can I track multiple outcomes of a multi-outcome market?</summary>

Yes. A multi-outcome market is tracked as a single event, and alerts fire on movement in any of its outcomes.

</details>

<details>
<summary>Do Polymarket events count against the wallet limit?</summary>

No. Events have their own **Polymarket Events** quota (see [Plan Limits](./plan-limits.md)).

</details>

<details>
<summary>What happens when a market resolves?</summary>

Tracking stops automatically. The event remains in your list as a historical record but no longer fires alerts. Periodically clean resolved events out via bulk-remove to keep slots free. <!-- VERIFY: confirm quota behaviour for resolved events -->

</details>

<details>
<summary>Can I receive alerts only on large positions?</summary>

Yes. Set a **high whale threshold** (e.g. $25,000) and disable price-move alerts in [Alerts & Filters](./alerts-and-filters.md). You'll only get pinged on size.

</details>

### Notifications

<details>
<summary>Can I route Polymarket alerts to a Telegram group instead of my private chat?</summary>

Yes. Connect a profile to a group via [Bot for Groups and Channels](https://etherdrops.gitbook.io/etherdrops-bot/advanced-tools/bot-for-groups-and-channels) and configure that profile to handle Polymarket events.

</details>

<details>
<summary>Why am I getting Polymarket alerts during my mute hours?</summary>

Mute schedules respect your account timezone. Confirm the timezone in `Settings → Notifications`. Per-event mutes are independent of the global mute schedule.

</details>

<details>
<summary>Can I disable Polymarket alerts without removing events?</summary>

Yes. Set the global Alert frequency to **Off**, or mute individual events. Tracking remains intact; only the notifications stop.

</details>

### Account & Data

<details>
<summary>What happens to my Polymarket Events when I delete my account?</summary>

All tracked Polymarket Events are removed permanently as part of account deletion. This cleanup behaviour was fixed on **April 9, 2026** — accounts deleted before that date may have left orphaned event records; contact support if you suspect this.

</details>

<details>
<summary>Does the bot store my Polymarket trading history?</summary>

The bot only stores **what you ask it to track** (event references, wallet addresses) and the alerts it has sent. It does not aggregate or republish your trading positions.

</details>

## 🔧 Troubleshooting

| Problem | Likely Cause | Fix |
|---|---|---|
| Event link not accepted | URL is a category page or invalid format | Open the specific event on `polymarket.com` and copy that URL |
| "Limit reached" message | Polymarket Events plan quota hit | Remove old events or [upgrade plan](./plan-limits.md) |
| Event added but no alerts | Thresholds too high, or market inactive | Lower thresholds in [Alerts & Filters](./alerts-and-filters.md); confirm market has recent volume |
| Wallet alerts don't show Polymarket activity | `Filters → Events → Polymarket` toggle is OFF | Enable in `Wallet → Filters → Events` |
| Polymarket alerts on wrong chain | Wallet trades happening on Ethereum/other, not Polygon | Polymarket is Polygon-only — this is expected |
| Stale events remain after account deletion | Account was deleted before Apr 9, 2026 cleanup fix | Contact support to clear orphans |
| Too many alerts | Thresholds too low, market highly active | Raise whale and price-move thresholds; switch to Digest mode |
| Per-event override not applying | Bulk edit recently overwrote it | Re-apply the override via the event's edit panel |
| Telegram cache shows old plan limit | Stale message | Send `/menu` to refresh |
| Resolved markets still listed | They're kept as history | Bulk-remove resolved events to free slots |

## 📚 Related Pages

* [Overview](./polymarket.md)
* [Quickstart](./quickstart.md)
* [Add Polymarket Event](./add-event.md)
* [Wallet Polymarket Activity](./wallet-activity.md)
* [Event Management](./event-management.md)
* [Alerts & Filters](./alerts-and-filters.md)
* [Plan Limits](./plan-limits.md)

## 💬 Still Stuck?

Reach out via the bot's Help Center entry, or browse the [main EtherDrops documentation](https://etherdrops.gitbook.io/etherdrops-bot/) for non-Polymarket-specific questions.

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
