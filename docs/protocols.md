# Protocols

Protocol diversity is the moat. A single tunnel type is a single point of failure against
deep packet inspection — so every active Sirin user holds credentials for all four
protocols below, and the subscription URL rotates between them automatically based on what
is passing the filters in their region today.

## The deck

### WireGuard

The modern baseline: a small, fast, kernel-level tunnel with excellent latency and battery
behaviour. When it isn't being actively filtered, it's the best experience available — so
it's the default the others fall back from.

**Trade-off:** its handshake has a recognisable signature, which sophisticated DPI can
fingerprint and drop. That's exactly why it isn't the *only* protocol.

### AmneziaWG

WireGuard with tunable traffic obfuscation layered on. It keeps WireGuard's performance
profile while masking the handshake characteristics that make vanilla WireGuard
classifiable. This is the heavy-filter workhorse: when a region starts dropping WireGuard,
AmneziaWG is usually still standing, and its obfuscation parameters can be tuned per
endpoint if a specific fingerprint gets targeted.

### VLESS + Reality

An Xray transport that borrows a genuine TLS handshake from a real, plausible destination
site. To an observer on the wire, the connection looks like ordinary HTTPS traffic to a
site they'd be reluctant to block wholesale. It's the hardest of the four to classify and
the most expensive for an adversary to block without significant collateral damage.

### Shadowsocks

A lightweight encrypted SOCKS proxy (the 2022 edition, with modern authenticated
encryption). Its small footprint and very broad client support make it a dependable
fallback — when the heavier transports are under pressure or unsupported by a user's
client of choice, Shadowsocks keeps a path open.

## Why rotation, not choice

Users don't pick a protocol, and they don't manually swap when one breaks. The subscription
URL does it for them:

1. The client polls the URL on its own schedule (typically every 6–24h).
2. Sirin ranks the four protocols for the caller's region by recent, measured health.
3. Anything currently blocked or degraded is dropped or deprioritised.
4. The client receives a fresh, ranked config list and uses the best one.

The result: a protocol can die in a region and the user rotates onto another one **before
they notice**, with no re-import, no app update, and no support ticket.

## Clients

Sirin issues standard subscription URLs and standard configs — it is deliberately *not*
another app you have to trust. It works with the mainstream, third-party clients people
already use:

- **v2rayNG / NekoBox / sing-box** — VLESS + Reality, Shadowsocks
- **AmneziaVPN** — AmneziaWG, WireGuard
- **WireGuard official app** — WireGuard
- **Clash-family clients** — subscription-aware, multi-protocol

The intelligence lives in the subscription URL on Sirin's side. The client just polls and
connects.
