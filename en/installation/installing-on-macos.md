# Installing on macOS

{% hint style="info" %}
**Before you start**

* macOS 12 (Monterey) or newer
* An active Sirin subscription — see [Quick Start](../getting-started/quick-start.md)
* Your subscription QR + link from [@getsirin\_bot](https://t.me/getsirin_bot)
{% endhint %}

## Pick your app

Sirin hands you **all four protocols in one subscription**. No single macOS app speaks all of them, so pick by what you need — most people start with AmneziaVPN.

{% tabs %}
{% tab title="AmneziaVPN (recommended)" %}
Best for **WireGuard + AmneziaWG** — the protocols that survive the heaviest filtering. This is the QR the bot shows first (the `vpn://` one).

{% stepper %}
{% step %}
### Install AmneziaVPN

Download the `.dmg` from [amnezia.org](https://amnezia.org), open it, and drag the app into **Applications**.

On first launch macOS may ask: _"Are you sure you want to open an application downloaded from the internet?"_ — click **Open**.

<figure><img src=".gitbook/assets/macos-amnezia-install.png" alt="Installing AmneziaVPN from the .dmg"><figcaption>[REAL CAPTURE] Installing AmneziaVPN — drag to Applications + Gatekeeper dialog</figcaption></figure>
{% endstep %}

{% step %}
### Allow the VPN

AmneziaVPN asks permission to install a system VPN configuration. Enter your admin password.

<figure><img src=".gitbook/assets/macos-vpn-permission.png" alt="macOS admin password prompt for VPN configuration"><figcaption>[REAL CAPTURE] macOS admin password prompt</figcaption></figure>
{% endstep %}

{% step %}
### Import your Sirin key

Open [@getsirin\_bot](https://t.me/getsirin_bot) in Telegram (desktop) and find the **AmneziaVPN** entry (the `vpn://` one). Copy the link, then in AmneziaVPN choose **+ → Paste from clipboard**.

_Prefer the camera? In AmneziaVPN choose **+ → Scan QR** and hold your phone showing the bot's `vpn://` QR up to the Mac's camera._

<figure><img src=".gitbook/assets/macos-amnezia-import.png" alt="Importing the key into AmneziaVPN on macOS"><figcaption>[REAL CAPTURE] AmneziaVPN — paste from clipboard / scan QR</figcaption></figure>
{% endstep %}

{% step %}
### Connect

Click the big connect button. Connection takes 1–3 seconds. To try a different protocol or server later, switch in the app — it's a one-tap change.

<figure><img src=".gitbook/assets/macos-amnezia-connected.png" alt="Active connection in AmneziaVPN on macOS"><figcaption>[REAL CAPTURE] Active connection in AmneziaVPN</figcaption></figure>
{% endstep %}
{% endstepper %}
{% endtab %}

{% tab title="Hiddify / Sing-Box (for VLESS + Shadowsocks)" %}
Best for **VLESS + Reality** and **Shadowsocks** — fast, low-profile protocols. Use the **subscription-link QR** (the `https://sub.sirin.one/…` one), not the `vpn://` one. On desktop, **Hiddify and Sing-Box are equally fine** — pick either.

{% stepper %}
{% step %}
### Install Hiddify or Sing-Box

Download Hiddify (or Sing-Box) for macOS from its official site, or use the link on [sirin.one](https://sirin.one). Open the `.dmg` and drag the app into **Applications**.
{% endstep %}

{% step %}
### Import the subscription

In the app choose **Add profile → from clipboard** and paste the `https://sub.sirin.one/…` link (or scan the bot's **subscription** QR). It pulls in VLESS + Shadowsocks and refreshes the server list on its own.

<figure><img src=".gitbook/assets/macos-hiddify-import.png" alt="Importing a subscription into Hiddify on macOS"><figcaption>[REAL CAPTURE] Hiddify / Sing-Box — add subscription</figcaption></figure>
{% endstep %}

{% step %}
### Connect

Click connect, approve the VPN configuration when macOS asks, and you're online.
{% endstep %}
{% endstepper %}
{% endtab %}
{% endtabs %}

## Verify it's working

Open Safari and visit [icanhazip.com](https://icanhazip.com). The IP should be Sirin's server — not your home network's.

{% hint style="success" %}
Want to confirm your region looks right too? Any "what's my IP" site will show the country your traffic exits from.
{% endhint %}

<details>

<summary>Other clients (only if you know what you're doing)</summary>

* **Official WireGuard app** (Mac App Store) — WireGuard only; can't import VLESS or Shadowsocks. The bot can hand you an on-demand `.conf` for the WG profile.
* **Sing-Box** — a solid alternative to Hiddify for VLESS + Shadowsocks on the desktop.

These are single-protocol or power-user tools — for the full Sirin bundle on macOS, stick with AmneziaVPN and/or Hiddify above.

</details>

## If it doesn't work

* **macOS blocks launch** — System Settings → Privacy & Security → **Open Anyway**.
* **QR won't scan** — copy the link from Telegram Desktop and paste it instead.
* **Can't connect on one protocol** — switch to another (that's the whole point of having four). VLESS/Shadowsocks live in Hiddify or Sing-Box; WireGuard/AmneziaWG in AmneziaVPN.
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
