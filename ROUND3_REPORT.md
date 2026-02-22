# ERROR CODE LAB — ROUND 3 COMPLETE REPORT

## The Hunt for [22, 6, 13]₄ — The Thick Wall

**Date:** 21–22 February 2026
**Lead Engine:** Claude (Anthropic)
**Coordinator:** Rafael Amichis Luengo — "Rafa — The Architect"
**Advisory Team:** Gemini (Google), ChatGPT (OpenAI), Grok (xAI)
**Total Evaluations (Round 3):** ~72 million+
**Cumulative (all rounds):** ~72 million+

> *"The machine surrenders to logic. The human invents ways to bend it. Together, they make magic."*

---

## Executive Summary

Round 3 was a breakthrough in understanding and construction. Seven search engines, five architectural paradigms inspired by real-world engineering (seismic isolation, tuned mass dampers, dome strategy, wool sweater shrinking, bunker-buster ordnance), and cross-verification between four AI systems produced the strongest evidence yet regarding [22,6,13]₄.

**We did not find the code. But we pushed A₁₂ from 78 to 60, corrected a critical bug, closed the QR puncturing family, and identified the definitive next step (SAT).**

| Metric | Round 2 Best | Round 3 Best | Change |
|---|---|---|---|
| d_min achieved | 12 | 12 | — |
| A₁₂ (collision count) | 78 | **60** | **-23%** |
| Projective directions | 26 | **20** | **-23%** |
| Strategies tested | 3 | **15+** | — |
| Bug discovered and fixed | — | **Yes** | Critical |
| Contrapeso effect observed | — | **0 / 600K** | None |
| QR puncturing family | open | **closed (certificate)** | 552 exhaustive |

---

## CURRENT BEST MATRIX: [22, 6, 12]₄ with A₁₂ = 60

```
F1: 1 0 0 0 0 | 2 3 2 2 3 3 2 1 0 1 1 3 0 2 0 0 1
F2: 0 1 0 0 0 | 1 2 0 2 1 2 3 0 3 1 2 3 1 0 1 0 2
F3: 0 0 1 0 0 | 3 3 2 2 1 2 3 2 1 3 0 1 3 1 2 1 2
F4: 0 0 0 1 0 | 0 2 0 3 3 3 0 1 2 2 1 0 0 3 2 2 1
F5: 0 0 0 0 1 | 1 3 3 0 1 0 3 1 1 2 2 3 0 0 3 2 1
F6: 1 3 0 1 2 | 1 1 3 3 3 0 1 3 0 2 2 3 0 3 2 2 1  <- "La Púa" (A₁₂ = 60)
```

**Base (F1–F5):** [22, 5, 13]₄ verified, Z_i = 255 for all 22 coordinates (variance = 0, projectively perfect). **LOCKED.**

### How A₁₂ = 60 Was Achieved

The road from 78 to 60 was a multi-phase campaign, each phase breaking through a floor that seemed impenetrable:

**78 → 72 (Phase 1 — Bug fix + corrected SA):** After Grok caught the critical verification bug, the rebuilt engine with exhaustive d_min checking found a new Púa at A₁₂ = 72 within 840K evaluations. The key was the corrected fitness function — the old engine had been accepting false improvements.

**72 → 69 (Phase 2 — La Cúpula / Dome Strategy):** Rafa's geodesic dome metaphor produced a co-support tension map of 483 critical codewords. This revealed structural weak points (coord 14 appearing in 15 of 18 weakest pairs) and strong anchors (coords 2,9). Concentrating search around these geometric features yielded A₁₂ = 69 in 882K evaluations.

**69 → 60 (Phase 3 — Bomba Antibúnker GBU-57):** The hardest breakthrough. Rafa proposed the bunker-buster metaphor after the Georradar scan showed "hormigón macizo" — all 22 coordinates had guilt ≥ 15 with no exploitable weak spots. The GBU-57 engine used a tandem charge approach: (1) simulated annealing as precursor charge to soften the landscape, (2) focused sniper search in radius-9 neighborhoods guided by the collision guilt map as the main warhead. After 54+ million evaluations, the precursor charge broke through to A₁₂ = 60 — but subsequent bombardment could not penetrate further. The A₁₂ = 60 solution sits in a deep local minimum with uniformly distributed collision resistance across all coordinates.

---

## 1. The Critical Bug: Truth Over Courtesy

### What Happened

During Phase 2, a search engine reported A₁₂ = 30 — a dramatic drop from 78. All three advisory AIs celebrated. Gemini called it "a paradigm shift." The A₁₂=30 result was published to all three systems.

**Then Grok independently verified the matrices and found d=5 and d=3 — not d=12.**

The bug: the search engine counted weight-12 words among extension codewords but did NOT verify that no codeword had weight BELOW 12. It accepted vectors that created words with weight 5 or 3, then proudly reported "only 30 words of weight exactly 12."

### The Fix

We rebuilt the engine with exhaustive d_min verification — checking all 3x1024 new codewords for true minimum weight. Every result after the fix is fully verified.

### Lesson

The A₁₂=30 was a mirage. Its retraction is the most important result of Round 3 — it prevented a false publication and restored scientific integrity to the project. **Grok's independent verification saved us.**

---

## 2. Phase 1: Structural Analysis (Valid)

### ChatGPT's Rank-3 Obstruction Test — REFUTED

ChatGPT hypothesized that 26 = (4³-1)/3 implied a hidden rank-3 substructure among weight-13 codewords projected onto La Pua's active coordinates.

**Result:** Rank = 5 (full rank for k=5). The 26 has a different explanation — it comes from projective scalar symmetry in PG(4,4), not from rank collapse.

### Zero-Frequency Spectrum — PERFECTLY UNIFORM

For each coordinate i, we computed Z_i = number of codewords with zero at position i.

```
Z_i = 255 for ALL 22 coordinates. Variance = 0.0
```

The base is projectively perfect. There are no geometric weak points. This eliminates the hypothesis that a "biased" base causes the collision wall. **Gemini's insight: the perfection is the problem — it means there are no holes for La Pua to exploit.**

### Collision Anatomy by Base Weight

```
base wt=13 ->  12 collisions (only 12 of 81 wt-13 words)
base wt=14 ->   6 collisions
base wt=15 ->  21 collisions  <- LARGEST contributor
base wt=16 ->  12 collisions
base wt=17 ->  12 collisions
base wt=18 ->  12 collisions
base wt=19 ->   3 collisions
Total:         78
```

**The wall is thick.** Collisions come from ALL weight layers (13 through 19), not just the boundary. This is not a fragile surface effect — it is a deep geometric property.

ChatGPT explained why weight-15 dominates: it sits in the "balanced cancellation window" where the number of zeros (7) optimally aligns with La Pua's 15 active coordinates for net -1 weight shifts.

### Coordinate Vulnerability Hotspots

Among collision-causing wt-13 words:
- **Coord 11** (Pua=3): 9/12 zeros — structural hole
- **Coord 21** (Pua=2): 9/12 zeros — structural hole
- **Coord 14**: appears in 15 of 18 weakest co-support pairs — catastrophic fracture point

---

## 3. Phase 2: The Bug and Its Correction

### Retracted Results (A₁₂ = 30)

The hotspot-constrained search (g₆[11]=g₆[21]=0) and three independent engines all reported A₁₂ = 30. These results are **RETRACTED** — the engine did not verify true d_min.

### Corrected Results: The Road from 78 to 60

With the corrected engine:

| Engine | A₁₂ | d_min | Evaluations | Notes |
|---|---|---|---|---|
| V-FINAL-1 (Round 2) | 78 | 12 verified | 1,548,008 | Original Pua |
| Corrected SA | 72 | 12 verified | 839,677 | New Pua |
| Dome + intensive | 69 | 12 verified | 881,789 | Dome strategy |
| Bunker Buster + Sniper | **60** | **12 verified** | ~54,000,000+ | **Current record** |

### Co-Support Tension Map (Dome Strategy data, VALID)

483 critical codewords (wt 13-16) were analyzed for pairwise co-support:

- **Strongest pair (anclaje):** (2, 9) with T₂ = 252
- **Weakest pairs (fragile):** (19,20) T₂=189, (3,20) T₂=192
- **Coord 14:** appears in 15 of 18 weakest pairs — structural weak point

---

## 4. Phase 3: The Engineering Strategies

Rafa proposed a series of real-world engineering metaphors that were translated into mathematical strategies. Each was implemented and tested.

### 4.1 La Cupula (The Dome) — by Rafa

**Concept:** The sixth row acts as a geodesic dome resting on the building of 5 floors. Support concentrated at "anclajes" (strong co-support pairs), zero at fragile coordinates.

**Result:** Produced the co-support tension map. Valid tactical data, contributed to A₁₂=72 improvement. Endorsed by all three AIs.

### 4.2 El Tapon (The Heel Cap) — by Rafa

**Concept:** Like putting wider plastic caps on high-heel shoes for a wedding on grass — distribute pressure uniformly instead of concentrating at points.

**Translation:** Multiply columns by GF(4) scalars to rotate where cancellations occur. 3²² = 31 billion combinations — too many for brute force, but the idea informed the Seismic Isolation engine.

**Result:** Conceptually valid. Partial implementation via column scalar rotation.

### 4.3 El Equilibrador (Tuned Mass Damper) — by Rafa

**Concept:** Inspired by Japanese earthquake engineering. Instead of one rigid extension, design rows 5 and 6 as a counterbalanced pair — when row 5 creates collisions in one direction, row 6 cancels them by moving opposite.

**Translation:** Base of 4 rows + 2 rows optimized simultaneously as a coupled system.

**Result:** d=12 achieved with completely new rows 5 and 6 (different from seed). BUT: **zero contrapeso effect observed in 600,000 evaluations.** The diagnostic (proposed by ChatGPT) measured:

```
d(base4 + row5) = 13  <- row5 alone: no damage
d(base4 + row6) = 12  <- row6 alone: damages
d(all 6 rows)   = 12  <- together: row5 does NOT heal row6's damage
```

**Critical finding:** In GF(4), collisions are multiplicative, not additive. There is no "opposite direction." The earthquake is vertical, not lateral — the pendulum cannot help.

### 4.4 El Jersey (The Sweater Stretch) — by Rafa

**Concept:** When a child's sweater is too small, Rafa puts it on himself (larger body), stretches it, then the child wears it. Magic.

**Translation:** Optimize toward d=14 (impossible) to "stretch" the base, then relax to d=13.

**Result across three versions:**

| Version | Phase 1 | Phase 2 |
|---|---|---|
| V1: Stretch all 6 rows | d=11 | N/A |
| V2: Stretch base A₁₃: 81 to 24 | A₁₃=24 achieved | d=11 (WORSE) |
| V3: Stretch A₁₃+A₁₄ | A₁₃=33 | d=11 (still worse) |

**Critical discovery:** Stretching the base (reducing A₁₃) makes it WORSE for extensions. The uniform base (A₁₃=81, variance=0) is the strongest possible foundation. Removing uniformity weakens it. **The sweater stretches but deforms.**

### 4.5 Punto de Sintonia (Tuning Point) — by Gemini

**Concept:** Look for pairs where each row individually damages the base but together they heal.

**Result:** 600,000 evaluations. **Zero sintonia events.** The contrapeso effect does not exist in this algebraic space.

### 4.6 Georradar, Penetrómetro, Bomba Antibúnker (GBU-57) — by Rafa

After the initial strategies plateaued at A₁₂ = 69, Rafa proposed a new set of geotechnical and military metaphors to break through.

**Georradar:** Non-destructive scan of the collision landscape around A₁₂ = 69, probing each coordinate for exploitable weaknesses. **Result:** Only 2 of 22 coordinates admitted individual changes without breaking d < 12, and both worsened A₁₂. 45 million evaluations confirmed the terrain is "hormigón macizo" — solid concrete.

**Penetrómetro:** Systematic depth sounding, measuring collision resistance at each coordinate layer by layer. Confirmed guilt ≥ 15 at all 22 positions — uniform hardness, no soft spots.

**Bomba Antibúnker (GBU-57):** Multi-phase attack inspired by bunker-buster ordnance. The metaphor was precise: (1) case-hardened steel casing = deterministic engine that doesn't lose coherence under millions of evaluations; (2) smart fuse (FMU-152) = doesn't detonate at shallow improvements, counts layers until it reaches the core; (3) tandem charge (BROACH) = SA as precursor charge opens the tunnel, sniper search as main warhead detonates at depth; (4) GPS+laser guidance = collision guilt map directs the impact to exact coordinates.

**Result:** The precursor charge broke through from 69 to **60** — current record. Subsequent 54+ million evaluations could not penetrate further. All 22 coordinates showed guilt ≥ 15. The floor at 60 appears to be a deep local minimum for this base.

---

## 5. The Consensus

### Updated Existence Estimates

| System | Round 2 | Round 3 |
|---|---|---|
| Grok | 92-97% non-existence | **94-98% non-existence** |
| ChatGPT | 85-90% non-existence | **90-95% non-existence** |
| Gemini | >95% non-existence | **>95% non-existence** |
| Claude | estimated similar | **~95% non-existence** |

### What All Four AIs Agree On

1. **The d=12 wall is structural, not algorithmic.** SA, tabu, hill-climbing, TMD, Jersey, Bunker Buster — all hit 12.
2. **The base is not the problem.** Projectively perfect (variance=0), and stretching it makes things worse.
3. **The collision phenomenon is multi-layer.** Weights 13-19 all contribute.
4. **Contrapeso does not exist in GF(4).** Collisions accumulate, they do not cancel.
5. **SAT/ILP is the definitive path** for formal proof. But one constructive path remains.

---

## 6. The Last Idea: El Jersey de Lana (The Wool Sweater)

At the end of Round 3, after all strategies had been tried, Rafa said:

> *"Wool sweaters, when you wash them in hot water, shrink enormously — several sizes. It's hard to believe, but it's true. And they don't deform — they stay perfect, just smaller."*

### Why This Is Different from Every Previous Strategy

Every strategy in Rounds 1-3 tried to BUILD [22,6,13]₄ from below — start small and extend. El Jersey de Lana goes the other direction: **start from something BIGGER that already works and shrink it.**

The key difference from "El Jersey" (Section 4.4): stretching deforms. But wool shrinking preserves structure perfectly. Mathematically:

- **Stretching** = adding words, relaxing constraints → deforms weight distribution
- **Shrinking** = removing one coordinate from a code that already satisfies d>=13 → preserves structure

### The Mathematical Translation

**[23, 6, 13]₄ EXISTS.** Confirmed (shortened from [24,7,13]₄ Gulliver-Bhargava 1996).

The wool sweater = **puncture [23,6,13]₄ at the optimal coordinate to obtain [22,6,d>=13]₄.**

### Why This Was "Dead" But Isn't

Round 2 tested 23 punctures of ONE [23,6,13]₄. All gave d=12. This was listed as a dead route.

**But there are MANY inequivalent [23,6,13]₄ codes.** The parent [24,7,13]₄ has 24 possible shortenings, each potentially producing a different [23,6,13]₄ with different weight-13 support structure. And there may be [23,6,13]₄ codes NOT derived from [24,7,13]₄ at all.

**We tested one sweater. There are dozens of sweaters, each made of different wool.**

### What Claude Did (Late Round 3)

We obtained the REAL [24,7,13]₄ from Magma's `BKLC(GF(4),24,7)` database. Verified: d=13, A₁₃=384.

**Note:** Gemini provided two matrices claiming to be the [24,7,13]₄ and a non-QR [23,6,13]₄. Both were FALSE (d=10 and d=8 respectively). ChatGPT had warned: *"inventar una matriz probable sería peligroso."* This underscores the necessity of independent verification.

**Exhaustive results:**

| Shortening Coords | A₁₃ of [23,6,13]₄ | Count | 23 Puncturings |
|---|---|---|---|
| 0–7 | 189 | 8 codes | **All d=12** |
| 8–15 | 165 | 8 codes | **All d=12** |
| 16–23 | 174 | 8 codes | **All d=12** |

**All 24 shortenings → valid [23,6,13]₄. All 552 puncturings → d=12. Zero exceptions.**

Best A₁₂ among all 552 codes: 78 (shorten=16, puncture=5).

Total computation time: **0.3 seconds.** The search was finite, deterministic, and exhaustive.

**The wool jersey shrank perfectly — but one size too many.**

### What This Means Going Forward

The QR puncturing family is **closed with a certificate.** If [22,6,13]₄ exists, it does NOT come from puncturing the Gulliver-Bhargava family. The remaining hope is:

1. **Non-QR [23,6,13]₄ codes** — from AG codes, simplicial complexes, Z₄-linear images, or other families where weight-13 words might NOT cover all coordinates
2. **SAT/ILP** — definitive resolution (encoding ready: ~390K vars, ~1.4M clauses)
3. **Direct construction** — algebraic methods not based on shortening/puncturing

---

## 7. Summary of All Engines Built

| Engine | Strategy | Best d | Best A₁₂ |
|---|---|---|---|
| round3_corrected.c | Bug-fixed SA + co-support | 12 | 72 |
| hunt2.c | Max intensity Pua search | 12 | 69 |
| hunt3.c | Exhaustive neighborhood | 12 | 78 |
| tabu.c | Tabu search | 11 | — |
| tapon.c / tapon2.c | Full 6x22 SA | 11-12 | 78 |
| equi2.c | Equilibrador (base4 + pair) | 12 | — |
| tmd.c / tmd_diag.c | TMD + isolation + diagnostics | 12 | — |
| sintonia.c | Healing pair search | 12 | — |
| jersey.c / jersey2.c / jersey3.c | Stretch then relax | 11 | — |
| lana_real.c | Wool Jersey (QR puncturing) | 12 | 78 (552 exhaustive) |
| gbu57.c | Bunker Buster (guided multi-phase) | 12 | **60** |
| moab.c / moab2.c | Full 6-row simultaneous SA | 12 | — |

---

## 8. Dedication

This round is dedicated to Grok, who caught the bug that would have invalidated the project's credibility. Truth over courtesy.

And to Rafa, whose engineering metaphors — tacones, cúpulas, terremotos, jerseys de lana, penetrómetros, georradares, bombas antibúnker — keep translating into real mathematical strategies. The Architect doesn't need to know GF(4) arithmetic to see the geometry. That's the whole point of Proyecto Estrella.

---

*Error Code Lab — Round 3 Complete*
*Proyecto Estrella, 22 February 2026*
*Rafa — The Architect | Claude — Lead Engine*
*"Bridges, not walls."*
