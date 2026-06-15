# Frequently asked questions

Short, honest answers. If yours isn't here, send `/support` in [@getsirin\_bot](https://t.me/getsirin_bot).

## General

<details>

<summary>What is Sirin?</summary>

An internet-access service you set up entirely through a Telegram bot. You get four protocols in one subscription, pay with crypto (or Telegram Stars for the trial), and there's no registration — no email, no phone, no cards.

</details>

<details>

<summary>How is Sirin different from a regular VPN?</summary>

Two things. First, it works **in both directions** — pick a server outside Russia to reach Western services, or a server inside Russia to reach Russian ones from abroad. Second, you carry **all four protocols at once**, so if one is being filtered you switch to another with one tap. No registration or email is required either.

</details>

<details>

<summary>Is Sirin open source?</summary>

Partly. The protocols are open (WireGuard, AmneziaWG, VLESS/Xray, Shadowsocks) and our recommended client, AmneziaVPN, is open source. The subscription and server infrastructure is closed — the same model as Amnezia Premium, Mullvad, and most working services.

</details>

<details>

<summary>Where are you registered?</summary>

A Georgian legal entity. Sirin is a commercial service operating under Georgian law — it does not circumvent sanctions and does not work with sanctioned persons.

</details>

## Payments & subscriptions

<details>

<summary>What payment methods do you accept?</summary>

**Crypto** via NOWPayments. The in-bot picker offers **USDT-TRC20, TON, BTC, and XMR** directly, with **Other coins →** for the full list (ETH, SOL, USDT-ERC20, and more) through the provider. **Telegram Stars are for the 7-day trial only** — monthly and annual plans are paid in crypto.

</details>

<details>

<summary>Why no card payments?</summary>

Cards require storing personal data and working through bank processing — both of which run against Sirin's privacy model.

</details>

<details>

<summary>How much does it cost?</summary>

| Plan | Price | How you pay |
| --- | --- | --- |
| Trial (7 days) | 99 ⭐ (≈ $1.99) | Telegram Stars only |
| Monthly | $7 | Crypto |
| Annual | $60 (≈ $5/mo) | Crypto |
| Team | from $20 / seat·mo, min 5 seats | Crypto, request-based |

See [Choosing a plan](../getting-started/choosing-a-plan.md) for the full breakdown. Team isn't self-serve in the bot yet — message `/support`.

</details>

<details>

<summary>Does it auto-renew?</summary>

No — renewal is **manual**. Before your plan ends, the bot reminds you, and you pay again if you want to keep going. We don't store cards and can't silently re-charge you.

</details>

<details>

<summary>Do you offer refunds?</summary>

Monthly and Annual are refundable within 7 days of payment — request it with `/support`. The trial is non-refundable (it's ≈ $1.99 and exists to be the test).

</details>

<details>

<summary>Can I share my subscription?</summary>

Technically it works on more than one device at a time, but a subscription is meant for one person. For families or teams the Team plan is the right fit.

</details>

## Servers & protocols

<details>

<summary>Where do I exit when I connect?</summary>

Your traffic **appears in Russia** (IPv4 egress). IPv6 is captured and blocked, so there's no IPv6 leak. You choose direction per server: a server **outside Russia** for Western services, or one **inside Russia** for Russian services from abroad. The current server list is visible in your client after you import the subscription.

</details>

<details>

<summary>Which protocol should I use?</summary>

Depends on your region and what you're doing:

* **VLESS + Reality** — the most block-resistant; disguises traffic as ordinary HTTPS.
* **AmneziaWG** — WireGuard with obfuscation; resists detection better than plain WireGuard.
* **WireGuard** — typically the fastest.
* **Shadowsocks** — a solid fallback, good over TCP where UDP is throttled.

Switching between them is a manual one-tap change in your client.

</details>

<details>

<summary>Which app imports which protocol?</summary>

This is the single most useful thing to know:

| App | Imports |
| --- | --- |
| **AmneziaVPN** | WireGuard, AmneziaWG (via the `vpn://` key) |
| **Hiddify** / **Sing-Box** | VLESS + Reality, Shadowsocks (via the `https://sub.sirin.one/…` link) |

Hiddify and Sing-Box do **not** do WireGuard/AmneziaWG, and importing VLESS/Shadowsocks into AmneziaVPN via our key is unreliable today. Pick the app that matches the protocol you want.

</details>

<details>

<summary>Does Sirin rotate or fail over automatically?</summary>

Not yet. Today you switch protocols and servers with one tap, and your subscription returns a **health-ranked** server list that shifts away from drained endpoints each time your client re-fetches it. **Fully automatic, switch-before-you-notice rotation is on the roadmap** for the dedicated Sirin app after launch — we don't claim it as a current feature.

</details>

<details>

<summary>Does Sirin work on a router?</summary>

Formally yes, if your router supports WireGuard or OpenWrt with the right modules — but we don't publish router instructions at launch.

</details>

<details>

<summary>Can I use it for torrents or streaming?</summary>

We don't forbid P2P, but we don't optimize for it and per-server speeds may be limited. Streaming may work but isn't guaranteed — services like Netflix actively block VPN IP ranges, and that's outside what a VPN can fix.

</details>

## Security & privacy

<details>

<summary>Do you keep logs of my activity?</summary>

No traffic or activity logs. The only identifier we hold is your Telegram ID; credentials and your subscription token are encrypted at rest (the token is stored only as a hash). We do keep **endpoint health metrics** — synthetic probes, not your activity — and raw health rows are discarded after 7 days. See [What we log, what we don't](../what-we-log-what-we-dont.md).

</details>

<details>

<summary>Do you share data with authorities?</summary>

Only under a lawful request through a Georgian court — and the activity logs typically demanded simply don't exist, because we don't keep them.

</details>

<details>

<summary>Can my ISP tell I'm using a VPN?</summary>

Your ISP sees encrypted traffic. **VLESS + Reality** and **AmneziaWG** are built to look like ordinary HTTPS, which makes detection much harder. Plain WireGuard and Shadowsocks in default configurations are easier to fingerprint.

</details>

<details>

<summary>How private is Telegram itself?</summary>

Telegram isn't the most private messenger, but for delivering subscriptions and configs it's adequate. Your chat with the bot isn't end-to-end encrypted, but it only ever contains technical setup info — never activity logs.

</details>

<details>

<summary>Do you use multi-hop?</summary>

No — Sirin is single-hop. Multi-hop adds latency without meaningfully improving privacy against realistic threats.

</details>

## About the service

<details>

<summary>Is there a dedicated Sirin app?</summary>

Not at launch. We use proven clients — AmneziaVPN (recommended), Hiddify, Sing-Box, and the official WireGuard app — rather than duplicating their work. A dedicated Sirin app (with automatic rotation) is on the roadmap. See the [installation guides](../installation/installing-on-ios-iphone-ipad.md).

</details>

<details>

<summary>Who runs Sirin?</summary>

A small team operating under a Georgian legal entity. We don't disclose team composition — that's part of our operational security.

</details>

<details>

<summary>When did Sirin launch?</summary>

Sirin is launching **21 June 2026**. If you're reading this earlier, that's the early-access window.

</details>

<details>

<summary>Is there a referral program or gifting?</summary>

Neither at launch. Both are likely later, but we don't promise dates.

</details>

***

## Still have a question?

{% hint style="info" %}
Send **`/support`** in [@getsirin\_bot](https://t.me/getsirin_bot) — that's also where account questions (language, closing your account, your subscription) are handled. Setup not working? Start with [Troubleshooting](troubleshooting.md).
{% endhint %}

{% content-ref url="troubleshooting.md" %}
[troubleshooting.md](troubleshooting.md)
{% endcontent-ref %}

{% content-ref url="../getting-started/choosing-a-plan.md" %}
[choosing-a-plan.md](../getting-started/choosing-a-plan.md)
{% endcontent-ref %}
