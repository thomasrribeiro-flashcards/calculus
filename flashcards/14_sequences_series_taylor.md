+++
order = 14
tags = ["math", "calculus", "sequences", "series", "convergence-tests", "power-series", "taylor-series", "maclaurin"]
+++

# Calculus — Sequences, Series, and Taylor Expansions

## 14.1 Sequence Convergence

Q: Why do we study sequences before series in calculus?
A: A series is defined as the limit of its sequence of partial sums, so understanding when sequences converge is a prerequisite. Every tool for series convergence ultimately reduces to asking whether a particular sequence has a limit.

C: A sequence $(a_n)_{n=1}^\infty$ converges to $L$ if for every $\varepsilon > 0$ there exists $N$ such that $n \geq N$ implies $[|a_n - L| < \varepsilon]$, where $a_n$ is the $n$-th term and $L$ is the candidate limit.

Q: What does $\lim_{n\to\infty} a_n = L$ mean geometrically?
A: Every open interval around $L$, no matter how small, eventually contains all terms of the sequence. Only finitely many terms may lie outside any given $\varepsilon$-neighborhood of $L$.

C: If $\lim_{n\to\infty} a_n$ does not exist or is $\pm\infty$, the sequence is said to [diverge], where $a_n$ is the $n$-th term of the sequence.

Q: Why does the sequence $a_n = (-1)^n$ diverge even though its terms stay bounded?
A: The terms oscillate between $-1$ and $+1$ and never settle near a single value $L$. No $\varepsilon < 1$ neighborhood can eventually contain every term, so no limit exists.

## 14.2 Limit Laws for Sequences

Q: Why do sequence limit laws mirror function limit laws?
A: A sequence is a function $a\colon \mathbb{N} \to \mathbb{R}$, so convergence is a special case of a function limit at infinity. Every algebraic property of $\lim_{x\to\infty}$ transfers directly to $\lim_{n\to\infty}$.

C: If $\lim a_n = A$ and $\lim b_n = B$, then $\lim(a_n + b_n) = [A + B]$, where $A, B$ are the individual limits.

C: If $\lim a_n = A$ and $\lim b_n = B \neq 0$, then $\lim(a_n / b_n) = [A/B]$, provided $b_n \neq 0$ for all $n$, where $A, B$ are the limits of the numerator and denominator sequences.

Q: Why does the squeeze theorem apply to sequences?
A: If $a_n \leq b_n \leq c_n$ eventually and $\lim a_n = \lim c_n = L$, then $b_n$ is trapped near $L$. This is essential for limits like $\lim \frac{\sin n}{n}$, where $|\sin n| \leq 1$ forces the ratio to $0$.

C: If $f$ is continuous at $L$ and $a_n \to L$, then $f(a_n) \to [f(L)]$, where $f$ is a real-valued function and $L$ is the limit of the sequence.

## 14.3 Monotone Convergence Theorem

Q: Why must a bounded monotonic sequence converge, even when we cannot compute the limit?
A: A monotonically increasing sequence that is bounded above cannot oscillate or escape, so the least upper bound (supremum) of its terms must be the limit. This is a consequence of the completeness of the real numbers — there are no "gaps" for the sequence to miss.

C: A sequence $(a_n)$ is [monotonically increasing] if $a_{n+1} \geq a_n$ for all $n$, where $a_n$ is the $n$-th term.

C: The Monotone Convergence Theorem states: every bounded monotonic sequence [converges], where "bounded" means all terms lie in some fixed interval $[m, M]$.

Q: How does the monotone convergence theorem justify the definition $e = \lim(1 + 1/n)^n$?
A: The sequence $a_n = (1 + 1/n)^n$ can be shown to be increasing and bounded above by $3$. By the theorem, a limit exists, and we define that limit to be $e$. Without monotone convergence, the existence of $e$ this way would be unclear.

## 14.4 Infinite Series as Limits of Partial Sums

Q: Why is an infinite sum not immediately well-defined?
A: Addition is a binary operation; we can only add finitely many terms by iterated application. An infinite sum requires a limit process: we define $\sum_{n=1}^\infty a_n$ as the limit of the finite partial sums, bridging algebra to analysis.

C: The $N$-th partial sum of $\sum_{n=1}^\infty a_n$ is $S_N = [\sum_{n=1}^N a_n]$, where $a_n$ is the $n$-th term of the series.

C: The infinite series $\sum_{n=1}^\infty a_n$ converges to $S$ if $\lim_{N\to\infty} S_N = [S]$, where $S_N$ is the $N$-th partial sum and $S$ is the value of the series.

Q: Why can rearranging an infinite series change its sum, unlike finite sums?
A: Commutativity of addition extends to finite sums by induction, but infinite sums depend on the ordering of partial sums. For conditionally convergent series, Riemann's rearrangement theorem shows you can rearrange terms to sum to any real number.

## 14.5 Geometric Series

Q: Why does a geometric series converge exactly when $|r| < 1$?
A: The partial sum is $S_N = a\frac{1 - r^N}{1 - r}$, where $a$ is the first term and $r$ is the common ratio. For $|r| < 1$, $r^N \to 0$, so $S_N \to a/(1-r)$. For $|r| \geq 1$, the terms $ar^n$ do not approach $0$, so the nth-term test forces divergence.

C: The geometric series $\sum_{n=0}^\infty ar^n$ converges iff $[|r| < 1]$, where $a \neq 0$ is the first term and $r$ is the common ratio.

C: When $|r| < 1$, $\sum_{n=0}^\infty ar^n = [a/(1 - r)]$, where $a$ is the first term and $r$ is the common ratio.

Q: Why is the geometric series a benchmark for comparison tests?
A: Its convergence is fully characterized by a single number $|r|$, and many other series can be bounded above or below by a geometric series. This makes it the canonical "yardstick" for the comparison, ratio, and root tests.

## 14.6 $p$-Series

Q: Why does $\sum 1/n^p$ converge iff $p > 1$?
A: By the integral test, $\sum 1/n^p$ behaves like $\int_1^\infty x^{-p}\,dx$. That improper integral converges iff $p > 1$ (where the antiderivative $x^{1-p}/(1-p)$ has a finite limit at infinity). For $p \leq 1$, the integral diverges, dragging the series with it.

C: The $p$-series $\sum_{n=1}^\infty 1/n^p$ converges iff $[p > 1]$, where $p$ is a real exponent.

C: The harmonic series $\sum_{n=1}^\infty 1/n$ is the $p$-series with $p = 1$, which [diverges], where divergence means partial sums grow without bound (like $\ln N$).

Q: Why is the harmonic series a famously counterintuitive example?
A: The terms $1/n$ approach $0$, so one might expect convergence, but they shrink too slowly: partial sums grow like $\ln N$, which tends to infinity. It shows $a_n \to 0$ is necessary but not sufficient for convergence.

## 14.7 Divergence Test (nth Term Test)

Q: What is the contrapositive statement of the divergence test?
A: If $\sum a_n$ converges, then $a_n \to 0$. The divergence test uses the contrapositive: if $a_n$ does NOT tend to $0$, then $\sum a_n$ cannot converge. It only detects divergence — it can never confirm convergence.

C: If $\lim_{n\to\infty} a_n \neq 0$ (or does not exist), then $\sum a_n$ [diverges], where $a_n$ is the general term of the series.

Q: Why does $a_n \to 0$ NOT guarantee convergence of $\sum a_n$?
A: The harmonic series $\sum 1/n$ is the counterexample: $1/n \to 0$ but the series diverges. Convergence requires the terms to shrink fast enough — specifically, fast enough for the partial sums to have a finite limit.

Q: Before a deeper test, why should you always check $\lim a_n$ first?
A: It is cheap to compute and eliminates obviously divergent candidates. If $a_n \not\to 0$, no further test is needed. Only if $a_n \to 0$ (the inconclusive case) do you invoke ratio, root, integral, or comparison tests.

## 14.8 Integral Test

Q: Why does the integral test work, geometrically?
A: If $f(x)$ is positive, continuous, and decreasing with $f(n) = a_n$, then the series $\sum a_n$ and integral $\int_1^\infty f(x)\,dx$ bound each other using rectangles. The sum is trapped between $\int_1^\infty f\,dx$ and $a_1 + \int_1^\infty f\,dx$, so both converge or both diverge.

C: The integral test applies when $f$ is positive, [decreasing], and continuous on $[1,\infty)$ with $f(n) = a_n$, where $a_n$ is the $n$-th term of the series and $f$ is the associated function.

C: By the integral test, $\sum_{n=1}^\infty a_n$ and $\int_1^\infty f(x)\,dx$ either both converge or both [diverge], where $f$ is positive and decreasing with $f(n) = a_n$.

Q: Why is the "decreasing" hypothesis of the integral test crucial?
A: The rectangle-integral comparison only works if successive terms shrink monotonically. Without monotonicity, $a_n$ could be larger than $f$'s local values and break the bound. In practice, check that $f'(x) < 0$ eventually.

## 14.9 Direct Comparison Test

Q: What is the logical structure of direct comparison for positive series?
A: Positive series have monotonically increasing partial sums. If $0 \leq a_n \leq b_n$ and $\sum b_n$ converges, partial sums of $\sum a_n$ are bounded above and must converge. Conversely, if $\sum a_n$ diverges and $a_n \leq b_n$, then $\sum b_n$ diverges too.

C: If $0 \leq a_n \leq b_n$ and $\sum b_n$ converges, then $\sum a_n$ [converges], where $a_n$ and $b_n$ are the general terms of the two series.

C: If $0 \leq b_n \leq a_n$ and $\sum b_n$ diverges, then $\sum a_n$ [diverges], where $a_n, b_n$ are general terms of positive series.

Q: Why must the direct comparison test use non-negative terms?
A: Without positivity, partial sums do not increase monotonically and the bounded-implies-convergent argument fails. Signed series require absolute convergence or the alternating series test instead.

## 14.10 Limit Comparison Test

Q: Why is the limit comparison test often more flexible than direct comparison?
A: You do not need to prove a strict inequality $a_n \leq b_n$; you only need $a_n/b_n \to c$ with $0 < c < \infty$. This handles cases where $a_n$ and $b_n$ differ by lower-order terms that would block a direct inequality.

C: If $a_n, b_n > 0$ and $\lim_{n\to\infty}(a_n/b_n) = c$ with $0 < c < \infty$, then $\sum a_n$ and $\sum b_n$ [both converge or both diverge], where $c$ is the finite positive limit ratio.

Q: How do you use limit comparison on $\sum \frac{n+1}{n^3+2}$?
A: The dominant behavior is $n/n^3 = 1/n^2$, so compare to $b_n = 1/n^2$. The ratio $a_n/b_n \to 1$, a finite positive constant, and $\sum 1/n^2$ converges (p-series, $p = 2$), so $\sum \frac{n+1}{n^3+2}$ converges.

Q: What happens in limit comparison when $c = 0$ or $c = \infty$?
A: The tests become one-directional: if $c = 0$ and $\sum b_n$ converges, $\sum a_n$ converges; if $c = \infty$ and $\sum b_n$ diverges, $\sum a_n$ diverges. The "both converge or both diverge" conclusion requires $0 < c < \infty$.

## 14.11 Ratio Test

Q: Why does the ratio test echo the geometric series?
A: If $|a_{n+1}/a_n| \to L < 1$, the tail of the series eventually behaves like a geometric series with ratio near $L$, which converges. If $L > 1$, the terms grow and $a_n \not\to 0$, forcing divergence.

C: Ratio test: if $\lim_{n\to\infty}|a_{n+1}/a_n| = L$, the series $\sum a_n$ converges absolutely when $L < 1$ and diverges when $[L > 1]$, where $L$ is the limit of consecutive-term ratios.

Q: Why is the ratio test inconclusive when $L = 1$?
A: Both $\sum 1/n$ (divergent) and $\sum 1/n^2$ (convergent) have ratio limits equal to $1$. The first-order ratio cannot distinguish them — you need a finer tool like the integral test or a $p$-series comparison.

Q: When is the ratio test the natural choice?
A: When $a_n$ contains factorials, exponentials, or products that cancel cleanly in $a_{n+1}/a_n$. For example, $\sum n!/n^n$ or $\sum 2^n/n!$ reduce dramatically in the ratio — that is the signal to try it first.

## 14.12 Root Test

Q: Why does the root test sometimes work when the ratio test fails?
A: The root test uses $\limsup |a_n|^{1/n}$, which handles $a_n$ defined by expressions of the form $b_n^n$ or with irregular ratios. It is strictly more powerful: if the ratio test gives a limit, the root test gives the same one, but the root test may succeed when consecutive ratios do not converge.

C: Root test: if $\lim_{n\to\infty}|a_n|^{1/n} = L$, the series $\sum a_n$ converges absolutely when $[L < 1]$ and diverges when $L > 1$, where $L$ is the limit of $n$-th roots.

Q: What form of $a_n$ makes the root test natural?
A: Terms like $a_n = (f(n))^n$ or $\left(\frac{n}{n+1}\right)^{n^2}$, where taking an $n$-th root produces a manageable expression. For example, $(n/(n+1))^{n^2}$ has $n$-th root $(n/(n+1))^n \to 1/e < 1$, so the series converges.

## 14.13 Alternating Series Test (Leibniz)

Q: Why does alternation help a series converge even if the absolute series diverges?
A: Successive terms of alternating sign partially cancel. If $|a_n|$ decreases monotonically to $0$, partial sums oscillate within shrinking envelopes and are forced to a common limit (Leibniz criterion). This is how $\sum (-1)^{n+1}/n$ converges despite the harmonic series diverging.

C: The alternating series $\sum (-1)^{n+1} b_n$ with $b_n > 0$ converges if $b_n$ is [monotonically decreasing] and $b_n \to 0$, where $b_n$ is the absolute value of the $n$-th term.

C: For a convergent alternating series, the error $|S - S_N| \leq [b_{N+1}]$, where $S$ is the true sum, $S_N$ is the $N$-th partial sum, and $b_{N+1}$ is the next term's absolute value.

Q: Why is the error bound $|S - S_N| \leq b_{N+1}$ so useful in practice?
A: It gives a computable, explicit truncation error for numerical approximation of alternating series. No integration or majorizing series is needed — the next term's size is the cap, making alternating series especially friendly for computation.

## 14.14 Absolute vs Conditional Convergence

Q: Why distinguish absolute from conditional convergence?
A: Absolutely convergent series ($\sum |a_n|$ converges) behave algebraically like finite sums: they can be rearranged and multiplied without changing the sum. Conditionally convergent series ($\sum a_n$ converges but $\sum |a_n|$ diverges) are fragile — rearrangement can change the sum to any real number.

C: A series $\sum a_n$ converges [absolutely] if $\sum |a_n|$ converges, where $|a_n|$ is the absolute value of the $n$-th term.

C: A series that converges but whose absolute series diverges is said to converge [conditionally], where the cancellation from signs is essential for convergence.

Q: Is $\sum (-1)^{n+1}/n$ absolutely or conditionally convergent, and why?
A: It converges by Leibniz (alternating, $1/n \to 0$ monotonically), but $\sum 1/n$ (the harmonic series) diverges. So it converges conditionally — only the alternation saves it.

## 14.15 Power Series and Radius of Convergence

Q: Why do power series behave like "infinite polynomials" only inside a disk?
A: A power series $\sum c_n (x - a)^n$ converges in an interval $|x - a| < R$ where the terms shrink fast enough, and diverges outside. Within this radius it can be differentiated and integrated term-by-term, but outside, the terms blow up.

C: A power series centered at $a$ has the form $\sum_{n=0}^\infty c_n (x - a)^n$, where $c_n$ is the $n$-th [coefficient] and $a$ is the center.

C: The radius of convergence $R$ is such that the power series converges absolutely for $|x - a| < R$ and [diverges] for $|x - a| > R$, where $R \in [0, \infty]$.

Q: How do you compute the radius of convergence using the ratio test?
A: Apply the ratio test to $|c_{n+1}(x-a)^{n+1} / (c_n(x-a)^n)| = |x - a| \cdot |c_{n+1}/c_n|$. If $|c_{n+1}/c_n| \to 1/R$, the ratio is $|x-a|/R$, which is less than $1$ iff $|x - a| < R$. This gives $R = \lim |c_n/c_{n+1}|$ when the limit exists.

## 14.16 Interval of Convergence

Q: Why must you always check the endpoints of a power series' interval separately?
A: The ratio and root tests determine the open interval $(a - R, a + R)$ where the series converges absolutely, but they are inconclusive at the boundary $|x - a| = R$. At each endpoint the series becomes a specific numeric series which may converge absolutely, conditionally, or diverge — you must test each individually.

C: The interval of convergence is the set of all $x$ for which $\sum c_n(x - a)^n$ [converges], which equals $(a - R, a + R)$ plus possibly one or both endpoints $x = a \pm R$.

Q: What are the four possible shapes of an interval of convergence?
A: $(a-R, a+R)$, $[a-R, a+R)$, $(a-R, a+R]$, or $[a-R, a+R]$, plus the degenerate cases $R = 0$ (a single point) and $R = \infty$ (all of $\mathbb{R}$). Which shape occurs depends entirely on endpoint behavior.

## 14.17 Taylor Series

Q: Why does the Taylor series use derivatives at $a$ as coefficients?
A: If $f(x) = \sum c_n(x-a)^n$, differentiating $k$ times and evaluating at $x = a$ kills every term except the $k$-th and gives $f^{(k)}(a) = k! \cdot c_k$. So $c_k = f^{(k)}(a)/k!$ — the coefficients are forced by local derivative data.

C: The Taylor series of $f$ at $a$ is $\sum_{n=0}^\infty \frac{f^{(n)}(a)}{n!}(x - a)^n$, where $f^{(n)}(a)$ is the $n$-th derivative at $a$ and $n!$ is the [factorial] of $n$.

Q: Before deriving Taylor's formula, predict: why should $c_n$ involve $n!$?
A: Repeated differentiation of $(x-a)^n$ produces $n!$ as the leading constant. Dividing by $n!$ undoes this combinatorial factor so each coefficient equals a clean derivative value. Without $n!$, the series would not reconstruct $f$'s derivatives cleanly.

Q: What does it mean for a function to equal its Taylor series?
A: The Taylor series converges to $f(x)$ on some interval around $a$, meaning the remainder $R_n(x) \to 0$ as $n \to \infty$. Not all smooth functions have this property — $e^{-1/x^2}$ extended by $0$ at $0$ has the zero Taylor series at $0$ but is not identically zero.

## 14.18 Maclaurin Series

Q: Why is the Maclaurin series just a special case of the Taylor series?
A: A Maclaurin series is a Taylor series centered at $a = 0$: $\sum \frac{f^{(n)}(0)}{n!} x^n$. It is not a new object; the name is historical convenience. Most textbook "standard expansions" ($e^x$, $\sin x$, $\cos x$) are Maclaurin series because $0$ is the simplest expansion point.

C: The Maclaurin series of $f$ is $\sum_{n=0}^\infty \frac{f^{(n)}(0)}{n!} x^n$, where $f^{(n)}(0)$ is the $n$-th derivative of $f$ evaluated at $[0]$.

## 14.19 Key Maclaurin Series

C: $e^x = \sum_{n=0}^\infty \frac{x^n}{n!} = 1 + x + \frac{x^2}{2!} + [\frac{x^3}{3!}] + \cdots$, valid for all real $x$, where $n!$ is the factorial.

C: $\sin x = \sum_{n=0}^\infty \frac{(-1)^n x^{2n+1}}{(2n+1)!} = x - \frac{x^3}{3!} + [\frac{x^5}{5!}] - \cdots$, valid for all real $x$, where the alternation comes from repeated derivatives of $\sin$.

C: $\cos x = \sum_{n=0}^\infty \frac{(-1)^n x^{2n}}{(2n)!} = 1 - \frac{x^2}{2!} + [\frac{x^4}{4!}] - \cdots$, valid for all real $x$.

C: $\ln(1+x) = \sum_{n=1}^\infty \frac{(-1)^{n+1} x^n}{n} = x - \frac{x^2}{2} + \frac{x^3}{3} - \cdots$, with radius of convergence $[R = 1]$, where $R$ is the radius of convergence.

C: $\frac{1}{1 - x} = \sum_{n=0}^\infty x^n = 1 + x + x^2 + \cdots$, valid for $[|x| < 1]$, where $x$ is the input variable (this is the geometric series).

Q: Why do $\sin x$ and $\cos x$ have alternating series with only odd (resp. even) powers?
A: The derivatives of $\sin$ cycle through $\sin, \cos, -\sin, -\cos$, giving $\sin^{(n)}(0) = 0, 1, 0, -1, \ldots$. Only odd-index derivatives are nonzero, producing only odd powers of $x$ with alternating signs. The same pattern applies to $\cos$ with even powers.

Q: How do you derive the Maclaurin series for $\ln(1+x)$ from $1/(1-x)$?
A: Start with $1/(1+u) = \sum (-u)^n$ (geometric with $r = -u$), valid for $|u|<1$. Integrate term-by-term from $0$ to $x$: $\ln(1+x) = \sum (-1)^n \frac{x^{n+1}}{n+1}$. Reindexing gives the standard form $\sum_{n\geq 1}(-1)^{n+1}x^n/n$.

## 14.20 Taylor's Theorem with Remainder

Q: Why do we need a remainder term for Taylor approximations?
A: A finite Taylor polynomial $T_n(x)$ is an approximation, not an equality. The remainder $R_n(x) = f(x) - T_n(x)$ measures the error. Taylor's theorem bounds this error, making the approximation rigorous and giving a criterion for when the full Taylor series equals $f$.

C: Lagrange form of the remainder: $R_n(x) = \frac{f^{(n+1)}(c)}{(n+1)!}(x - a)^{n+1}$ for some $c$ between $a$ and $x$, where $f^{(n+1)}$ is the $(n+1)$-th derivative and $c$ is an [unknown] intermediate point.

C: The Taylor series of $f$ converges to $f(x)$ at a point $x$ iff $\lim_{n\to\infty} R_n(x) = [0]$, where $R_n(x)$ is the remainder after $n$ terms.

Q: Why does the Maclaurin series of $e^x$ converge to $e^x$ for all $x$?
A: Lagrange remainder gives $|R_n(x)| \leq e^{|x|} |x|^{n+1}/(n+1)!$. For fixed $x$, $|x|^{n+1}/(n+1)! \to 0$ as $n \to \infty$ (factorial dominates exponential), so $R_n \to 0$ everywhere. The series equals $e^x$ globally.

## 14.21 Using Taylor Series to Evaluate Limits

Q: Why can Taylor series resolve $0/0$ limits that L'Hôpital struggles with?
A: Taylor series reveal the leading-order behavior of both numerator and denominator as polynomials in $(x - a)$. Canceling the common leading power directly shows the limit. L'Hôpital requires repeatedly checking indeterminate form and differentiating; Taylor series handle several orders at once.

Q: How would you compute $\lim_{x\to 0} (\sin x - x)/x^3$ using series?
A: Expand $\sin x = x - x^3/6 + x^5/120 - \cdots$, so $\sin x - x = -x^3/6 + x^5/120 - \cdots$. Divide by $x^3$ to get $-1/6 + x^2/120 - \cdots$, which tends to $-1/6$. No repeated differentiation needed.

Q: How do you compute $\lim_{x \to 0}(e^x - 1 - x)/x^2$ with Taylor series?
A: $e^x = 1 + x + x^2/2 + x^3/6 + \cdots$, so $e^x - 1 - x = x^2/2 + x^3/6 + \cdots$. Dividing by $x^2$ gives $1/2 + x/6 + \cdots \to 1/2$. Two L'Hôpital applications would give the same answer with more work.

## 14.22 P:/S: Interval of Convergence of $\sum \frac{(x-2)^n}{n \cdot 3^n}$

P: Find the interval of convergence for $\sum_{n=1}^\infty \frac{(x-2)^n}{n \cdot 3^n}$, where $x$ is the variable and $n$ runs over positive integers.

S:
**IDENTIFY**: Power series centered at $a = 2$ with coefficients $c_n = 1/(n \cdot 3^n)$. We need the radius $R$ plus endpoint behavior at $x = 2 \pm R$.

**PLAN**:
- Apply ratio test to find $R$
- Determine the open interval $(2 - R, 2 + R)$
- Test each endpoint separately (ratio test is inconclusive there)

**EXECUTE**:
1. Ratio test: compute $L = \lim |a_{n+1}/a_n|$ where $a_n = (x-2)^n/(n \cdot 3^n)$:
$$\left|\frac{a_{n+1}}{a_n}\right| = \left|\frac{(x-2)^{n+1}}{(n+1)3^{n+1}} \cdot \frac{n \cdot 3^n}{(x-2)^n}\right| = \frac{n}{n+1} \cdot \frac{|x-2|}{3}$$
2. As $n \to \infty$, $n/(n+1) \to 1$, so $L = |x-2|/3$.
3. Convergence requires $L < 1$, i.e. $|x - 2| < 3$, giving radius $R = 3$ and open interval $(-1, 5)$.
4. Endpoint $x = 5$: series becomes $\sum 3^n/(n \cdot 3^n) = \sum 1/n$, the harmonic series — diverges.
5. Endpoint $x = -1$: series becomes $\sum (-3)^n/(n \cdot 3^n) = \sum (-1)^n/n$, an alternating harmonic series — converges (conditionally, by Leibniz).

**EVALUATE**:
- Interval of convergence: $[-1, 5)$ — includes left endpoint, excludes right.
- Sanity check: $R = 3$ matches $c_n/c_{n+1} = (n+1)3^{n+1}/(n \cdot 3^n) \cdot$ reciprocal $\to 3$.
- Conditional convergence at $x = -1$; absolute convergence for $|x - 2| < 3$.

## 14.23 P:/S: Maclaurin Series for $\cos x$ and Approximation of $\cos(0.1)$

P: Derive the Maclaurin series for $f(x) = \cos x$ from first principles and use the first three nonzero terms to approximate $\cos(0.1)$, bounding the error.

S:
**IDENTIFY**: Taylor-series construction at $a = 0$ for $\cos x$, followed by numerical approximation with Lagrange-remainder error bound.

**PLAN**:
- Compute derivatives $f^{(n)}(0)$ for $n = 0, 1, 2, \ldots$ and spot the pattern
- Assemble the Maclaurin series
- Plug in $x = 0.1$, truncate to three nonzero terms
- Use Lagrange remainder (or alternating-series bound, since the series alternates) to bound the error

**EXECUTE**:
1. Derivatives of $f(x) = \cos x$: $f' = -\sin x$, $f'' = -\cos x$, $f''' = \sin x$, $f^{(4)} = \cos x$, cycling with period $4$.
2. Values at $0$: $f(0) = 1, f'(0) = 0, f''(0) = -1, f'''(0) = 0, f^{(4)}(0) = 1, \ldots$ — only even derivatives nonzero, alternating $\pm 1$.
3. Maclaurin series: $\cos x = \sum_{n=0}^\infty \frac{(-1)^n x^{2n}}{(2n)!} = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \cdots$.
4. Evaluate at $x = 0.1$ using first three nonzero terms ($n = 0, 1, 2$):
$$\cos(0.1) \approx 1 - \frac{(0.1)^2}{2} + \frac{(0.1)^4}{24} = 1 - 0.005 + \frac{0.0001}{24}$$
$$= 1 - 0.005 + 0.0000041\overline{6} \approx 0.9950041\overline{6}$$
5. Error bound (alternating-series: error $\leq$ next term): $|R| \leq (0.1)^6/6! = 10^{-6}/720 \approx 1.39 \times 10^{-9}$.

**EVALUATE**:
- Approximation $\cos(0.1) \approx 0.99500417$, accurate to roughly $9$ decimal places.
- Actual value (calculator): $\cos(0.1) = 0.995004165\ldots$ — matches.
- Sanity check: for small $x$, $\cos x \approx 1 - x^2/2$ dominates, and $x^4/24$ is a tiny correction ($\sim 4 \times 10^{-6}$). The series converges extremely fast near $0$, validating Taylor series as a practical numerical tool.
