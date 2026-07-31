# KLTu Public Whitepaper (Overview)

**Kinetic Lattice Topology — post-quantum session wire and native homomorphic evaluation**

**Author:** Dr. Jinhyuk Fred Chung (Xylonix)  
**Document type:** Public overview (not a substitute for the formal Zenodo papers)  
**Version:** 0.1 (GitHub)  
**Date:** 2026  

**Contact:** X2hello@xylonixscience.com  
**Repository:** https://github.com/JFCSG/KLTu  

---

## 1. Purpose of this document

This whitepaper is a **short public narrative** of the KLTu research program for engineers, auditors, and partners.  

It explains:

- why post-quantum **session cryptography** and **homomorphic evaluation** are treated as connected but distinct planes;
- how KLTu positions a **FIPS 203 ML-KEM wire** path beside a **native lattice FHE** evaluation path;
- where to find the **archival scientific record** (Papers B and C);
- what a **lab demo** is intended to show—and what it does not claim.

**This document does not replace** the formal publications. Measurement claims, parameter tables, and experimental protocols are defined in the Zenodo records cited below.

---

## 2. Archival publications (source of scientific record)

| ID | Role | Archival DOI |
|----|------|----------------|
| **Paper B** | Native KEM/DSA interop with FIPS-aligned wire and liboqs-class stacks | [10.5281/zenodo.21719064](https://doi.org/10.5281/zenodo.21719064) |
| **Paper C** | FHE evaluation context, FIPS bridge narrative, measurement posture | [10.5281/zenodo.21543529](https://doi.org/10.5281/zenodo.21543529) |

How to cite: see [`CITATIONS.md`](../CITATIONS.md).

---

## 3. Problem framing

Two pressures dominate practical post-quantum deployment:

1. **Interoperability** — session establishment must speak standard **FIPS 203 ML-KEM** (and related PQC) wire formats so independent implementations (including widely used reference stacks) can interoperate.
2. **Computation on protected data** — some workflows need **homomorphic** operations so an evaluator can compute on ciphertexts **without holding the client secret key**.

Treating “the ciphertext bytes that travel on the wire” as automatically identical to “the ciphertext object that FHE gates consume” is a common category error. KLTu’s public architecture story keeps those planes explicit.

---

## 4. Architectural idea (high level)

KLTu organizes work into connected layers:

### 4.1 Post-quantum session plane (Paper B emphasis)

- FIPS 203 **ML-KEM-768 / ML-KEM-1024** style wire sizes and behaviors as used for **key encapsulation** and interop testing against reference stacks.
- Goal: **shared-secret agreement** and verifiable interop—not “encrypt an arbitrary integer under KEM and call that FHE.”

### 4.2 Homomorphic evaluation plane (Paper C emphasis)

- Native lattice **FHE-style** evaluation (addition and related operations under the paper’s scope).
- Evaluator path designed so **operation requests need not carry secret keys**.
- Measurement posture in Paper C includes paths that aim to avoid routine full programmable bootstrapping for the reported regimes (see paper for exact definitions and limits).

### 4.3 Bridge narrative

Between **standard wire bytes** and **evaluation objects**, KLTu describes an explicit **conversion / ingest** boundary:

- conversion is **not** “the evaluator decapsulates the user’s message under the client secret key to do arithmetic in the clear”;
- public documentation stresses **zero secret key on the evaluate path** for the demo and for the intended audit story;
- exact packing, sizes, and algorithms are specified in the papers and implementation catalogues—not fully expanded in this overview.

A useful mental model used in lab documentation:

| Layer | Informal role |
|-------|----------------|
| **F** | FIPS-oriented ML-KEM **wire** ciphertext bytes |
| **P** | Packed / intermediate form used at the bridge boundary |
| **R** | Rich evaluation representation used by FHE-style gates |

Numbers and formal definitions belong in Papers B/C and the technical catalogues, not in marketing paraphrase.

---

## 5. What the lab demo is for

The public program includes a **controlled browser demo** (lab / Funnel access model) so auditors can walk a transparent flow:

1. Establish or supply **wire-oriented** ciphertext material under a declared parameter set.  
2. Submit **evaluation** requests (e.g. homomorphic addition) **without** sending secret keys to the evaluator API.  
3. Recover or check results on the **client-held** key side where the demo design requires it.  
4. Inspect an **audit-oriented** trail that the operate path did not accept secret key fields.

The demo is for **education and validation of the story**, not a production SLA, not a certification, and not an open invitation to submit sensitive data.

Access policy and screenshots live under [`demo/`](../demo/) as they are published. Security posture: [`SECURITY.md`](../SECURITY.md).

---

## 6. Explainer video

A public YouTube explainer accompanies this overview:

- https://youtu.be/PTuTUWofkto
- https://youtu.be/PucVw8m3gQo

Recommended viewer path: problem framing → plane separation → demo walk-through → pointers to Papers B and C.

---

## 7. Non-claims (read carefully)

This whitepaper and the GitHub front door **do not** claim:

- CMVP, NIAP, or other formal product certification;
- that **raw** ML-KEM encapsulation ciphertexts are universal FHE operands with no bridge model;
- that every proprietary noise-management option (including internal “full-PBS replacement” research options) is published in full;
- that the full production engine or defense-integrated host tree is open-sourced in this repository.

Any quantitative latency or correctness figures should be taken from the **papers’ measurement sections** (or later errata), not from informal demo wall-clock times over a network UI.

---

## 8. Intellectual property and collaboration

Copyright © 2026 Dr. Jinhyuk Fred Chung / Xylonix.  
See [`NOTICE.md`](../NOTICE.md).

Licensing of the formal papers follows each Zenodo record.  
This overview does not grant a license to unpublished engine source.

**Collaboration / licensing:** X2hello@xylonixscience.com  

---

## 9. Document history

| Version | Date | Notes |
|---------|------|--------|
| 0.1 | 2026-08 | Initial public overview on GitHub (JFCSG/KLTu) |

---

## 10. References

1. Chung, J. F. — Paper B — https://doi.org/10.5281/zenodo.21719064  
2. Chung, J. F. — Paper C — https://doi.org/10.5281/zenodo.21543529  
3. KLTu public repository — https://github.com/JFCSG/KLTu  
