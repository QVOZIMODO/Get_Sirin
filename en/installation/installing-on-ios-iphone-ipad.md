# Installing on iOS (iPhone, iPad)

{% hint style="info" %}
**Before you start**

* iOS 14 or newer
* An active Sirin subscription — see [Quick Start](../getting-started/quick-start.md)
* Your subscription QR + link from [@getsirin\_bot](https://t.me/getsirin_bot)
{% endhint %}

## Pick your app

Sirin hands you **all four protocols in one subscription**. No single iOS app speaks all of them, so pick by what you need — most people start with AmneziaVPN.

{% tabs %}
{% tab title="AmneziaVPN (recommended)" %}
Best for **WireGuard + AmneziaWG** — the protocols that survive the heaviest filtering. This is the QR the bot shows first (the `vpn://` one).

{% stepper %}
{% step %}
### Install AmneziaVPN

From the App Store: [apps.apple.com/app/amneziavpn](https://apps.apple.com/app/amneziavpn/id1600529900)

<figure><img src=".gitbook/assets/ios-amnezia-appstore.png" alt="AmneziaVPN on the App Store"><figcaption>[REAL CAPTURE] AmneziaVPN page in the App Store</figcaption></figure>
{% endstep %}

{% step %}
### Allow the VPN

On first launch iOS asks permission to add a VPN configuration. Tap **Allow**.

<figure><img src=".gitbook/assets/ios-vpn-permission.png" alt="iOS VPN permission dialog"><figcaption>[REAL CAPTURE] iOS VPN permission dialog</figcaption></figure>
{% endstep %}

{% step %}
### Import your Sirin key

In [@getsirin\_bot](https://t.me/getsirin_bot), open your delivery message and find the **AmneziaVPN QR** (the `vpn://` code). In AmneziaVPN tap **+ → Scan QR** and point your camera at it.

_No camera? Long-press the `vpn://` link in Telegram to copy it, then in AmneziaVPN choose **Paste from clipboard**._

<figure><img src=".gitbook/assets/ios-amnezia-import.png" alt="Importing the key into AmneziaVPN"><figcaption>[REAL CAPTURE] AmneziaVPN — add + scan QR</figcaption></figure>
{% endstep %}

{% step %}
### Connect

Tap the big button in the center. Connection takes 1–3 seconds. To try a different protocol or server later, reopen the app and switch — it's a one-tap change.

<figure><img src=".gitbook/assets/ios-amnezia-connected.png" alt="Active connection in AmneziaVPN"><figcaption>[REAL CAPTURE] Active connection in AmneziaVPN</figcaption></figure>
{% endstep %}
{% endstepper %}
{% endtab %}

{% tab title="Hiddify (for VLESS + Shadowsocks)" %}
Best for **VLESS + Reality** and **Shadowsocks** — fast, low-profile protocols. Use the **subscription-link QR** (the `https://sub.sirin.one/…` one), not the `vpn://` one.

{% stepper %}
{% step %}
### Install Hiddify

From the App Store: search **Hiddify**, or use the link on [sirin.one](https://sirin.one).
{% endstep %}

{% step %}
### Import the subscription

In Hiddify tap **+ → Add from QR code** and scan the bot's **subscription** QR (or paste the `https://sub.sirin.one/…` link). Hiddify pulls in VLESS + Shadowsocks and refreshes the server list on its own.

<figure><img src=".gitbook/assets/ios-hiddify-import.png" alt="Importing a subscription into Hiddify"><figcaption>[REAL CAPTURE] Hiddify — add from QR / subscription link</figcaption></figure>
{% endstep %}

{% step %}
### Connect

Tap connect, allow the VPN configuration when iOS asks, and you're online.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
**Sing-Box on iOS** also works for VLESS + Shadowsocks, but the App Store build lags behind the Android one — if a brand-new feature is missing, that's why. Hiddify is the smoother default on iPhone.
{% endhint %}
{% endtab %}
{% endtabs %}

## Verify it's working

Open Safari and visit [icanhazip.com](https://icanhazip.com). The IP should be Sirin's server — not your home or mobile provider's.

{% hint style="success" %}
Want to confirm your region looks right too? Any "what's my IP" site will show the country your traffic exits from.
{% endhint %}

<details>

<summary>Other clients (only if you know what you're doing)</summary>

* **Official WireGuard app** — WireGuard only; can't import VLESS or Shadowsocks. Fine as a backup for the WG profile.
* **Shadowrocket** (paid) — solid VLESS + Shadowsocks support if you already own it.

These are single-protocol or power-user tools — for the full Sirin bundle on iOS, stick with AmneziaVPN and/or Hiddify above.

</details>

## If it doesn't work

* **App won't start** — delete and reinstall from the App Store.
* **QR won't scan** — copy the link from Telegram and paste it instead.
* **Can't connect on one protocol** — switch to another (that's the whole point of having four). VLESS/Shadowsocks live in Hiddify; WireGuard/AmneziaWG in AmneziaVPN.
* **Still stuck** — see [Troubleshooting](../support/troubleshooting.md), or send `/support` in the bot.

{% hint style="warning" %}
Trying to import the **VLESS** key directly into **AmneziaVPN**? It can be unreliable right now — use **Hiddify** for VLESS + Shadowsocks, and keep AmneziaVPN for WireGuard + AmneziaWG.
{% endhint %}
