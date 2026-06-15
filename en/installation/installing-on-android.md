# Installing on Android

{% hint style="info" %}
**Before you start**

* Android 8 or newer
* An active Sirin subscription — see [Quick Start](../getting-started/quick-start.md)
* Your subscription QR + link from [@getsirin\_bot](https://t.me/getsirin_bot)
{% endhint %}

## Pick your app

Sirin hands you **all four protocols in one subscription**. No single Android app speaks all of them, so pick by what you need — most people start with AmneziaVPN.

{% tabs %}
{% tab title="AmneziaVPN (recommended)" %}
Best for **WireGuard + AmneziaWG** — the protocols that survive the heaviest filtering. This is the QR the bot shows first (the `vpn://` one).

{% stepper %}
{% step %}
### Install AmneziaVPN

Two ways, in order of preference:

* **APK from the official site** — [amnezia.org](https://amnezia.org). Usually the most up-to-date build, always available.
* **Google Play** — [play.google.com/store/apps/details?id=org.amnezia.vpn](https://play.google.com/store/apps/details?id=org.amnezia.vpn). May be unavailable in some regions; if so, use the APK.

Installing the APK prompts Android to allow "installation from unknown sources" — that's expected.

<figure><img src=".gitbook/assets/android-amnezia-download.png" alt="AmneziaVPN download page on amnezia.org"><figcaption>[REAL CAPTURE] AmneziaVPN download page on amnezia.org</figcaption></figure>
{% endstep %}

{% step %}
### Allow the VPN

On first launch Android asks permission to add a VPN configuration. Tap **Allow**.

<figure><img src=".gitbook/assets/android-vpn-permission.png" alt="Android VPN permission dialog"><figcaption>[REAL CAPTURE] Android VPN permission dialog</figcaption></figure>
{% endstep %}

{% step %}
### Import your Sirin key

In [@getsirin\_bot](https://t.me/getsirin_bot), open your delivery message and find the **AmneziaVPN QR** (the `vpn://` code). In AmneziaVPN tap **+ → Scan QR** and point your camera at it.

_No camera? Long-press the `vpn://` link in Telegram to copy it, then in AmneziaVPN choose **Paste from clipboard**._

<figure><img src=".gitbook/assets/android-amnezia-import.png" alt="Importing the key into AmneziaVPN"><figcaption>[REAL CAPTURE] AmneziaVPN — add + scan QR</figcaption></figure>
{% endstep %}

{% step %}
### Connect

Tap the big button in the center. Connection takes 1–3 seconds. To try a different protocol or server later, reopen the app and switch — it's a one-tap change.

<figure><img src=".gitbook/assets/android-amnezia-connected.png" alt="Active connection in AmneziaVPN"><figcaption>[REAL CAPTURE] Active connection in AmneziaVPN</figcaption></figure>
{% endstep %}
{% endstepper %}
{% endtab %}

{% tab title="Hiddify (for VLESS + Shadowsocks)" %}
Best for **VLESS + Reality** and **Shadowsocks** — fast, low-profile protocols. Use the **subscription-link QR** (the `https://sub.sirin.one/…` one), not the `vpn://` one.

{% stepper %}
{% step %}
### Install Hiddify

From Google Play: search **Hiddify**, or use the link on [sirin.one](https://sirin.one). Where Play is unavailable, grab the APK from Hiddify's official releases.
{% endstep %}

{% step %}
### Import the subscription

In Hiddify tap **+ → Add from QR code** and scan the bot's **subscription** QR (or paste the `https://sub.sirin.one/…` link). Hiddify pulls in VLESS + Shadowsocks and refreshes the server list on its own.

<figure><img src=".gitbook/assets/android-hiddify-import.png" alt="Importing a subscription into Hiddify"><figcaption>[REAL CAPTURE] Hiddify — add from QR / subscription link</figcaption></figure>
{% endstep %}

{% step %}
### Connect

Tap connect, allow the VPN configuration when Android asks, and you're online.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
**Sing-Box** also works on Android for VLESS + Shadowsocks and uses the same subscription QR. Hiddify is the smoother default for most people; Sing-Box is a fine alternative if you prefer it.
{% endhint %}
{% endtab %}
{% endtabs %}

## Verify it's working

Open your browser and visit [icanhazip.com](https://icanhazip.com). The IP should be Sirin's server — not your home or mobile provider's.

{% hint style="success" %}
Want to confirm your region looks right too? Any "what's my IP" site will show the country your traffic exits from.
{% endhint %}

<details>

<summary>Other clients (only if you know what you're doing)</summary>

* **v2rayNG** ([GitHub](https://github.com/2dust/v2rayNG)) — VLESS + Reality and Shadowsocks; no WireGuard/AmneziaWG. Removed from Google Play in some regions, so grab the APK from GitHub. Import via the `vless://` / `ss://` URI.
* **Official WireGuard app** — WireGuard only; can't import VLESS or Shadowsocks. Fine as a backup for the WG profile.

These are single-protocol or power-user tools — for the full Sirin bundle on Android, stick with AmneziaVPN and/or Hiddify above.

</details>

## If it doesn't work

* **APK won't install** — enable "Install from unknown sources" in Android settings.
* **QR won't scan** — copy the link from Telegram and paste it instead.
* **Can't connect on one protocol** — switch to another (that's the whole point of having four). VLESS/Shadowsocks live in Hiddify; WireGuard/AmneziaWG in AmneziaVPN.
* **Still stuck** — see [Troubleshooting](../support/troubleshooting.md), or send `/support` in the bot.

{% content-ref url="../getting-started/quick-start.md" %}
[quick-start.md](../getting-started/quick-start.md)
{% endcontent-ref %}

{% content-ref url="../support/troubleshooting.md" %}
[troubleshooting.md](../support/troubleshooting.md)
{% endcontent-ref %}

{% hint style="warning" %}
Trying to import the **VLESS** key directly into **AmneziaVPN**? It can be unreliable right now — use **Hiddify** (or Sing-Box) for VLESS + Shadowsocks, and keep AmneziaVPN for WireGuard + AmneziaWG.
{% endhint %}
