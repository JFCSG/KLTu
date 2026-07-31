# KLTu — Kinetic Lattice Topology

**Unified post-quantum cryptography and homomorphic evaluation**  
Proprietary research by **Dr. Jinhyuk Fred Chung / Xylonix**

KLTu connects **FIPS 203 ML-KEM** session wire formats with a **native lattice FHE** evaluation path so arithmetic can be performed on bridged ciphertexts **without the evaluator holding secret keys**, under the measurement and non-claim discipline of the formal papers below.

> This repository is the **public front door** (overview, citations, demo policy, media).  
> The archival scientific records are the Zenodo publications—not this README.

---

## Formal publications

| Paper | Focus | Archival record |
|-------|--------|-----------------|
| **Paper B** | Native KEM/DSA interop with FIPS 203 / 204 wire and liboqs-class stacks | 
[doi:10.5281/zenodo.21719064](https://doi.org/10.5281/zenodo.21719064) |
| **Paper C** | FHE evaluation, FIPS bridge context, Path-O style measurement posture | 
[doi:10.5281/zenodo.21543529](https://doi.org/10.5281/zenodo.21543529) |

---

## Explainer video

YouTube: (https://youtu.be/PTuTUWofkto)
YouTube: (https://youtu.be/PucVw8m3gQo)

---

## Public demo (lab)

A browser sandbox demonstrates the intended **Layer-F (FIPS wire) → bridge → homomorphic op → bridge → recover** workflow for educational and auditor-facing validation.

https://bh-node-01.tail297226.ts.net/kltu-demo/?tab=c

- Access is **controlled** (lab / Tailscale Funnel posture), not an unrestricted open internet service.
- Evaluator paths are designed so **operation requests do not carry secret keys**.
- Rate limits and demo-only disclaimers apply.

Screenshots and access notes may be added under [`demo/`](demo/) as they are published.

---

## What this work is / is not

**Is**
- A research architecture for PQC session wire + native FHE evaluation
- Backed by formal papers (B & C) with explicit measurement scope
- Aimed at transparent auditor-facing demonstration of the bridge story

**Is not**
- A drop-in CMVP product claim
- A claim that raw ML-KEM ciphertexts are universal FHE operands without the defined bridge model
- A release of the full production engine or defense-integrated host tree in this repository

---

## Repository contents (planned)

| Path | Role |
|------|------|
| `README.md` | This front page |
| `docs/WHITEPAPER.md` | Short public narrative (optional PDF later) |
| `CITATIONS.md` | BibTeX / cite strings for Papers B & C |
| `SECURITY.md` | Scope, non-goals, contact for issues |
| `NOTICE.md` | Copyright and ownership |
| `demo/` | Screenshots and access policy only |

Source code for the full KLTu engine is **not** mirrored here by default.

---

## Contact

**Xylonix / KLTu** — `X2hello@xylonixscience.com`

---

## Copyright

Copyright © 2026 Dr. Jinhyuk Fred Chung / Xylonix. All rights reserved.  
Papers B & C remain under their respective Zenodo licenses.  
This overview text may be linked freely; redistribution of figures from the papers follows each paper’s license terms.
