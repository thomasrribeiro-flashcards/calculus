+++
order = 10
subject = "mathematics"
tags = ["math", "calculus", "definite-integral", "riemann-sum", "fundamental-theorem", "ftc"]
+++

# Calculus — The Definite Integral and the Fundamental Theorem

## 10.1 Motivating Problem: Area Under a Curve

Q: Why is computing the area under a curve $y = f(x)$ on $[a, b]$ a non-trivial problem?
A: Unlike a rectangle or triangle, a curve has no fixed base and height, so elementary area formulas do not apply. The region's top edge changes continuously, so we need a way to approximate it with known shapes (rectangles) and then take a limit as the approximation is refined.

Q: Before defining the definite integral, predict: how could you estimate the area under $y = x^2$ from $0$ to $1$ using only rectangles?
A: Slice $[0, 1]$ into $n$ equal subintervals, build a rectangle over each using the function value at some point in the subinterval as the height, and sum their areas. Letting $n \to \infty$ should squeeze the approximation to the true area.

C: The central problem that motivates the definite integral is finding the [signed area] between the graph of $f$ and the $x$-axis on an interval $\lbrack a, b\rbrack $.

Q: Why is area a useful model even for integrals of non-geometric quantities (like velocity over time)?
A: Because integration accumulates the product $f(x)\,dx$ over an interval, any quantity that is a rate times a variable (velocity × time, force × distance, density × length) can be interpreted geometrically as "area under the rate curve," giving the total accumulated quantity.

## 10.2 Approximating Area with Rectangles

C: In a [left Riemann sum], each rectangle's height is $f$ evaluated at the left endpoint of its subinterval.

C: In a [right Riemann sum], each rectangle's height is $f$ evaluated at the right endpoint of its subinterval.

C: In a [midpoint Riemann sum], each rectangle's height is $f$ evaluated at the midpoint of its subinterval.

Q: Why does the midpoint rule typically give a better area estimate than left or right sums for a smooth function?
A: Midpoint evaluation balances the over- and under-estimation that left/right endpoints produce on curved regions. For functions with moderate curvature, the errors above and below the true curve partially cancel, giving smaller total error than endpoint rules.

Q: For an increasing function $f$ on $[a, b]$, how do the left and right Riemann sums compare to the true area?
A: The left sum underestimates (each rectangle sits below the curve) and the right sum overestimates (each rectangle rises above the curve). The true area is squeezed between them.

## 10.3 Partitions

C: A [partition] of $\lbrack a, b\rbrack $ is a finite set $P = \{x_0, x_1, \dots, x_n\}$ with $a = x_0 < x_1 < \cdots < x_n = b$, dividing $\lbrack a, b\rbrack $ into $n$ subintervals.

C: The width of the $i$-th subinterval of a partition is $\Delta x_i = [x_i - x_{i-1}]$, where $x_i$ and $x_{i-1}$ are its right and left endpoints.

C: The [norm] (or mesh) of a partition $P$ is $\|P\| = \max_i \Delta x_i$, the width of its widest subinterval.

Q: Why do we measure the "fineness" of a partition by its norm $\|P\|$ rather than by $n$, the number of subintervals?
A: With unequal widths, a partition can have many subintervals yet still contain one very wide one that poorly approximates area. Sending $\|P\| \to 0$ forces every subinterval (not just the average) to shrink, which is what we need for a well-defined limit.

Q: What does it mean for a partition to be "regular" (uniform)?
A: All subintervals have equal width $\Delta x = (b - a)/n$. Then $\|P\| = \Delta x$, and taking $n \to \infty$ is equivalent to taking $\|P\| \to 0$.

## 10.4 Riemann Sums

C: A [Riemann sum] for $f$ over a partition $P$ of $\lbrack a, b\rbrack $ with sample points $x_i^* \in \lbrack x_{i-1}, x_i\rbrack $ is $\sum_{i=1}^n f(x_i^*)\,\Delta x_i$, where $\Delta x_i = x_i - x_{i-1}$.

Q: In the Riemann sum $\sum_{i=1}^n f(x_i^*)\,\Delta x_i$, what do $f(x_i^*)$ and $\Delta x_i$ represent geometrically?
A: $f(x_i^*)$ is the signed height of the $i$-th rectangle (positive above the $x$-axis, negative below), and $\Delta x_i$ is its base width. Their product is the signed area of one rectangle; the sum is the total signed area of the approximation.

Q: Why can the sample point $x_i^*$ be chosen anywhere in $[x_{i-1}, x_i]$?
A: For an integrable function, the choice does not affect the limit as $\|P\| \to 0$. Every sample choice (left, right, midpoint, or otherwise) is squeezed to the same value, which is exactly what makes the definite integral well-defined.

## 10.5 Definite Integral as Limit

C: The [definite integral] of $f$ from $a$ to $b$ is $\int_a^b f(x)\,dx = \lim_{\|P\|\to 0}\sum_{i=1}^n f(x_i^*)\,\Delta x_i$, where $P$ is a partition of $\lbrack a, b\rbrack $, $\Delta x_i$ its subinterval widths, and $x_i^* \in \lbrack x_{i-1}, x_i\rbrack $ a sample point.

Q: In the notation $\int_a^b f(x)\,dx$, what do the symbols $\int$, $a$, $b$, $f(x)$, and $dx$ encode?
A: $\int$ is a stylized "S" for sum, $a$ and $b$ are the lower and upper limits of integration, $f(x)$ is the integrand (the function being integrated), and $dx$ indicates the variable of integration and represents the infinitesimal width $\Delta x_i$ in the limit.

Q: Why is the definite integral a number, while an indefinite integral (antiderivative) is a family of functions?
A: The definite integral $\int_a^b f(x)\,dx$ has fixed numeric limits, so the limit of Riemann sums yields a single real number. The indefinite integral $\int f(x)\,dx = F(x) + C$ has no limits, leaving $x$ free and a family of antiderivatives parameterized by the constant $C$.

C: The variable $x$ in $\int_a^b f(x)\,dx$ is called a [dummy variable] because replacing it by any other symbol, e.g. $\int_a^b f(t)\,dt$, gives the same number.

## 10.6 When Is $f$ Riemann Integrable?

C: Every [continuous] function on a closed bounded interval $\lbrack a, b\rbrack $ is Riemann integrable.

C: A function that is [bounded] on $\lbrack a, b\rbrack $ and has only finitely many discontinuities there is Riemann integrable.

Q: Why does continuity on $[a, b]$ guarantee integrability?
A: A continuous function on a closed, bounded interval is uniformly continuous and bounded. This ensures that upper and lower Riemann sums converge to the same limit as $\|P\| \to 0$, so the defining limit of Riemann sums exists and is unique.

Q: Give an example of a non-integrable bounded function on $[0, 1]$ and explain why.
A: The Dirichlet function $f(x) = 1$ if $x$ is rational, $0$ otherwise. On every subinterval, $\sup f = 1$ and $\inf f = 0$, so upper sums always equal $1$ and lower sums always equal $0$. They never converge to a common value, so $f$ is not Riemann integrable.

C: A [piecewise-continuous] function on $\lbrack a, b\rbrack $ (continuous except at finitely many jumps) is Riemann integrable.

## 10.7 Geometric Interpretation: Signed Area

Q: What does "signed area" mean for $\int_a^b f(x)\,dx$?
A: Regions where $f(x) > 0$ contribute positive area (above the $x$-axis), and regions where $f(x) < 0$ contribute negative area (below the $x$-axis). The definite integral is the net area: area above minus area below.

Q: Why is $\int_{-1}^{1} x\,dx = 0$ even though the graph encloses nonzero area with the $x$-axis?
A: The region from $-1$ to $0$ lies below the axis (negative signed area) and is the mirror image of the region from $0$ to $1$ above the axis (positive signed area). The two signed areas cancel exactly, giving net zero.

C: The geometric [total area] between the graph of $f$ and the $x$-axis on $\lbrack a, b\rbrack $ is $\int_a^b |f(x)|\,dx$, which is always non-negative.

Q: How do signed area and total area differ for $f(x) = \sin x$ on $[0, 2\pi]$?
A: Signed area: $\int_0^{2\pi} \sin x\,dx = 0$ because the positive half over $[0, \pi]$ cancels the negative half over $[\pi, 2\pi]$. Total area: $\int_0^{2\pi}|\sin x|\,dx = 4$, counting both bumps positively.

## 10.8 Linearity

C: Linearity of the definite integral: $\int_a^b [c\,f(x) + d\,g(x)]\,dx = c\int_a^b f(x)\,dx + d\int_a^b g(x)\,dx$, for constants $c, d$ and integrable $f, g$.

Q: Why is linearity of the integral a consequence of the definition as a limit of Riemann sums?
A: Each Riemann sum $\sum [c\,f(x_i^*) + d\,g(x_i^*)]\Delta x_i$ splits as $c\sum f(x_i^*)\Delta x_i + d\sum g(x_i^*)\Delta x_i$ by ordinary sum linearity. Limits preserve finite linear combinations, so the property carries to the integral.

Q: Why is there no analogous "product rule" like $\int fg = \int f \cdot \int g$?
A: Riemann sums do not distribute over products: $\sum f(x_i^*)g(x_i^*)\Delta x_i$ is not the product of $\sum f\,\Delta x$ and $\sum g\,\Delta x$. Integration of products requires techniques like integration by parts, derived from the product rule for derivatives.

## 10.9 Additivity Over Intervals

C: Additivity: if $a \le b \le c$ and $f$ is integrable on $[a, c]$, then $\int_a^c f(x)\,dx = [\int_a^b f(x)\,dx + \int_b^c f(x)\,dx]$.

Q: Why does additivity $\int_a^c = \int_a^b + \int_b^c$ make sense geometrically?
A: The signed area between $x = a$ and $x = c$ is the union of the signed areas on $[a, b]$ and $[b, c]$, which meet only at $x = b$ (a set of zero area). So the total area decomposes cleanly into the sum of the pieces.

Q: How does additivity let you integrate piecewise-defined functions?
A: Split the interval at each breakpoint of the definition. Integrate each piece using its own formula, then sum the results. This is exactly how you handle $\int_{-1}^{2} f$ when $f$ is defined differently on $[-1, 0]$ and $[0, 2]$.

## 10.10 Reversing the Limits of Integration

C: Reversing limits: $\int_a^b f(x)\,dx = [-\int_b^a f(x)\,dx]$, where $a$ and $b$ are the original lower and upper limits.

Q: Why is the convention $\int_b^a f = -\int_a^b f$ adopted?
A: It makes additivity $\int_a^c = \int_a^b + \int_b^c$ hold for any ordering of $a$, $b$, $c$, not just $a \le b \le c$. Without this sign convention, formulas would need cases for every interval ordering.

C: As a corollary of reversing limits, $\int_a^a f(x)\,dx = [0]$ for any integrable $f$, since the interval has zero width.

## 10.11 Comparison Properties

C: Comparison property: if $f(x) \le g(x)$ for all $x \in [a, b]$ and both are integrable, then $[\int_a^b f(x)\,dx \le \int_a^b g(x)\,dx]$.

Q: Why does $f \le g$ on $[a, b]$ imply $\int_a^b f \le \int_a^b g$?
A: Every Riemann sum for $f$ is term-by-term at most the corresponding sum for $g$, since $f(x_i^*) \le g(x_i^*)$ and $\Delta x_i \ge 0$. The inequality is preserved in the limit, giving the integral inequality.

C: Bounding property: if $m \le f(x) \le M$ on $[a, b]$, then $m(b-a) \le \int_a^b f(x)\,dx \le M(b-a)$, where $m$ and $M$ are lower and upper bounds of $f$.

Q: How does the bounding property $m(b-a) \le \int_a^b f \le M(b-a)$ help estimate an integral you cannot compute exactly?
A: It sandwiches the integral between the area of the smallest enclosing rectangle ($M(b-a)$) and the largest inscribed rectangle ($m(b-a)$). For instance, knowing $0 \le e^{-x^2} \le 1$ on $[0, 1]$ gives $0 \le \int_0^1 e^{-x^2}\,dx \le 1$ without any computation.

## 10.12 Mean Value Theorem for Integrals

C: The [average value] of a continuous function $f$ on $\lbrack a, b\rbrack $ is $\bar f = \frac{1}{b-a}\int_a^b f(x)\,dx$, where $a$ and $b$ are the endpoints.

C: Mean Value Theorem for Integrals: if $f$ is continuous on $[a, b]$, there exists $[c \in (a, b)]$ such that $f(c) = \frac{1}{b-a}\int_a^b f(x)\,dx$.

Q: Why does the Mean Value Theorem for Integrals guarantee a point where $f$ equals its average value?
A: Because $f$ is continuous on $[a, b]$, it attains its minimum $m$ and maximum $M$. The average $\bar f$ lies between $m$ and $M$ (by the bounding property), and the Intermediate Value Theorem guarantees some $c \in (a, b)$ with $f(c) = \bar f$.

Q: How should you geometrically interpret the average value $\bar f = \frac{1}{b-a}\int_a^b f$?
A: It is the height of the rectangle over $[a, b]$ whose area $\bar f \cdot (b-a)$ equals $\int_a^b f(x)\,dx$. Picture "flattening" the region under the curve into a rectangle with the same width and the same signed area.

## 10.13 Fundamental Theorem of Calculus, Part 1

C: FTC Part 1: if $f$ is continuous on an interval containing $a$, and $F(x) = \int_a^x f(t)\,dt$, then $F$ is differentiable and $F'(x) = [f(x)]$, where $t$ is the dummy integration variable.

Q: Why is the function $F(x) = \int_a^x f(t)\,dt$ called an "accumulation function"?
A: As $x$ increases, $F(x)$ accumulates signed area between $a$ and $x$ under the graph of $f$. $F$ records the total signed area swept out from the fixed lower limit $a$ up to the variable upper limit $x$.

Q: Give the intuition behind why $F'(x) = f(x)$ when $F(x) = \int_a^x f(t)\,dt$.
A: Increasing the upper limit from $x$ to $x + h$ adds a thin strip of approximate area $f(x)\cdot h$ to $F$. So $F(x+h) - F(x) \approx f(x)\,h$, and dividing by $h$ and letting $h \to 0$ gives $F'(x) = f(x)$.

Q: Before seeing the proof, predict: what should $\frac{d}{dx}\int_0^x \cos t\,dt$ equal, and why?
A: It should equal $\cos x$. FTC Part 1 says differentiating an accumulation function returns the integrand evaluated at the upper limit — differentiation and integration undo each other when composed this way.

## 10.14 Why FTC 1 Says "Differentiation Undoes Integration"

Q: In what precise sense does FTC Part 1 say differentiation is the inverse of integration?
A: It says the operator "integrate $f$ from $a$ to $x$" followed by "differentiate with respect to $x$" returns $f(x)$. That is, $\frac{d}{dx}\int_a^x f(t)\,dt = f(x)$ — differentiating an accumulation function recovers the original integrand.

Q: Why is FTC Part 1 surprising from the perspective of a student who learned derivatives and integrals as separate operations?
A: Derivatives measure instantaneous rates of change while integrals measure accumulated totals — seemingly unrelated. FTC Part 1 reveals they are inverse operations, unifying the differential and integral calculus into one coherent theory.

Q: If $F(x) = \int_a^x f(t)\,dt$ and $f$ is continuous, why must $F$ be continuous as well (not just differentiable)?
A: Because differentiability at every point of an interval implies continuity there. So FTC Part 1 gives something stronger than continuity — $F$ is smooth enough to have a derivative equal to $f$.

## 10.15 Fundamental Theorem of Calculus, Part 2

C: FTC Part 2: if $f$ is continuous on $[a, b]$ and $F$ is any antiderivative of $f$ (so $F'(x) = f(x)$), then $\int_a^b f(x)\,dx = [F(b) - F(a)]$.

C: The notation $[F(x)]_a^b$ or $F(x)\big|_a^b$ is shorthand for $[F(b) - F(a)]$, the evaluation used in FTC Part 2.

Q: Why can you use any antiderivative $F$ in FTC Part 2, not just one specific one?
A: Two antiderivatives of the same $f$ differ by a constant: $F_2(x) = F_1(x) + C$. Then $F_2(b) - F_2(a) = [F_1(b) + C] - [F_1(a) + C] = F_1(b) - F_1(a)$. The constant cancels in the subtraction, so the value is independent of which antiderivative you pick.

Q: How is FTC Part 2 proved from FTC Part 1?
A: Define $G(x) = \int_a^x f(t)\,dt$. By Part 1, $G' = f$, so $G$ is an antiderivative. Any other antiderivative is $F(x) = G(x) + C$. Then $F(b) - F(a) = G(b) - G(a) = \int_a^b f(t)\,dt - 0 = \int_a^b f(t)\,dt$.

## 10.16 Why FTC Part 2 Is How We Compute Integrals

Q: Why is FTC Part 2 the practical workhorse of integration?
A: It replaces the impossibly tedious process of computing a limit of Riemann sums with a two-step recipe: find an antiderivative $F$ of $f$, then evaluate $F(b) - F(a)$. Every concrete definite integral you compute in practice uses this shortcut.

Q: What does FTC Part 2 require of $f$ that FTC Part 1 does not emphasize?
A: Both require continuity on $[a, b]$, but Part 2 explicitly requires that an antiderivative $F$ exists and is known. Part 1 implicitly supplies one (the accumulation function), while Part 2 presumes you can find or recognize a concrete $F$.

Q: Why does having an elementary antiderivative matter for $\int_0^1 e^{-x^2}\,dx$ versus $\int_0^1 e^{x}\,dx$?
A: $e^x$ has the elementary antiderivative $e^x$, so FTC Part 2 gives $e^1 - e^0 = e - 1$ instantly. $e^{-x^2}$ has no elementary antiderivative, so FTC Part 2 cannot be applied in closed form — we need numerical methods or special functions (erf).

## 10.17 Leibniz Rule for Variable Limits

C: Leibniz rule (variable upper limit): $\frac{d}{dx}\int_a^{g(x)} f(t)\,dt = [f(g(x))\cdot g'(x)]$, assuming $f$ is continuous and $g$ is differentiable.

C: General Leibniz rule: $\frac{d}{dx}\int_{u(x)}^{v(x)} f(t)\,dt = [f(v(x))v'(x) - f(u(x))u'(x)]$, where $u, v$ are differentiable limits.

Q: Why does the Leibniz rule for variable limits include the factor $g'(x)$?
A: The upper limit $g(x)$ depends on $x$, so differentiating uses the chain rule. Let $F(u) = \int_a^u f(t)\,dt$; by FTC Part 1, $F'(u) = f(u)$. Then $\frac{d}{dx}F(g(x)) = F'(g(x))\cdot g'(x) = f(g(x))\cdot g'(x)$.

Q: For $\frac{d}{dx}\int_{u(x)}^{v(x)} f(t)\,dt$, why does the lower-limit term carry a minus sign?
A: Split the integral at a constant: $\int_u^v = \int_c^v - \int_c^u$ (by additivity and reversing limits). Differentiating each piece by the chain rule gives $f(v)v' - f(u)u'$ — the minus sign originates from $\int_u^c = -\int_c^u$.

## 10.18 Procedure: Compute $\int_0^2 (x^2 + 1)\,dx$

P: Compute $\int_0^2 (x^2 + 1)\,dx$ using the Fundamental Theorem of Calculus.

S:
**IDENTIFY**: Definite integral of a polynomial on $[0, 2]$. Integrand $f(x) = x^2 + 1$ is continuous everywhere, so FTC Part 2 applies and we need an antiderivative $F$ with $F'(x) = x^2 + 1$.

**PLAN**:
- Use linearity: $\int (x^2 + 1)\,dx = \int x^2\,dx + \int 1\,dx$.
- Apply the power rule for antiderivatives: $\int x^n\,dx = \frac{x^{n+1}}{n+1} + C$ for $n \ne -1$.
- Take $F(x) = \frac{x^3}{3} + x$ (drop the $+C$ since it cancels in the evaluation $F(2) - F(0)$).
- Evaluate $F(b) - F(a) = F(2) - F(0)$.

**EXECUTE**:
1. Antiderivative: $F(x) = \dfrac{x^3}{3} + x$.
2. Upper limit: $F(2) = \dfrac{2^3}{3} + 2 = \dfrac{8}{3} + 2 = \dfrac{8}{3} + \dfrac{6}{3} = \dfrac{14}{3}$.
3. Lower limit: $F(0) = \dfrac{0^3}{3} + 0 = 0$.
4. Subtract: $\int_0^2 (x^2 + 1)\,dx = F(2) - F(0) = \dfrac{14}{3} - 0 = \dfrac{14}{3}$.

**EVALUATE**:
- Units/sanity: on $[0, 2]$ the integrand $x^2 + 1$ ranges from $1$ (at $x=0$) to $5$ (at $x=2$). So the integral must lie in $[1\cdot 2, 5\cdot 2] = [2, 10]$ by the bounding property. $\dfrac{14}{3} \approx 4.67$, comfortably in range.
- Differentiation check: $\dfrac{d}{dx}\left[\dfrac{x^3}{3} + x\right] = x^2 + 1$ ✓, confirming $F$ is a valid antiderivative.
- Answer: $\int_0^2 (x^2 + 1)\,dx = \dfrac{14}{3}$.

## 10.19 Procedure: Differentiate $F(x) = \int_1^{x^2} \sin(t^2)\,dt$

P: If $F(x) = \int_1^{x^2} \sin(t^2)\,dt$, find $F'(x)$.

S:
**IDENTIFY**: Derivative of an integral with a constant lower limit ($1$) and a variable upper limit ($x^2$). The integrand $\sin(t^2)$ has no elementary antiderivative, so direct computation of the integral is not possible — but FTC Part 1 plus the chain rule (Leibniz rule) lets us differentiate without evaluating.

**PLAN**:
- Recognize the form $F(x) = \int_a^{g(x)} f(t)\,dt$ with $a = 1$, $g(x) = x^2$, $f(t) = \sin(t^2)$.
- Apply the Leibniz rule: $F'(x) = f(g(x))\cdot g'(x)$.
- Compute $g'(x)$ and substitute $g(x)$ into $f$.

**EXECUTE**:
1. Identify pieces: $f(t) = \sin(t^2)$, $g(x) = x^2$.
2. Compute $g'(x) = 2x$.
3. Evaluate integrand at upper limit: $f(g(x)) = \sin((x^2)^2) = \sin(x^4)$.
4. Multiply by chain-rule factor: $F'(x) = f(g(x))\cdot g'(x) = \sin(x^4)\cdot 2x = 2x\sin(x^4)$.

**EVALUATE**:
- Sanity at $x = 1$: $g(1) = 1$ equals the lower limit, so $F(1) = \int_1^1 \sin(t^2)\,dt = 0$. The formula gives $F'(1) = 2(1)\sin(1) = 2\sin(1) \approx 1.68$, a finite nonzero slope — consistent with $F$ starting at $0$ and increasing.
- Structural check: the $2x$ factor must appear because the upper limit is $x^2$, not $x$; dropping it is the most common error.
- Answer: $F'(x) = 2x\sin(x^4)$.
