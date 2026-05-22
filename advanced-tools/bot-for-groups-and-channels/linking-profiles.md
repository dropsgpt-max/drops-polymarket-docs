# 🔗 Linking Profiles

The **Profile connection system** in Drops Bot allows you to choose **which alerts go to which group or topic**. It may sound a little technical at first, but we’ll walk you through every detail — **no confusion, no guesswork**.

### 👥 **Step 1: Add the Bot to the Group First**

Before connecting a Profile, the Drops Bot must be **added to the group**.\
👉 _If you haven’t done this yet,_ [_click here for instructions_](create-and-manage-profiles.md#how-to-add-the-bot-to-a-group)

***

### 🔗 **How to Connect a Profile to a Group or Channel**

The process for connecting a Profile to a **group** or a **channel** is exactly the same.

{% stepper %}
{% step %}
Go to the **group** where the bot was previously added.
{% endstep %}

{% step %}
In the group chat, send the following command:

```
/use_thread Main
```

Replace `Main` with the name of the Profile you want to link.

> You can find the correct Profile name in the bot’s menu under **“Profiles”**,\
> or by sending the `/profiles` command in your **private chat with the bot**.
{% endstep %}
{% endstepper %}

{% hint style="success" %}
You’ll receive a **confirmation** — the **Profile is now successfully connected to the group**.
{% endhint %}

***

### 💬 **How to Connect a Profile to a Topic (Thread)**

Telegram groups can have **topics (threads)** — separate discussion areas. You can link a different Profile to each topic!

{% stepper %}
{% step %}
Make sure Drops Bot is already added to the group
{% endstep %}

{% step %}
Open the **topic (thread)** you want to configure

Send the command:

```
/use_thread Main
```

Replace `Main` with the name of the Profile you want to link.

> You can find the correct Profile name in the bot’s menu under **“Profiles”**,\
> or by sending the `/profiles` command in your **private chat with the bot**.
{% endstep %}
{% endstepper %}

{% hint style="success" %}
The **Profile is now linked** specifically to that **topic**.
{% endhint %}

***

### ⚠️ Important Clarification

Profiles are **linked to the user who added the bot** to the group.\
Here’s what that means:

* If **User A** added DropsBot to the group, only **User A’s Profiles** can be connected.
* **User B** **cannot** connect their own Profiles or add their own instance of DropsBot to the same group.

This ensures consistent management and prevents conflicts between users and bot instances.

***

### 🧠 Key Notes to Remember

* **Only the user who added the bot** can manage Profiles for that group
* **You can connect different Profiles to different topics** within the same group
* **Other users cannot add another Drops Bot** or connect unrelated Profiles

***

With this setup, you can route:

* Wallet alerts to _Topic A_
* NFT swaps to _Topic B_
* Token launches to Topic _C_

All with **clean separation** and **perfect control** — no chaos, no overlap.
