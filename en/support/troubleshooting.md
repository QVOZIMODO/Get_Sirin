# Troubleshooting

Most problems come down to one of three things: the payment hasn't confirmed yet, the wrong key went into the wrong app, or the protocol you're on is being blocked right now. Find your symptom below and work through the fix.

{% hint style="info" %}
**The fastest fix is often the right app.** Sirin hands you **all four protocols in one subscription**, but no single app speaks all of them. **WireGuard + AmneziaWG** live in **AmneziaVPN**; **VLESS + Reality and Shadowsocks** live in **Hiddify** (or Sing-Box). If something won't import or won't connect, the most common cause is a protocol in the wrong client.
{% endhint %}

## Quick reference

| Symptom | Most likely cause | Jump to |
| --- | --- | --- |
| Paid, but nothing arrived | Payment not yet confirmed on-chain, or sent on the wrong network | [Payment didn't arrive](#i-paid-but-nothing-arrived) |
| Bot is silent | Telegram blocked in your region, or a transient issue | [Bot won't respond](#the-bot-doesnt-respond) |
| Key won't import / won't connect | Wrong protocol in the wrong app | [Client won't connect](#imported-but-the-client-wont-connect) |
| Connected, but no internet | A second VPN, DNS, or firewall conflict | [Connected but no internet](#connected-but-no-internet) |
| Worked yesterday, not today | The protocol you were on is now being filtered | [Worked yesterday, not today](#it-worked-yesterday-not-today) |
| Slow | Distant or busy server, or provider throttling | [Slow speeds](#speed-is-slow) |
| One specific site won't load | The site blocks VPN IPs, or you need the other direction | [A specific site won't load](#a-specific-site-wont-load) |

***

## I paid but nothing arrived

{% hint style="warning" %}
**Crypto confirmation depends on the blockchain, not on us.** It's usually a few minutes, but it isn't instant and we can't speed it up. Send `/status` to see where your payment stands.
{% endhint %}

{% stepper %}
{% step %}
### Check `/status` in the bot

If it shows **awaiting confirmation**, the network just hasn't confirmed your transaction yet. Give it a few more minutes.
{% endstep %}

{% step %}
### Still nothing after a while? Check the chain

Look up your transaction in a block explorer (Tronscan for USDT-TRC20, mempool.space for BTC, etc.). If it's **confirmed on-chain but the bot hasn't seen it**, send `/support` and include the transaction hash.
{% endstep %}

{% step %}
### Did you send on the wrong network?

USDT exists on several networks. If you sent **USDT-ERC20** to a **USDT-TRC20** address (or any mismatch), the funds went somewhere we can't reach and **can't recover**. Always match the network shown at checkout before sending.
{% endstep %}
{% endstepper %}

## The bot doesn't respond

{% hint style="info" %}
Sirin lives entirely inside Telegram. If Telegram itself can't reach you, the bot can't either.
{% endhint %}

1. Check whether **Telegram works at all** for you right now. If Telegram is blocked in your region, you'll need another way to reach it first (yes — the chicken-and-egg problem).
2. Check the service status at [status.sirin.one](https://status.sirin.one).
3. If Telegram is fine and status is green but the bot is silent, wait 5–10 minutes, then send `/support`.

## Imported but the client won't connect

This is almost always a **protocol-in-the-wrong-app** problem. Match the key to the client:

| You're using | Import this | In this app |
| --- | --- | --- |
| WireGuard / AmneziaWG | the `vpn://` QR | **AmneziaVPN** |
| VLESS + Reality / Shadowsocks | the `https://sub.sirin.one/…` subscription link or QR | **Hiddify** (or Sing-Box) |

{% hint style="danger" %}
**Don't import the VLESS / Shadowsocks key into AmneziaVPN.** Via Sirin's one-tap key, AmneziaVPN imports **WireGuard and AmneziaWG** reliably — but the Xray/VLESS import through our key is unreliable today. For **VLESS + Reality and Shadowsocks, use Hiddify** instead.
{% endhint %}

{% stepper %}
{% step %}
### Confirm what you imported

In Hiddify you should have added a **subscription link** (`https://sub.sirin.one/…`), not a single config. In AmneziaVPN you should have scanned the **`vpn://`** QR.
{% endstep %}

{% step %}
### Try a different server, then a different protocol

In your client, pick another server from the list. If that doesn't help, switch protocols — that's the whole point of having four. Switching is a **manual one-tap** action in the client.
{% endstep %}

{% step %}
### Reinstall the app

Delete and reinstall the client from the store. This resolves more import quirks than we'd like to admit.
{% endstep %}

{% step %}
### Still stuck? `/support`

Send `/support` with the details listed at the [bottom of this page](#none-of-this-helped).
{% endstep %}
{% endstepper %}

## Connected but no internet

The tunnel is up but pages won't load — usually a routing conflict on the device.

1. **Only one VPN at a time.** Two active VPNs almost always break routing. Disable any other VPN profile.
2. **iOS / macOS:** Settings → VPN → make sure the Sirin profile is the only one enabled.
3. **Windows:** check that antivirus or firewall isn't blocking your VPN client.
4. **Restart the connection.** Disconnect, reconnect. Sometimes that's all it needs.
5. **Try a different server or protocol** in the client.

## It worked yesterday, not today

{% hint style="warning" %}
**There is no automatic, switch-before-you-notice failover today** — that's on the [roadmap](#whats-on-the-roadmap). What does happen: your subscription returns a **health-ranked** server list that shifts away from drained endpoints the **next time your client re-fetches it**. So the fix is to refresh and switch manually.
{% endhint %}

{% stepper %}
{% step %}
### Refresh your subscription

In the client, open the Sirin subscription and tap **Refresh** / **Update** / **Sync**. This pulls a fresh, health-ranked server list.
{% endstep %}

{% step %}
### Switch to a different server or protocol

After refreshing, pick a different server — or a different protocol entirely (one tap). If WireGuard is being filtered, try VLESS + Reality in Hiddify, and vice versa.
{% endstep %}

{% step %}
### Check for an incident

If nothing works in your region, check [status.sirin.one](https://status.sirin.one). A regional incident means we already know and are on it.
{% endstep %}
{% endstepper %}

## Speed is slow

1. **Try a nearer server.** Distance adds latency.
2. **Try a different protocol.** WireGuard and AmneziaWG (UDP) are usually faster than Shadowsocks over TCP.
3. **Measure without the VPN.** If your bare connection is slow too, that's your provider, not Sirin.
4. **In Russia, some providers throttle UDP.** If WireGuard/AmneziaWG feel slow, switch to a TCP-based protocol like **VLESS + Reality** or **Shadowsocks**.

## A specific site won't load

{% hint style="info" %}
Some banks, streaming services, and government portals deliberately block known VPN IP ranges, or require an IP from a specific country. This isn't always fixable on our side.
{% endhint %}

* **Reaching Russian services from abroad?** Choose a server **inside Russia**.
* **Reaching Western services from Russia?** Choose a server **outside Russia**.
* If switching direction still doesn't help, the site is likely blocking on something other than IP (cookies, browser fingerprint), which is outside what a VPN can change.

***

## None of this helped

Send **`/support`** in [@getsirin\_bot](https://t.me/getsirin_bot). To get a fast answer, include:

* What exactly fails (which step)
* Device and OS
* Which client app you're using
* Which protocol and server you selected
* Your approximate region (country, city)

{% hint style="info" %}
Account questions — changing language, closing your account, anything about your subscription — also go through **`/support`**. (Language can be switched any time with the 🌐 button in the menu or the inline buttons on `/start`.)
{% endhint %}

## What's on the roadmap

{% hint style="info" %}
🔭 **Automatic rotation / switch-before-you-notice failover** is planned for the dedicated Sirin app after launch. Today, switching protocols and servers is a fast manual one-tap action, and the subscription re-ranks servers on each refresh. We'd rather ship it honestly than claim it early.
{% endhint %}

***

## Related pages

{% content-ref url="../installation/installing-on-ios-iphone-ipad.md" %}
[installing-on-ios-iphone-ipad.md](../installation/installing-on-ios-iphone-ipad.md)
{% endcontent-ref %}

{% content-ref url="frequently-asked-questions.md" %}
[frequently-asked-questions.md](frequently-asked-questions.md)
{% endcontent-ref %}
