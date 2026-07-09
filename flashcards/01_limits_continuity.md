+++
order = 1
subject = "Mathematics"
tags = ["math", "calculus", "limits", "continuity", "epsilon-delta", "squeeze-theorem"]
+++

# Calculus — Limits and Continuity

## 1.1 Why Calculus Starts with Limits

Q: Why does calculus need the concept of a "limit" to get started?
A: Calculus is fundamentally about things that change continuously and about quantities that we cannot compute by plain arithmetic — instantaneous rates of change and exact areas under curves. Both require evaluating expressions that look like $0/0$ or infinite sums of vanishing pieces, which are undefined in algebra. The limit is the tool that rigorously captures what a quantity "approaches" as inputs get arbitrarily close to a target, without requiring that exact value to be attained. Without limits, concepts like velocity at an instant or the slope of a curve at a single point would be meaningless.

Q: What does it mean, intuitively, for $x$ to "approach" a number $a$?
A: It means $x$ takes values closer and closer to $a$ (from either side) without necessarily ever equaling $a$. The idea is about a process, not a destination: we examine the behavior of a function as its input is chosen ever nearer to $a$. Crucially, the value of the function at $a$ itself is ignored — only the behavior arbitrarily near $a$ matters.

C: In calculus, $x \to a$ means $x$ gets [arbitrarily close] to $a$ without necessarily equaling $a$.

Q: Why do we care about the behavior of a function near a point rather than at the point itself?
A: Many of the most important quantities in calculus, such as instantaneous velocity or the slope of a tangent line, are defined by expressions that become $0/0$ when evaluated exactly at the point of interest. By examining the function's behavior as we approach the point, we can extract a well-defined value even where direct evaluation fails. This separation of "value at $a$" from "behavior near $a$" is the key conceptual leap.

## 1.2 Informal Definition of a Limit

C: The notation $\lim_{x\to a} f(x) = L$ means that $f(x)$ can be made [arbitrarily close] to $L$ by taking $x$ sufficiently close to $a$ (but not equal to $a$), where $f$ is a function, $a$ is the input value being approached, and $L$ is the limiting output value.

Q: In the statement $\lim_{x\to a} f(x) = L$, what do $f$, $x$, $a$, and $L$ represent?
A: $f$ is a function of one variable. $x$ is the independent input variable which is allowed to vary. $a$ is the specific value that $x$ is approaching (it need not be in the domain of $f$). $L$ is the real number that the outputs $f(x)$ get arbitrarily close to as $x$ approaches $a$. Note $L$ is a fixed number, not a variable.

Q: Why does the informal definition of a limit say "$x$ close to $a$ but not equal to $a$"?
A: Because the limit describes a trend or approach, not an evaluation. The function $f$ may fail to be defined at $a$, or it may be defined there with a value unrelated to its surrounding behavior (for example, a point pulled off the curve). Excluding $x = a$ lets the limit capture the "surrounding" behavior faithfully, independent of any isolated definition at $a$.

C: In the definition of $\lim_{x\to a} f(x) = L$, the value of $f$ at $x = a$ is [irrelevant], where $f$ is the function and $a$ is the point being approached.

## 1.3 One-Sided Limits

C: The [left-hand limit] $\lim_{x\to a^-} f(x) = L$ means $f(x)$ approaches $L$ as $x$ approaches $a$ through values less than $a$, where $f$ is the function, $a$ is the point approached, and $L$ is the limiting value.

C: The [right-hand limit] $\lim_{x\to a^+} f(x) = L$ means $f(x)$ approaches $L$ as $x$ approaches $a$ through values greater than $a$, where $f$ is the function, $a$ is the approached point, and $L$ is the limiting value.

Q: Why do one-sided limits exist as a separate concept from two-sided limits?
A: Some functions behave differently on the left and right of a point — consider a step function or the function $|x|/x$ near $0$. A single two-sided limit cannot describe such behavior because it would have to take two different values simultaneously. One-sided limits let us describe each side independently, giving precise language for jumps, endpoints of intervals, and asymptotic behavior approached from a single direction.

Q: What is the difference between $\lim_{x\to a^-} f(x)$ and $\lim_{x\to a^+} f(x)$?
A: The minus sign superscript indicates $x$ approaches $a$ from below (through values $x < a$), while the plus sign indicates $x$ approaches from above (through values $x > a$). Both are separate limits in their own right and need not equal each other; when they disagree, the two-sided limit does not exist.

## 1.4 Existence of a Two-Sided Limit

C: The two-sided limit $\lim_{x\to a} f(x)$ exists if and only if [both one-sided limits exist and are equal], where $f$ is the function and $a$ is the point being approached.

Q: Why is the equality of both one-sided limits required for the two-sided limit to exist?
A: The two-sided limit asks for a single value $L$ that $f(x)$ approaches regardless of which side $x$ comes from. If the left-hand and right-hand limits disagree, no single $L$ can satisfy the definition from both sides simultaneously. If either one-sided limit fails to exist at all (for instance, due to oscillation or unbounded growth), then the two-sided limit also fails.

Q: If $\lim_{x\to 1^-} f(x) = 3$ and $\lim_{x\to 1^+} f(x) = 5$, does $\lim_{x\to 1} f(x)$ exist?
A: No. Because the one-sided limits disagree (3 vs. 5), there is no single number $L$ that $f(x)$ approaches from both sides at $x = 1$. The two-sided limit does not exist; this situation describes a jump discontinuity at $x = 1$.

## 1.5 Limits Where the Function Is Undefined

Q: Can $\lim_{x\to a} f(x)$ exist even when $f(a)$ is undefined? Why?
A: Yes. The limit only depends on $f$'s behavior near $a$, not at $a$. A classic example is $f(x) = (x^2 - 1)/(x - 1)$, which is undefined at $x = 1$ (the expression yields $0/0$), yet $f(x) = x + 1$ for all $x \neq 1$, so $\lim_{x\to 1} f(x) = 2$. The limit sees past the "hole" in the graph.

C: A [removable discontinuity] occurs when $\lim_{x\to a} f(x)$ exists but either $f(a)$ is undefined or $f(a) \neq \lim_{x\to a} f(x)$, where $f$ is the function and $a$ is the point in question.

Q: Why is a removable discontinuity called "removable"?
A: Because the limit $L = \lim_{x\to a} f(x)$ exists, we can "remove" the discontinuity by redefining (or defining) $f(a) = L$. This yields a new function that agrees with $f$ everywhere except possibly at $a$, and that is continuous at $a$. The only obstruction to continuity is the isolated point — the surrounding behavior already "wants" to reach $L$.

## 1.6 Formal Epsilon-Delta Definition

C: Formally, $\lim_{x\to a} f(x) = L$ means: for every $\epsilon > 0$ there exists a $\delta > 0$ such that [$0 < |x - a| < \delta$] implies $|f(x) - L| < \epsilon$, where $\epsilon$ is the target output tolerance, $\delta$ is the input tolerance, $a$ is the approached point, and $L$ is the limit.

Q: In the $\epsilon$-$\delta$ definition, what role does $\epsilon$ play and what role does $\delta$ play?
A: $\epsilon$ (epsilon) is a challenge: an arbitrary positive tolerance specifying how close to $L$ we demand $f(x)$ to be. $\delta$ (delta) is the response: a positive distance around $a$ such that all $x$ within that distance (and $x \neq a$) are guaranteed to produce $f(x)$ within $\epsilon$ of $L$. The definition requires a valid $\delta$ to exist for every possible $\epsilon$, no matter how small.

Q: Why does the formal limit definition require $0 < |x - a|$ rather than just $|x - a| < \delta$?
A: The strict inequality $0 < |x - a|$ excludes the case $x = a$. Limits describe behavior as $x$ approaches $a$, never requiring evaluation at $a$ itself. Allowing $x = a$ would force $f(a)$ to equal $L$, destroying the distinction between the value of the function at a point and its limiting behavior around the point.

Q: Why must the $\epsilon$-$\delta$ definition work for every $\epsilon > 0$, not just small ones?
A: The definition demands we can make $f(x)$ arbitrarily close to $L$. If we only handled some values of $\epsilon$, we would not have ruled out the possibility of $f(x)$ staying a fixed distance from $L$. By requiring a $\delta$ for every $\epsilon > 0$, no matter how tiny, we guarantee the function truly homes in on $L$ without any residual gap.

## 1.7 Why Epsilon-Delta Captures "Arbitrarily Close"

Q: Why is the $\epsilon$-$\delta$ definition considered a rigorous version of the informal "arbitrarily close" idea?
A: "Arbitrarily close" means the distance from $f(x)$ to $L$ can be made smaller than any positive number we choose. The $\epsilon$ in the definition is that arbitrary positive number. For each such $\epsilon$, the existence of a working $\delta$ says we have a concrete procedure to force the gap $|f(x) - L|$ below $\epsilon$. Quantifying the informal phrase this way turns a vague intuition into a checkable mathematical statement.

Q: What goes wrong with the informal "limit" idea that the $\epsilon$-$\delta$ definition fixes?
A: The informal idea relies on unquantified words like "close" and "approaches," which are ambiguous and allow pathological counterexamples (such as highly oscillatory functions) to slip through. The $\epsilon$-$\delta$ formulation specifies closeness with explicit numerical tolerances and makes the logical structure (for-every / there-exists) precise, enabling rigorous proofs and eliminating ambiguity.

## 1.8 Limit Laws

C: The [sum law] for limits states $\lim_{x\to a}\lbrack f(x) + g(x)\rbrack  = \lim_{x\to a} f(x) + \lim_{x\to a} g(x)$, provided both individual limits exist, where $f$ and $g$ are functions and $a$ is the approached point.

C: The [product law] for limits states $\lim_{x\to a}\lbrack f(x)g(x)\rbrack  = \big(\lim_{x\to a} f(x)\big)\big(\lim_{x\to a} g(x)\big)$, provided both individual limits exist, where $f$ and $g$ are functions and $a$ is the approached point.

C: The [quotient law] for limits states $\lim_{x\to a}\frac{f(x)}{g(x)} = \frac{\lim_{x\to a} f(x)}{\lim_{x\to a} g(x)}$, provided $\lim_{x\to a} g(x) \neq 0$, where $f$ and $g$ are functions and $a$ is the approached point.

C: The [constant multiple law] for limits states $\lim_{x\to a}\lbrack c \cdot f(x)\rbrack  = c \cdot \lim_{x\to a} f(x)$, where $c$ is a real constant, $f$ is a function, and $a$ is the approached point.

Q: Why does the quotient law require $\lim_{x\to a} g(x) \neq 0$?
A: Division by zero is undefined, so if the denominator's limit is zero, the naive division in the right-hand formula fails. In such cases the actual limit may still exist (requiring separate techniques like factoring or L'Hopital's rule), may be infinite, or may not exist at all. The condition ensures the law gives a meaningful answer.

Q: Why are the limit laws useful in practice?
A: They let us decompose a limit of a complicated expression into limits of simpler building blocks. Combined with the fact that $\lim_{x\to a} x = a$ and $\lim_{x\to a} c = c$ for any constant $c$, the laws allow evaluation of any polynomial or rational limit (when the denominator is nonzero) by direct substitution, without reasoning from the $\epsilon$-$\delta$ definition every time.

## 1.9 Direct Substitution

Q: What does "direct substitution" mean for computing a limit, and when is it valid?
A: Direct substitution means evaluating $\lim_{x\to a} f(x)$ by simply computing $f(a)$. It is valid precisely when $f$ is continuous at $a$ — that is, when the limit equals the function value at $a$. All polynomials, rational functions (where the denominator is nonzero), roots, trigonometric, exponential, and logarithmic functions are continuous on their domains, so direct substitution works at any point in the domain.

C: For any function $f$ continuous at $a$, $\lim_{x\to a} f(x) = [f(a)]$, where $a$ is the approached input and $f(a)$ is the function value at $a$.

Q: Why is it a mistake to always use direct substitution without checking the function first?
A: Direct substitution fails whenever the function is undefined at $a$ (e.g., a zero denominator) or when $a$ lies at a discontinuity. In those cases plugging in either produces an indeterminate form like $0/0$ or a misleading value (a jump or hole that does not reflect the limit). Always verify the substitution is valid before using it.

## 1.10 Indeterminate Forms

C: An expression like $0/0$ that arises when direct substitution is attempted is called an [indeterminate form] because its value cannot be determined without further analysis of the specific functions involved.

Q: Why is $0/0$ called "indeterminate" rather than simply "undefined"?
A: "Undefined" means no value can be assigned. "Indeterminate" is stronger: different pairs of functions producing $0/0$ in a limit can yield any real number, or $\pm\infty$, or no limit at all. For example $\lim_{x\to 0} x/x = 1$, $\lim_{x\to 0} x^2/x = 0$, and $\lim_{x\to 0} x/x^2$ does not exist as a finite number — all three are $0/0$ in form. The symbol tells us we need more work, not that the limit fails.

Q: When does the indeterminate form $0/0$ typically arise in limit problems?
A: It arises when both numerator and denominator share a common factor that vanishes at $a$, such as $\lim_{x\to 2}(x^2 - 4)/(x - 2)$ where both top and bottom equal zero at $x = 2$. Such forms also appear in the definition of the derivative $\lim_{h\to 0}[f(a+h) - f(a)]/h$, which is why resolving $0/0$ limits is so central to calculus.

## 1.11 Algebraic Techniques for 0/0 Limits

Q: Why does factoring often resolve a $0/0$ limit for a rational function?
A: A $0/0$ form in $\lim_{x\to a} p(x)/q(x)$ means $(x - a)$ is a factor of both $p(x)$ and $q(x)$. Since the limit ignores $x = a$ itself, we can cancel the common factor for $x \neq a$, producing a simpler expression whose limit can be found by direct substitution. Factoring exposes and removes the shared root causing the indeterminacy.

Q: Why does multiplying by a conjugate help evaluate limits involving square roots?
A: Multiplying $\sqrt{A} - \sqrt{B}$ by its conjugate $\sqrt{A} + \sqrt{B}$ yields $A - B$, eliminating the square roots. This often reveals a cancellable factor of $(x - a)$ in the numerator that was hidden by the root. After cancellation, direct substitution usually gives the limit.

C: For a $0/0$ limit involving a square root like $\lim_{x\to a}\frac{\sqrt{f(x)} - c}{x - a}$, multiply by the [conjugate] $\sqrt{f(x)} + c$ over itself to rationalize the numerator, where $f$ is a function, $a$ is the approached point, and $c$ is a constant.

## 1.12 Special Limit: sin(x)/x

C: The special trigonometric limit $\lim_{x\to 0} \frac{\sin x}{x} = [1]$, where $x$ is measured in radians.

Q: Why must $x$ be in radians for $\lim_{x\to 0} \sin(x)/x = 1$ to hold?
A: The limit equals the derivative of $\sin x$ at $0$, and the derivative formulas $d/dx[\sin x] = \cos x$ only hold when $x$ is in radians. In degrees, the limit instead equals $\pi/180$, because $\sin(x^\circ)$ equals $\sin(\pi x/180)$ in radians. Radians are the "natural" unit that makes calculus formulas for trig functions clean.

Q: Why is $\lim_{x\to 0} \sin(x)/x = 1$ considered a fundamental special limit?
A: It is the key building block for differentiating all trigonometric functions. It also captures the geometric fact that for small angles (in radians), $\sin x \approx x$ — the arc and the chord of a unit circle become indistinguishable as the angle shrinks. Many other trig limits reduce to this one.

## 1.13 Special Limit: (1 - cos x)/x

C: The special trigonometric limit $\lim_{x\to 0} \frac{1 - \cos x}{x} = [0]$, where $x$ is measured in radians.

Q: Why does $\lim_{x\to 0}(1 - \cos x)/x = 0$ even though both numerator and denominator vanish at $x = 0$?
A: Near $x = 0$, $1 - \cos x$ behaves like $x^2/2$ (from its Taylor expansion), while the denominator is $x$. The ratio behaves like $x/2$, which approaches $0$. Algebraically, multiplying by the conjugate $(1+\cos x)/(1+\cos x)$ converts the numerator to $\sin^2 x$ and yields $\sin x \cdot (\sin x/x) \cdot 1/(1+\cos x) \to 0 \cdot 1 \cdot 1/2 = 0$.

## 1.14 The Squeeze Theorem

C: The [Squeeze Theorem] (also called Sandwich Theorem) states: if $g(x) \leq f(x) \leq h(x)$ near $a$ (except possibly at $a$) and $\lim_{x\to a} g(x) = \lim_{x\to a} h(x) = L$, then $\lim_{x\to a} f(x) = L$, where $g$ and $h$ are the bounding functions, $f$ is the function being evaluated, $a$ is the approached point, and $L$ is the common limit.

Q: Why does the Squeeze Theorem work intuitively?
A: If $f$ is trapped between two functions that both approach $L$, then $f$ has no room to go anywhere else — every value of $f(x)$ near $a$ lies within the shrinking gap between $g(x)$ and $h(x)$, and that gap closes around $L$. Since $f$ cannot escape bounds that collapse to a single point, its limit must also be $L$.

Q: When is the Squeeze Theorem most useful?
A: When $f$ itself is too wild to analyze directly — for example, when it involves an oscillating factor like $\sin(1/x)$ — but we can bound it above and below by simpler functions whose limits we can compute. Bounding $\sin$ and $\cos$ by $\pm 1$ is the most common application, turning products involving bounded oscillation into tractable limits.

## 1.15 Infinite Limits and Vertical Asymptotes

C: We write $\lim_{x\to a} f(x) = [\infty]$ to mean $f(x)$ grows without bound as $x$ approaches $a$, where $f$ is the function and $a$ is the approached point. This limit does not "exist" as a finite number but the notation describes the unbounded behavior.

C: A [vertical asymptote] of $f$ occurs at $x = a$ if $\lim_{x\to a^-} f(x) = \pm\infty$ or $\lim_{x\to a^+} f(x) = \pm\infty$, where $f$ is the function and $a$ is the location of the asymptote.

Q: Why don't infinite limits count as "existing limits" in the usual sense?
A: The definition of a limit requires a real number $L$ that $f(x)$ approaches; $\infty$ is not a real number but a description of unbounded growth. Saying "$\lim = \infty$" is a convenient shorthand for "the limit does not exist, and specifically $f$ grows without bound." Still, this behavior is important enough to deserve its own notation because it describes asymptotes.

Q: Why do rational functions typically have vertical asymptotes where the denominator is zero?
A: When the denominator of $p(x)/q(x)$ approaches zero while the numerator approaches a nonzero value, the quotient's magnitude blows up. If the denominator vanishes but the numerator also vanishes (yielding $0/0$), the point may instead be a removable discontinuity — so vertical asymptotes require the denominator alone to vanish while the numerator stays nonzero.

## 1.16 Limits at Infinity and Horizontal Asymptotes

C: The notation $\lim_{x\to \infty} f(x) = L$ means that $f(x)$ can be made arbitrarily close to $L$ by taking $x$ [sufficiently large], where $f$ is the function and $L$ is the limiting value.

C: A [horizontal asymptote] of $f$ at level $L$ means $\lim_{x\to \infty} f(x) = L$ or $\lim_{x\to -\infty} f(x) = L$, where $f$ is the function and $L$ is the level the outputs approach.

Q: What is the difference between a limit at infinity and an infinite limit?
A: A limit at infinity, $\lim_{x\to\infty} f(x)$, asks what value $f$ approaches as the input grows without bound — the limit may be a finite number, infinite, or nonexistent. An infinite limit, $\lim_{x\to a} f(x) = \infty$, asks what the output does as $x$ approaches a finite point $a$ — describing unbounded growth of the output. One concerns large inputs; the other concerns large outputs.

Q: For a rational function $p(x)/q(x)$, how does the degree of numerator and denominator determine the limit at infinity?
A: If $\deg(p) < \deg(q)$, the limit is $0$ (denominator dominates). If $\deg(p) = \deg(q)$, the limit is the ratio of leading coefficients. If $\deg(p) > \deg(q)$, the magnitude grows without bound, so the limit is $\pm\infty$ depending on signs. This reflects which term dominates as $x$ becomes very large.

## 1.17 Continuity at a Point

C: A function $f$ is continuous at $x = a$ if three conditions hold: (1) $f(a)$ is [defined], (2) $\lim_{x\to a} f(x)$ exists, and (3) $\lim_{x\to a} f(x) = f(a)$, where $f$ is the function and $a$ is the point in question.

Q: Why does the definition of continuity at $a$ require all three conditions rather than just one?
A: Each condition rules out a different failure mode. Condition (1) rules out holes where $f$ is not defined; (2) rules out jumps and blow-ups where no limit exists; (3) rules out the case where both $f(a)$ and the limit exist but disagree (a point pulled off the curve). Any one condition failing breaks continuity, so all three are needed to guarantee "no break" at $a$.

Q: Intuitively, what does continuity at a point mean?
A: It means the graph of $f$ has no break, hole, or jump at $x = a$ — you could draw through $a$ without lifting your pencil. Equivalently, small changes in input produce small changes in output near $a$, with no sudden surprises. Formally, the function's limiting behavior matches its actual value.

## 1.18 Continuity on an Interval; Common Continuous Functions

C: A function is [continuous on an interval] if it is continuous at every point of that interval (with one-sided continuity at any endpoints included in the interval).

Q: Which families of functions are continuous on their entire domains?
A: Polynomials (continuous on all of $\mathbb{R}$), rational functions (continuous except where the denominator is zero), root functions (continuous on their domains), exponential and logarithmic functions, and trigonometric functions (continuous except where they are undefined, like $\tan x$ at odd multiples of $\pi/2$). Sums, products, quotients, and compositions of continuous functions are continuous wherever the result is defined.

Q: Why are compositions of continuous functions continuous?
A: If $g$ is continuous at $a$ and $f$ is continuous at $g(a)$, then a small change in $x$ near $a$ produces a small change in $g(x)$ near $g(a)$, which in turn produces a small change in $f(g(x))$ near $f(g(a))$. The chain of "small changes produce small changes" preserves continuity through composition.

## 1.19 Intermediate Value Theorem

C: The [Intermediate Value Theorem (IVT)] states: if $f$ is continuous on the closed interval $\lbrack a, b\rbrack $ and $N$ is any value between $f(a)$ and $f(b)$, then there exists at least one $c$ in $\lbrack a, b\rbrack $ with $f(c) = N$, where $f$ is the function, $\lbrack a, b\rbrack $ is the interval, $N$ is the target output value, and $c$ is the guaranteed input.

Q: Why does the IVT require continuity — what breaks if the function is discontinuous?
A: The IVT relies on the graph of $f$ being an unbroken curve from $(a, f(a))$ to $(b, f(b))$; any horizontal line at height $N$ between the endpoints must be crossed. A discontinuity introduces a jump, and the curve may skip over $N$ entirely — going from below $N$ directly to above $N$ without ever achieving $N$. Continuity forbids such skips.

Q: What is a typical application of the IVT?
A: Proving that equations have solutions without having to find them. If a continuous function changes sign on $[a, b]$ (so $f(a) < 0 < f(b)$), the IVT guarantees a root $c$ with $f(c) = 0$. This is the foundation of root-finding methods like bisection, and it lets us prove existence results for zeros of polynomials, fixed points, and solutions to transcendental equations.

## 1.20 Types of Discontinuities

C: A [removable discontinuity] at $a$ occurs when $\lim_{x\to a} f(x)$ exists but differs from $f(a)$ (or $f(a)$ is undefined), where $f$ is the function and $a$ is the discontinuity point.

C: A [jump discontinuity] at $a$ occurs when both one-sided limits of $f$ at $a$ exist but are not equal, where $f$ is the function and $a$ is the discontinuity point.

C: An [infinite discontinuity] at $a$ occurs when at least one one-sided limit of $f$ at $a$ is $\pm\infty$, producing a vertical asymptote, where $f$ is the function and $a$ is the discontinuity point.

Q: How can you tell the three discontinuity types apart from a graph?
A: A removable discontinuity looks like an isolated hole in an otherwise smooth curve (possibly with a stray dot off to the side). A jump discontinuity looks like a step: the curve arrives at one height from the left and suddenly starts at a different height on the right. An infinite discontinuity shows the curve shooting up to $+\infty$ or down to $-\infty$ at a vertical asymptote.

Q: Why is only the first type called "removable"?
A: Because we can define (or redefine) $f(a)$ to equal $\lim_{x\to a} f(x)$, curing the discontinuity with a single point change. Jump discontinuities cannot be removed this way because the two one-sided limits disagree — no single value of $f(a)$ can match both. Infinite discontinuities cannot be removed at all because the function is unbounded near $a$.

## 1.21 Worked Problem: Evaluating a 0/0 Limit by Factoring

P: Evaluate $\lim_{x\to 2}\frac{x^2 - 4}{x - 2}$ using algebra.

S:
**IDENTIFY**: This is a limit of a rational function where direct substitution of $x = 2$ gives $(4 - 4)/(2 - 2) = 0/0$, an indeterminate form. The $0/0$ signals that $(x - 2)$ is a common factor of numerator and denominator.

**PLAN**:
- Factor the numerator to expose the shared factor of $(x - 2)$.
- Cancel the common factor, which is valid because the limit ignores $x = 2$ itself.
- Apply direct substitution to the simplified expression.

**EXECUTE**:
1. Factor the numerator using difference of squares: $x^2 - 4 = (x - 2)(x + 2)$.
2. Rewrite the expression: $\frac{(x - 2)(x + 2)}{x - 2}$.
3. Cancel $(x - 2)$ for $x \neq 2$, leaving $x + 2$.
4. Take the limit by direct substitution: $\lim_{x\to 2}(x + 2) = 2 + 2 = 4$.

**EVALUATE**:
- The answer $L = 4$ is finite, as expected for a removable discontinuity.
- Sanity check: plug $x = 2.01$ into the original expression: $(4.0401 - 4)/(0.01) = 4.01$, close to $4$. Plug $x = 1.99$: $(3.9601 - 4)/(-0.01) = 4.01$. Both sides approach $4$, confirming the result.
- Geometric interpretation: $f(x) = (x^2 - 4)/(x - 2)$ is identical to the line $y = x + 2$ except for a hole at $(2, 4)$; the limit fills that hole.

## 1.22 Worked Problem: Applying the Squeeze Theorem

P: Use the Squeeze Theorem to show $\lim_{x\to 0} x^2 \sin(1/x) = 0$.

S:
**IDENTIFY**: A limit as $x \to 0$ of a product where $\sin(1/x)$ oscillates infinitely often near $x = 0$ (so it has no limit on its own), multiplied by $x^2$ which approaches $0$. The oscillating factor is bounded, so the Squeeze Theorem applies.

**PLAN**:
- Bound $\sin(1/x)$ between $-1$ and $1$ using the standard range of sine.
- Multiply the bounds by $x^2$ (positive for $x \neq 0$, so inequalities preserve direction) to get bounds on the whole expression.
- Compute the limits of the two bounding functions; if they agree, the Squeeze Theorem delivers the answer.

**EXECUTE**:
1. For all $x \neq 0$, $-1 \leq \sin(1/x) \leq 1$ because sine's range is $[-1, 1]$ regardless of input.
2. Multiply through by $x^2 \geq 0$: $-x^2 \leq x^2 \sin(1/x) \leq x^2$.
3. Compute the limits of the bounds: $\lim_{x\to 0}(-x^2) = 0$ and $\lim_{x\to 0} x^2 = 0$.
4. Since both bounds approach $0$ and the middle expression is trapped between them near $x = 0$, the Squeeze Theorem gives $\lim_{x\to 0} x^2 \sin(1/x) = 0$.

**EVALUATE**:
- The result is intuitive: even though $\sin(1/x)$ oscillates wildly as $x \to 0$, the $x^2$ factor damps the amplitude to zero.
- Note that $\sin(1/x)$ alone has no limit at $0$ (it oscillates between $-1$ and $1$ forever), so this problem genuinely needs the Squeeze Theorem — limit laws like "limit of product equals product of limits" would fail here because one factor's limit does not exist.
- The technique generalizes: any bounded function multiplied by something approaching $0$ has a limit of $0$.
