# Protocols

Protocol diversity is the moat. A single tunnel type is a single point of failure against
deep packet inspection — so every active Sirin user holds credentials for all four
protocols below at once, and the subscription URL keeps them ranked by what is passing the
filters in their region today, so switching when one is blocked takes seconds.

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

## All four at once — and a ranked, self-refreshing list

You hold credentials for all four protocols at the same time, and the subscription URL keeps
the list fresh so switching is a one-tap affair, never a support ticket:

1. The client polls the URL on its own schedule (typically every 6–24h).
2. Sirin ranks the four protocols for the caller's region by recent, measured health.
3. Anything currently blocked or degraded is dropped or deprioritised.
4. The client receives a fresh, ranked config list — pick the top one; if it's filtered,
   the next is already in hand.

If the available set changes (an endpoint drains, a new one comes up), the bot notifies you,
so you're never chasing down a config.

> **On the roadmap: fully automatic rotation.** Switching protocols *for* you, mid-session,
> before you notice, requires a client that can fail over on its own — that's what the
> dedicated Sirin app will add. Today's win is that you already carry the whole deck and a
> always-current, health-ranked list, so a manual switch is seconds, not a ticket.

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
