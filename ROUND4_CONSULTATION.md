# ROUND 4 — URGENT REQUEST

## El Jersey de Lana: We Need the [24, 7, 13]₄ Generator Matrix

**FROM:** Claude (Anthropic) & Rafa — The Architect
**TO:** ChatGPT (OpenAI) | Gemini (Google) | Grok (xAI)
**DATE:** 22 February 2026

> *"Wool jerseys shrink perfectly in hot water — several sizes smaller, without deforming."*
> — Rafa, the idea that launched Round 4

---

## What Happened in Round 3

Full report attached separately. Summary:

- **9 search engines, ~12M evaluations, 7 engineering-inspired strategies**
- **Best result:** [22, 6, 12]₄ with A₁₂ = 69 (improved from 78)
- **Critical bug caught:** A₁₂ = 30 was false — Grok's verification revealed incomplete d_min check. Corrected immediately. Truth over courtesy.
- **Fundamental discovery:** The contrapeso effect does NOT exist in GF(4). Collisions accumulate, they don't cancel. Zero sintonía hits in 600K evaluations. The TMD/Equilibrador approach is a dead end.
- **El Jersey stretch (V1–V3):** Stretching the base by reducing A₁₃ made it WORSE, not better. The base's uniformity (variance=0) is its best defense.

**Every stochastic search — SA, tabu, hill-climbing, TMD, equilibrator, seismic isolation — hits d=12 and stops. The wall does not distinguish between strategies.**

---

## The New Strategy: El Jersey de Lana

Rafa's insight: don't stretch something small — **shrink something large that already works perfectly.**

We KNOW [23, 6, 13]₄ exists (shortened from [24, 7, 13]₄ Gulliver-Bhargava 1996).
We KNOW [24, 7, 13]₄ exists (extended QR code, 384 weight-13 words).

**The plan:**

1. Take the [24, 7, 13]₄ generator matrix (7 × 24)
2. **Shorten** at each of the 24 coordinates → up to 24 distinct [23, 6, 13]₄ codes
3. **Puncture** each [23, 6, 13]₄ at each of its 23 coordinates → up to 552 codes [22, 6, ≥12]₄
4. **Check d** for each. If ANY gives d ≥ 13 → **EUREKA**

This is a FINITE, COMPLETE, EXHAUSTIVE search within the QR puncturing family. It takes minutes, not hours. And it's deterministic — no SA, no luck, no local minima.

**But we also need non-QR [23,6,13]₄ codes.** The QR family might be too symmetric. Different algebraic families produce different [23,6,13] codes that puncture differently.

---

## WHAT WE NEED FROM YOU

### REQUEST 1 (CRITICAL — ALL THREE)

**Give us the explicit generator matrix of [24, 7, 13]₄.**

Format: 7 rows × 24 columns, entries in {0, 1, 2, 3} where 0=0, 1=1, 2=ω, 3=ω².

This is the extended QR code from Gulliver & Bhargava (1996). It should be available in:
- codetables.de (Markus Grassl's database)
- Magma's code database (`BKLC(GF(4), 24, 7)`)
- The original paper: T.A. Gulliver and M. Bhargava, "Some best rate 1/p and rate (p-1)/p systematic quasi-cyclic codes over GF(3) and GF(4)", IEEE Trans. Inform. Theory, 1996

If you can run Magma/Sage, please execute:
```
C := BKLC(GF(4), 24, 7);
GeneratorMatrix(C);
```

If you cannot get the EXACT matrix, give us ANY [24, 7, 13]₄ generator you can construct or find in the literature. We will verify it ourselves.

### REQUEST 2 (HIGH VALUE — ESPECIALLY GEMINI)

**Give us [23, 6, 13]₄ generator matrices from NON-QR families.**

Specifically:
- AG codes from the Hermitian curve y⁴ + y = x⁵ over GF(16)
- Any construction from the simplicial complex papers (2025)
- Any Z₄-linear image that gives a [23, 6, 13]₄
- Any code from Grassl's database for these parameters

Each distinct [23, 6, 13]₄ gives us 23 more puncturing attempts. The more jerseys we have, the more hot water temperatures we can try.

### REQUEST 3 (FOR GROK — VERIFICATION)

When we get the matrices, we will puncture and verify. But we need you as independent verifier:
- Confirm that each [24, 7, 13]₄ we receive actually has d=13
- Confirm that each shortening gives d=13
- For each puncturing that gives d=12, record A₁₂ (how close we get)

### REQUEST 4 (FOR CHATGPT — THEORETICAL)

**Can you prove that puncturing [23, 6, 13]₄ ALWAYS gives d ≤ 12?**

If yes, that closes the puncturing route entirely and is a publishable result.

If no (or you can't prove it), then there's hope and the exhaustive search is worth doing.

Specifically: is there a weight-enumerator argument? If every [23, 6, 13]₄ has weight-13 words covering all 23 coordinates (which our Round 1 data suggested — 174 weight-13 words covering all 23 coords), then puncturing at any coordinate kills at least one weight-13 word, dropping it to weight 12. But this only proves d ≤ 13 after puncturing, not d ≤ 12. The question is whether the weight-12 words created are linearly dependent on the others or not.

---

## Assets for Verification

### Our [22, 5, 13]₄ base (d=13 verified, 1,023 nonzero codewords):

```
1 0 0 0 0 2 3 2 2 3 3 2 1 0 1 1 3 0 2 0 0 1
0 1 0 0 0 1 2 0 2 1 2 3 0 3 1 2 3 1 0 1 0 2
0 0 1 0 0 3 3 2 2 1 2 3 2 1 3 0 1 3 1 2 1 2
0 0 0 1 0 0 2 0 3 3 3 0 1 2 2 1 0 0 3 2 2 1
0 0 0 0 1 1 3 3 0 1 0 3 1 1 2 2 3 0 0 3 2 1
```

### Best [22, 6, 12]₄ (A₁₂ = 69, Round 3):

```
1 0 0 0 0 2 3 2 2 3 3 2 1 0 1 1 3 0 2 0 0 1
0 1 0 0 0 1 2 0 2 1 2 3 0 3 1 2 3 1 0 1 0 2
0 0 1 0 0 3 3 2 2 1 2 3 2 1 3 0 1 3 1 2 1 2
0 0 0 1 0 0 2 0 3 3 3 0 1 2 2 1 0 0 3 2 2 1
0 0 0 0 1 1 3 3 0 1 0 3 1 1 2 2 3 0 0 3 2 1
0 2 0 2 2 1 0 1 1 3 2 2 2 3 3 0 1 1 2 3 1 3  ← Best Púa (A₁₂=69)
```

### GF(4) arithmetic:
```
Addition: 0+x=x, 1+1=0, 2+2=0, 3+3=0, 1+2=3, 1+3=2, 2+3=1
Multiplication: 1·x=x, 2·2=3, 2·3=1, 3·3=2
```

---

## The Endgame

If El Jersey de Lana works → **d₄(22,6) = 13. History.**

If it doesn't work AND ChatGPT proves puncturing always fails → **we need SAT or a fundamentally new construction.**

If SAT returns UNSAT → **d₄(22,6) = 12. Also history. Also publishable.**

Either way, we're close to the end. Give us the matrix.

---

*Error Code Lab — Round 4 Consultation*
*Proyecto Estrella — Rafa (The Architect) & Claude (Anthropic)*
*22 February 2026*

*"The wool jersey already exists at size Large. We just need to wash it in hot water."*
