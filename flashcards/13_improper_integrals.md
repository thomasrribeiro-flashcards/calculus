+++
order = 13
subject = "Math"
tags = ["math", "calculus", "improper-integrals", "convergence", "divergence", "comparison-test"]
+++

# Calculus — Improper Integrals

## 13.1 Why the Riemann Integral Definition Fails

Q: Why does the standard Riemann integral definition fail on an unbounded interval like $[1, \infty)$?
A: The Riemann construction partitions a closed, bounded interval $[a,b]$ into finitely many pieces of finite width. An unbounded interval admits no such finite partition, so the limit-of-Riemann-sums definition simply has nothing to operate on. We must extend the definition via a separate limiting process.

Q: Why does the Riemann integral also fail when the integrand $f$ is unbounded on $[a,b]$?
A: Riemann sums require choosing sample values $f(x_i^*)$ in each subinterval; if $f$ blows up near some point, those sample values are unbounded and the sums have no finite limit. Again we need a separate limit that carefully approaches the singularity from a safe distance.

C: An integral is called [improper] when the interval is infinite or when the integrand is unbounded on the interval of integration.

## 13.2 Type 1: Infinite Interval

C: A [Type 1 improper integral] has an infinite interval of integration, e.g. $\int_a^\infty f(x)\,dx$, where $a$ is a finite real lower bound.

Q: What conceptual question does $\int_1^\infty f(x)\,dx$ ask?
A: It asks whether the total area under $y=f(x)$ over the entire unbounded interval $[1,\infty)$ is a finite number. Intuitively, even though the region extends forever, the function may decay fast enough that the accumulated area settles to a finite limit.

## 13.3 Type 1 Definition as a Limit

C: For $f$ continuous on $[a,\infty)$, we define $\int_a^\infty f(x)\,dx = \lim_{b\to\infty}\int_a^b f(x)\,dx$, where $b$ is a finite upper bound that grows without bound.

Q: Why define $\int_a^\infty f\,dx$ using a limit over a proper integral, rather than directly?
A: On each finite interval $[a,b]$ the ordinary Riemann integral is well defined, producing a function $F(b)=\int_a^b f\,dx$. Taking $\lim_{b\to\infty}F(b)$ transfers the problem to a standard real-number limit, for which we already have tools (L'Hopital, squeeze theorem, etc.).

## 13.4 Convergence vs Divergence

C: An improper integral [converges] if the defining limit exists as a finite real number, and [diverges] otherwise (including to $\pm\infty$ or by oscillation).

Q: Can an improper integral "diverge" in more than one way?
A: Yes. The limit can fail to exist by tending to $+\infty$, by tending to $-\infty$, or by oscillating without approaching any value (e.g. $\int_0^\infty \cos x\,dx$). All three cases are lumped together as divergence: only a finite limit counts as convergence.

## 13.5 Doubly Infinite Intervals

C: For $f$ continuous on $\mathbb{R}$, we split $\int_{-\infty}^\infty f(x)\,dx = [\int_{-\infty}^c f(x)\,dx + \int_c^\infty f(x)\,dx]$, where $c$ is any finite real number.

Q: Why is the choice of split point $c$ in $\int_{-\infty}^\infty f\,dx$ irrelevant to convergence?
A: Any two choices $c_1, c_2$ differ by the proper integral $\int_{c_1}^{c_2} f\,dx$, which is a finite number. Adding a finite constant to either piece cannot change whether the total limit is finite, so convergence and the total value are independent of $c$.

## 13.6 Both Pieces Must Converge Independently

C: $\int_{-\infty}^\infty f(x)\,dx$ converges only if [both] $\int_{-\infty}^c f\,dx$ and $\int_c^\infty f\,dx$ converge separately; we do not take a single symmetric limit.

Q: Why isn't $\lim_{R\to\infty}\int_{-R}^R f(x)\,dx$ a valid definition of $\int_{-\infty}^\infty f\,dx$?
A: A symmetric limit can conceal cancellation. For $f(x)=x$, the symmetric limit is $0$ for every $R$, yet each half $\int_0^\infty x\,dx$ diverges, so the true doubly infinite integral does not exist. Requiring both halves to converge independently rules out this false convergence (called the Cauchy principal value).

## 13.7 Type 2: Unbounded Integrand

C: A [Type 2 improper integral] has a finite interval but an integrand with a vertical asymptote (infinite discontinuity) at an endpoint or interior point.

Q: Give a canonical example of a Type 2 improper integral and explain why it is improper.
A: $\int_0^1 \frac{1}{\sqrt{x}}\,dx$ is Type 2 because $1/\sqrt{x}\to\infty$ as $x\to 0^+$. The interval $[0,1]$ is finite, but the integrand is unbounded near the left endpoint, so the ordinary Riemann integral does not apply and we need a limiting definition.

## 13.8 Type 2 Definition as a Limit

C: If $f$ is continuous on $(a,b]$ with $\lim_{x\to a^+}f(x)=\pm\infty$, we define $\int_a^b f(x)\,dx = [\lim_{t\to a^+}\int_t^b f(x)\,dx]$, where $t$ approaches the singularity from inside the interval.

Q: Why must $t\to a^+$ (one-sided) in the Type 2 limit, rather than a general two-sided limit?
A: The function is only defined on one side of the singularity within the integration interval, so only that side is available. Approaching from the right ensures $t$ stays inside $(a,b]$ where $f$ is continuous and the inner integral $\int_t^b f\,dx$ is an ordinary Riemann integral.

## 13.9 Interior Singularities

C: If $f$ has a singularity at an interior point $c\in(a,b)$, we split $\int_a^b f\,dx = \int_a^c f\,dx + \int_c^b f\,dx$ and require each piece to [converge independently].

Q: Why is blindly computing $\int_{-1}^1 \frac{1}{x}\,dx$ by antiderivative wrong?
A: The integrand has a singularity at $x=0$, an interior point. Writing $\ln|x|\Big|_{-1}^1 = 0$ ignores that both $\int_{-1}^0$ and $\int_0^1$ of $1/x$ diverge to $-\infty$ and $+\infty$ respectively. By the independence requirement, the full integral diverges; the cancellation is illusory.

## 13.10 p-Integral at Infinity

C: $\int_1^\infty \frac{1}{x^p}\,dx$ converges iff [$p > 1$], and its value is $\frac{1}{p-1}$.

Q: Derive why $\int_1^\infty \frac{1}{x^p}\,dx$ converges precisely when $p>1$.
A: For $p\neq 1$, $\int_1^b x^{-p}\,dx = \frac{b^{1-p}-1}{1-p}$. As $b\to\infty$, $b^{1-p}\to 0$ iff $1-p<0$, i.e. $p>1$, giving limit $\frac{1}{p-1}$. For $p\leq 1$ the power $b^{1-p}$ grows (or for $p=1$, $\ln b$ grows), so the integral diverges.

## 13.11 p-Integral Near Zero

C: $\int_0^1 \frac{1}{x^p}\,dx$ converges iff [$p < 1$], and its value is $\frac{1}{1-p}$.

Q: Derive why $\int_0^1 \frac{1}{x^p}\,dx$ converges precisely when $p<1$.
A: For $p\neq 1$, $\int_t^1 x^{-p}\,dx = \frac{1-t^{1-p}}{1-p}$. As $t\to 0^+$, $t^{1-p}\to 0$ iff $1-p>0$, i.e. $p<1$, giving limit $\frac{1}{1-p}$. For $p\geq 1$, $t^{1-p}$ (or $\ln t$ when $p=1$) blows up and the integral diverges.

## 13.12 Why the p-Rules Flip

Q: Why does large $p$ help convergence at infinity but hurt it near zero?
A: At infinity, a large $p$ makes $1/x^p$ decay faster, so the tail area shrinks quickly enough to be finite. Near zero, a large $p$ makes $1/x^p$ blow up faster, so the spike near the singularity is too sharp to integrate. In both places what matters is whether the singularity is "mild enough" — tails must decay fast, spikes must grow slowly.

C: The p-integral convergence rules are opposite because fast decay helps at infinity but fast growth [hurts] near a finite singularity.

## 13.13 Direct Comparison Test

C: If $0 \leq f(x) \leq g(x)$ on $[a,\infty)$ and $\int_a^\infty g\,dx$ [converges], then $\int_a^\infty f\,dx$ converges, where $f$ and $g$ are both continuous and nonnegative.

Q: Why does $0\leq f\leq g$ with $\int g<\infty$ force $\int f$ to converge?
A: Because $f\geq 0$, the partial integral $F(b)=\int_a^b f\,dx$ is monotonically increasing in $b$. The inequality $f\leq g$ gives $F(b)\leq \int_a^b g\,dx \leq \int_a^\infty g\,dx$, a finite upper bound. A monotone bounded sequence converges, so $\lim_{b\to\infty}F(b)$ exists.

## 13.14 Contrapositive of Comparison

C: If $0\leq f\leq g$ and $\int_a^\infty f\,dx$ [diverges], then $\int_a^\infty g\,dx$ also diverges.

Q: When applying comparison, how do you decide whether to look for a larger or a smaller comparison function?
A: To prove convergence of $\int f$, dominate it above: find $g\geq f$ whose integral is known to converge. To prove divergence of $\int g$, bound it below: find $f\leq g$ whose integral is known to diverge. Going the wrong direction (smaller than something divergent, larger than something convergent) gives no information.

## 13.15 Limit Comparison Test

C: If $f,g>0$ on $[a,\infty)$ and $\lim_{x\to\infty}\frac{f(x)}{g(x)} = L$ with $0<L<\infty$, then $\int_a^\infty f\,dx$ and $\int_a^\infty g\,dx$ [either both converge or both diverge].

Q: Why is limit comparison often easier than direct comparison?
A: Direct comparison demands a clean pointwise inequality, which can fail on small regions or require tedious algebra. Limit comparison only needs the ratio to tend to a positive finite constant, capturing that $f$ and $g$ have the same asymptotic magnitude. For rational or algebraic integrands, you just pick $g$ as the dominant-term behavior at infinity.

## 13.16 Absolute Convergence

C: If $\int_a^\infty |f(x)|\,dx$ converges, then $\int_a^\infty f(x)\,dx$ converges; we say $\int f$ converges [absolutely].

Q: Why does absolute convergence imply convergence for improper integrals?
A: Write $f = f^+ - f^-$ where $f^+ = \max(f,0)\geq 0$ and $f^- = \max(-f,0)\geq 0$, so $|f|=f^++f^-$. If $\int|f|$ is finite, then both nonnegative pieces $\int f^\pm$ are bounded by it, hence convergent by monotone boundedness. Their difference $\int f$ is then a difference of two finite numbers.

Q: Why does absolute convergence matter practically?
A: It lets you apply comparison tests (which require nonnegative integrands) to a signed or oscillating $f$ by studying $|f|$ instead. Once $\int |f|$ is shown finite, we get $\int f$ for free, sidestepping the delicate cancellation analysis that oscillating integrals would otherwise require.

## 13.17 Canonical Examples

C: $\int_0^\infty e^{-x}\,dx = [1]$, the prototypical convergent Type 1 integral.

Q: Why does $\int_0^\infty e^{-x}\,dx$ converge while $\int_1^\infty \frac{1}{x}\,dx$ diverges, even though both integrands tend to zero?
A: Convergence is about how fast the integrand decays, not just that it decays. $e^{-x}$ decays exponentially — faster than any polynomial — giving a tail that shrinks rapidly enough for a finite total. $1/x$ decays only like a power with $p=1$, which is exactly on the divergent side of the $p$-test threshold. Decaying to zero is necessary but not sufficient.

C: $\int_1^\infty \frac{1}{x}\,dx = [\infty]$ (diverges), the boundary case of the $p$-test at infinity.

## 13.18 Applications: Probability Densities

Q: Why do improper integrals appear in probability theory?
A: A probability density function $f$ on $\mathbb{R}$ must satisfy $\int_{-\infty}^\infty f(x)\,dx = 1$, because total probability is $1$. Since real-valued random variables can in principle take any real value, this normalization is inherently an improper integral on the doubly infinite interval.

C: For a valid probability density $f$ on $\mathbb{R}$, we require $f(x)\geq 0$ and $\int_{-\infty}^\infty f(x)\,dx = [1]$.

Q: Why must a probability density decay at infinity?
A: If $f$ did not tend to zero fast enough, its integral over $\mathbb{R}$ would diverge and could not equal $1$. Convergence of the normalization integral forces tail decay (e.g. the Gaussian $e^{-x^2/2}$ decays extremely fast, guaranteeing a finite, normalizable total mass).

## 13.19 Evaluating $\int_1^\infty \frac{1}{x^2}\,dx$

P: Evaluate $\int_1^\infty \frac{1}{x^2}\,dx$, where the integrand is $1/x^2$ on the infinite interval $[1,\infty)$.

S:
**IDENTIFY**: Type 1 improper integral (infinite upper limit), $p$-integral form with $p=2>1$, so we expect convergence.

**PLAN**:
- Rewrite as $\lim_{b\to\infty}\int_1^b x^{-2}\,dx$ to convert into a standard Riemann integral plus a real-number limit.
- Apply the power rule antiderivative $\int x^{-2}\,dx = -x^{-1}+C$.
- Evaluate at the bounds and take $b\to\infty$.

**EXECUTE**:
1. $\int_1^b x^{-2}\,dx = \left[-\frac{1}{x}\right]_1^b = -\frac{1}{b} + 1 = 1 - \frac{1}{b}$.
2. Take the limit: $\lim_{b\to\infty}\left(1 - \tfrac{1}{b}\right) = 1 - 0 = 1$.
3. Conclude $\int_1^\infty \frac{1}{x^2}\,dx = 1$.

**EVALUATE**:
- The limit is a finite real number, so the integral converges; its value is $1$.
- Sanity check with $p$-rule: $\frac{1}{p-1} = \frac{1}{2-1} = 1$. ✓
- Geometric sense: the tail area beyond $x=b$ equals $1/b$, which shrinks to $0$, so the cumulative area stabilizes at $1$.

## 13.20 Comparison Test on $\int_1^\infty \frac{1}{\sqrt{x^3+1}}\,dx$

P: Determine whether $\int_1^\infty \frac{1}{\sqrt{x^3+1}}\,dx$ converges, where the integrand $f(x)=1/\sqrt{x^3+1}$ is positive and continuous on $[1,\infty)$.

S:
**IDENTIFY**: Type 1 improper integral with positive integrand; direct evaluation is hard because $1/\sqrt{x^3+1}$ has no elementary antiderivative. This calls for a comparison test.

**PLAN**:
- Identify the dominant behavior of $\sqrt{x^3+1}$ as $x\to\infty$: the "+1" becomes negligible, so $\sqrt{x^3+1}\approx x^{3/2}$.
- Therefore compare $f(x)=1/\sqrt{x^3+1}$ against $g(x)=1/x^{3/2}$, a $p$-integral with $p=3/2>1$ (known convergent).
- Establish a pointwise inequality $0 \leq f(x) \leq g(x)$, then apply the direct comparison test.

**EXECUTE**:
1. For $x\geq 1$: $x^3 + 1 \geq x^3 > 0$, so $\sqrt{x^3+1} \geq \sqrt{x^3} = x^{3/2}$.
2. Taking reciprocals of positive quantities reverses the inequality: $0 < \frac{1}{\sqrt{x^3+1}} \leq \frac{1}{x^{3/2}}$.
3. The dominating integral $\int_1^\infty \frac{1}{x^{3/2}}\,dx$ converges by the $p$-test ($p=3/2>1$), with value $\frac{1}{3/2-1}=2$.
4. By direct comparison, $\int_1^\infty \frac{1}{\sqrt{x^3+1}}\,dx$ converges (and its value is at most $2$).

**EVALUATE**:
- Convergence was the expected outcome since $f$ behaves asymptotically like $1/x^{3/2}$.
- Verification via limit comparison: $\lim_{x\to\infty}\frac{1/\sqrt{x^3+1}}{1/x^{3/2}} = \lim_{x\to\infty}\frac{x^{3/2}}{\sqrt{x^3+1}} = 1$, a finite positive constant, so both integrals share the same convergence status. ✓
- Note we did NOT compute the exact value; the comparison test only certifies convergence, which is often all we need.
