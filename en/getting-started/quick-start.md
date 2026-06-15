# Quick Start

From zero to a working connection in a couple of minutes. No registration, no email, no card.

{% hint style="info" %}
**Before you start**

* Telegram (latest version)
* A way to pay: **Telegram Stars** for the 7-day trial, or a **crypto wallet** with a small balance for Monthly / Annual
* A VPN client for your device — pick it during the [Installation](../installation/) step (most people start with AmneziaVPN)
{% endhint %}

## The five steps

{% stepper %}
{% step %}
### Open the bot

Go to [@getsirin\_bot](https://t.me/getsirin_bot) or scan the QR code on [sirin.one](https://sirin.one), then tap **Start**.

<figure><img src=".gitbook/assets/qs-bot-start.png" alt="Sirin bot profile with the Start button"><figcaption>[REAL CAPTURE] @getsirin_bot profile screen with the Start button</figcaption></figure>
{% endstep %}

{% step %}
### Choose your language

On first launch the bot offers **English or Russian** as inline buttons. You can switch any time later from the **🌐** button in the menu — there's no slash command for it.
{% endstep %}

{% step %}
### Choose a plan

| Plan | Price | Pays with |
| --- | --- | --- |
| **Trial** | 99 ⭐ (≈ $1.99) · 7 days | Telegram Stars |
| **Monthly** | $7 / mo | Crypto |
| **Annual** | $60 / yr | Crypto |

See [Choosing a Plan](choosing-a-plan.md) for the full breakdown.

<figure><img src=".gitbook/assets/qs-plan-menu.png" alt="Plan selection menu in the bot"><figcaption>[REAL CAPTURE] Plan selection menu in @getsirin_bot</figcaption></figure>

{% hint style="info" %}
**Stars pays for the trial only.** Monthly and Annual are paid in crypto — see [Paying with Crypto](paying-with-crypto.md).
{% endhint %}
{% endstep %}

{% step %}
### Pay

{% tabs %}
{% tab title="Trial — Telegram Stars" %}
Tap to pay **99 ⭐** through Telegram's built-in payment. One tap, no blockchain, instant.
{% endtab %}

{% tab title="Monthly / Annual — Crypto" %}
Pick a coin — **USDT (TRC-20)**, **TON**, **BTC**, or **XMR** (tap **Other coins →** for more) — and send the exact amount to the address the bot shows. Confirmation usually arrives in a few minutes.
{% endtab %}
{% endtabs %}

<figure><img src=".gitbook/assets/qs-payment.png" alt="Crypto payment screen with address and QR code"><figcaption>[REAL CAPTURE] Crypto payment screen with address and QR code</figcaption></figure>
{% endstep %}

{% step %}
### Receive your configuration and connect

Once payment is confirmed, the bot sends you a personal subscription link (`https://sub.sirin.one/…`) and a QR code. **One link — all four protocols, both directions.**

Open your client, import via QR or link, and enable the connection.

<figure><img src=".gitbook/assets/qs-delivery.png" alt="Bot delivery message with subscription link and QR code"><figcaption>[REAL CAPTURE] Bot delivery message with subscription link and QR code</figcaption></figure>
{% endstep %}
{% endstepper %}

{% hint style="success" %}
That's it. No account to manage, nothing to remember but the bot.
{% endhint %}

## What you actually got

* **All four protocols** in one subscription — WireGuard, AmneziaWG, VLESS + Reality, Shadowsocks
* **Servers in both directions** — outside Russia and inside it
* **No activity or traffic logs** — only endpoint health metrics

{% hint style="info" %}
🔭 **On the roadmap — automatic rotation.** Today you switch protocols and servers with one tap, and your client picks up a fresh, health-ranked server list each time it refreshes. Fully automatic switch-before-you-notice rotation arrives with the dedicated Sirin app, post-launch.
{% endhint %}

## If something isn't working

* **QR won't scan** — copy the link from Telegram and paste it into your client instead.
* **One protocol won't connect** — switch to another; that's the point of having four.
* **Still stuck** — see [Troubleshooting](../support/troubleshooting.md), or send `/support` in the bot.

{% content-ref url="../installation/" %}
[installation](../installation/)
{% endcontent-ref %}

{% content-ref url="paying-with-crypto.md" %}
[paying-with-crypto.md](paying-with-crypto.md)
{% endcontent-ref %}
