---
layout:
  width: default
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
---

# 📩 Common Issues

If you don't find a solution to your specific problem here or require immediate assistance, we recommend reaching out to our dedicated support team directly via Telegram: [**@edrops\_support**](https://t.me/edrops_support)

***

## Alerts or Swaps Are Not Being Received

**Description:** You're experiencing delays or a complete absence of alerts for your tracked wallets (e.g., on BSC or BASE networks) or token swaps for an extended period (e.g., several hours).

**Solution:** This issue is often related to Telegram's internal messaging limits or your bot’s subscription plan.

1. **Check Bot Availability:** Send `/check` in a private chat with your active bot to view available backup instances and their current load. Red means high load, yellow means medium load, and green means low load. Select an available lower-load instance; your tracked data and settings synchronize automatically.
2. **Check Plan Limits:** It's possible you have reached the hourly message limit according to your bot’s current **subscription plan**. When this limit is reached, alerts will temporarily cease. An example of a message you might receive when hitting a message limit is:

> ⚠️ **Limit Reached**
>
> You have reached the maximum number of groups/channels for your **Basic** plan.
>
> To add the bot to more groups, please **upgrade your plan**.

{% hint style="warning" %}
If alerts are still not being received after trying the above solutions, please try disabling the **Filter Scam** option in the bot's settings.
{% endhint %}

***

## Bot Not Responding to Commands in a Group

**Description:** After successfully adding the bot to a Telegram group, it fails to react to commands.

**Solution:** Clear both the Telegram membership and the Profile broadcast connection before adding a fresh bot instance.

{% stepper %}
{% step %}
**Remove the bot from Telegram**

Completely remove Drops Bot from the Telegram group.
{% endstep %}

{% step %}
**Remove the group from the Profile broadcast list**

In a private chat with Drops Bot, go to **Main Menu** → **Tracking** → **My Profiles** → tap `✏️` next to the Profile → **Broadcast** → tap `🗑️` next to the group → **✅ Confirm**.
{% endstep %}

{% step %}
**Check the result**

Removing the group from the broadcast list stops alerts from this Profile but does not remove Drops Bot from the Telegram group. Step 1 removes the bot itself.
{% endstep %}

{% step %}
**Change the bot instance**

Send `/check` in a private chat with the active bot. The command shows available backup instances and their current load: red means high, yellow means medium, and green means low. Select an available lower-load instance; your tracked data and settings synchronize automatically.
{% endstep %}

{% step %}
**Add the bot again**

Follow [Bot for Groups, Channels, and Topics](../advanced-tools/bot-for-groups-and-channels/#how-to-add-the-bot-to-a-group) to reconnect the group and select the Profile that should broadcast alerts.
{% endstep %}
{% endstepper %}

***

## Unwanted Notifications in Your Private Bot Chat: How to Manage and Disable Them

If you are consistently receiving messages from the bot in your private chat, this indicates that you have previously configured or activated specific alerts. The bot is informing you about events you've specified, such as:

* **Coin Price Changes or Transactions:** Alerts regarding swaps, significant price fluctuations for cryptocurrencies you are tracking.
* **Wallet Activity:** Notifications about incoming or outgoing transactions on your monitored cryptocurrency wallets.
* **NFT, Gas Alerts, or Other Specific Notifications:** Depending on the bot's functionality, these could include other types of customized alerts you've set up.

**Steps to Disable Notifications:**

To manage these notifications, you need to identify which type of alert the incoming message belongs to (e.g., a [coin alert](../core-features/coins/coin-management/), [wallet alert](../core-features/wallets/wallet-management/), [NFT alert](../core-features/nft/), [gas alert](../core-features/gas-alerts/), etc.).

Then:

1. **Navigate to the corresponding settings section** within the bot's interface (e.g., "Coins," "Wallets," "NFTs").
2. **Locate and either disable or remove** the specific alert that you no longer wish to receive.

Detailed instructions on how to navigate and disable specific alert types can be found in the relevant sections of this documentation.
