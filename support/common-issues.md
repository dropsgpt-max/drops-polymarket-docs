# 📩 Common Issues

If you don't find a solution to your specific problem here or require immediate assistance, we recommend reaching out to our dedicated support team directly via Telegram: [**@drops\_support**](https://t.me/edrops_support)

***

## Alerts or Swaps Are Not Being Received

**Description:** You're experiencing delays or a complete absence of alerts for your tracked wallets (e.g., on BSC or BASE networks) or token swaps for an extended period (e.g., several hours).

**Solution:** This issue is often related to Telegram's internal messaging limits or your bot’s subscription plan.

1. **Switch Bot Instances:** Try switching to a different bot instance. You can view available bots by sending the `/check` command in a private chat with your active bot. Switching instances may help you bypass temporary Telegram messaging limits.
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

**Description:** After successfully adding the bot to a Telegram group, it fails to react to any commands.

**Solution:** This issue typically indicates an incomplete removal or improper connection of the bot.

1. **Remove Bot from Group:** Begin by completely removing the bot from your Telegram group.
2. **Verify Complete Deletion:** Ensure the bot has been fully removed from your profile's tracked groups:
   * Navigate to: **Main menu** → **Tracking** → **My Profiles**.
   * Open the editing menu for any profile by tapping the `/EDIT` command.
   * If the group still appears, tap **Delete Group** and select the group you want to remove.
3. **Change Bot Instance:** After confirming the bot is entirely removed from the group and your profile, you will need to change your active bot instance. Send the `/check` command in a private chat with your current bot to see available bot instances.
4. **Re-add Bot:** Once you have switched to a new bot instance, attempt to connect the bot to your group by following the instructions in the [Add Bot to a Group or Channel](../advanced-tools/bot-for-groups-and-channels/create-and-manage-profiles.md#how-to-add-the-bot-to-a-group) guide.

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
