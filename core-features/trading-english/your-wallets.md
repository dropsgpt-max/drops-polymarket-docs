# 👛 Your Wallets

#### 🔹 **Main Wallet Block**

Each connected wallet includes:

* **Your Wallets List** – Displays all added wallets for trading
* **Wallet Name** _(clickable)_ – Opens the wallet’s page on **Solscan**
* **/EDIT** – Opens editing options for that specific wallet
* **Wallet Address** – Public Solana address used for swaps and holding tokens
* **Balance:** – Current SOL balance and its USD equivalent
* **Positions:** – Total number of token holdings in the wallet

***

#### 🔘 **Wallet Action Buttons**

* **➕ Generate Wallet** – Create a new wallet directly from the bot
* **↙️ Import Wallet** – Import one or more existing wallets using private keys
* **✏️ Edit All Wallets** – Mass edit all added wallets
* **↩ Back** – Return to the main trading menu

***

#### ✏️ **Editing a Wallet (/EDIT)**

When you tap **/EDIT** on a wallet, the following options become available:

* **✏ Rename Wallet** – Change the wallet’s display name
* **📩 Export Private Key** – Export the private key (be cautious with this!)
* **🗑 Delete** – Remove the wallet from your trading list
* **↩ Back** – Return to the Trading main menu

***

### 🔄 **How to Import a Wallet**

{% stepper %}
{% step %}
Open the **Trading Menu** (`/trading`)
{% endstep %}

{% step %}
Go to **👛 Your Wallets**
{% endstep %}

{% step %}
Tap **↙️ Import Wallet**
{% endstep %}

{% step %}
Paste a **private key**, or import multiple keys:

* One per line
* Or upload a `.txt` or `.csv` file (max size **100 KB**)
{% endstep %}
{% endstepper %}

{% hint style="success" %}
The imported wallets will be added to your trading interface and ready for use.
{% endhint %}
