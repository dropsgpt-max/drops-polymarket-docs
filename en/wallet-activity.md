# Polymarket Wallet Activity

## 🔁 Track Polymarket Trades of Watched Wallets

While [Add Polymarket Event](./add-event.md) watches **one market regardless of who trades on it**, Wallet Polymarket Activity does the opposite — it watches **one wallet across every Polymarket market it touches**. Combine the two and you cover both ends of the firehose.

> [!NOTE]
> Wallet Polymarket Activity is a **per-wallet toggle** inside the existing wallet tracking flow. You don't add wallets separately — you enable Polymarket as an event type on wallets you're already watching.

## 🎯 How It Works

Drops Bot already monitors Polygon transactions for your tracked wallets. When the **Polymarket** event type is enabled in that wallet's filter, the bot recognises Polymarket-related transactions (share purchases, sales, position adjustments) and emits a dedicated alert instead of a generic transfer log.

The relevant menu path is:

```
Wallet → Filters → Events → Polymarket
```

This mirrors the same `Filters → Events` pattern used by liquidations, swaps, and other wallet event types.

## 🪜 Enable Polymarket on a Watched Wallet

### 1. Open your wallet list

`Main Menu → Tracking → Wallets`, then tap the wallet you want to configure (or `/edit` if you prefer commands).

<!-- screenshot: wallet list view -->

### 2. Open Filters → Events

Tap **Filters**, then **Events**. You'll see a list of event types: Transfers, Swaps, NFT Transfers, Approvals, Polymarket, and others.

### 3. Toggle Polymarket on

Switch the **Polymarket** toggle to ON.

> [!NOTE]
> **Default state.** Since the April 9, 2026 release, the Polymarket toggle defaults to **enabled** for newly added wallets. <!-- VERIFY: confirm default state -->

### 4. Save and exit

Confirm changes. The wallet's next Polymarket trade on Polygon will produce a Telegram alert.

> [!TIP]
> **Tracking active.** No further setup needed. The wallet will now emit Polymarket-flavoured alerts in addition to whatever else you have enabled.

## 📨 What Alerts Look Like

A typical Polymarket wallet alert contains:

* **Wallet** — address and the label you gave it
* **Action** — Buy / Sell / Position Adjustment
* **Market** — event name and outcome (e.g. "Will X happen by Date? — YES")
* **Size** — number of shares and USD-equivalent
* **Price** — execution price per share
* **Link** — direct link to the Polymarket event

<!-- screenshot: a Polymarket wallet activity alert in Telegram -->

## 🧰 Tips

* **Label your wallets clearly** before enabling — `vitalik.eth`, `whale-1`, `my-cold-wallet`. Alerts read much faster when each wallet has a name.
* **Combine with [Save Previous Filters](https://etherdrops.gitbook.io/etherdrops-bot/)** so new wallets inherit your Polymarket toggle setting automatically.
* **Group routing** — route Polymarket-only alerts to a dedicated Telegram group via [Bot for Groups and Channels](https://etherdrops.gitbook.io/etherdrops-bot/advanced-tools/bot-for-groups-and-channels) if you want to silo this stream from the rest of your activity feed.

## ❓ FAQ

<details>
<summary>Does Wallet Polymarket Activity count against my Polymarket Events limit?</summary>

No. The Polymarket Events limit only applies to **event-level** tracking (added via event link). Wallet-level Polymarket activity uses your **Wallet** limit. See [Plan Limits](./plan-limits.md) for both quotas.

</details>

<details>
<summary>Can I get Polymarket alerts only, with no other wallet events?</summary>

Yes. Open `Filters → Events` and disable everything except **Polymarket**. The wallet will then only ping you on Polymarket transactions.

</details>

<details>
<summary>Why am I getting Polymarket alerts on a wallet that isn't on Polygon?</summary>

The wallet itself isn't network-bound — Drops Bot tracks it across all supported chains. The Polymarket toggle specifically picks up the Polymarket-related transactions on **Polygon**, regardless of what the wallet does on other chains.

</details>

<details>
<summary>What about wallets I add in bulk?</summary>

Bulk-added wallets inherit the same default filter state, including Polymarket. If you have **Save Previous Filters** enabled, they inherit your last-used preset instead.

</details>

## 🔧 Troubleshooting

| Issue | Likely Cause | Fix |
|---|---|---|
| Wallet alerts arrive but no Polymarket-flavoured ones | `Filters → Events → Polymarket` is OFF | Toggle it ON |
| Polymarket-flavoured alerts but no detail (no market name) | Display label rendering issue / cached preview | Re-enter the wallet edit view and save; if it persists, report via Help Center |
| Too much noise from one wallet | The wallet is highly active across many markets | Tune per-wallet thresholds in `Filters → Events` <!-- VERIFY: granular threshold support per event type --> |
| Polymarket trades on Ethereum mainnet not reported | Polymarket is Polygon-only; mainnet trades are not Polymarket | No fix needed — this is expected |

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
