# KLTu Public Claim / Non-Claim Matrix

## Claims
- FIPS 203/204-aligned interop planes (see Zenodo papers B, C, E).
- Role-separated Native DSA v2 (mesh) + FIPS 204 (audit).
- Lattice estimator (classical): Native DSA M / KLTu-KEM-768 ≈ 2^196.4; Native DSA H / KLTu-KEM-1024 ≈ 2^262.3 — not inferior to NIST Category 3 / 5 classical cost scales.
- Product FHE with strap-managed depth; residual hybrid ML-DSA-65 verify is a separate leveled path.

## Non-claims
- Full-blind ML-DSA verify entirely in ciphertext: NO
- FHE signature generation: NO
- Native = NIST standardized Category 3/5 algorithm label: NO
- FIPS 140 / Common Criteria certificate: NO
