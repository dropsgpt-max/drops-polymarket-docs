# Configuring Polymarket Alerts

## 🔔 Alert Settings

Polymarket alerts are tuned **per-odd** — each tracked outcome has its own settings panel. There is no separate global Polymarket settings screen; defaults are applied when a new odd is added, and you adjust them individually from the watchlist.

## 📝 Per-Odd Settings Panel

Open `/polymarket → tap an odd's ✏️ deep-link`. The edit panel is a single 7-row keyboard with one button per setting:

| Button | What it does | Value type |
|---|---|---|
| **🔈 Notifications** | Master ON/OFF for this odd. Icon encodes state: 🔈 = enabled, 🔇 = muted. | Toggle |
| **📉 Price Change** | Fires when the odd's price moves by at least the configured percentage. | Percent (e.g. 5%) |
| **🚨 Price Target** | Fires when the odd crosses a specific absolute price level. | Cents (e.g. 50¢) |
| **♻️ Swaps Alert** | Fires on share-swap trades occurring on the market. | Toggle / threshold |
| **📊 Volume Target** | Fires when cumulative volume crosses a configured USD threshold. | USD (e.g. $5,000) |
| **🗑 Delete** | Stops tracking this odd. | Action |
| **↩ Back** | Return to the watchlist. | Action |

Tapping any threshold button opens a value picker; the current value is shown in the button label after a colon (e.g. `📉 Price Change: 5%`).

> [!NOTE]
> Each tracked odd has **its own independent settings**. If you track multiple outcomes of the same event, you can give each one different thresholds — for example, only ping on `France YES` price moves but watch volume on `Spain YES`.

## 🎚️ Telegram Notification Routing

**Personal chat**

By default, all Polymarket alerts arrive in your private Drops Bot chat — same place as your other notifications.

**Group / channel**

Connect a profile to a Telegram group or channel via [Bot for Groups and Channels](https://etherdrops.gitbook.io/etherdrops-bot/advanced-tools/bot-for-groups-and-channels). You can route Polymarket alerts exclusively to that group while keeping other event types in your private chat.

**Mute schedule**

Set quiet hours from `Settings → Notifications` to suppress all alerts (Polymarket included) during specific time ranges. Useful for sleep schedules or focus blocks.

## 🧪 Suggested Threshold Recipes

Three starting points for the per-odd panel. Tune from there based on how chatty the market is.

**🪶 Watch-only / low noise**

| Setting | Value |
|---|---|
| 🔈 Notifications | ON |
| 📉 Price Change | `10%` |
| 🚨 Price Target | leave unset |
| ♻️ Swaps Alert | OFF |
| 📊 Volume Target | `$10,000` |

You'll get a handful of pings per day on a liquid market — mainly large volume jumps and big price moves.

**⚡ Active trader**

| Setting | Value |
|---|---|
| 🔈 Notifications | ON |
| 📉 Price Change | `3%` |
| 🚨 Price Target | set a level you care about |
| ♻️ Swaps Alert | ON |
| 📊 Volume Target | `$1,000` |

Frequent pings — best for markets you're actively positioning on.

**🐳 Whale-watcher**

| Setting | Value |
|---|---|
| 🔈 Notifications | ON |
| 📉 Price Change | OFF (or very high, e.g. `25%`) |
| 🚨 Price Target | leave unset |
| ♻️ Swaps Alert | ON |
| 📊 Volume Target | `$25,000` |

Only large-size flow comes through, regardless of price movement.

> [!WARNING]
> **Highly liquid markets can flood your chat at low thresholds.** Major elections may produce dozens of `Volume Target: $1,000` triggers per hour. Start with the conservative recipe and loosen up.

## ❓ FAQ

<details>
<summary>Why am I not getting alerts even though the market is moving?</summary>

The most common reason is that the move hasn't crossed your **Price Change** percentage, or trades haven't crossed your **Volume Target**. Open the odd's ✏️ panel and lower the relevant threshold, or turn on **Swaps Alert** if you want per-trade notifications.

</details>

<details>
<summary>Can I disable Polymarket alerts entirely without removing tracked odds?</summary>

Yes — toggle **🔈 Notifications** to off (🔇) on each odd you want silenced. Tracking stays intact; the bot just stops pinging for those odds.

</details>

<details>
<summary>Do quiet hours apply to Polymarket alerts?</summary>

A Telegram-wide mute schedule (`Settings → Notifications`) suppresses every Drops Bot alert during the configured window, Polymarket included.

</details>

<details>
<summary>Do my thresholds carry over when I add more odds to the same event?</summary>

No — each odd starts fresh with the bot's default values. Adjust them individually after adding.

</details>

## 🔧 Troubleshooting

| Issue | Likely Cause | Fix |
|---|---|---|
| No alerts at all | All odds have **🔈 Notifications** off (🔇) | Re-enable in each odd's ✏️ panel |
| Some odds alert, others don't | Per-odd thresholds differ — quieter odds need tighter settings | Lower **Price Change** / **Volume Target** in the silent odd's ✏️ panel |
| Too many alerts | Thresholds too low or **Swaps Alert** on for a busy market | Raise **Price Change** / **Volume Target**, or turn off **Swaps Alert** |
| Alerts during quiet hours | Telegram-side mute not applied / timezone mismatch | Check `Settings → Notifications` and your device timezone |

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
