# Classwork feedback 20260911

**Student:** Alex
**Classwork:** Classwork 01 — B2.1 Programming Fundamentals (variables, data types, substring manipulation)
**Date:** 2026-09-11
**Marked:** 2026-09-14

## Score

**64 / 100**

| Question | Score |
|---|---|
| Q1 — data types, naming, print vs println | 11/12 |
| Q2 — string manipulation (tracing) | 12/14 |
| Q3 — scope of variables + tracing | 8/16 |
| Q4 — debugging and scope | 8/14 |
| Q5 — program using all data types | 9/20 |
| Q6 — substring-manipulation program | 16/24 |

Note: `Classwork01_20260911_marked_p1.png` … `_p3.png` in this folder show every
mark and deduction in place on your script.

## Feedback on incorrect answers

**Q1 (b) (-1 mark)**
- `2ndPlace` and `while` have reasons; `firstPlace` and `studentName` are
  judged VALID but no reason is given (starts with a letter, not a keyword).

**Q2 (f) (-2 marks)**
- You wrote `0`. `indexOf("xyz")` returns **-1** when the substring is not found,
  not `0`. `0` would mean "found at the very first position".

**Q3 (a) (-6 marks)**
- Your `y (global)` column is correct throughout (always `2`) — that is the key
  idea and you have it.
- But the **x (global)** column reads 5 → 5 → 11 → 5 → 5. Once `update()` runs
  `x = x + 3`, x becomes `8` and **never changes again**. There is no step in
  the program that produces `11`.
- There is also an output `Inside update(): 11 10` — `update()` is called only
  **once**, so it can only print that line once.
- The expected values are:
  `x = 5, 8, 8, 8, 8, 8, 8` and
  `y (local) = –, –, 10, 10, 13, 13, –`, with outputs
  `Inside update(): 8 10`, `Inside modify(): 8 13`, `Outside: 8 2`.

**Q3 (b) (-2 marks)**
- You say `y` inside `update()` is a local variable and `y` in `main()` is the
  global variable — correct. What is missing is the second half: the global `y`
  is **never changed**, so it is still `2` when `main()` prints. Say what each
  value *is*, not only that the two variables are different.

**Q4 (a) (-4 marks)**
- "The `score` used in `increaseScore()` is a local variable, which cannot be
  printed in `main()`" — the first half is right, but it is not the reason for
  the compile error. The error is in the declaration itself:
  `int score = score + 10;` is **self-referential** — the `score` on the right
  refers to the local variable being declared, which has no value yet. The
  compiler reports *"variable score might not have been initialized"*.

**Q4 (b) (-2 marks)**
- The rewritten method is correct (`score = score + 10;` — the `int` removed).
  You did not state the output: **`Final score: 10`**.

**Q5 (-11 marks)**
- Only `int age` and `String name` are declared — `double`, `char` and
  `boolean` are missing, so three of the five data types are absent.
- You used `println()` only; the question asks for a **mixture** of `print()`
  and `println()`.
- Only two of the five values are output, and no expected output is shown.

**Q6 (-8 marks)**
- (b) correct approach — `indexOf("M")` then `substring`. Using a hard-coded
  length of `7` works here but is fragile; `indexOf(" ")` would be safer.
- (c) `substring(index2, 7)` is wrong: `index2` is `10` and `7` is smaller, so
  this **throws a StringIndexOutOfBoundsException**. It should be
  `substring(index2)`.
- (a) You never used `trim()`; you rebuilt the name as
  `firstName + " " + surname`, which leaves the trailing spaces in place.
- (d) and (e) are correct.
- (f) was not attempted (`replace("mjackson", "mj")` was the answer).

## What went well

- Q1 (a): all four data types accepted. Your `INTEGER` / `REAL` are valid
  A-Level pseudocode type names, so they count here.
- Q1 (c): both the output *and* the explanation are right — this is one of the
  most commonly missed questions in the class.
- Q2 was strong: 6 of 8 correct.
- Q6 was the best in the class — the overall approach to splitting a string with
  `indexOf` + `substring` is exactly right, and (d) and (e) are clean.

## Next steps

1. `indexOf` returns an **int index**; **-1** means "not found" (it never returns 0 for a miss).
2. A variable assigned once keeps that value — re-check every line of a trace
   table and ask "does this line actually change x?"
3. Give the *reason* for each judgement in "state, giving a reason" questions.
4. For a declaration like `int score = score + 10;`, remember the local
   variable **shadows** the field — hence "might not have been initialized".

---
_Marks and margin notes are also marked up on your scanned script
(`Classwork01_20260911_marked_p1.png` … `_p3.png`)._
