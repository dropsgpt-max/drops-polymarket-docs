# ❌ Error

## **Error Handling in Drops Bot: Common Issues & Solutions**

When using blockchain-based features like swaps, liquidity tracking, and smart contract interactions, errors may occur due to various factors. Here's a detailed breakdown of the most common errors, their causes, and how to resolve them.

### **1. Slippage Control**

{% hint style="danger" %}
#### Error

#### **“Failed due to ‘executing swap was failed on the blockchain. Reason: Exceeds desired slippage limit’”**
{% endhint %}

{% tabs %}
{% tab title="📍 Cause" %}
Your slippage tolerance is set too low. The actual market price changed more than your allowed slippage.
{% endtab %}

{% tab title="💡 What is Slippage?" %}
The difference between the expected execution price and the actual price when the transaction goes through. It helps protect users from volatile market moves.
{% endtab %}

{% tab title="✅ Solution" %}
Increase the slippage tolerance in [settings](settings.md) to allow successful transaction execution during market volatility.
{% endtab %}
{% endtabs %}

### **2. Solana Fee Reserve Required**

{% hint style="danger" %}
#### Error

#### **“Failed due to 'Balance is not enough to transfer and cover Solana fees’”**
{% endhint %}

{% tabs %}
{% tab title="📍 Cause" %}
Insufficient SOL balance to cover transaction fees.
{% endtab %}

{% tab title="✅ Solution" %}
To successfully execute transactions, you need to have an additional **0.01 SOL** in your account as a reserve. These funds are intended to cover any unexpected issues that may arise during the transaction process.
{% endtab %}
{% endtabs %}

### **3. Account is Frozen**

{% hint style="danger" %}
#### Error

#### **“Executing swap was failed on the blockchain. Reason: account is frozen”**
{% endhint %}

{% tabs %}
{% tab title="📍 Cause" %}
The wallet contains suspicious or unauthorized tokens, triggering a "frozen" status on-chain.
{% endtab %}

{% tab title="✅ Solution" %}
* Check your wallet's token list
* Remove suspicious or unknown tokens
* Avoid manually adding unchecked tokens
* If compromised, **create a new wallet** and transfer safe assets only
{% endtab %}

{% tab title="🔒 Recommendation" %}
Use tools like **Token Sniffer**, **DexTools**, or **CoinGecko** to verify token safety before interacting with them.
{% endtab %}
{% endtabs %}

### **4. Invalid Recipient Address**

{% hint style="danger" %}
#### Error

#### **“Failed due to ‘there was an error while executing transfer’”**
{% endhint %}

{% tabs %}
{% tab title="📍 Cause" %}
Issues with the recipient address:

* Incorrect format
* Wrong network
* Non-existent or inactive wallet
{% endtab %}

{% tab title="✅ Solution" %}
* Double-check the address format (should start with `0x` and be 42 characters for EVM chains)
* Make sure it belongs to the correct network
* Avoid addresses copied from untrusted sources
{% endtab %}
{% endtabs %}

### **5. Failed to Build Swap Route**

{% hint style="danger" %}
#### Error

#### **“Failed due to ‘failed to build swap route details’”**
{% endhint %}

{% tabs %}
{% tab title="📍 Cause" %}
The swap aggregator (e.g., Jupiter) cannot find a route between the selected tokens due to:

* Lack of liquidity
* No available pool
* Unsupported or unknown token
* Transaction amount too large/small
{% endtab %}

{% tab title="✅ Solution" %}
* Use **Jupiter manually** to explore possible routes
* **Lower the swap amount**
{% endtab %}
{% endtabs %}

### **6. Transaction Not Confirmed**

{% hint style="danger" %}
#### Error

#### **“Failed due to ‘tx (tx hash) was not confirmed, please try to increase fee or contact support’”**
{% endhint %}

{% tabs %}
{% tab title="📍 Cause" %}
* Low priority fee
* Network congestion
{% endtab %}

{% tab title="✅ Solution" %}
* **Increase the Priority Fee** in DropsBot settings
* Retry the transaction with a higher fee
* Monitor network load before sending important transactions
{% endtab %}
{% endtabs %}

### **7. General Processing Error**

{% hint style="danger" %}
#### Error

#### **“There was an error while processing transaction”**
{% endhint %}

{% tabs %}
{% tab title="📍 Cause" %}
A generic failure due to:

* Blockchain/network issues
* Smart contract errors
* Insufficient funds
* Invalid input or swap parameters
* Router malfunctions
{% endtab %}

{% tab title="✅ Solution" %}
* Retry the transaction — sometimes it’s a temporary issue
* Ensure **sufficient balance** for gas
* Recheck all inputs (token pairs, values, routes)
* Wait and confirm **network stability**
{% endtab %}
{% endtabs %}

### ✅ General recommendations:

* Avoid interacting with unverified tokens
* Check liquidity and swap routes in advance
* Monitor network congestion
* Use only trusted wallets and addresses
* If you encounter suspicious errors — recreate your wallet and transfer assets manually
