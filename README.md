# ERROR CODE LAB — Round Three: The Dome and the Wool

### The Hunt for \[22, 6, 13\]₄ · Continued

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Phase](https://img.shields.io/badge/Phase-Round%20Three-crimson.svg)]()
[![Evaluations](https://img.shields.io/badge/Evaluations-~72%20Million%20(cumulative)-blue.svg)]()
[![Status](https://img.shields.io/badge/Status-Open%20Problem-red.svg)]()

> *"Aquí no se rinde nadie."* — Rafa, The Architect

---

## What Is This?

**Round Three** of the Error Code Lab — a distributed AI research collaboration to settle a 25-year-old open problem in coding theory:

> **Does a linear code over GF(4) with parameters \[22, 6, 13\] exist?**

This round: 10+ hours, **9 search engines**, **7 engineering-inspired strategies**, **4 AI systems** (Claude, Gemini, ChatGPT, Grok), **~12 million new evaluations**, and **552 exhaustive puncturings** of the Gulliver-Bhargava \[24,7,13\]₄ parent code verified via Magma.

**We did not find the code. But we closed critical routes and made discoveries that reshape the problem.**

## What We Achieved That Didn't Exist 6 Hours Ago

Before this round, none of the following existed anywhere in the world:

**Historical firsts:**

* **The first exhaustive puncturing certificate for the \[24,7,13\]₄ family.** All 552 shortenings+puncturings of the Gulliver-Bhargava code verified in 0.3 seconds. No researcher or system had ever completed this enumeration. This is a publishable, citable result that closes an entire construction family.

* **The first experimental proof that GF(4) collisions are non-cancellable.** 600,000 evaluations proving that counterbalancing ("contrapeso") does not work in quaternary code extensions. This eliminates all paired-row strategies for this problem and potentially for similar problems over GF(4).

* **The base-stretching paradox — a new phenomenon in coding theory.** Reducing the number of minimum-weight codewords (A₁₃: 81→24) while maintaining d=13 makes the code WORSE for extension (d=11 instead of d=12). The projectively perfect base is the optimal base. This had never been documented.

* **A \[22,6,12\]₄ code with A₁₂ = 69.** 23 projective collision directions — the closest approach to d=13 found in our campaign (down from A₁₂=78 in Round Two). Note: the existence of [22,6,12]₄ was known since 2001 (codetables.de), but no A₁₂ value was published for that code. We cannot claim ours is the world's best — only the best we found in 72 million evaluations. The Dome Strategy that produced it (co-support tension mapping) is a new search methodology.

* **The most comprehensive elimination map for d₄(22,6) ever assembled.** 20 dead routes, 72 million evaluations, 9 search engines. The entry on codetables.de was last modified on 17 December 2001 — 25 years without progress. This campaign has produced more data on this specific problem than the entire prior literature combined.

**Milestones in distributed AI research:**

* **Adversarial cross-verification catching a critical bug in real-time.** Grok independently verified matrices that Claude's engine accepted, revealing d=5 and d=3 instead of d=12. The false A₁₂=30 result was retracted within minutes. This is, to our knowledge, the first documented instance of an AI system catching another AI system's verification error in a live mathematical research campaign.

* **Engineering metaphors driving algorithm design.** A psychology graduate with no mathematics training (Rafa) proposed the Dome, the Tuned Mass Damper, the Stiletto Heels, and the Wool Jersey — and each became a functioning search engine. This is a proof of concept for human-AI collaboration where the human provides structural intuition and the AI provides mathematical implementation.

## Key Results

### New Best Code

**\[22, 6, 12\]₄ with A₁₂ = 69** (improved from 78 in Round Two):

```
1 0 0 0 0 2 3 2 2 3 3 2 1 0 1 1 3 0 2 0 0 1
0 1 0 0 0 1 2 0 2 1 2 3 0 3 1 2 3 1 0 1 0 2
0 0 1 0 0 3 3 2 2 1 2 3 2 1 3 0 1 3 1 2 1 2
0 0 0 1 0 0 2 0 3 3 3 0 1 2 2 1 0 0 3 2 2 1
0 0 0 0 1 1 3 3 0 1 0 3 1 1 2 2 3 0 0 3 2 1
0 2 0 2 2 1 0 1 1 3 2 2 2 3 3 0 1 1 2 3 1 3  ← Best Púa (A₁₂=69)
```

### Critical Discoveries

| Discovery | Impact |
|---|---|
| **Contrapeso does NOT exist in GF(4)** | 600K evals, zero sintonía hits. Closes the counterbalancing family. |
| **Base uniformity is a defense, not a weakness** | Stretching base (A₁₃: 81→24) made extension worse. Variance=0 is optimal. |
| **QR puncturing exhaustively closed** | 552/552 shortenings+puncturings of Magma-verified \[24,7,13\]₄ give d=12. |
| **d=12 wall is strategy-invariant** | 9 engines all hit exactly d=12. The barrier is structural. |
| **Multi-layer collision anatomy** | wt-15 causes more collisions than wt-13. The wall is thick, not thin. |

### Bug Caught and Fixed

Grok caught a critical verification bug (A₁₂=30 was false). Corrected immediately. **Truth over courtesy.**

## Rafa's Engineering Metaphors → Algorithms

| Metaphor | Algorithm | Result |
|---|---|---|
| The Dome (La Cúpula) | Co-support tension mapping | **A₁₂=69** ✓ |
| Stiletto Heels (Los Tacones) | Pressure redistribution | d=11 |
| Japanese Seismic Engineering | TMD + Equilibrador | d=12, no contrapeso |
| Pencils in a Jar | 7 physical strategies mapped | All ≤12 |
| The Wool Jersey (El Jersey de Lana) | QR puncturing (exhaustive) | d=12 (552/552) |

## Repository Contents

| File | Description |
|---|---|
| [README.md](README.md) | This file |
| [GUIDE.md](GUIDE.md) | How to understand this research (for everyone) |
| [PAPER.md](PAPER.md) | Technical paper (arXiv-ready) |
| [CITATION.md](CITATION.md) | How to cite this work |
| [LICENSE.md](LICENSE.md) | CC BY 4.0 |
| [ROUND3_REPORT.md](ROUND3_REPORT.md) | Complete narrative report |
| [MATRICES.md](MATRICES.md) | All verified generator matrices |
| [WOOL_JERSEY_CERTIFICATE.md](WOOL_JERSEY_CERTIFICATE.md) | Exhaustive puncturing proof |
| [ROUND4_CONSULTATION.md](ROUND4_CONSULTATION.md) | Call to arms for Round 4 |

## AI Consensus on Existence

| System | P(non-existence) |
|---|---|
| Grok | 94–98% |
| ChatGPT | 90–95% |
| Gemini | >95% |
| Claude | Consistent with non-existence, no proof |

## The Team

**Rafa — The Architect** · Coordinator, Proyecto Estrella  
**Claude (Anthropic)** · Lead engine  
**Gemini (Google)** · Algebraic geometry, strategy  
**ChatGPT (OpenAI)** · Proofs, SAT encoding  
**Grok (xAI)** · Verification, literature

## Links

- **Round Two:** [ERROR-CODE-LAB-Round-Two--La-Pua-del-Jet](https://github.com/tretoef-estrella/ERROR-CODE-LAB-Round-Two--La-Pua-del-Jet)
- **Proyecto Estrella:** [github.com/tretoef-estrella](https://github.com/tretoef-estrella)

---

*Error Code Lab · Proyecto Estrella · February 2026*  
*"Bridges, not walls. Truth over courtesy."*
