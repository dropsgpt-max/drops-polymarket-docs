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

# 👤 Bot for Groups, Channels, and Topics

Profiles let you keep separate tracking setups and send different alerts to Telegram groups, channels, or topics.

`Main` is created automatically and is used for private alerts. When you connect `Main` to a group or channel, all alerts you receive privately are also mirrored to that destination. You can add Custom Profiles for different audiences or strategies. Each Profile has its own tracking settings and can broadcast to one or more destinations.

### Profiles at a glance

The Profile list keeps the important information visible.

<div align="center"><figure><img src="https://2854945133-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FE1xatl7EJgINFUiyMW2P%2Fuploads%2F3IO1Z0ENDAvrlnXSgbN8%2Fprofiles-list-light-framed.png?alt=media" alt="Drops Bot Profile list showing Main and Custom Profiles with edit, delete, tracking, and Broadcast controls" width="375"><figcaption><p>Profile list with tracking counters and Broadcast destinations.</p></figcaption></figure></div>

<details>

<summary>How to read the Profile list</summary>

* Tap `✏️` next to a Profile name to open **Edit Profile**.
* Tap `🗑️` next to a Custom Profile to delete it. `Main` cannot be deleted, so it has no trash icon.
* One active destination appears as `Broadcast: <Group name>`.
* Multiple active destinations appear as `Broadcast: <N> Groups`.

</details>

### Create a Profile

{% stepper %}
{% step %}
Open Drops Bot in a private chat.
{% endstep %}

{% step %}
Go to **Main Menu** → **Tracking** → **My Profiles**.
{% endstep %}

{% step %}
Tap **➕ Add Profile**.
{% endstep %}

{% step %}
Enter a name for the new Profile.
{% endstep %}
{% endstepper %}

{% hint style="success" %}
Your new Profile is ready. Open it with `✏️` to configure what it tracks and where it broadcasts.
{% endhint %}

### Edit or rename a Profile

{% stepper %}
{% step %}
Go to **Main Menu** → **Tracking** → **My Profiles**.
{% endstep %}

{% step %}
Tap `✏️` next to the Profile name.

<div align="left"><figure><img src="https://2854945133-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FE1xatl7EJgINFUiyMW2P%2Fuploads%2Fufcjtsn1vhTcrppfI1EY%2Fedit-profile-light-framed.png?alt=media" alt="Edit Profile menu with Predictions, Coins, Wallets, NFTs, Gas Price, Funding, Duplicate, Rename, Broadcast, and Delete controls" width="375"><figcaption><p>Edit Profile settings and management controls.</p></figcaption></figure></div>
{% endstep %}

{% step %}
Choose the action you need:

* To update tracking settings, tap **Predictions**, **Coins**, **Wallets**, **NFTs**, **Gas Price**, **Funding**, or another available option.
* To change the Profile name, tap **✏️ Rename** and enter the new name.
* To remove a Custom Profile, tap **🗑️ Delete** and confirm the deletion. This removes the Profile settings and stops its broadcasts, but Drops Bot stays in the connected Telegram groups. The `Main` Profile cannot be deleted.
{% endstep %}
{% endstepper %}

The settings are independent for every Profile. Changes made in one Profile do not affect the others.

{% hint style="info" %}
A Profile can send alerts to one or more connected groups, channels, or topics.
{% endhint %}

### How to Add the Bot to a Group

{% stepper %}
{% step %}
Open Drops Bot in a private chat and go to **Main Menu** → **Tracking** → **My Profiles**.
{% endstep %}

{% step %}
Tap **📣 Add Bot to Group**.
{% endstep %}

{% step %}
Choose the Profile that will send notifications.

If you have only one Profile, Drops Bot skips this screen. If you have more than one, the **Select bot profile to send notifications** screen appears. It shows up to 10 Profiles per page; use the pagination buttons to browse the rest.

<div align="left"><figure><img src="https://2854945133-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FE1xatl7EJgINFUiyMW2P%2Fuploads%2FdCwrSqKZgrLsHq2FNel1%2Fselect-profile-light-framed.png?alt=media" alt="Select bot profile to send notifications screen with ten Profiles and pagination controls" width="375"><figcaption><p>Select a Profile before adding Drops Bot to a group or channel.</p></figcaption></figure></div>
{% endstep %}

{% step %}
Select the Telegram group and add Drops Bot as an administrator.
{% endstep %}

{% step %}
Alerts from the selected Profile start broadcasting to the main chat. In a forum group, this is the **General** topic by default.
{% endstep %}
{% endstepper %}

{% hint style="success" %}
Drops Bot is connected and ready to broadcast alerts from the selected Profile.
{% endhint %}

{% hint style="warning" %}
Only the user who added Drops Bot can manage the group's Profiles. Other users cannot connect their Profiles to this bot instance. Change the selected Profile inside Drops Bot in a private chat, not with a Profile-name command in the group.
{% endhint %}

{% hint style="info" %}
One active Drops Bot instance manages Profiles and Broadcast settings for each group or channel. In groups, additional backup instances can be added to distribute alert delivery; they synchronize automatically with the active instance.
{% endhint %}

### How to Add the Bot to a Channel

Telegram uses a different admin flow for channels.

{% stepper %}
{% step %}
Open Drops Bot in a private chat and go to **Main Menu** → **Tracking** → **My Profiles**.
{% endstep %}

{% step %}
Tap **📣 Add Bot to Group** and select the Profile that will send notifications.
{% endstep %}

{% step %}
Open the channel settings and tap **Subscribers**.
{% endstep %}

{% step %}
Select Drops Bot, tap **Make Admin**, then tap **Done**.
{% endstep %}
{% endstepper %}

{% hint style="success" %}
Drops Bot can now post alerts from the selected Profile to the channel.
{% endhint %}

### Broadcast to a Telegram topic

First add Drops Bot to the forum group using the flow above.

{% stepper %}
{% step %}
In a private chat with Drops Bot, select the Profile that should broadcast to the topic.
{% endstep %}

{% step %}
Open the topic that should receive alerts from this Profile.
{% endstep %}

{% step %}
As a group administrator, send:

```
/usetopic
```
{% endstep %}

{% step %}
To assign another Profile to another topic, return to the private chat and switch to that Profile. Then open the other topic and send `/usetopic` again.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
`/usetopic` is for administrators only and applies the currently selected Profile to the topic where the command is sent. Do not add a Profile name to the command.
{% endhint %}

### Manage Profile broadcasts

The button in **Edit Profile** changes with the current state:

* `Broadcast: <Group name>` — the Profile broadcasts to one group.
* `Broadcast: <N> Groups` — the Profile broadcasts to multiple groups.
* `Broadcast: 0 Groups` — Drops Bot is present in one or more groups, but this Profile is not broadcasting to any of them. Follow Missing alerts in your group? to enable a destination and check alert delivery.
* `📣 Add Bot to Group` — Drops Bot has not been added to any group yet.

{% stepper %}
{% step %}
Go to **Main Menu** → **Tracking** → **My Profiles**, then tap `✏️` next to the Profile.
{% endstep %}

{% step %}
Tap **Broadcast** in the **Edit Profile** menu.
{% endstep %}

{% step %}
The Broadcast screen lists all available groups.

Tap the current `On` or `Off` state next to a group to switch broadcasting for that destination. The message updates immediately.

<div align="left"><figure><img src="https://2854945133-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FE1xatl7EJgINFUiyMW2P%2Fuploads%2FipcfNSQHaQ0i7tHDeZGM%2Fbroadcast-light-framed.png?alt=media" alt="Broadcast management screen showing groups with On and Off states, individual delete controls, Add to New Group, and Remove All Groups" width="375"><figcaption><p>Manage where the selected Profile broadcasts alerts.</p></figcaption></figure></div>
{% endstep %}

{% step %}
Tap `🗑️` next to a group to remove it from this Profile's broadcast list, or tap **Remove All Groups** to clear the entire list.
{% endstep %}

{% step %}
Review the confirmation and tap **✅ Confirm**. Tap **❌ Cancel** to keep the current broadcast list.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Removing a group from the broadcast list stops alerts from this Profile. It does not remove Drops Bot from the Telegram group.
{% endhint %}
