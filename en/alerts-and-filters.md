# Configuring Polymarket Alerts

## 🔔 Alert Settings

Polymarket alerts are tunable at **two levels**: globally (defaults applied to every Polymarket event you track) and individually (per-event overrides). This page walks through both.

> [!NOTE]
> **Inheritance rule.** When you add a new event, it inherits the current **global** settings. Per-event overrides are applied on top and never affect the global preset.

## 🌐 Global Polymarket Options

`Main Menu → Settings → Tracking Settings → Polymarket` <!-- VERIFY: exact menu path for global Polymarket settings -->

The global panel exposes:

* **🔔 Alert frequency** — `Real-time` / `Throttled` / `Digest`. Real-time pings on every qualifying event; Digest groups updates into periodic summaries.
* **📈 Default price-move threshold** — odds shift that must occur before a price alert fires. Lower = noisier, higher = quieter.
* **💰 Default whale threshold** — minimum USD-equivalent trade size that qualifies as a "whale" alert.
* **📊 Volume spike alerts** — toggle on/off; threshold is `% jump over rolling 1h average`.
* **🟢 New trader alerts** — toggle on/off; surfaces first-time entrants on the market.
* **🔕 Mute schedule** — quiet hours during which Polymarket alerts are suppressed.
<!-- VERIFY: confirm which of these toggles exist; some are reasonable additions to validate against UI -->

## 📝 Individual Event Settings

Open `/polymarket → tap an odd's ✏️ deep-link`. The edit panel is a single 7-row keyboard with one button per setting:

* **🔈 Notifications** — master ON/OFF for this odd. The icon encodes state: **🔈** = enabled, **🔇** = muted.
* **📉 Price Change** — fires when the odd's price moves by at least the configured percentage.
* **🚨 Price Target** — fires when the odd crosses a specific absolute price level (in ¢).
* **♻️ Swaps Alert** — fires on share-swap trades occurring on the market.
* **📊 Volume Target** — fires when cumulative volume crosses a configured USD threshold.
* **🗑 Delete** — stops tracking this odd.
* **↩ Back** — return to the watchlist.

Tapping any of the four threshold buttons opens a value picker; the current value is shown in the button label after a colon (e.g. `📉 Price Change: 5%`).

## 🎚️ Telegram Notification Routing

**Personal chat**

By default, all Polymarket alerts arrive in your private Drops Bot chat — same place as your other notifications.

**Group / channel**

Connect a profile to a Telegram group or channel via [Bot for Groups and Channels](https://etherdrops.gitbook.io/etherdrops-bot/advanced-tools/bot-for-groups-and-channels). You can route Polymarket alerts exclusively to that group while keeping other event types in your private chat.

**Mute schedule**

Set quiet hours from `Settings → Notifications` to suppress all alerts (Polymarket included) during specific time ranges. Useful for sleep schedules or focus blocks.

## 🧪 Recommended Presets

* **Watch-only / low noise** — Digest frequency, price-move ≥ 10 pp, whale ≥ $5,000. You'll get a few digested updates per day per event.
* **Active trader** — Real-time, price-move ≥ 3 pp, whale ≥ $1,000. Expect frequent pings; better for markets you're actively positioning on.
* **Whale-watcher** — Real-time, disable price-move alerts, whale ≥ $25,000. Only large trades come through, regardless of odds movement.

> [!WARNING]
> **Lowering thresholds for highly liquid markets can flood your chat.** Markets like major elections may produce dozens of whale-tier trades per hour. Start conservatively and loosen up.

## ❓ FAQ

<details>
<summary>Why am I not getting alerts even though the market is moving?</summary>

The most common reason is that the move hasn't crossed your **price-move threshold**, or the trades haven't crossed your **whale threshold**. Lower thresholds in the global panel or override per-event.

</details>

<details>
<summary>Can I disable Polymarket alerts entirely without removing events?</summary>

Yes — set global Alert frequency to **Off**, or mute individual events. Your tracking stays intact; only the notifications stop.

</details>

<details>
<summary>Do mute schedules apply per event or globally?</summary>

The global mute schedule covers all Polymarket alerts at once. Per-event mute is a separate, simpler ON/OFF toggle.

</details>

<details>
<summary>What happens when I edit global thresholds — do existing events update?</summary>

Existing events keep any **per-event overrides** they already have. Events without overrides immediately use the new global value.

</details>

## 🔧 Troubleshooting

| Issue | Likely Cause | Fix |
|---|---|---|
| No alerts despite enabling everything | Global Alert frequency set to **Off** | Switch to Real-time, Throttled, or Digest |
| Some events alert, others don't | Per-event override mutes them or sets very high thresholds | Open the event's edit panel and reset to global |
| Too many alerts | Thresholds too low | Raise price-move and whale thresholds; switch to Digest frequency |
| Alerts during quiet hours | Mute schedule not applied / timezone mismatch | Confirm timezone in `Settings → Notifications` |

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
