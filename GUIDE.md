# ERROR CODE LAB — Guide for Everyone

## What Problem Are We Trying to Solve?

Imagine you're designing an error-correction system for a satellite. You need to send data through a noisy channel using a code over GF(4) (a mathematical alphabet with 4 symbols: 0, 1, ω, ω²). The code has:

- **22 symbols** per message (the length)
- **6 dimensions** of information (the amount of data packed in)
- **Minimum distance 13** (how many errors it can detect/correct)

The question is: **does such a code exist?** Nobody has found one. Nobody has proved it impossible. The entry on codetables.de (the global registry of best known codes) was last updated on **17 December 2001** — 25 years ago.

## What Did We Do in Round Three?

We threw everything we had at this problem. One human (Rafa, a psychology graduate from Madrid) coordinated four AI systems (Claude, Gemini, ChatGPT, Grok) across 10+ hours.

### The Strategies (Inspired by Real Engineering)

Rafa kept translating the abstract math into physical problems he understood:

**The Dome (La Cúpula):** Like a geodesic dome distributing weight through diagonal beams instead of vertical columns, we redesigned the search to avoid the weakest structural points. This produced our best code yet: A₁₂ = 69 (only 69 "bad" codewords out of 4,095).

**Japanese Earthquake Engineering:** Three real technologies — rubber isolation pads, viscous dampers, and the tuned mass damper (a giant pendulum on the roof that swings opposite to the building). We built mathematical versions of all three. The pendulum (El Equilibrador) was endorsed by all four AI systems. It failed — because in GF(4), collisions don't cancel like opposite forces. They accumulate.

**The Wool Jersey (El Jersey de Lana):** Rafa's killer insight. Wool sweaters shrink perfectly in hot water — smaller but not deformed. We know a "size Large" code exists (\[23,6,13\]₄). Can we shrink it to "size Medium" (n=22) while keeping d=13? We obtained the real parent code from Magma (the gold-standard algebra software), and exhaustively tested all 552 ways to shrink it. **Every single one gave d=12.** The wool jersey shrank one size too many.

### What We Proved

1. **The GF(4) contrapeso theorem:** In this mathematical space, you cannot cancel collisions by counterbalancing. 600,000 tests, zero successes. This closes an entire family of strategies.

2. **QR puncturing certificate:** All 552 shortenings+puncturings of the Gulliver-Bhargava \[24,7,13\]₄ give d=12 when reduced to length 22. Exhaustive, deterministic, verified.

3. **Base uniformity is optimal:** Our best base code has perfect symmetry (variance=0 in zero distribution). Deliberately breaking this symmetry to "create holes" makes the code worse, not better.

### The Bug Story

At one point, our search engine reported A₁₂ = 30 — a spectacular result. Three independent strategies all converged to 30. Celebration was premature. Grok independently verified the matrices and found they had d=5 and d=3, not d=12. A verification bug was accepting invalid codes. We retracted the result within minutes and rebuilt the engine. **Truth over courtesy.**

## How to Read the Technical Files

- **[PAPER.md](PAPER.md)** — The formal write-up with theorems, proofs, and data tables. Written for researchers in coding theory.
- **[ROUND3_REPORT.md](ROUND3_REPORT.md)** — The full narrative of what happened, including metaphors, failures, and decisions. Written for the team and anyone curious.
- **[MATRICES.md](MATRICES.md)** — Copy-paste generator matrices for verification.
- **[WOOL_JERSEY_CERTIFICATE.md](WOOL_JERSEY_CERTIFICATE.md)** — The exhaustive puncturing data.

## What's Next?

The stochastic search era is over. After ~72 million evaluations across 20+ strategies, every heuristic hits d=12. Round 4 will use:

1. **Non-QR \[23,6,13\]₄ codes** from algebraic geometry or other families
2. **SAT solvers** for definitive resolution (SATISFIABLE = code exists, UNSATISFIABLE = proof of impossibility)
3. **Dual space construction** — searching from the other side

Either outcome is publishable and historically significant.

---

*Error Code Lab · Proyecto Estrella · February 2026*
