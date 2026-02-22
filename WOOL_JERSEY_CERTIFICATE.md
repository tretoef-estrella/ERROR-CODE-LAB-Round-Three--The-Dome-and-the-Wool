# El Jersey de Lana — Exhaustive Puncturing Certificate

## Statement

**All 552 shortenings+puncturings of the Magma-verified \[24,7,13\]₄ (Gulliver-Bhargava) yield \[22,6,12\]₄ codes. No puncturing within this family produces d ≥ 13.**

## Method

1. Obtained the \[24,7,13\]₄ generator matrix from Magma's `BKLC(GF(4),24,7)` database
2. Verified d=13 by enumerating all 16,383 nonzero codewords (A₁₃=384)
3. **Shortened** at each of the 24 coordinate positions (Gaussian elimination to remove one row and one column), producing 24 codes of type \[23,6,≥13\]₄
4. For each \[23,6,13\]₄, **punctured** at each of the 23 remaining positions, producing up to 552 codes of type \[22,6,≥12\]₄
5. Verified d for each by enumerating all 4,095 nonzero codewords

## Results

All 24 shortenings produced valid \[23,6,13\]₄ codes, falling into three distinct weight distribution families:

| Shortening Coords | A₁₃ | Count |
|---|---|---|
| 0–7 | 189 | 8 codes |
| 8–15 | 165 | 8 codes |
| 16–23 | 174 | 8 codes |

**All 552 punctured codes have d = 12.** None achieved d ≥ 13.

```
Shorten  0: [23,6,13] A13=189 → 23 punctures → all d=12
Shorten  1: [23,6,13] A13=189 → 23 punctures → all d=12
Shorten  2: [23,6,13] A13=189 → 23 punctures → all d=12
Shorten  3: [23,6,13] A13=189 → 23 punctures → all d=12
Shorten  4: [23,6,13] A13=189 → 23 punctures → all d=12
Shorten  5: [23,6,13] A13=189 → 23 punctures → all d=12
Shorten  6: [23,6,13] A13=189 → 23 punctures → all d=12
Shorten  7: [23,6,13] A13=189 → 23 punctures → all d=12
Shorten  8: [23,6,13] A13=165 → 23 punctures → all d=12
Shorten  9: [23,6,13] A13=165 → 23 punctures → all d=12
Shorten 10: [23,6,13] A13=165 → 23 punctures → all d=12
Shorten 11: [23,6,13] A13=165 → 23 punctures → all d=12
Shorten 12: [23,6,13] A13=165 → 23 punctures → all d=12
Shorten 13: [23,6,13] A13=165 → 23 punctures → all d=12
Shorten 14: [23,6,13] A13=165 → 23 punctures → all d=12
Shorten 15: [23,6,13] A13=165 → 23 punctures → all d=12
Shorten 16: [23,6,13] A13=174 → 23 punctures → all d=12
Shorten 17: [23,6,13] A13=174 → 23 punctures → all d=12
Shorten 18: [23,6,13] A13=174 → 23 punctures → all d=12
Shorten 19: [23,6,13] A13=174 → 23 punctures → all d=12
Shorten 20: [23,6,13] A13=174 → 23 punctures → all d=12
Shorten 21: [23,6,13] A13=174 → 23 punctures → all d=12
Shorten 22: [23,6,13] A13=174 → 23 punctures → all d=12
Shorten 23: [23,6,13] A13=174 → 23 punctures → all d=12
```

Best A₁₂ among all 552 codes: **78** (shorten=16, puncture=5).

## Interpretation

The \[24,7,13\]₄ parent has A₁₃=384 weight-13 codewords. These words cover all 24 coordinates — every coordinate belongs to the support of multiple weight-13 codewords. When we shorten at any coordinate, the resulting \[23,6,13\]₄ inherits this coverage property. When we then puncture, at least one weight-13 codeword loses its coordinate, dropping to weight 12.

This is consistent with ChatGPT's structural analysis: in codes near the Griesmer bound, weight-13 words form a near-uniform covering design. Puncturing such codes almost always reduces d by exactly 1.

## Scope and Limitations

This certificate covers **only** the QR (Gulliver-Bhargava) family. It does NOT prove that \[22,6,13\]₄ is impossible — only that it cannot be obtained by shortening+puncturing from this specific \[24,7,13\]₄ parent.

A \[22,6,13\]₄ could still exist if:
- A non-QR \[23,6,13\]₄ exists where some coordinate is NOT in the support of any weight-13 word
- The code arises from a completely different construction family (AG codes, Z₄-linear, etc.)
- The code has no known parent at n=23 or n=24

## Verification

The parent matrix is available in [MATRICES.md](MATRICES.md). The shortening and puncturing operations are standard linear algebra over GF(4). The entire computation takes <1 second on commodity hardware.

To reproduce: obtain `BKLC(GF(4),24,7)` from Magma, perform all 24×23=552 shorten+puncture operations, verify d for each.

## Origin of the Strategy

The "Wool Jersey" metaphor was proposed by Rafa (The Architect):

> *"Wool jerseys shrink dramatically in hot water — several sizes — without deforming. They come out perfect, just smaller."*

Translation: take a code that exists at n=23 (the large jersey), and "shrink" it to n=22 (puncturing = hot water). The jersey shrank perfectly — but one size too many.

---

*Error Code Lab · Round Three · February 2026*
*Proyecto Estrella*
