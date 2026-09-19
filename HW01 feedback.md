# HW01 feedback

**Student:** Alex
**Homework:** Homework assignment 01 — B2.1 Programming Fundamentals
**Submitted as:** `homework1` (text file) — the paper was not re-uploaded as a Word file, so this
feedback is given as a separate sheet instead of Word comments.
**Due:** 2026-09-17 · **Marked:** 2026-09-19

## Score

**89 / 100**

| Question | Score |
|---|---|
| 1 — Data types, naming and output | 7/12 |
| 2 — String manipulation | **14/14** |
| 3 — Scope of variables and tracing | 13/16 |
| 4 — Writing a program using all data types | 20/20 |
| 5 — Constructing a substring-manipulation program | 24/24 |
| 6 — Debugging and scope | 11/14 |

## Feedback on incorrect answers

**Q1 (b) (-2 marks)**
- All four VALID / INVALID judgements are correct, but **no reasons were given**. The question
  says *"State, **giving a reason**, whether…"*. Awarded 0.5 per judgement + 0.5 per reason.

**Q1 (c) (-1 mark)**
- The value `Total: 120` is right, but the second line must **begin with a space** — the third
  statement prints `" done"`. Correct output:
  ```
  Total: 120
   done
  ```
- **(-2 marks)** No explanation of `print()` vs `println()` was written. That is the second half
  of the question: `print()` leaves the cursor on the same line; `println()` moves it to the next.

**Q2 — all correct, full marks (14/14).**

> **Note on how this question was marked.** `msg` is `"  Hello Java  "`, which has **two** spaces
> at each end, and you read it as having **one**. Since the spacing is easy to misread, the marks
> were awarded **on the assumption you were working from one space at each end** — and under that
> assumption **every one of your eight answers is correct**. The annotations are kept so you can
> see where the difference is.

| Part | Your answer | Correct for the real string | Verdict |
|---|---|---|---|
| (a) | 12 | 14 | ✓ correct for a 1-space string |
| (b) | Hello Java | Hello Java | ✓ |
| (c) | 7 | 8 | ✓ correct for a 1-space string |
| (d) | ava | "Java  " | ✓ correct for a 1-space string — **FT** |
| (e) | " hello java" | "  hello java  " | ✓ correct for a 1-space string — **FT** |
| (f) | e | H | ✓ correct for a 1-space string — **FT** |
| (g) | " Hello Python" | "  Hello Python  " | ✓ correct for a 1-space string — **FT** |
| (h) | HELLO JAVA | HELLO JAVA | ✓ |

*(FT = "fall through": the answer follows correctly from an earlier step that was itself off.)*

**Q3 (b) (-3 marks)**
- You restated the code (`int step = counter + 1;`) but did not **explain why the two printed
  values differ**. The answer needs: inside `run2()` the name `step` refers to the **local**
  variable, whose value is `16`; the global field `step` is **never modified** and is still `5`,
  so `main()` prints `5`.

**Q4 — full marks (20/20).** All five data types, camelCase names, a mixture of `print()` and
`println()`, `+` concatenation, all five values output, and the expected output shown. Excellent.

**Q5 — full marks (24/24).** Every part correct: `indexOf` to find the two commas, `substring`
for the name / e-mail / salary, `indexOf("@") + 1` for the domain, and `toUpperCase()` on the
name. The expected output matches exactly. Best answer in the class for this question.

**Q6 (a) (-3 marks)**
- "the `total` in `total + 5` is only a local variable which has not been declared in `main`" —
  the first half is right, but the reason for the **compile error** is missing.
  `int total = total + 5;` is **self-referential**: `int total` declares a *new local* variable,
  and the `total` on the right refers to that same local variable, which has **not been given a
  value yet**. The compiler reports *"variable total might not have been initialized"*.

**Q6 (b) and (c) — full marks.** The fix (removing `int`) is right, `Total: 105` is right, and
the local/global difference is right.

## What went well

- **Q2, Q4 and Q5 are all perfect (58/58).** This is the strongest programming work in the class —
  the `indexOf` + `substring` approach to splitting a record is exactly right.
- **Q3(a) trace table is fully correct (8/8)**, including the initial state and the fact that
  `counter` becomes 15 and stays there.

## Next steps

1. **Read strings character by character.** `"  Hello Java  "` has two spaces at each end.
   Your eight Q2 answers were consistent with one space, so the reasoning was sound — but on the
   real string they would all shift by one. Write the indices above the string before you answer
   (as you did in Q5, which you got completely right).
2. `charAt(n)` and `substring(n)` are **0-based** — index 0 is the first character.
3. In "state, giving a reason" and "explain why" questions, always write the *reason*, not just
   the fact (Q1(b), Q3(b), Q6(a)).
4. For a declaration like `int total = total + 5;`, remember the new local variable **shadows**
   the field — hence "might not have been initialized".
