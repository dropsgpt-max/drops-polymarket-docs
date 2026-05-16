# Polymarket Changelog

A reverse-chronological log of changes to Polymarket tracking in Drops Bot. Drawn from the official changelog mirror; UI-side details that aren't in the public announcement are flagged.

## 2026-04-09 — Polymarket Events Cleanup Fix

Polymarket events are removed when an account is deleted.

**What's New**

* Polymarket events cleared after account deletion
* Previous event data no longer persists after removal

**Why it matters**

* Prevents leftover Polymarket events after account deletion
* Ensures account data is fully removed

> [!NOTE]
> Same release shipped **Liquidation Alerts** for Hyperliquid L1 wallets (unrelated to Polymarket but landed the same day).

## 2026-03-10 — Polymarket Event Tracking *(launch)*

Polymarket event tracking and wallet-based activity alerts available on the Polygon network.

**What's New**

* Polymarket event tracking supported through event links
* Polymarket activity tracking available for monitored wallets
* Polymarket option added in wallet `Filters → Events` settings
* Real-time alerts delivered for tracked Polymarket activity

**How It Works**

* Polymarket event link forwarded to the bot to start event tracking
* Wallet Polymarket option enabled in `Filters → Events` settings
* Tracked wallet activity monitored for Polymarket events on Polygon

**Why It Matters**

* Provides monitoring of Polymarket events through direct event tracking
* Enables detection of Polymarket activity for tracked wallets
* Delivers alerts when tracked Polymarket activity occurs

## 📚 Related Pages

* [Overview](./polymarket.md)
* [Plan Limits](./plan-limits.md)
* [Wallet Polymarket Activity](./wallet-activity.md)
* [Drops Bot global changelog](https://etherdrops.gitbook.io/etherdrops-bot/help-center/changelog) — non-Polymarket bot changes

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
