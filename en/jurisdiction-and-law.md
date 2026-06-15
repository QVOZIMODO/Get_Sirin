# Jurisdiction and law

Where we're registered, what law applies, and what we can — and can't — produce when someone comes knocking.

## Where Sirin is registered

Sirin operates as a legal entity in **Georgia**. The specific company name and registration details are listed in the website footer and on any invoices issued to B2B clients.

Georgia was chosen because:

* It's not part of the Eurasian Union and is not required to execute Russian legal requests directly.
* It's not an EU member, which simplifies cryptocurrency payment processing.
* Local law doesn't require VPN providers to connect to state censorship systems or maintain activity logs.
* Entity registration and banking work quickly and predictably there.

{% hint style="info" %}
This isn't an "offshore" or a jurisdictional trick. It's simply a working country for this kind of business.
{% endhint %}

## What law applies to us

Primarily Georgian. In practice that means:

* We maintain tax reporting to the Georgian tax authorities.
* We comply with lawful court orders issued through the Georgian legal system.
* Disputes involving us are heard in Georgian courts.

## Third-party requests

Russian authorities have no direct legal access to us. Requests from any state must go through Georgian courts via the mutual legal assistance (MLAT) mechanism — slow, expensive, and requiring legitimate grounds.

If we receive a lawful request through a Georgian court, we'll respond with what we have. And, as the [logging page](what-we-log-what-we-dont.md) describes, what we have is almost nothing:

| Question | What we can answer |
| --- | --- |
| Which sites did this user visit? | **We don't know.** No traffic or DNS logs exist. |
| When did they connect or disconnect? | **We don't know.** No connection timestamps. |
| What is their name, email, or phone? | **We don't know.** No such PII is collected. |
| What *do* you hold? | Telegram ID, subscription status, payment history. |

{% hint style="success" %}
Even under full legal cooperation, we **physically cannot** produce "user activity logs" — they don't exist. This isn't a legal posture, it's an architectural fact.
{% endhint %}

## The warrant canary

{% hint style="info" %}
**Our warrant canary is live.** We publish and **re-sign it monthly** with our PGP key, available at **`/pgp`** and in **`/.well-known/security.txt`**. As long as the canary keeps appearing, freshly signed, it states that we have not received any secret legal demand or gag order. If it goes stale or disappears, treat that as a signal.
{% endhint %}

## What you can do on your side

We don't know your Telegram ID unless you start the bot. So if you want minimal linkage to your identity:

* Create a Telegram account on an anonymous SIM or number.
* Pay with **XMR**, or with USDT (TRC-20) through an exchange that has no KYC tied to you.
* When you're done, message the bot and run **`/support`** to ask us to delete your account.

{% hint style="info" %}
These are recommendations, not requirements. Most users don't need this level of separation — but if you do, you can achieve it without our involvement.
{% endhint %}

## What we don't do

* We don't share data with third parties voluntarily.
* We don't act on informal requests, "friendly conversations," or pressure without a court order.
* We don't run a Tor mirror (despite what some VPN marketing implies is standard) — if you see one claiming to be us, it isn't.

## Disclaimer

{% hint style="warning" %}
We are not lawyers, and this page is not legal advice. The legality of VPN use in your country is your responsibility. In Russia, using a VPN to bypass blocks is legally ambiguous; criminal liability for it is not established as of this writing (2026), but administrative liability is possible in specific cases. If you need analysis of your specific situation, consult a lawyer.
{% endhint %}
