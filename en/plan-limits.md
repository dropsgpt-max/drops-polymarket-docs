# Polymarket Plan Limits

## 💳 How Many Events You Can Track

The **Polymarket Events** quota — the number of markets you can track at event-level — scales with your subscription tier. Wallet-level Polymarket Activity (see [Wallet Activity](./wallet-activity.md)) uses your separate **Wallets** quota and is not affected by the limits below.

## 📋 Polymarket Events by Plan

| Plan | Polymarket Events |
|---|---|
| **Free / Basic** | 20 |
| **Advanced** | 100 |
| **Pro** | 500 |
| **Wallet Sniper** | 500 |
| **Custom** | Configurable |

> [!NOTE]
> **Custom plans** let you set the Polymarket Events limit independently of other quotas. Useful if you want, say, the Free wallet limit but a Pro-level Polymarket allowance.

<!-- VERIFY: confirm exact plan names. The mirror lists 20/100/500/500/Configurable; plan labels reconstructed from context. -->

## 📈 What Happens When You Hit the Limit

When you reach your plan limits (e.g., wallets, Polymarket events, coins, NFTs), the bot will notify you and suggest options:

* Remove an old event to free a slot
* Tap **Build Custom Plan** on the upsell card the bot returns
* Open `/menu` and navigate to the Subscription section for an upgrade

You won't lose any of your existing events — adding new ones simply stops working until you free space or upgrade.

When you hit the limit, the `/polymarket` reply itself switches to the **upsell shape**: instead of your watchlist you'll see a card whose only CTA is **Build Custom Plan**.

## 💳 Upgrade Path

The fastest path is the **Build Custom Plan** button on the upsell card. It opens the plan-builder where Polymarket Events, Wallets, Coins, and NFTs can each be sized independently.

For detailed plan comparison (price, all quotas, payment methods), see the [main Subscription docs](https://etherdrops.gitbook.io/etherdrops-bot/).

## 🧹 Account Deletion & Data Cleanup

Deleting your account permanently removes your **tracked wallets and Polymarket Events** along with all settings.

> [!WARNING]
> **Polymarket cleanup was fixed on April 9, 2026.** Earlier versions of the bot left orphaned Polymarket event records after account deletion. If you deleted an account before that date and are starting fresh, contact support to ensure stale records are cleared.

## ❓ FAQ

<details>
<summary>Do resolved events still count against my limit?</summary>

Resolved events stop generating alerts but may remain in your list as historical records. Bulk-remove them periodically to free slots. <!-- VERIFY: confirm whether resolved events occupy quota -->

</details>

<details>
<summary>Does Wallet Polymarket Activity count toward the Polymarket Events quota?</summary>

No. Wallet-level Polymarket activity is metered against your **Wallets** quota, not the Polymarket Events quota. The two limits are independent.

</details>

<details>
<summary>Can I get a higher Polymarket limit without raising my wallet limit?</summary>

Yes — switch to a **Custom plan**, which lets you configure each quota independently.

</details>

<details>
<summary>What's the difference between Pro and Wallet Sniper for Polymarket?</summary>

Both currently offer the same **500-event** Polymarket allowance. Differences between the two plans are in wallet allowances, alert features, and pricing — not Polymarket-specific. <!-- VERIFY: plan label semantics -->

</details>

## 🔧 Troubleshooting

| Issue | Likely Cause | Fix |
|---|---|---|
| "Limit reached" on adding | At plan cap | Remove an event or upgrade |
| Count seems wrong | Resolved events still counted | Bulk-remove resolved events |
| Upgraded but limit unchanged | Telegram cache | Send `/menu` to refresh; if still stale, restart the chat |
| Custom plan limit not applied | Plan configuration pending | Check `💳 Subscription` for current effective limits |

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
