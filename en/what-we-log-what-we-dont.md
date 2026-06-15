# What we log, what we don't

An honest inventory. We don't hand you a glossy "zero-logs" banner and walk away — every working service has *some* operational data. Instead, we tell you exactly what we store, why, and for how long, and we draw a hard line: **no user activity or traffic logs, ever.**

{% hint style="success" %}
**The short version.** The only thing that identifies you is your Telegram ID. No name, phone, address, email, raw IP, user agent, or device fingerprint is stored. We keep no record of which sites you visit, what you download, or when you connect.
{% endhint %}

## The whole picture at a glance

| What we store | What we **don't** store |
| --- | --- |
| Your Telegram ID | Your name, phone, address, passport |
| Subscription status (tier, expiry) | Your email* |
| Per-protocol cryptographic credentials (encrypted) | Your raw IP address |
| Payment history (amount, currency, txn ID, date) | User agent / device fingerprint |
| Aggregated server health metrics | Your traffic, DNS queries, browsing history |
| | Connection / disconnection timestamps |

<sub>\* B2B `contact_email` is the **one** exception — see the note below. It is never collected for individual users.</sub>

## What we necessarily store

**Your Telegram ID.** Without it we can't tell one user from another. It is the *only* identifier we hold. We don't know your name, phone number, or email — only the numeric ID Telegram assigns.

**Your subscription status.** Active or not, which tier, when it expires. The bot needs this to decide whether to hand you a configuration.

**Per-protocol cryptographic credentials.** Public keys for WireGuard and AmneziaWG, identifiers for VLESS + Reality, passwords for Shadowsocks. Your client needs these to connect.

{% hint style="info" %}
**Encrypted at rest.** Your credential data and your subscription token are stored **Fernet-encrypted** at rest. The subscription token itself is never stored in plaintext — we keep only an **HMAC hash** of it. Key exchange for WireGuard, AmneziaWG, and VLESS + Reality uses **X25519**, with **ChaCha20-Poly1305** for encryption. (The only Ed25519 key we hold is the PGP key that signs our [warrant canary](jurisdiction-and-law.md) — not anything tied to your traffic.)
{% endhint %}

**Payment history.** Amount, currency, the transaction ID from the payment processor, and the date. Required for tax reporting through our Georgian entity and for processing refunds.

**The B2B exception — `contact_email`.** If you buy a **Team** plan, we store one invoicing email in an isolated table, used solely to send invoices and receipts. This is the single piece of contact PII anywhere in the system, and it never applies to individual subscriptions.

**Server operational metrics.** Aggregate load, throughput, and error counts per server. These are server-level numbers — never tied to an individual user.

## What we store temporarily

**Health signals.** Sirin runs **synthetic probes** against its own endpoints to know which protocols are working in which regions today. These are operational health checks — **not records of your activity or traffic.** When a real subscription fetch happens, what's recorded is reduced to the **2-character ISO country code** (never the IP), the protocol, and success/failure.

{% hint style="info" %}
**GeoIP, done minimally.** When we resolve a request's country, the raw IP is released **immediately** after lookup. Only the 2-character country code is persisted. The full IP never lands on disk.
{% endhint %}

Raw health-signal rows are deleted after **7 days** and rolled into hourly summaries that carry no per-user link.

## What we don't store

**Your IP address.** When you connect to a Sirin server, the network sees your IP — like every server on the internet does. We do not log it and we do not save it.

**Your traffic.** Which sites you open, what you request, what you download — we don't see it and we don't store it. A Sirin server routes your packets; it does not inspect them.

**Your DNS queries.** Where you want to go is nobody's business but yours.

**Connection timestamps.** When you connected and when you disconnected — not logged. We only know your subscription is active.

**Your email, name, phone, payment card, passport, address.** We never ask, so we can't store them. (Team invoicing email aside — see above.)

**Browser history, app lists, chat contents.** Outside what any VPN provider can see in the first place.

{% hint style="info" %}
**About egress.** Your traffic egresses in **Russia** over IPv4 (for example, a St. Petersburg address). IPv6 is captured and rejected at the endpoint, so there is no native IPv6 leak.
{% endhint %}

## How long we keep things

| What | How long |
| --- | --- |
| Telegram ID and subscription status | While subscription is active + 30 days |
| Cryptographic credentials | While subscription is active, then destroyed |
| Subscription token (as HMAC hash) | While subscription is active, then destroyed |
| B2B invoicing email | While the Team account is active (invoicing only) |
| Payment history | 5 years (Georgian tax-law requirement) |
| Raw health signals | 7 days |
| Aggregated health summaries | Up to 12 months |
| Server operational metrics | 30 days |

## Removing your account

<details>

<summary>How do I delete my data?</summary>

There's no self-serve delete button today. To close your account and have your data removed, message [@getsirin\_bot](https://t.me/getsirin_bot) and run **`/support`** — ask us to delete your account. Your Telegram ID and all linked data (credentials, subscription, health signals) are removed from the active database. Payment history is retained in **anonymized** form (amount, date, currency) solely for tax reporting, unlinked from your ID.

</details>

## What happens if someone arrives with a legal request

The honest answer is that there is almost nothing to hand over. See the next page.

{% content-ref url="jurisdiction-and-law.md" %}
[jurisdiction-and-law.md](jurisdiction-and-law.md)
{% endcontent-ref %}
