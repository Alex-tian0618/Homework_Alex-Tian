# Classwork feedback 20261106

**Student:** Alex
**Classwork:** Classwork 20261106 — B2.2 Data structures
(arrays · pass-by-reference)
**Date:** 2026-11-06 · **Marked:** 2026-11-06
**Answer language:** written in A-Level pseudocode — accepted (full credit for correct content).

## Score

**82 / 100**

| Question | Score |
|---|---|
| Q1 — Reading arrays | 26/30 |
| Q2 — Writing array methods and a complete program | 17/30 |
| Q3 Part B — Pass-by-reference | 39/40 |

Full marked pages: `Classwork20261106_marked_p1..p4.png`

## Feedback on incorrect answers

**Q1(b) — 8/10**
- The trace table is correct. The output is **8 21**: `a[1] = 8` and `a[3] = 21`, not 6 8.

**Q1(d) — 2/4**
- You give the fix (`nums[i]`) but not the reason. The enhanced-for variable `v` is a **copy** of each element, so `v = v * 2` cannot change the array.

**Q2(a) — 7/10**
- `i` **is** initialised before the loop — credited.
- The function header has **no parameter list**: it must take `Data : ARRAY[...] OF INTEGER`.
- `i <- i + 1` is **inside the IF**: the first odd value makes the loop infinite. Move the increment after `ENDIF`.

**Q2(b) — 10/20**
- There is **no deduction for not writing `average` itself** — the call is what matters.
- But the call `DoubleAverage(T : ARRAY[...] OF INTEGER)` has invalid syntax, the result is never stored (`Avg` stays 0), and the loop therefore compares with 0. The reading loop is correct.

**Q3(d) — 9/10**
- The colon is there, but it is very faint and cramped — write `BYREF X : INTEGER` clearly. The swap body and the output 9 5 are correct.

## What went well

- **Q1(a) — full marks.** All five values correct.
- **Q1(c) — 6/6.** Runtime error, bounds and the stop are all correct.
- **Q3 — 39/40.** Trace, BYREF explanation and Replace are correct; only the faint colon in Swap costs a mark.

## Next steps

- Check every function header: name, **parameter list with types**, return type.
- Put the loop counter update **outside** the IF, so every iteration advances.
- Store the result of a call in a variable before using it; write the call with just the array name.
