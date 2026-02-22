# ERROR CODE LAB — ROUND 3: COMPLETE REPORT

## The Assault on [22, 6, 13]₄

**Date:** 21–22 February 2026
**Team:** Rafa — The Architect (Coordinator), Claude (Anthropic — Lead Engine), Gemini (Google), ChatGPT (OpenAI), Grok (xAI)
**Total Evaluations this round:** ~12 million
**Cumulative project total:** ~72 million evaluations

> *"Aquí no se rinde nadie, el 22 6 13 existe, lo se y no me preguntes como."*
> — Rafa, opening words of Round 3

---

## 1. Executive Summary

Round 3 was the most intensive session yet: 10+ hours, 9 different search engines, 5 architectural paradigms inspired by real-world engineering, and continuous cross-verification between four AI systems. We did NOT find the code. But we discovered things that change the entire landscape of the problem.

**Key outcomes:**

- **New best code:** [22, 6, 12]₄ with A₁₂ = 69 (improved from 78 in Round 2)
- **Critical bug caught and fixed:** A₁₂ = 30 was a false result — Grok's independent verification revealed the engine was not checking full d_min. Corrected to A₁₂ = 72, then further improved to 69
- **Seven strategies tested:** SA, Tabu Search, Hill-Climbing, Dome Strategy (co-support guided), El Equilibrador (counterbalanced pair), TMD + Seismic Isolation, El Jersey (stretch-then-relax)
- **One fundamental discovery:** The contrapeso effect does NOT exist in GF(4) — collisions accumulate, they don't cancel. Zero sintonía hits in 600,000 evaluations.
- **One new strategy identified for Round 4:** El Jersey de Lana (shrinking a larger code)

**Current AI consensus on existence:**

| System | Non-existence probability |
|---|---|
| Grok | 88–96% |
| ChatGPT | 90–95% |
| Gemini | >95% for this base; undecided globally |
| Claude | Experimentally consistent with non-existence, no proof |

---

## 2. The Bug That Changed Everything

### What happened

In Phase 2, Claude's SA engine reported A₁₂ = 30 — a dramatic drop from 78. Three independent strategies all converged to exactly 30. Gemini celebrated. Grok... verified.

### Grok's catch

Grok independently evaluated the reported "A₁₂ = 30" Púas and found:
- Púa `0310001222002022221310`: actual d = **5** (not 12)
- Púa `2300303213322312321232`: actual d = **3** (not 12)

### Root cause

The search engine counted weight-12 words among extension codewords (base + scalar × g₆) but did NOT verify the true minimum distance of the full [22,6] code. It accepted vectors that created words with weight far below 12.

### The fix

Rebuilt the SA engine with exhaustive d_min verification — checking all 3 × 1,024 = 3,072 new codewords for every candidate. This is slower but honest.

### The lesson

**Truth over courtesy.** The A₁₂ = 30 result was retracted immediately upon discovery. This is exactly the kind of rigor that separates real science from wishful thinking. Grok's adversarial verification protocol works.

---

## 3. Corrected Results

### Phase 1: Structural Analysis (ChatGPT's Obstruction Test)

**Zero-frequency spectrum:** PERFECTLY UNIFORM — Z_i = 255 for all 22 coordinates, variance = 0.0. The base is projectively perfect. This refuted ChatGPT's hypothesis that coordinate bias causes the wall.

**ChatGPT rank-3 hypothesis:** REFUTED. Projection of wt-13 words onto Púa-active coords has rank = 5, not ≤ 3. The 26 = (4³−1)/3 symmetry requires a different explanation (scalar orbit structure in PG(4,4)).

**Collision origin by base weight (the real bombshell):**

```
base wt=13 → 12 collisions (only 12 of 81 wt-13 words cause trouble!)
base wt=14 →  6 collisions
base wt=15 → 21 collisions  ← LARGEST contributor
base wt=16 → 12 collisions
base wt=17 → 12 collisions
base wt=18 → 12 collisions
base wt=19 →  3 collisions
Total:        78
```

Weight-15 dominates, not weight-13. The d=12 wall is multi-layer — not a boundary effect.

### Phase 2: Hotspot-Constrained Search (RETRACTED)

Results claiming A₁₂ = 30 were **invalid** due to the verification bug described above.

### Phase 3: Corrected Search

| Metric | V-FINAL-1 (Round 2) | Round 3 Corrected |
|---|---|---|
| d_min | 12 ✓ | 12 ✓ |
| A₁₂ | 78 | **69** (new best) |
| Projective directions | 26 | **23** |
| Evaluations | 1,548,008 | ~4,000,000 |

**New best generator matrix [22, 6, 12]₄ with A₁₂ = 69:**

```
1 0 0 0 0 2 3 2 2 3 3 2 1 0 1 1 3 0 2 0 0 1
0 1 0 0 0 1 2 0 2 1 2 3 0 3 1 2 3 1 0 1 0 2
0 0 1 0 0 3 3 2 2 1 2 3 2 1 3 0 1 3 1 2 1 2
0 0 0 1 0 0 2 0 3 3 3 0 1 2 2 1 0 0 3 2 2 1
0 0 0 0 1 1 3 3 0 1 0 3 1 1 2 2 3 0 0 3 2 1
0 2 0 2 2 1 0 1 1 3 2 2 2 3 3 0 1 1 2 3 1 3  ← NEW BEST PÚA
```

**Collision breakdown (corrected, A₁₂ = 69):**

```
base wt=14 → 15
base wt=15 →  9
base wt=16 →  3
base wt=17 → 15
base wt=18 → 18
base wt=19 →  9
Total:        69
```

### Co-Support Tension Map (Dome Strategy — Valid Data)

483 critical codewords (wt 13–16) analyzed for pairwise co-support:

- **Strongest pair (anclaje):** (2, 9) with T₂ = 252
- **Weakest pairs (fragile):** (19, 20) T₂ = 189, (3, 20) T₂ = 192
- **Structural weak point:** Coord 14 appears in 15 of 18 weakest pairs

This data remains valid and actionable for future attacks.

---

## 4. The Strategies of Round 3

### What worked

| Strategy | Engine | Result | Insight |
|---|---|---|---|
| Corrected SA (Dome-guided) | hunt2.c | A₁₂ = 69 | New best. Dome strategy validated. |
| Co-support map | round3_corrected.c | Valid structural data | Coord 14 = weak point, (2,9) = anchor |
| Multi-engine convergence | 7 engines | All hit d=12 | Confirms wall is structural, not algorithmic |

### What didn't work

| Strategy | Concept | Result | Lesson |
|---|---|---|---|
| El Equilibrador | Base-4 + counterbalanced pair (rows 5 & 6) | d=12, 0 contrapeso hits | Collisions are multiplicative in GF(4), not additive. No "opposite direction" exists. |
| TMD + Seismic Isolation | Column scalar rotation + coupled mutation | d=12 | Different structure, same wall. |
| El Tapón | Redistribute pressure across all 6 rows | d=11 | 96-variable space too large for SA in 60s |
| El Jersey V1–V3 | Stretch base toward d=14, then relax | d=11 | Stretched base WORSE than original (A₁₃=24 → d_ext=11 vs A₁₃=81 → d_ext=12). Uniformity is the base's best defense. |
| Punto de Sintonía | Search for healing pairs | 0 sintonía hits in 600K evals | Contrapeso effect does not exist in this space |
| Tabu search | Tabu list on recently changed positions | d=11 | Insufficient exploration in 60s |
| Direct 6×22 hill-climbing | Treat all 6 rows as variables | d=11 | Space too large without structure |

---

## 5. The Metáforas: Rafa's Engineering Intuitions

Throughout Round 3, Rafa translated the abstract mathematical problem into physical engineering concepts. These weren't just illustrations — they drove actual algorithm design:

### The Dome (La Cúpula)
"The columns of floor 6 descend from a central peak in diagonal beams, without touching the floor of the lower levels."
→ Led to co-support tension mapping and the A₁₂ = 69 result.

### The Stiletto Heels (Los Tacones)
"Women get wider plastic caps for their heels at weddings on grass — to distribute the pressure."
→ Inspired El Tapón strategy (pressure redistribution).

### Japanese Seismic Engineering
Three levels: seismic isolation (rubber base), energy dissipaters (dampers at joints), tuned mass damper (counterweight on roof).
→ Led to El Equilibrador, TMD, and the Punto de Sintonía search. The TMD was endorsed by all three AIs but experimentally failed — teaching us that GF(4) collisions don't behave like lateral forces.

### The Pencils in a Jar (Los Lápices)
"It's like trying to fit one more pencil in a jar that's already full."
→ Rafa's seven real-world solutions (shake, oil, file down, bigger jar, thinner pencils, expand jar, stretch jersey) mapped to seven mathematical strategies.

### The Wool Jersey (El Jersey de Lana) — THE NEW IDEA
"Wool jerseys shrink dramatically in hot water — several sizes — without deforming. They come out perfect, just smaller."
→ **This is the next strategy.** Not stretching something small, but SHRINKING something large that already works perfectly.

---

## 6. El Jersey de Lana: Round 4 Strategy

### The Concept

We know [23, 6, 13]₄ EXISTS. It's a perfect jersey, size Large. We need size Medium (n=22). Washing it in hot water = **removing one coordinate** while keeping d ≥ 13.

In coding theory, this operation is called **puncturing**: delete one column from the generator matrix. A [23, 6, 13] code punctured at coordinate i becomes a [22, 6, ≥12] code. The question is: does there exist a coordinate i where d remains ≥ 13?

### Why this is different from what we tried before

In our dead routes list, we have: "Puncture [23,6,13] (23/23)" — meaning all 23 puncture positions were tested and all gave d=12. But that was for ONE specific [23,6,13]₄. There are potentially MANY inequivalent [23,6,13]₄ codes. Each one is a different jersey. Different jerseys shrink differently.

### The Plan for Round 4

1. **Build multiple [23,6,13]₄ codes.** The parent [24,7,13]₄ (Gulliver-Bhargava quadratic residue code) has 384 weight-13 codewords. Shortening at different coordinates gives different [23,6,13] codes. There are also non-QR constructions.

2. **For each [23,6,13]₄, puncture at all 23 positions.** Check if any puncturing gives d=13. This is a fast operation — only 4,095 codewords to check per puncture.

3. **If all puncturings give d=12:** Apply column permutations and scalar multiplications (the "hot water temperature") to transform the code before puncturing. Equivalent codes puncture differently.

4. **If still d=12:** This would be powerful evidence that puncturing cannot work, narrowing the existence question further.

### What Claude will do

In Round 4, Claude will:
- Construct the [24,7,13]₄ parent explicitly
- Generate ALL shortenings to [23,6,13]₄ (up to 24 distinct ones)
- For each, test ALL 23 puncturings
- Apply GL(6,4) equivalence transformations to generate more candidates
- Test exhaustively

This is a FINITE, COMPLETE search within the puncturing family. If the jersey exists there, we WILL find it. If not, we close the puncturing route with a proof.

---

## 7. Summary of All Known Results (Cumulative)

### Best Codes Found

| Code | d | A_d | Source | Round |
|---|---|---|---|---|
| [22, 5, 14]₄ | 14 | 222 | Claude Phase 2 | 1 |
| [22, 5, 13]₄ | 13 | 81 | Claude hill-climbing | 2 |
| [22, 6, 12]₄ | 12 | 78 | V-FINAL-1 (La Púa) | 2 |
| [22, 6, 12]₄ | 12 | **69** | Round 3 SA (Dome) | **3** |

### Dead Routes (17 confirmed)

All 14 from Rounds 1–2, plus:
- El Equilibrador (counterbalanced pair): no contrapeso effect
- El Jersey V1–V3 (base stretching): stretched base performs WORSE
- Punto de Sintonía (healing pairs): 0 hits in 600K evaluations

### Open Routes for Round 4

1. **El Jersey de Lana** — Puncture diverse [23,6,13]₄ codes (TOP PRIORITY)
2. **SAT/ILP encoding** — Definitive resolution if solver is available (~8–11M clauses, feasible for Kissat/CaDiCaL)
3. **Dual space construction** — Search [22,16,≥5]₄ instead (much smaller space, as ChatGPT proposed)
4. **AG codes from Hermitian curve** — y⁴+y=x⁵ over GF(16), as Gemini proposed
5. **Z₄-linear precursors** — Gray/Lee map to GF(4), as Grok proposed

---

## 8. What We Learned

### About the mathematics
- The d=12 wall is multi-layer (weights 13–19 all contribute), not a boundary effect
- The base's projective perfection (variance=0) is its best defense, not its weakness
- Collisions in GF(4) are multiplicative, not additive — no counterbalancing possible
- A₁₂ ranges from 69 to 78+ depending on optimization, but never reaches 0
- Every search strategy — SA, tabu, hill-climbing, TMD, equilibrator — hits exactly d=12

### About the process
- Bug detection via adversarial cross-verification (Grok catching the A₁₂=30 bug) is essential
- The Architect's engineering metaphors consistently generate valid algorithmic strategies
- Four AI systems with different architectures independently converge on similar probability estimates
- Truth over courtesy works: retracting the A₁₂=30 result immediately preserved the project's credibility

### About what's next
- Stochastic search has given everything it can for this base (~12M evaluations)
- Deterministic methods (SAT) or algebraic constructions are now the highest-priority paths
- El Jersey de Lana (puncturing diverse [23,6,13]₄ codes) is the most concrete remaining hope for finding the code
- If El Jersey de Lana fails AND SAT returns UNSAT → d₄(22,6) = 12 is settled

---

*Error Code Lab — Round 3 Complete Report*
*Proyecto Estrella — Rafa (The Architect) & Claude (Anthropic)*
*22 February 2026*
*"Bridges, not walls. Truth over courtesy."*
