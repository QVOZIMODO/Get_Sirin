# Privacy posture

Privacy isn't a feature toggle in Sirin — it's the architecture. The guiding rule is
simple: **you cannot leak, sell, or be subpoenaed for what you never held.** So we hold as
little as the service can physically run on.

## What we store, in full

| We store | Why |
| --- | --- |
| Telegram ID | The account identity — already surrendered to Telegram; we treat it as the boundary, not the starting point |
| Encrypted subscription token | The credential behind your subscription URL; encrypted at rest, stored hashed |
| Encrypted protocol credentials | Your per-protocol client keys; encrypted at the app layer before the database sees them |
| Coarse region | Country-level only, derived at request time, used purely to rank healthy endpoints |

## What we deliberately never store

- **Email, name, phone, postal address** — none of it, on any model.
- **Raw IP address** — never written to the database. Region is derived coarsely and the
  raw address is discarded.
- **Device fingerprint or user-agent** — not collected.
- **Per-user browsing or connection activity** — there is no such log. Recording which sites
  a user reaches would defeat the entire point of the product.
- **Card or bank details** — payment is crypto or Telegram Stars only, because card rails
  are identity.

## How it's enforced

This isn't a privacy *policy* sitting on top of a database that quietly knows everything —
it's enforced at the schema:

- **Schema review at every migration.** Any change that would add an identifying field is
  rejected by default; an exception requires an explicit, documented architecture decision.
- **No-PII as a hard invariant.** The user model is reviewed against a list of forbidden
  column types each time a migration touches it.
- **Encryption at rest.** Subscription tokens and credentials are encrypted at the
  application layer (Fernet) before insertion. The key lives in process memory, never in the
  database and never in a backup — so a stolen database, or a stolen backup, is unreadable.
- **Short memory.** Raw health signals expire after 7 days. Only anonymous aggregates,
  carrying no user identifier, are retained to drive rotation decisions.

## Consequences we accept

Holding nothing has a cost, and we take it on purpose:

- **No password recovery, no "forgot my account".** Your Telegram account *is* your Sirin
  account. Lose the former and you lose the latter. That's consistent with the threat model.
- **No email channel.** We can't email you about service changes — announcements happen
  in-bot and on a signed status page instead.
- **No marketing funnel built on captured identity.** There's no list to build, because
  there's no email to capture.

## Jurisdiction

Sirin is run by an independent operator with no central legal domicile. Your privacy is a
**product-level guarantee** — enforced by what's built and what's deliberately absent — not
a promise that hinges on which country's courts apply. The encryption is the policy.

## Verifiability

We publish a **[signed warrant canary](https://sirin.one/canary)** and refresh it on a
schedule. As long as it's signed and current, the statements in it hold. If it ever goes
stale or unsigned, treat that as the signal it is.

We also won't promise absolutes. No security product that claims 100% is telling the truth.
What we promise is to tell you honestly what works, what doesn't, and what changed.
