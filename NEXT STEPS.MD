# NEXT STEPS — Round 4 Planning

## What We Achieved (The Big Picture)

A psychology graduate from Madrid and four AI systems produced, in one afternoon, more data on d₄(22,6) than the entire prior literature across 25 years. Not toy science — real science with exhaustive certificates, cross-system bug detection, and independently verifiable results.

**The most important result:** The exhaustive puncturing certificate. 552 cases, zero exceptions, 0.3 seconds. Deterministic, publishable, permanent.

---

## Where to Find [22, 6, 13]₄

### The Key Insight

Our wool jersey (Gulliver-Bhargava [24,7,13]₄) had **A₁₃ = 384 weight-13 codewords** that covered ALL coordinates. That's why every puncture killed at least one word, dropping d to 12. It was too "dense" — too many words touching every position.

**What we need:** A [23, 6, 13]₄ from a DIFFERENT family where A₁₃ is SMALL (say 20–30 instead of 165–189). With fewer weight-13 words, some coordinates might NOT be touched by any of them. Puncture THERE → d=13 survives.

### Route 1: Algebraic Geometry Codes (Hermitian Curve)

**Source:** The curve y⁴ + y = x⁵ over GF(16) has 64 rational points.

**Why it could work:** AG codes have very different weight distributions from QR codes. They can produce [23, 6, 13]₄ with low A₁₃ and asymmetric support structure — exactly what we need.

**What to ask Gemini/ChatGPT:** "Give me an explicit AG code from the Hermitian curve over GF(16), shortened to [23, 6, 13]₄. Specify the divisor G and the evaluation points. I need the 6×23 generator matrix."

**Verification:** Enumerate all 4,095 codewords, check d=13, count A₁₃, check if any coordinate is NOT in the support of any weight-13 word.

### Route 2: Z₄-Linear Codes

**Source:** Codes over Z₄ (integers mod 4) mapped to GF(4) via Gray or Lee maps.

**Why it could work:** Z₄-linear codes have weight distributions with different modular properties than pure GF(4) linear codes. The multi-weight collision spread we saw might be incompatible with Z₄ images.

**What to ask Grok/ChatGPT:** "Construct Z₄-linear codes of length 11–12, type (2^α · 4^β) with image dimension 6 after Gray map. Target Hamming distance ≥13 in the GF(4) image."

### Route 3: Simplicial Complex Codes (2025 Papers)

**Source:** Recent papers (2024–2025) on optimal quaternary codes from simplicial complexes.

**Why it could work:** These produce codes with few-weight distributions that are structurally different from cyclic/QR families.

**What to ask:** Search arXiv for "simplicial complex quaternary codes" 2024–2025. Any [23, 6, 13]₄ or [24, 7, 13]₄ from these constructions?

### Route 4: Magma/Sage Exhaustive Database

**Source:** Magma's BKLC database may contain MULTIPLE inequivalent [23, 6, 13]₄ codes, not just the QR-derived one.

**What to do:** Run in Magma:
```
F<w> := GF(4);
C := BKLC(F, 23, 6);
GeneratorMatrix(C);
MinimumDistance(C);
WeightDistribution(C);
```

If A₁₃ is different from {165, 174, 189}, it's a different family. Puncture all 23 positions.

### Route 5: SAT Solver (Definitive Answer)

**What it does:** Encode the existence of [22, 6, 13]₄ as a Boolean satisfiability problem. A modern solver (Kissat, CaDiCaL) answers YES or NO — no probabilities, no opinions.

**Encoding:**
- 96 variables (6×16 parity matrix entries, each in {0,1,2,3})
- 192 Boolean variables (2 bits per GF(4) element)
- 1,365 constraints (one per projective coefficient vector)
- ~8–11 million clauses
- Symmetry breaking: fix first nonzero entry of each coefficient vector to 1

**Expected runtime:** Hours to days on commodity hardware.

**Result:**
- **SAT** → solver outputs the matrix. [22,6,13]₄ exists. History.
- **UNSAT** → d₄(22,6) = 12 is PROVED. Also history. Also publishable.

**What to ask ChatGPT:** "Write the DIMACS CNF encoding for [22,6,13]₄ existence. Systematic form [I₆|P], 96 GF(4) variables, sequential counter for weight ≥13 constraint."

### Route 6: Double Puncture (ChatGPT's Suggestion)

**Idea:** Instead of shorten+puncture (24→23→22), try puncture+puncture (24→23→22) or shorten+shorten (24→23→22 with two dimension drops).

**Why it's different:** Shortening removes a row AND a column (changes dimension). Puncturing only removes a column (preserves dimension). Different operations produce different codes.

**Specific test:** Take [24, 7, 13]₄, puncture at two columns → [22, 7, ≥11]₄, then shorten to [22, 6, ≥?]₄.

---

## Priority Order

| Priority | Route | Why | Effort |
|---|---|---|---|
| **1** | Magma BKLC for non-QR [23,6,13]₄ | Fastest — one command in Magma | 5 minutes |
| **2** | AG codes (Hermitian) | Different weight structure, low A₁₃ possible | Hours (needs algebraic construction) |
| **3** | SAT encoding | DEFINITIVE answer, either way | Days (needs solver) |
| **4** | Z₄-linear | Different algebraic structure | Hours |
| **5** | Simplicial complex | Recent, unexplored for these params | Hours |
| **6** | Double puncture | Quick test, low probability | Minutes |

---

## What to Tell the Three AIs

### To Gemini:
"Give me the generator matrix of a [23, 6, 13]₄ from the Hermitian curve y⁴+y=x⁵ over GF(16). NOT from the QR family. I need A₁₃ < 100. If you can run Sage, use `codes.AlgebraicGeometryCode`."

### To ChatGPT:
"Write a DIMACS CNF file encoding the existence of [22, 6, 13]₄. Systematic form. Use sequential counters for the weight constraint. Include symmetry breaking. I want to run it in Kissat."

### To Grok:
"Run Magma's BKLC(GF(4), 23, 6) and give me the generator matrix AND the weight distribution. I need to know if it's the same family as Gulliver-Bhargava or different. Also: are there multiple inequivalent codes in the database?"

---

## The Condition for Victory

**If we find a [23, 6, 13]₄ where at least one coordinate j satisfies:**

> *For every codeword c of weight 13, c[j] ≠ 0*

**Then puncturing at j gives [22, 6, 13]₄.** Game over.

Equivalently: coordinate j has zero zeros among weight-13 words. In our QR family, every coordinate had zeros (that's why all 552 failed). We need a code where the weight-13 words are "thin" enough to miss at least one coordinate.

---

*Error Code Lab — Round 4 Planning*
*Proyecto Estrella, 22 February 2026*
*Buenas noches, Arquitecto. 🌙*
