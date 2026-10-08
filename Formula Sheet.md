---
title: Formula Sheet
course: CSE 221 Algorithms
tags:
  - cse221
  - formulas
---

# Formula Sheet (running)

Add to this after every lecture.

## Growth order of running times (Lecture 01)

$$1 < \log n < n < n\log n < n^2 < n^3 < 2^n$$

![](attachments/diagrams/lecture-01-growth-order.svg)

## Cost measures (Lecture 01)

- Time complexity: how fast the algorithm produces its result (run time)
- Space complexity: how much memory it consumes

## Lecture 02: Time complexity of loops

**Simplifying a count** (in this order):
1. Drop constant terms.
2. Keep only the highest-growth term.
3. Drop constant factors. Never drop a power or an exponent ($\sqrt{n}$ stays, $4^n$ stays).

**Loop patterns** (worst case):

| Loop | Iterations | Complexity |
|---|---|---|
| `i = 0; i < n; i++` | $n$ | $O(n)$ |
| `i = n; i > 0; i--` | $n$ | $O(n)$ |
| `i = 1; i < n; i *= 2` (or `*= 3`) | $\log_2 n$ (or $\log_3 n$) | $O(\log n)$ |
| `i = n; i > 1; i /= 2` (or `/= 3`, `/= 9`) | $\log_2 n$ (or $\log_3 n$, $\log_9 n$) | $O(\log n)$ |
| `i = 1; i * i <= n; i++` | $\sqrt{n}$ | $O(\sqrt{n})$ |

**Solving for the iteration count $k$:**

$$a^k = n \;\Rightarrow\; k = \log_a n \qquad\qquad \frac{n}{a^k} = 1 \;\Rightarrow\; k = \log_a n \qquad\qquad k^2 = n \;\Rightarrow\; k = \sqrt{n}$$

**Combining loops:**
- Sequential (independent) loops: add the counts, then keep the larger term.
- Nested loops: multiply the outer count by the inner count.

**Number series** (inner loop starting at `j = i`):

$$1 + 2 + \dots + n = \frac{n(n+1)}{2} = \frac{n^2}{2} + \frac{n}{2} \;\Rightarrow\; O(n^2)$$

**Growth order:**

$$O(1) < O(\log n) < O(\sqrt{n}) < O(n) < O(n\log n) < O(n^2) < O(2^n)$$

For a logarithmic answer the base may be dropped: write $O(\log n)$. A wrong base is marked wrong.

Related: [INDEX](INDEX.md) | [Course Overview](Course%20Overview.md)

