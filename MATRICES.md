# Verified Generator Matrices

All matrices verified by exhaustive codeword enumeration. Notation: 0=0, 1=1, 2=ω, 3=ω².

---

## \[24, 7, 13\]₄ — Gulliver-Bhargava (from Magma BKLC)

Source: `BKLC(GF(4), 24, 7)` in Magma. Verified: d=13, A₁₃=384.

```
1 0 0 0 0 0 0 1 2 0 3 1 3 0 0 3 3 1 3 0 3 1 2 1
0 1 0 0 0 0 0 1 1 2 3 2 2 3 0 3 2 2 2 3 3 2 3 3
0 0 1 0 0 0 0 1 1 1 1 2 1 2 3 3 0 3 1 2 0 2 0 2
0 0 0 1 0 0 0 1 1 1 2 0 1 1 2 0 1 1 0 1 1 1 0 1
0 0 0 0 1 0 0 1 2 1 2 3 3 1 1 1 2 0 2 0 2 0 3 1
0 0 0 0 0 1 0 1 3 2 2 3 0 3 1 2 2 3 3 2 3 3 2 2
0 0 0 0 0 0 1 1 0 3 1 3 0 0 3 2 1 3 0 3 1 2 1 3
```

16,383 codewords enumerated. d = **13** ✓. A₁₃ = **384**.

---

## \[22, 5, 13\]₄ — Round Two Base

Source: Hill-climbing construction, Round Two. Verified: d=13, A₁₃=81.

```
1 0 0 0 0 2 3 2 2 3 3 2 1 0 1 1 3 0 2 0 0 1
0 1 0 0 0 1 2 0 2 1 2 3 0 3 1 2 3 1 0 1 0 2
0 0 1 0 0 3 3 2 2 1 2 3 2 1 3 0 1 3 1 2 1 2
0 0 0 1 0 0 2 0 3 3 3 0 1 2 2 1 0 0 3 2 2 1
0 0 0 0 1 1 3 3 0 1 0 3 1 1 2 2 3 0 0 3 2 1
```

1,023 codewords enumerated. d = **13** ✓. A₁₃ = **81**. Zero-frequency spectrum: Z_i = 255 for all 22 coordinates (variance = 0).

---

## \[22, 6, 12\]₄ — Best Known (Round Three)

Source: Dome-guided SA, Round Three. A₁₂ = **69** (23 projective collision directions).

```
1 0 0 0 0 2 3 2 2 3 3 2 1 0 1 1 3 0 2 0 0 1
0 1 0 0 0 1 2 0 2 1 2 3 0 3 1 2 3 1 0 1 0 2
0 0 1 0 0 3 3 2 2 1 2 3 2 1 3 0 1 3 1 2 1 2
0 0 0 1 0 0 2 0 3 3 3 0 1 2 2 1 0 0 3 2 2 1
0 0 0 0 1 1 3 3 0 1 0 3 1 1 2 2 3 0 0 3 2 1
0 2 0 2 2 1 0 1 1 3 2 2 2 3 3 0 1 1 2 3 1 3
```

4,095 codewords enumerated. d = **12** ✓. A₁₂ = **69**. Collision breakdown: wt14→15, wt15→9, wt16→3, wt17→15, wt18→18, wt19→9.

---

## \[22, 6, 12\]₄ — Round Two Best (for comparison)

Source: La Púa del Jet, V-FINAL-1. A₁₂ = **78** (26 projective collision directions).

```
1 0 0 0 0 2 3 2 2 3 3 2 1 0 1 1 3 0 2 0 0 1
0 1 0 0 0 1 2 0 2 1 2 3 0 3 1 2 3 1 0 1 0 2
0 0 1 0 0 3 3 2 2 1 2 3 2 1 3 0 1 3 1 2 1 2
0 0 0 1 0 0 2 0 3 3 3 0 1 2 2 1 0 0 3 2 2 1
0 0 0 0 1 1 3 3 0 1 0 3 1 1 2 2 3 0 0 3 2 1
1 0 2 0 2 1 2 3 0 0 3 3 0 3 0 2 1 2 3 0 2 2
```

---

## GF(4) Arithmetic Reference

```
Addition (XOR-like):
  0+x = x    1+1 = 0    2+2 = 0    3+3 = 0
  1+2 = 3    1+3 = 2    2+3 = 1

Multiplication:
  0·x = 0    1·x = x
  2·2 = 3    2·3 = 1    3·3 = 2

Inverse: inv(1)=1, inv(2)=3, inv(3)=2
```

---

*Error Code Lab · Round Three · February 2026*
