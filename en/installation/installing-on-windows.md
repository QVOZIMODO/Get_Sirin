# Installing on Windows

{% hint style="info" %}
**Before you start**

* Windows 10 or 11
* Administrator rights for the first install (to add VPN drivers)
* An active Sirin subscription — see [Quick Start](../getting-started/quick-start.md)
* Your subscription QR + link from [@getsirin\_bot](https://t.me/getsirin_bot)
{% endhint %}

## Pick your app

Sirin hands you **all four protocols in one subscription**. No single Windows app speaks all of them, so pick by what you need — most people start with AmneziaVPN.

{% tabs %}
{% tab title="AmneziaVPN (recommended)" %}
Best for **WireGuard + AmneziaWG** — the protocols that survive the heaviest filtering. This is the QR the bot shows first (the `vpn://` one).

{% stepper %}
{% step %}
### Install AmneziaVPN

Download the `.exe` installer from [amnezia.org](https://amnezia.org). Windows SmartScreen may warn _"Windows protected your PC"_ — click **More info → Run anyway**. The installer requests administrator rights; allow it and follow the wizard.

<figure><img src=".gitbook/assets/windows-amnezia-install.png" alt="AmneziaVPN installer with SmartScreen prompt"><figcaption>[REAL CAPTURE] AmneziaVPN installer + SmartScreen "Run anyway"</figcaption></figure>
{% endstep %}

{% step %}
### Allow the VPN drivers

On first launch Windows asks permission to install the WireGuard/TAP drivers. Click **Allow**.

<figure><img src=".gitbook/assets/windows-vpn-driver.png" alt="Windows VPN driver installation dialog"><figcaption>[REAL CAPTURE] Windows driver installation dialog</figcaption></figure>
{% endstep %}

{% step %}
### Import your Sirin key

Open [@getsirin\_bot](https://t.me/getsirin_bot) in Telegram Desktop and find the **AmneziaVPN** entry (the `vpn://` one). Copy the link, then in AmneziaVPN choose **+ → Paste from clipboard**.

_Prefer the camera? Choose **+ → Scan QR** and hold your phone showing the bot's `vpn://` QR up to your webcam._

<figure><img src=".gitbook/assets/windows-amnezia-import.png" alt="Importing the key into AmneziaVPN on Windows"><figcaption>[REAL CAPTURE] AmneziaVPN — paste from clipboard / scan QR</figcaption></figure>
{% endstep %}

{% step %}
### Connect

Click the big connect button. Connection takes 1–3 seconds. To try a different protocol or server later, switch in the app — it's a one-tap change.

<figure><img src=".gitbook/assets/windows-amnezia-connected.png" alt="Active connection in AmneziaVPN on Windows"><figcaption>[REAL CAPTURE] Active connection in AmneziaVPN</figcaption></figure>
{% endstep %}
{% endstepper %}
{% endtab %}

{% tab title="Hiddify / Sing-Box (for VLESS + Shadowsocks)" %}
Best for **VLESS + Reality** and **Shadowsocks** — fast, low-profile protocols. Use the **subscription-link QR** (the `https://sub.sirin.one/…` one), not the `vpn://` one. On desktop, **Hiddify and Sing-Box are equally fine** — pick either.

{% stepper %}
{% step %}
### Install Hiddify or Sing-Box

Download Hiddify (or Sing-Box) for Windows from its official site, or use the link on [sirin.one](https://sirin.one). Run the installer.
{% endstep %}

{% step %}
### Import the subscription

In the app choose **Add profile → from clipboard** and paste the `https://sub.sirin.one/…` link (or scan the bot's **subscription** QR). It pulls in VLESS + Shadowsocks and refreshes the server list on its own.

<figure><img src=".gitbook/assets/windows-hiddify-import.png" alt="Importing a subscription into Hiddify on Windows"><figcaption>[REAL CAPTURE] Hiddify / Sing-Box — add subscription</figcaption></figure>
{% endstep %}

{% step %}
### Connect

Click connect, approve the VPN configuration when Windows asks, and you're online.
{% endstep %}
{% endstepper %}
{% endtab %}
{% endtabs %}

## Verify it's working

Open your browser and visit [icanhazip.com](https://icanhazip.com). The IP should be Sirin's server — not your home network's.

{% hint style="success" %}
Want to confirm your region looks right too? Any "what's my IP" site will show the country your traffic exits from.
{% endhint %}

<details>

<summary>Other clients (only if you know what you're doing)</summary>

* **Official WireGuard for Windows** — WireGuard only; can't import VLESS or Shadowsocks. The bot can hand you an on-demand `.conf` for the WG profile.
* **v2rayN** ([GitHub](https://github.com/2dust/v2rayN)) — VLESS + Reality and Shadowsocks for power users.

These are single-protocol or power-user tools — for the full Sirin bundle on Windows, stick with AmneziaVPN and/or Hiddify above.

</details>

## If it doesn't work

* **SmartScreen blocks the installer** — click **More info → Run anyway**.
* **Drivers won't install** — run AmneziaVPN as administrator.
* **Connected but no internet** — check that your antivirus/firewall isn't blocking AmneziaVPN, then try switching protocol or server.
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
