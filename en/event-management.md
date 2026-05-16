# Event Management

## 🛠️ Managing Your Tracked Events

Once you've added a few Polymarket events, you'll want a single place to review, edit, and clean them up. This page covers the day-to-day housekeeping flow.

{% hint style="info" %}
Polymarket Event management follows the same UX pattern as **Coin Management** in the bot — list view, single-item edit, bulk operations. If you're used to managing coins, this will feel identical.
{% endhint %}

## 👀 Viewing All Tracked Events

Type **`/polymarket`** to open your watchlist directly. The body is titled **`Your Polymarket Events Watchlist`**. Each tracked odd appears as a row containing:

* The event title and chosen outcome (e.g. `🟦 Will <outcome>? <price>¢`)
* An inline 🗑 deep-link to remove the odd in one tap (backed by a `?start=DELpmev_…` start parameter)
* An inline ✏️ deep-link that opens the edit panel for this odd

<!-- screenshot: Polymarket Events list view -->

Below the body, a 4-button entry keyboard provides **Add Event/Wallet**, **Polymarket Wallets**, **Trending Events**, and **Back**. The keyboard auto-collapses when the watchlist grows long.

## ✏️ Editing a Specific Event

Tap the ✏️ deep-link on the watchlist row. The edit panel opens as a 7-row keyboard:

* **🔈 Notifications** — ON/OFF for this odd (🔈 on / 🔇 off)
* **📉 Price Change** — percentage-move threshold
* **🚨 Price Target** — absolute price target (in ¢)
* **♻️ Swaps Alert** — alerts on share-swap trades
* **📊 Volume Target** — cumulative-volume threshold
* **🗑 Delete** — stop tracking this odd
* **↩ Back** — return to the watchlist

See [Configuring Polymarket Alerts](./alerts-and-filters.md) for what each threshold does.

Per-event overrides win over the global Polymarket settings. To roll back, hit **Reset to global**.

## 📦 Bulk Editing All Tracked Events

For changes that apply across every Polymarket event you're tracking:

`Polymarket Events → ⚙️ Bulk Edit`

This applies a single change (e.g. raise all price-move thresholds to 10 pp) across the whole list in one step. Use it when you want to reduce noise globally without touching each event individually.

{% hint style="warning" %}
**Bulk edit overwrites per-event overrides.** If you've fine-tuned individual events, bulk-editing the same parameter will reset those fine-tunings. Confirm twice before applying.
{% endhint %}

## 🗑️ Removing an Event

### Single Removal

In the event's edit panel, tap **🗑️ Remove**. Confirmation prompt → tap **Yes** → event disappears from your list.

### Bulk Removal

`Polymarket Events → ⚙️ Bulk → Remove`. Select multiple events or remove all. The freed slots become immediately available to add new events.

{% hint style="warning" %}
**Resolved markets aren't auto-removed.** Markets that have already resolved stay in your list as a historical record. They don't generate new alerts, but they may still occupy a slot. Periodically clean them up with bulk removal. <!-- VERIFY: confirm whether resolved events occupy slots -->
{% endhint %}

## ⚡ Quick Access

* **`/polymarket`** — opens the watchlist directly. The reply takes one of three shapes:
  * **Empty** — `"You are not tracking any Polymarket events yet"` plus the 4-button entry keyboard.
  * **Populated** — `"Your Polymarket Events Watchlist"` with 🗑 / ✏️ inline links per row.
  * **Upsell** — shown when your plan limit is exceeded, carrying a **Build Custom Plan** CTA.
* `/menu` → `Tracking` → `Polymarket Events` — same destination, one extra hop.
* Forwarding any `polymarket.com/event/<slug>` URL into the chat — adds a new event without leaving the conversation.

## ❓ FAQ

<details>
<summary>How many events can I edit at once?</summary>

Bulk edit applies a change to your entire Polymarket Events list in a single operation. There's no per-batch cap separate from your plan's overall event limit.

</details>

<details>
<summary>Can I export my event list?</summary>

<!-- VERIFY: does export exist for Polymarket events, similar to wallet export? -->
Export functionality follows the same pattern as wallet and coin export, if available — check the bulk menu in your bot. If not present, this feature has not yet shipped for Polymarket Events.

</details>

<details>
<summary>Will I lose my settings if I remove and re-add an event?</summary>

Yes. Removal clears all per-event overrides. Re-adding the event starts fresh with global defaults.

</details>

## 🔧 Troubleshooting

| Issue | Likely Cause | Fix |
|---|---|---|
| Edit button does nothing | Stale Telegram message | Re-open the event via the list, not via an older notification |
| Bulk operation seems stuck | Large list, processing in background | Wait a few seconds; if no response after 30s, retry |
| Removed event still alerts | Notification queued before deletion | Should clear within one alert cycle; if not, report via Help Center |
| Resolved events still showing | They are kept as historical records | Bulk-remove them to free slots |

---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available on this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on this page's URL with the `ask` query parameter set to your question (URL-encoded). The response will contain context tailored to your query, drawn from the full EtherDrops Bot documentation.
