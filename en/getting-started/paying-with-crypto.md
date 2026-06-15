# Paying with Crypto

We accept cryptocurrency because it matches our privacy model: no card, no bank account, no name — we don't need any of it.

{% hint style="info" %}
**Stars vs. crypto, quickly.** Telegram Stars pays for the **7-day trial only** (99 ⭐, instant, no blockchain). **Monthly and Annual are paid in crypto.**
{% endhint %}

## What we accept

The in-bot picker offers four coins directly, plus a link to the full list:

| Coin | Network | Notes |
| --- | --- | --- |
| **USDT** | TRC-20 | The default — fast and cheap |
| **TON** | TON | Convenient if you're already in the Telegram ecosystem |
| **BTC** | Bitcoin | The classic |
| **XMR** | Monero | Maximum privacy |
| **Other coins →** | — | Opens the payment provider's full list (ETH, SOL, USDT on other networks, and more) |

{% hint style="warning" %}
**Network matters — especially for USDT.** TRC-20 ≠ ERC-20 ≠ BEP-20. Send on the wrong network and the money goes nowhere we can recover. The bot tells you which network it expects — match it exactly.
{% endhint %}

## How it works

{% stepper %}
{% step %}
### Choose a plan and a coin

In the bot, pick **Monthly** or **Annual**, then a currency. The bot generates a unique address and the exact amount to send.

<figure><img src=".gitbook/assets/crypto-address-qr.png" alt="Bot screen with payment address and QR code"><figcaption>[REAL CAPTURE] Bot screen with payment address and QR code</figcaption></figure>
{% endstep %}

{% step %}
### Copy the address or scan the QR

Before sending, check that:

* The **address** matches what the bot shows
* The **network** matches (for USDT especially)
* The **amount** is exact — round slightly up if your wallet subtracts the network fee separately
{% endstep %}

{% step %}
### Send the payment

Confirmation time depends on the blockchain and isn't something we control — but it's **usually a few minutes**.

<figure><img src=".gitbook/assets/crypto-status.png" alt="Payment status screen in the bot"><figcaption>[REAL CAPTURE] Payment status screen in the bot</figcaption></figure>
{% endstep %}

{% step %}
### Get your subscription

As soon as the blockchain confirms, the bot sends your subscription link (`https://sub.sirin.one/…`) and configuration QR.

<figure><img src=".gitbook/assets/crypto-confirmed.png" alt="Payment confirmation message in the bot"><figcaption>[REAL CAPTURE] Payment confirmation message in the bot</figcaption></figure>
{% endstep %}
{% endstepper %}

## If you don't have crypto yet

Options, ordered by convenience:

{% tabs %}
{% tab title="Telegram Wallet" %}
Built right into Telegram. Buy USDT or TON without leaving the app — the simplest path for newcomers. USDT via P2P usually takes a few minutes.
{% endtab %}

{% tab title="An exchange" %}
Binance, Bybit, OKX — buy USDT and withdraw to any TRC-20 wallet (for example, Trust Wallet). Cheapest path if you already have an account.
{% endtab %}

{% tab title="P2P with someone you know" %}
If you'd rather skip a KYC exchange, ask someone who already uses crypto. We don't run a P2P service and don't recommend specific individuals.
{% endtab %}
{% endtabs %}

{% hint style="info" %}
We deliberately don't walk you "by the hand" through buying crypto — it's outside our scope. First time and stuck? Send `/support` in the bot and we'll point you in the right direction.
{% endhint %}

## What can go wrong

| Problem | What happens | What to do |
| --- | --- | --- |
| **Wrong network** | Funds are lost — we can't recover them | Always verify the network before sending |
| **Sent too little** | The bot waits for the full amount | Send the difference to the same address |
| **Confirmation slow** | Network is congested or the fee was too low | Usually just wait; if over 2 hours, send `/support` |

## Refunds

{% hint style="success" %}
**Monthly & Annual — refundable within 7 days of payment, no questions asked.** Refunds go to an address you specify, in the same currency. Request it with `/support` in the bot.
{% endhint %}

The trial (99 ⭐) is non-refundable — it exists to be the test.

{% content-ref url="choosing-a-plan.md" %}
[choosing-a-plan.md](choosing-a-plan.md)
{% endcontent-ref %}
