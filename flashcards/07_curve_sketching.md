+++
order = 7
subject = "mathematics"
tags = ["math", "calculus", "curve-sketching", "monotonicity", "concavity", "inflection", "asymptotes"]
+++

# Calculus — Curve Sketching

## 7.1 What Curve Sketching Achieves

Q: Why bother with curve sketching when graphing software is universally available?
A: Sketching forces you to read a function's structure analytically — domain, critical points, concavity, asymptotes — rather than trusting a pixelated output. It trains the mental link between a formula and its shape, exposes features a grapher might hide (removable singularities, narrow extrema, slow asymptotic behavior), and is essential when you must predict behavior symbolically in proofs, optimization, or applied modeling.

Q: What qualitative features define the "shape" of a graph that sketching aims to capture?
A: The domain, intercepts with the axes, symmetry, intervals of increase/decrease, local and global extrema, intervals of concavity, inflection points, and the behavior near discontinuities and at infinity (asymptotes). Together these determine the graph up to minor scaling.

C: Curve sketching aims at [qualitative] understanding of a function's graph, producing a picture that is correct in shape even if not in exact scale.

## 7.2 First Derivative Test — Sign of $f'$

Q: What does the sign of $f'(x)$ tell you about $f$ at a single point?
A: It tells you the instantaneous direction of $f$ at that point: $f'(x) > 0$ means $f$ is momentarily increasing (tangent slopes up), $f'(x) < 0$ means momentarily decreasing, and $f'(x) = 0$ means the tangent is horizontal — a candidate for a local extremum or a flat spot.

Q: Why do we study the sign of $f'$ on intervals rather than just at isolated points?
A: Monotonicity is an interval property: knowing $f'(c) > 0$ at one point does not guarantee $f$ is increasing on a neighborhood unless $f'$ stays positive throughout. Sign analysis on intervals, obtained from critical points, produces statements like "$f$ is increasing on $(a,b)$" that are needed for a sketch.

C: The [first derivative test] uses the sign of $f'$ on each interval between critical points to determine where $f$ is increasing or decreasing.

## 7.3 Monotonicity from the Sign of $f'$

Q: Why does $f' > 0$ on an interval $(a,b)$ imply $f$ is increasing there?
A: Pick any $x_1 < x_2$ in $(a,b)$. By the Mean Value Theorem there exists $c \in (x_1, x_2)$ with $f(x_2) - f(x_1) = f'(c)(x_2 - x_1)$. Since $f'(c) > 0$ and $x_2 - x_1 > 0$, the right side is positive, so $f(x_2) > f(x_1)$. Thus $f$ is strictly increasing.

C: If $f'(x) < 0$ for all $x$ in an open interval, then $f$ is [decreasing] on that interval (by the Mean Value Theorem).

Q: Can a function be increasing on an interval even if $f'(x) = 0$ at some points inside it?
A: Yes. For example $f(x) = x^3$ has $f'(0) = 0$, yet $f$ is strictly increasing on all of $\mathbb{R}$ because $f'(x) = 3x^2 \geq 0$ with equality only at the isolated point $x = 0$. Monotonicity requires $f' \geq 0$ with $f'$ not identically zero on any subinterval.

## 7.4 Classifying Critical Points via First Derivative Test

C: A [critical point] of $f$ is a point $c$ in the domain where $f'(c) = 0$ or $f'(c)$ does not exist.

Q: How does the sign change of $f'$ at a critical point $c$ classify it?
A: If $f'$ changes from $+$ to $-$ at $c$, then $f$ was rising and starts falling, so $c$ is a local maximum. If $f'$ changes from $-$ to $+$, $c$ is a local minimum. If $f'$ does not change sign (e.g., $+$ to $+$ or $-$ to $-$), $c$ is neither — it is a horizontal inflection or saddle-like point.

Q: Why is the first derivative test more general than the second derivative test?
A: The first derivative test only needs $f'$ to exist in a neighborhood of $c$ and change sign; it works even when $f''(c)$ is zero, undefined, or hard to compute. The second derivative test fails or is inconclusive in exactly those cases, but the first derivative test still delivers a classification.

## 7.5 Second Derivative Test

C: The [second derivative test] says that if $f'(c) = 0$ and $f''(c) > 0$, then $c$ is a local minimum of $f$.

Q: Why does $f'(c) = 0$ together with $f''(c) > 0$ imply a local minimum at $c$?
A: $f''(c) > 0$ means $f'$ is increasing near $c$. Combined with $f'(c) = 0$, this forces $f' < 0$ just left of $c$ and $f' > 0$ just right of $c$. By the first derivative test, $f$ decreases into $c$ and increases away, so $c$ is a local minimum.

Q: When is the second derivative test inconclusive, and what should you do?
A: When $f'(c) = 0$ and $f''(c) = 0$ (or $f''(c)$ does not exist), the test gives no information — the point could be a max, min, or inflection. Fall back to the first derivative test: examine the sign of $f'$ on either side of $c$.

## 7.6 Concavity

C: A function is [concave up] on an interval if $f''(x) > 0$ there; graphically the curve opens upward like a cup.

C: A function is [concave down] on an interval if $f''(x) < 0$ there; graphically the curve opens downward like a cap.

Q: What geometric property of the graph does concavity capture beyond monotonicity?
A: Monotonicity tells you whether the curve is going up or down; concavity tells you how the curve bends. A concave-up curve lies above its tangent lines (cup shape); a concave-down curve lies below its tangent lines (cap shape). The graph can be increasing while being concave up (accelerating) or concave down (decelerating).

## 7.7 Why Concavity Reflects the Rate of Change of Slope

Q: Why does $f'' > 0$ correspond to an upward-opening curve?
A: $f''$ is the derivative of $f'$, so $f'' > 0$ means the slope $f'$ is increasing. An increasing slope — going from negative to less negative to positive to more positive — bends the graph upward, producing the characteristic cup shape of concave-up curves.

Q: If $f$ is increasing and concave down, what is happening to the rate of growth?
A: $f$ is still rising ($f' > 0$), but the slope is decreasing ($f'' < 0$), so growth is decelerating. The curve rises but flattens, like $\sqrt{x}$ for $x > 0$ or $\ln(x)$ — eventually growth slows even though $f$ keeps increasing.

## 7.8 Inflection Points

C: An [inflection point] of $f$ is a point where the concavity of $f$ changes (from concave up to concave down, or vice versa).

Q: Why is a sign change in $f''$ required for an inflection point, not just $f'' = 0$?
A: Concavity is defined by the sign of $f''$, so an inflection is a place where that sign flips. The condition $f''(c) = 0$ is only necessary — $f(x) = x^4$ has $f''(0) = 0$ but $f''(x) \geq 0$ everywhere, so $0$ is not an inflection. Without a genuine sign change, the graph does not change its bending direction.

## 7.9 Finding Candidate Inflection Points

Q: What is the procedure for locating inflection points of $f$?
A: First, find all $x$ in the domain where $f''(x) = 0$ or $f''(x)$ is undefined — these are the candidates. Then test the sign of $f''$ on each side of each candidate: if the sign changes, it is an inflection point; if it stays the same, it is not.

P: Find all inflection points of $f(x) = x^4 - 4x^3$.

S:
**IDENTIFY**: Inflection-point search requires second-derivative sign analysis on a polynomial.

**PLAN**:
- Compute $f''$.
- Solve $f''(x) = 0$ to get candidates.
- Check whether $f''$ changes sign at each candidate.

**EXECUTE**:
1. $f'(x) = 4x^3 - 12x^2$.
2. $f''(x) = 12x^2 - 24x = 12x(x - 2)$.
3. Candidates: $x = 0$ and $x = 2$.
4. Sign of $f''$: for $x < 0$, $f'' > 0$ (up); for $0 < x < 2$, $f'' < 0$ (down); for $x > 2$, $f'' > 0$ (up).
5. Both $x = 0$ and $x = 2$ show sign changes, so both are inflection points.

**EVALUATE**: At $x = 0$, concavity flips up→down; at $x = 2$, down→up. Points: $(0, 0)$ and $(2, -16)$.

## 7.10 Relationships Between $f$, $f'$, $f''$

Q: How do the graphs of $f$, $f'$, and $f''$ relate graphically?
A: Zeros of $f'$ are horizontal tangents of $f$ (candidate extrema). Zeros of $f''$ are candidate inflection points of $f$, and also critical points of $f'$. Where $f' > 0$, $f$ rises; where $f'' > 0$, both $f$ is concave up and $f'$ is increasing. Reading the sign and zero patterns of $f''$ and $f'$ reconstructs the shape of $f$.

Q: If you see a local maximum on the graph of $f'$, what feature does that correspond to on the graph of $f$?
A: A local maximum of $f'$ is where $f''$ changes from positive to negative, which is an inflection point of $f$ where concavity switches from up to down. It is also the point where $f$ is rising fastest (if $f' > 0$ there) before its slope begins to decrease.

## 7.11 Vertical Asymptotes

C: A [vertical asymptote] of $f$ at $x = a$ occurs when $\lim_{x \to a^{\pm}} f(x) = \pm\infty$, where $a$ is typically a point where the denominator vanishes but the numerator does not.

Q: Why does a zero of the denominator not always produce a vertical asymptote?
A: If the numerator also vanishes at the same point with at least equal multiplicity, the factor cancels and the apparent singularity is removable — the limit is finite. For example, $\frac{x^2 - 1}{x - 1} = x + 1$ for $x \neq 1$, so $x = 1$ is a hole, not an asymptote. You need the numerator to stay nonzero while the denominator goes to zero.

## 7.12 Horizontal Asymptotes

C: A [horizontal asymptote] of $f$ is a line $y = L$ such that $\lim_{x \to \infty} f(x) = L$ or $\lim_{x \to -\infty} f(x) = L$.

Q: For a rational function $f(x) = \frac{p(x)}{q(x)}$, how does comparing degrees determine the horizontal asymptote?
A: Let $n = \deg p$, $m = \deg q$. If $n < m$, then $y = 0$ is the horizontal asymptote. If $n = m$, the horizontal asymptote is $y = \frac{a_n}{b_m}$, the ratio of leading coefficients. If $n > m$, there is no horizontal asymptote (the function grows without bound).

## 7.13 Slant (Oblique) Asymptotes

Q: When does a rational function $f(x) = \frac{p(x)}{q(x)}$ have a slant asymptote instead of a horizontal one?
A: Exactly when $\deg p = \deg q + 1$. Polynomial long division gives $f(x) = (mx + b) + \frac{r(x)}{q(x)}$, where $\deg r < \deg q$, so the remainder term vanishes as $x \to \pm\infty$. The line $y = mx + b$ is the slant (oblique) asymptote.

C: For a rational function with numerator degree [one more than] denominator degree, polynomial division yields a slant asymptote.

P: Find the slant asymptote of $f(x) = \frac{x^2 + 1}{x - 1}$.

S:
**IDENTIFY**: Degree of numerator (2) exceeds degree of denominator (1) by 1 → slant asymptote exists.

**PLAN**: Perform polynomial long division of $x^2 + 1$ by $x - 1$.

**EXECUTE**:
1. $x^2 \div x = x$; multiply back: $x(x - 1) = x^2 - x$; subtract: $(x^2 + 1) - (x^2 - x) = x + 1$.
2. $x \div x = 1$; multiply back: $1 \cdot (x - 1) = x - 1$; subtract: $(x + 1) - (x - 1) = 2$.
3. So $f(x) = x + 1 + \frac{2}{x - 1}$.
4. As $x \to \pm\infty$, $\frac{2}{x - 1} \to 0$.

**EVALUATE**: The slant asymptote is $y = x + 1$. The curve approaches this line from above as $x \to \infty$ (since $\frac{2}{x-1} > 0$) and from below as $x \to -\infty$.

## 7.14 Symmetry and Periodicity

C: A function is [even] if $f(-x) = f(x)$ for all $x$ in the domain; its graph is symmetric about the $y$-axis.

C: A function is [odd] if $f(-x) = -f(x)$ for all $x$ in the domain; its graph is symmetric about the origin.

Q: Why is checking symmetry early useful in a sketching routine?
A: If $f$ is even, you only need to analyze $x \geq 0$ and reflect across the $y$-axis; if odd, you analyze $x \geq 0$ and rotate $180^\circ$ about the origin. Periodic functions need only be sketched on one period. This halves or fractions the work and prevents inconsistent sketches on either side.

C: A function is [periodic] with period $T$ if $f(x + T) = f(x)$ for all $x$, and $T > 0$ is the smallest such value.

## 7.15 Full Sketching Procedure

P: Outline a systematic procedure for sketching the graph of a general function $f(x)$.

S:
**IDENTIFY**: Full curve-sketching task — need structural plus local-behavior information.

**PLAN**: Combine domain, symmetry, asymptotes, and derivative analysis in a fixed order so nothing is missed.

**EXECUTE**:
1. **Domain**: determine where $f$ is defined; exclude division by zero, negative radicands, log arguments $\leq 0$, etc.
2. **Intercepts**: compute $f(0)$ and solve $f(x) = 0$.
3. **Symmetry/periodicity**: test even/odd; check for periodicity.
4. **Asymptotes**: vertical (from domain gaps), horizontal (from $\lim_{x \to \pm\infty}$), slant (rational, degree difference 1).
5. **First derivative**: compute $f'$, find critical points, build a sign chart for monotonicity, classify extrema.
6. **Second derivative**: compute $f''$, find candidate inflections, build a sign chart for concavity.
7. **Synthesis**: combine all information and sketch.

**EVALUATE**: Cross-check: the sketch must respect every constraint — domain, asymptotes, increase/decrease, concavity, and computed point values.

## 7.16 Reading Off Features from a Sign Chart

Q: How do you read a combined sign chart of $f'$ and $f''$ to describe the graph shape on an interval?
A: Four cases arise. $f' > 0, f'' > 0$: increasing and concave up (curve rising and accelerating, cup shape). $f' > 0, f'' < 0$: increasing and concave down (rising but flattening, cap shape). $f' < 0, f'' > 0$: decreasing and concave up (falling but decelerating). $f' < 0, f'' < 0$: decreasing and concave down (falling and accelerating downward).

C: On a combined sign chart, the boundary points are [critical points] of $f$ (zeros or undefined points of $f'$) and candidate inflection points (zeros or undefined points of $f''$).

## 7.17 Sketching $f(x) = x^3 - 3x^2 + 2$

P: Sketch $f(x) = x^3 - 3x^2 + 2$: find critical points, inflection, and intervals of monotonicity and concavity.

S:
**IDENTIFY**: Cubic polynomial — smooth, defined on $\mathbb{R}$, no asymptotes. Need $f'$ and $f''$ analysis.

**PLAN**:
- Compute $f'$, $f''$; find zeros; build sign charts.
- Evaluate $f$ at critical and inflection points for coordinates.

**EXECUTE**:
1. Domain: all of $\mathbb{R}$. Symmetry: neither even nor odd. No asymptotes (polynomial).
2. $f'(x) = 3x^2 - 6x = 3x(x - 2)$. Critical points: $x = 0, 2$.
3. Sign of $f'$: $x < 0$: $+$ (increasing); $0 < x < 2$: $-$ (decreasing); $x > 2$: $+$ (increasing).
4. Classify: at $x = 0$, $f'$ flips $+ \to -$ → local max, $f(0) = 2$. At $x = 2$, $- \to +$ → local min, $f(2) = 8 - 12 + 2 = -2$.
5. $f''(x) = 6x - 6 = 6(x - 1)$. Candidate inflection: $x = 1$.
6. Sign of $f''$: $x < 1$: concave down; $x > 1$: concave up. Inflection at $(1, 1 - 3 + 2) = (1, 0)$.
7. End behavior: $f \to -\infty$ as $x \to -\infty$, $f \to +\infty$ as $x \to +\infty$ (odd-degree leading term $x^3$).

**EVALUATE**: Sketch passes through local max $(0, 2)$, inflection $(1, 0)$, local min $(2, -2)$. Concave down on $(-\infty, 1)$, concave up on $(1, \infty)$. Increasing on $(-\infty, 0) \cup (2, \infty)$, decreasing on $(0, 2)$. Shape matches a standard cubic with two turning points.

## 7.18 Sketching $f(x) = \dfrac{x^2}{x^2 - 1}$

P: Sketch $f(x) = \dfrac{x^2}{x^2 - 1}$, including asymptotes and extrema.

S:
**IDENTIFY**: Rational function; denominator zeros produce possible vertical asymptotes; equal-degree numerator and denominator give a horizontal asymptote.

**PLAN**:
- Domain, symmetry, asymptotes first.
- Then $f'$ for extrema, $f''$ for concavity.

**EXECUTE**:
1. Domain: $x^2 - 1 \neq 0 \Rightarrow x \neq \pm 1$.
2. Symmetry: $f(-x) = \frac{(-x)^2}{(-x)^2 - 1} = f(x)$ → even, symmetric about $y$-axis.
3. Intercepts: $f(0) = 0$; $f(x) = 0 \iff x = 0$.
4. Vertical asymptotes: $x = \pm 1$. As $x \to 1^-$: $x^2 \to 1$, $x^2 - 1 \to 0^-$, so $f \to -\infty$. As $x \to 1^+$: denominator $\to 0^+$, $f \to +\infty$. By symmetry, analogous at $x = -1$.
5. Horizontal asymptote: degrees equal; leading coefficients $1/1 = 1$, so $y = 1$.
6. $f'(x)$: by quotient rule with $u = x^2$, $v = x^2 - 1$, $u' = 2x$, $v' = 2x$:
$$f'(x) = \frac{2x(x^2 - 1) - x^2(2x)}{(x^2 - 1)^2} = \frac{-2x}{(x^2 - 1)^2}.$$
7. $f'(x) = 0 \iff x = 0$. Sign: denominator positive everywhere in the domain, so $f'$ has the sign of $-2x$. $x < 0$ (excluding $-1$): $f' > 0$ (increasing); $x > 0$ (excluding $1$): $f' < 0$ (decreasing).
8. At $x = 0$: $f'$ flips $+ \to -$ → local maximum, $f(0) = 0$.
9. Concavity: computing $f''$ and checking sign (or noting behavior): $f'' > 0$ on $(-\infty, -1) \cup (1, \infty)$ (concave up, curve approaches $y = 1$ from above), $f'' < 0$ on $(-1, 1)$ (concave down, peak at origin). No inflection points in the domain (candidates occur only at excluded $x = \pm 1$).

**EVALUATE**: Graph has a local max at $(0, 0)$, vertical asymptotes at $x = \pm 1$, horizontal asymptote $y = 1$. On $(-\infty, -1)$ and $(1, \infty)$ the curve sits above $y = 1$ and approaches it; on $(-1, 1)$ the curve dips from $+\infty$ near $x = -1^+$, through the peak $(0, 0)$ — wait: recheck. As $x \to -1^+$, denominator $\to 0^-$ (since $x^2 - 1 < 0$ for $|x| < 1$), numerator $\to 1 > 0$, so $f \to -\infty$. As $x \to 1^-$, similarly $f \to -\infty$. So on $(-1, 1)$, $f$ rises from $-\infty$ to $0$ at $x = 0$ and falls back to $-\infty$, consistent with a local max at $(0,0)$ and concave-down middle branch. Symmetry about the $y$-axis confirms the two outer branches mirror each other.
