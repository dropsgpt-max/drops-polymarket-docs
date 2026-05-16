# Polymarket Wallet Activity

> [!WARNING]
> **Draft based on the changelog.** The feature was announced on **March 10, 2026** as *"Polymarket activity tracking available for monitored wallets"* with a new *"Polymarket option in wallet Filters → Events settings"*. The exact UI labels, default toggle state, and alert message layout below are reconstructed from that announcement and are not yet test-covered. Treat anything not marked as confirmed as a best-effort sketch.

## 🔁 Track Polymarket Trades of Watched Wallets

While [Add Polymarket Event](./add-event.md) watches **one market regardless of who trades on it**, Wallet Polymarket Activity does the opposite — it watches **one wallet across every Polymarket market it touches**. Combine the two and you cover both ends of the firehose.

> [!NOTE]
> Wallet Polymarket Activity is a **per-wallet toggle** inside the existing wallet tracking flow. You don't add wallets separately — you enable Polymarket as an event type on wallets you're already watching.

## 🎯 How It Works

Drops Bot already monitors Polygon transactions for your tracked wallets. The Mar 10, 2026 release added a **Polymarket** option to each wallet's `Filters → Events` panel: when it's on, Polymarket-related transactions surface as a dedicated alert flavour rather than as generic transfers.

The path mentioned in the changelog is:

```
Wallet → Filters → Events → Polymarket
```

This mirrors the `Filters → Events` pattern used by liquidations, swaps, and other wallet event types. <!-- VERIFY: exact menu wording -->

## 🪜 Enable Polymarket on a Watched Wallet

### 1. Open your wallet list

`Main Menu → Tracking → Wallets`, then tap the wallet you want to configure (or `/edit` if you prefer commands).

<!-- screenshot: wallet list view -->

### 2. Open Filters → Events

Tap **Filters**, then **Events**. You should see a list of event types — Transfers, Swaps, NFT Transfers, Approvals, **Polymarket**, and others. <!-- VERIFY: full list of event-type labels and their order -->

### 3. Toggle Polymarket on

Switch the **Polymarket** toggle to ON.

> [!NOTE]
> **Default state unconfirmed.** The Apr 9, 2026 release shipped a Polymarket cleanup fix (events removed on account deletion). Whether new wallets get the Polymarket toggle pre-enabled by default is **not stated in the changelog** — verify by adding a fresh wallet and checking its `Filters → Events`. <!-- VERIFY: default toggle state for newly added wallets -->

### 4. Save and exit

Confirm changes. The wallet's next Polymarket trade on Polygon will produce a Telegram alert.

> [!TIP]
> **Tracking active.** No further setup needed. The wallet will now emit Polymarket-flavoured alerts in addition to whatever else you have enabled.

## 📨 What Alerts Look Like

The exact format isn't documented in the public changelog, but based on the bot's other event-flavoured alerts, a Polymarket wallet alert is expected to include the wallet label, the action (buy / sell), the market and outcome it touched, the trade size, and a link back to Polymarket. <!-- VERIFY: capture a real alert sample and replace this approximation -->

**Approximate layout** (mock-up, replace with a real screenshot once captured):

```
🟦 vitalik.eth · Polymarket
Bought 50 shares · "Will France win 2026 WC?" · YES
Size: $11.70 · Price: 23.4¢
↗ polymarket.com/event/2026-fifa-world-cup-winner-595
```

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
