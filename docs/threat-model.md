# Threat model (public overview)

This is a sanitized summary of how Sirin reasons about adversaries. It states the posture
without the operational specifics — current mitigations-in-progress, capacities, and
infrastructure detail are kept private.

Sirin is a privacy-critical VPN whose users, by definition, have adversarial counterparties.
The stakes of a breach are higher than a typical online service, so the design assumes a
capable opponent rather than a careless one.

## What we're protecting (in priority order)

1. **The link between a person and the fact that they use Sirin at all** — let alone which
   endpoint, protocol, or region.
2. **Subscription tokens** — the credential behind a user's config list.
3. **Endpoint server keys** — compromise would let an endpoint be impersonated.
4. **Encrypted credentials in the database.**
5. **Operational continuity** — serving users without extended outage.

## Adversaries we design against

- **State-level DPI operator** — large-scale passive monitoring, active probing, real-time
  protocol classification, asymmetric block lists. Cannot break sound cryptography.
- **A provider under legal pressure** — able to image or seize a server's disk within its
  jurisdiction.
- **Opportunistic attacker** — exploiting known software vulnerabilities, credential
  stuffing, phishing.
- **Malicious or compromised insider** — production access; constrained by audit logging
  and separation of sensitive capabilities.
- **A user abusing the support agent** — unbounded text input attempting prompt injection or
  cross-user escalation.

## Key threats and how Sirin holds up

| Threat | Posture |
| --- | --- |
| **Database seizure / dump** | Credentials and subscription tokens are app-layer encrypted; the key never lives in the DB or its backups. No email/name/IP on any row. Raw health signals expire at 7 days. |
| **Endpoint seizure** | Endpoints store only server keys and a peer list — no user identifiers. Per-endpoint secrets don't grant impersonation of the rest of the fleet. Detection + drain + destroy is the response. |
| **DPI protocol blocking** | Four protocols with automatic rotation; obfuscated transports (AmneziaWG) and handshake-mimicking transports (VLESS + Reality) to resist classification. |
| **Prompt injection on the agent** | Two-layer design: the LLM layer can only emit a suggestion; a deterministic validator checks schema, policy, and cross-user attempts before any mutation. Every decision is logged. |
| **Payment webhook forgery** | HMAC verification on every callback, plus periodic reconciliation against the provider's own record of truth. |
| **User's own Telegram account compromise** | Outside our control; mitigated with confirmation prompts on sensitive flows and encouragement of account 2FA. |

## Honest limits

We don't claim absolutes, and the threat model says so explicitly:

- A sufficiently advanced future classifier that defeats all four protocols simultaneously
  is the moat's hard limit — the answer there is new protocols, not a clever config.
- The Telegram ID is plaintext by necessity; an attacker with the database learns *which
  Telegram accounts hold a subscription*, though nothing about their activity.
- No security product that promises 100% is being honest. Sirin's promise is narrower and
  keepable: to tell users truthfully what works, what doesn't, and what changed.

## Review

The threat model is reviewed on a regular cadence and after any incident. Material changes
are recorded as architecture decisions.
