# Security policy — KLTu public repository

## Scope of this repository

This repository is a **public overview** (documentation, citations, demo policy).  
It does **not** currently ship the full KLTu production engine, host configurations, or defense-integrated services.

## Demo / lab services

Any interactive demo referenced from this project is:

- Intended for **evaluation and education**, not production traffic
- Operated under **controlled access** (lab / Tailscale Funnel posture)
- **Rate-limited**
- Designed so **homomorphic evaluation requests do not require or accept secret keys** on the evaluator path

Do not submit production secrets, private keys, or personal data to demo endpoints.

## Reporting issues

- **Public docs / broken links:** open a GitHub Issue on this repository (if Issues are enabled), or email below.
- **Suspected vulnerability in a system you operate that uses KLTu-related research:** email **X2hello@xylonixscience.com** with a factual description. Do not attach secret key material.

## Non-goals / non-claims

- No CMVP, FIPS validation, or certification claim is made by this repository alone.
- Papers B and C define scientific scope; this repo does not expand those claims.
- No warranty of fitness for any particular purpose.

## Contact

Xylonix / KLTu — X2hello@xylonixscience.com
