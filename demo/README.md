# KLTu lab demo — access and overview

This folder documents the **public-facing lab demonstration** of KLTu’s  
**FIPS-oriented wire → bridge → homomorphic evaluation → recover** story.

It does **not** host production engines, secret keys, or a full server dump.

---

## Purpose

The demo lets auditors and researchers:

1. Work with **declared parameter sets** (e.g. ML-KEM-768 / ML-KEM-1024 class wire sizes where applicable).  
2. Submit **homomorphic evaluation** requests (e.g. addition; multiplication only if enabled and labeled honestly).  
3. Confirm that the **evaluator path does not accept secret keys**.  
4. Perform **client-side recover / check** against expected integer results when the flow provides key material only to the client role.

It is an **educational and validation** surface, not a production deployment.

---

## Access model

| Item | Policy |
|------|--------|
| **Hosting** | Controlled lab host (Tailscale / Funnel posture) |
| **Public Internet** | Not offered as an unrestricted open bind of workers |
| **Rate limit** | Enforced (on the order of a few operations per minute per client) |
| **Secrets** | Do **not** paste production private keys or personal data |
| **Availability** | Best-effort; may be offline during maintenance |

**How to request access**

- Email: **X2hello@xylonixscience.com**  
- Subject line: `KLTu demo access request`  
- Include: your name/org, purpose (audit / research / press), and preferred contact.

When access is granted, you will receive the current Funnel or lab URL.  
URLs may change; this document is the stable policy entry point.

---

## Intended user flow (conceptual)

```text
Block 1  Generate or supply wire material + client key material (client role)
Block 2  Optional scramble / hygiene step (clear local sensitive fields after copying off-site)
Block 3  Paste ciphertexts → FHE Add / Mult on evaluator (no secret key in request)
Block 4  Paste result + client secret → recover value → compare to expected integer
```

Exact on-screen labels may evolve; the **role separation** (client holds SK; evaluator does not) is the invariant.

---

## What you should see (honesty checks)

- Clear **DEMO ONLY** labeling.  
- Parameter set selection (e.g. 768 vs 1024 class).  
- Ciphertext fields with **length / size** feedback when paste sizes mismatch.  
- Operate / evaluate actions that **reject** secret-key fields.  
- Recover / decrypt only on the path that intentionally uses **client-held** key material.  
- Optional session audit download for “operate did not receive SK”-style evidence.

Wall-clock times in a browser include **network and serialization**.  
For scientific latency, use **Papers B & C** measurement sections—not UI timers alone.

---

## Screenshots

Add static images here as they are approved for public release:

| File | Description |
|------|-------------|
| `screenshots/01-overview.png` | Landing / header / demo-only badge |
| `screenshots/02-wire-and-keys.png` | Parameter select, integers, CT and key fields |
| `screenshots/03-evaluate.png` | Paste CTs, Add/Mult, output CT |
| `screenshots/04-recover.png` | Recover value vs expected integer |

*Placeholder: images not yet uploaded.*

To upload later: repo → `demo/screenshots/` → **Add file** → **Upload files**.

---

## Related documents

| Doc | Role |
|-----|------|
| [Paper B](https://doi.org/10.5281/zenodo.21543529) | KEM / FIPS interop record |
| [Paper C](https://doi.org/10.5281/zenodo.21523834) | FHE / bridge measurement record |
| [Public whitepaper](../docs/WHITEPAPER.md) | Narrative overview |
| [SECURITY.md](../SECURITY.md) | Scope and reporting |
| [CITATIONS.md](../CITATIONS.md) | How to cite |

---

## Non-goals

- Not a certification evidence package by itself.  
- Not a promise of 24/7 uptime.  
- Not permission to attack infrastructure beyond the published demo rules.  
- Not a release of full KLTu engine source.

---

Copyright © 2026 Dr. Jinhyuk Fred Chung / Xylonix.  
Demo policy contact: X2hello@xylonixscience.com
```

---
