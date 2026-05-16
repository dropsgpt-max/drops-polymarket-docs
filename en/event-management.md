# Event Management

## 🛠️ Managing Your Tracked Events

Once you've added a few Polymarket events, you'll want a single place to review, edit, and clean them up. This page covers the day-to-day housekeeping flow.

{% hint style="info" %}
Polymarket Event management follows the same UX pattern as **Coin Management** in the bot — list view, single-item edit, bulk operations. If you're used to managing coins, this will feel identical.
{% endhint %}

## 👀 Viewing All Tracked Events

`Main Menu → Tracking → Polymarket Events` opens the full list. Each row shows:

* The event title
* Current odds / leading outcome
* 24h volume
* Quick-action buttons (Edit, Remove)

<!-- screenshot: Polymarket Events list view -->

For long lists, paginate with the navigation buttons under the message. <!-- VERIFY: confirm pagination identical to wallet list pagination -->

## ✏️ Editing a Specific Event

Tap an event row, then **Edit**, to open its individual settings panel.

You can change:

* **🔔 Alert frequency** — how often the bot is allowed to ping you for this event
* **📈 Price-move threshold** — minimum odds shift (e.g. ≥ 5 percentage points) before an alert fires
* **💰 Trade-size threshold** — minimum USD-equivalent trade size that qualifies as a "whale" alert
* **🔕 Mute schedule** — quiet hours specific to this event
<!-- VERIFY: exact per-event setting names and presence of mute schedule per event -->

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

* `/menu` → `Tracking` → `Polymarket Events` — full UI
* `/edit` → `Polymarket Events` — jump straight to edit mode <!-- VERIFY: shortcut command availability for Polymarket -->

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
