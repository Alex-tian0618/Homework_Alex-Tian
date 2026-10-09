# Classwork feedback 20261009

**Student:** Alex
**Classwork:** Classwork 20261009 — B2.3 Programming Constructs
(functions · selection · repetition · library functions incl. `Random`)
**Date:** 2026-10-09 · **Marked:** 2026-10-09
**Answer language:** A-Level pseudocode — accepted throughout.

## Score

**72 / 100**

| Question | Score |
|---|---|
| Q1 — Reading functions and loops | 25/30 |
| Q2 — Library functions: the `Random` class | 21/30 |
| Q3 — Writing a complete program (Collatz) | 26/40 |

Full marked pages: `Classwork20261009_marked_AS_20261009_Alex_p1..p3.png`

## Feedback on incorrect answers

**Q1 (d) — 1/6**
- The question asks for the difference between a method that returns **`void`** and one that
  returns a **value**. You compared `area()` with `label()` — but both of those return a value.
  The `void` method in this paper is **`countUp(int n)`** in part (b): it hands nothing back, it
  only prints.
- A value-returning method sends a value back to the caller, which can be stored, printed or used
  in a calculation. A `void` method cannot — writing `System.out.println(countUp(4));` would be
  an error.

**Q2 (a) (iii) — 1/2**
- Identifying that the loop runs four times is right. The other half of the mark is that
  `nextInt()` produces a **new** pseudo-random value on **every call** — that is why four numbers
  appear rather than the same number four times.

**Q2 (a) (iv) — 3/4**
- You named two real benefits ("reduce the lines of code", "decrease the potential mistakes"),
  which is close. Slide 38 names them as **reuse of code** and **improve reliability** — use those
  words in the exam.
- The link back to `Random` is only half made: say explicitly that calling `rnd.nextInt(6)`
  replaces a random-number generator you would otherwise have had to write and test yourself.

**Q2 (b) (i) — 4/5**
- The class already declares `static Random rnd = new Random();`. Use that object:
  `RETURN rnd.nextInt(6) + 1`.
- `Random(1..6)` is not A-Level pseudocode and ignores the object you were given.

**Q2 (c) (i) — 1/3**
- `nextDouble()` returns a `REAL` in **0.0 ≤ x < 1.0**. You wrote "0 to 2".
- "Circle" is correct, but add the detail: a circle of **radius 0.5 centred at (0.5, 0.5)** —
  which is why the test uses 0.25 (that is r²).

**Q2 (c) (ii) — 2/4**
- Good: `cnt / N` is the chance that a point lands inside the circle.
- But the square's area is **1**, not 4. The circle's area is `πr² = π × 0.5² = 0.25π`.
  So `cnt / N ≈ 0.25π`, and multiplying by 4 recovers π.

**Q2 (c) (iii) — 1/3**
- The reason is **integer division**, not "Pi is a double". `cnt` and `N` are both `int`, so
  `4 * cnt / N` is worked out in whole numbers and the fraction is discarded. Writing `4.0`
  makes the whole expression use `double` arithmetic.

**Q3 (b) — 8/10**
- It happens to return 8 for n = 6, but the structure is fragile: `RETURN Count + 1` is a fudge,
  and the function returns **3** for n = 1 (it should return 0).
- The clean, exam-standard form is a pre-condition loop:
  `Count <- 0` / `WHILE n <> 1` / `n <- NextTerm(n)` / `Count <- Count + 1` / `ENDWHILE` /
  `RETURN Count`.

**Q3 (c) — 5/6**
- Good answer. Add the other half of the idea: a `for` loop needs its repetition count to be
  **known before the loop starts**, and here that count cannot be known until the sequence runs.

**Q3 (d) — 5/16**
- Three separate faults:
  1. You output `NextTerm(n)`, so the sequence is missing its **first** term — the output starts
     at 3, not 6. Output `n` and then advance, or output `n` before the update.
  2. The loop destroys `n`, so `Steps(n)` is called on the value 1 and returns 1. Keep the user's
     number in a second variable (e.g. `start`) and call `Steps(start)`.
  3. The required label is `Steps: <count>` — you output the bare number.
- Also your expected output for 7 is wrong: `steps(7)` is **16**, not 11.

## What went well

- **Q1 (a), (b), (c)** — all three outputs exact, all 24 marks.
- **Q2 (a) (i), (ii)** and **Q3 (a)** — perfect.
- **Q2 (b) (ii)** — calling `Roll()` inside a `FOR` loop and joining with `& " "` is exactly right.
- **Q3 (c)** — the reasoning about an unknown number of repetitions is sound.

## Next steps

1. **Read the question's examples before answering.** In Q1 (d) the phrase *"an example of each
   **from this question**"* was the clue that `void` was in play — and the `void` method is the one
   in part (b). Two questions this paper lost marks purely to misreading (Q1(d)) or to naming a
   different part of the syllabus (Q2(a)(iv) → slide 35 instead of slide 38).
2. **Integer division is a favourite exam trap.** Whenever an expression mixes a literal with
   `int` variables and the answer must be a fraction, at least one operand must be `double`.
3. **Always keep the original input.** In Q3 (d) the moment you overwrite `n` you can no longer
   call any function that needs the starting value. Save it first.
