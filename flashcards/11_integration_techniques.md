+++
order = 11
subject = "Math"
tags = ["math", "calculus", "integration", "u-substitution", "integration-by-parts", "partial-fractions", "trig-substitution"]
+++

# Calculus — Techniques of Integration

## 11.1 Why Techniques Are Needed

Q: Why do we need specialized integration techniques beyond a basic list of antiderivatives?
A: Most integrands don't match a basic rule directly. Integration is pattern-recognition: the techniques (substitution, parts, trig sub, partial fractions) are systematic ways to transform an integrand into a form whose antiderivative is known.

Q: Why is integration fundamentally harder than differentiation?
A: Every elementary function has an elementary derivative, but many elementary functions (e.g. $e^{-x^2}$ or $\sin(x)/x$) have no elementary antiderivative. So integration sometimes fails outright, and even when it succeeds, there is no single algorithm — we must guess a transformation, try it, and verify by differentiating back.

C: The set of functions we can differentiate mechanically is [larger] than the set we can integrate in closed form.

## 11.2 $u$-Substitution — Reversing the Chain Rule

Q: What differentiation rule does $u$-substitution reverse, and why does that matter?
A: It reverses the chain rule. The chain rule says $\frac{d}{dx}F(g(x)) = F'(g(x))\cdot g'(x)$, so integrating $F'(g(x))\cdot g'(x)$ must give $F(g(x)) + C$. Substitution is just a bookkeeping device that lets us recognize this pattern and compute the antiderivative of $F'$ in a cleaner variable.

C: $u$-substitution is the integration technique that reverses the [chain rule] of differentiation.

Q: Before seeing the general procedure, predict: if the integrand contains $f(g(x))$ multiplied by $g'(x)$, what substitution should work?
A: Let $u = g(x)$. Then $du = g'(x)\,dx$, and the integral becomes $\int f(u)\,du$, which is usually much simpler because the inner function has been absorbed into $u$.

## 11.3 Procedure for $u$-Substitution

P: What is the general step-by-step procedure for $u$-substitution on an indefinite integral $\int h(x)\,dx$?

S:
**IDENTIFY**: Indefinite integral where the integrand contains a composite function $f(g(x))$ and (up to a constant factor) the derivative $g'(x)$ is also present.

**PLAN**:
- Choose $u = g(x)$ (the inner function of the composite)
- Compute $du = g'(x)\,dx$
- Rewrite the entire integrand in terms of $u$ and $du$

**EXECUTE**:
1. Set $u = g(x)$, so $du = g'(x)\,dx$
2. Solve for $dx$ if needed: $dx = du / g'(x)$
3. Substitute to get $\int f(u)\,du$ — every $x$ must disappear
4. Compute $\int f(u)\,du = F(u) + C$ using a known antiderivative
5. Back-substitute $u = g(x)$ to get the answer in $x$: $F(g(x)) + C$

**EVALUATE**:
- Check by differentiating $F(g(x))$ via the chain rule; it must equal the original integrand
- If any $x$ remains after substitution, the choice of $u$ was wrong — try a different inner function

## 11.4 Adjusting Bounds for Definite Integrals

Q: When doing $u$-substitution on a definite integral $\int_a^b f(g(x))g'(x)\,dx$, why can (and should) you change the bounds instead of back-substituting?
A: Because $u = g(x)$ is a new variable, the original limits $x = a$ and $x = b$ are $x$-values and don't apply to $u$. Converting them to $u$-values via $u(a) = g(a)$ and $u(b) = g(b)$ lets you evaluate $\int_{g(a)}^{g(b)} f(u)\,du$ directly, skipping the back-substitution step and avoiding mistakes.

C: In a definite integral, after substituting $u = g(x)$, the new limits of integration are $u = [g(a)]$ and $u = [g(b)]$.

Q: What goes wrong if you change the variable to $u$ but forget to change the bounds?
A: You would evaluate $F(u)$ at the old $x$-limits, which is meaningless — the numbers $a$ and $b$ refer to values of $x$, not $u$. You must either (1) change the bounds to $g(a)$ and $g(b)$, or (2) back-substitute to $x$ before plugging in $a$ and $b$.

## 11.5 Recognizing When $u$-Substitution Works

Q: What structural feature of an integrand signals that $u$-substitution will work?
A: The integrand has the form $f(g(x)) \cdot g'(x)$ — a composite function times (a constant multiple of) the derivative of its inner function. Common clues: a "messy" inner expression whose derivative, up to a constant, is sitting as another factor in the integrand.

C: $u$-substitution works when the integrand has the shape $f(g(x))\cdot [g'(x)]$, up to a constant multiple.

Q: Why is $\int x \cos(x^2)\,dx$ a good candidate for $u$-substitution, while $\int \cos(x^2)\,dx$ is not?
A: In the first integral, the derivative of the inner function $x^2$ is $2x$, which matches (up to a factor of $2$) the $x$ already multiplying $\cos(x^2)$. Setting $u = x^2$ gives $du = 2x\,dx$, cleanly converting the integral to $\frac{1}{2}\int \cos u\,du$. In the second integral, there is no $x$ factor to absorb the $du$, so $u$-sub fails — and in fact $\int \cos(x^2)\,dx$ has no elementary antiderivative.

## 11.6 Integration by Parts

C: The integration by parts formula is $\int u\,dv = [uv - \int v\,du]$.

Q: What is integration by parts, and when should you reach for it?
A: It is the integration technique that reverses the product rule. Reach for it when the integrand is a product of two functions of different types (e.g. polynomial times exponential, or polynomial times logarithm), where one factor simplifies when differentiated and the other remains easy to integrate.

## 11.7 Derivation from the Product Rule

Q: Derive the integration-by-parts formula from the product rule.
A: Start with $(uv)' = u'v + uv'$, where $u$ and $v$ are functions of $x$. Integrate both sides: $\int (uv)'\,dx = \int u'v\,dx + \int uv'\,dx$, giving $uv = \int v\,du + \int u\,dv$. Rearranging yields $\int u\,dv = uv - \int v\,du$.

C: Integration by parts comes from integrating the [product rule] $(uv)' = u'v + uv'$ and solving for one of the two integrals on the right.

## 11.8 Choosing $u$ and $dv$ — LIATE

Q: What is the LIATE heuristic, and why does it help?
A: LIATE is a priority list for choosing $u$ in integration by parts: Logarithmic, Inverse trig, Algebraic (polynomial), Trig, Exponential. Whichever type appears first in the list should be chosen as $u$ (the factor to differentiate); the other factor becomes $dv$ (the factor to integrate). It works because functions earlier in the list tend to get simpler when differentiated (logs and inverse trig collapse to algebraic expressions), while those later are easy to integrate.

C: The LIATE priority for choosing $u$ in integration by parts is [Logarithmic], Inverse trig, Algebraic, Trig, Exponential.

Q: In $\int x \ln x\,dx$, which factor should be $u$ and why?
A: Let $u = \ln x$, because logs come first in LIATE and $\ln x$ simplifies to $1/x$ when differentiated. Then $dv = x\,dx$, so $du = dx/x$ and $v = x^2/2$. The resulting $\int v\,du = \int x/2\,dx$ is elementary.

## 11.9 Solvable Loops in Integration by Parts

Q: How can integration by parts produce an equation you can solve algebraically for the original integral?
A: For integrands like $e^x \sin x$, applying IBP twice produces $\int e^x \sin x\,dx = (\text{stuff}) - \int e^x \sin x\,dx$. The same integral reappears on the right with the opposite sign, so you move it to the left side: $2\int e^x \sin x\,dx = (\text{stuff})$, then divide by $2$. The "loop" becomes a linear equation in the unknown integral.

C: For $\int e^x \sin x\,dx$, two applications of integration by parts make the original integral [reappear] on the right-hand side, letting you solve algebraically.

Q: Why does the loop trick work only when the integrand is a product of an exponential and a trig function (or similar pair)?
A: Both $e^x$ and $\sin x / \cos x$ reproduce themselves (up to sign) after one or two derivatives. So after two applications of IBP, the structure of the integrand recurs, giving an equation involving the original integral. For pairs where differentiation eventually kills one factor (like polynomial × exponential), the process terminates instead of looping.

## 11.10 Tabular Integration

Q: What is tabular integration, and when is it ideal?
A: Tabular integration is a shortcut for repeated integration by parts when one factor is a polynomial (which becomes $0$ after finitely many derivatives) and the other is easy to integrate repeatedly (like $e^{ax}$ or $\sin(ax)$). You build a table: successive derivatives of the polynomial in one column, successive antiderivatives of the other factor in another, then multiply diagonally with alternating signs.

P: Evaluate $\int x^2 e^x\,dx$ using tabular integration.

S:
**IDENTIFY**: Product of polynomial $x^2$ (vanishes after 3 derivatives) and $e^x$ (easy to integrate repeatedly) — textbook case for tabular IBP.

**PLAN**:
- Column D: successive derivatives of $x^2$ until $0$
- Column I: successive antiderivatives of $e^x$
- Multiply diagonals with alternating signs $+, -, +, \ldots$

**EXECUTE**:
| Sign | D ($x^2$ and derivatives) | I ($e^x$ and antiderivatives) |
|------|---------------------------|-------------------------------|
| $+$  | $x^2$                     | $e^x$                         |
| $-$  | $2x$                      | $e^x$                         |
| $+$  | $2$                       | $e^x$                         |
| —    | $0$                       | $e^x$                         |

Result: $\int x^2 e^x\,dx = x^2 e^x - 2x e^x + 2 e^x + C$.

**EVALUATE**: Differentiate: $(x^2 e^x)' = 2x e^x + x^2 e^x$, $(-2x e^x)' = -2e^x - 2x e^x$, $(2e^x)' = 2e^x$. Sum: $x^2 e^x$. ✓

## 11.11 Trigonometric Integrals: Odd/Even Powers

Q: How do you integrate $\int \sin^m x \cos^n x\,dx$ when at least one of $m, n$ is odd?
A: Peel off one copy of the odd-powered function to serve as $du$, and convert the remaining even power to the other function using $\sin^2 x + \cos^2 x = 1$. For example, if $n$ is odd, write $\cos^n x = \cos^{n-1} x \cdot \cos x$, convert $\cos^{n-1} x = (1 - \sin^2 x)^{(n-1)/2}$, and let $u = \sin x$.

C: For $\int \sin^3 x \cos^4 x\,dx$, the odd power is on [$\sin$], so we peel off one $\sin x$ and substitute $u = \cos x$.

Q: Why does the "peel off one, convert the rest" strategy fail when both $m$ and $n$ are even?
A: There is no single $\sin x$ or $\cos x$ available as $du$, and converting an even power using $\sin^2 + \cos^2 = 1$ just swaps one even-power problem for another. We need a different tool: the power-reduction identities.

## 11.12 Power-Reduction Identities for Even Powers

C: The half-angle identity $\sin^2 x = [(1 - \cos 2x)/2]$ reduces an even power of $\sin$ to a first power of $\cos(2x)$.

C: The half-angle identity $\cos^2 x = [(1 + \cos 2x)/2]$ reduces an even power of $\cos$ to a first power of $\cos(2x)$.

Q: Why do power-reduction identities turn even-power trig integrals into something tractable?
A: They trade a squared trig function (hard to integrate) for a constant plus $\cos(2x)$ (easy to integrate). Applied repeatedly, they reduce $\sin^{2k} x$ or $\cos^{2k} x$ to a sum of terms of the form $\cos(2jx)$, each of which integrates to $\sin(2jx)/(2j)$.

## 11.13 Trig Substitution: $\sqrt{a^2 - x^2}$

C: For integrands containing $\sqrt{a^2 - x^2}$, substitute $x = [a\sin\theta]$ so the radical becomes $a\cos\theta$.

Q: Why does $x = a\sin\theta$ eliminate the square root in $\sqrt{a^2 - x^2}$?
A: Substituting gives $\sqrt{a^2 - a^2\sin^2\theta} = \sqrt{a^2(1 - \sin^2\theta)} = \sqrt{a^2\cos^2\theta} = a|\cos\theta|$. The Pythagorean identity converts the difference of squares inside the radical into a perfect square, so the root disappears.

## 11.14 Trig Substitution: $\sqrt{a^2 + x^2}$

C: For integrands containing $\sqrt{a^2 + x^2}$, substitute $x = [a\tan\theta]$ so the radical becomes $a\sec\theta$.

Q: Why does $x = a\tan\theta$ work for $\sqrt{a^2 + x^2}$?
A: Substituting yields $\sqrt{a^2 + a^2\tan^2\theta} = \sqrt{a^2(1 + \tan^2\theta)} = \sqrt{a^2\sec^2\theta} = a|\sec\theta|$. The identity $1 + \tan^2\theta = \sec^2\theta$ turns the sum of squares into a single squared term, eliminating the radical.

## 11.15 Trig Substitution: $\sqrt{x^2 - a^2}$

C: For integrands containing $\sqrt{x^2 - a^2}$, substitute $x = [a\sec\theta]$ so the radical becomes $a\tan\theta$.

Q: Why does $x = a\sec\theta$ work for $\sqrt{x^2 - a^2}$?
A: Substituting gives $\sqrt{a^2\sec^2\theta - a^2} = \sqrt{a^2(\sec^2\theta - 1)} = \sqrt{a^2\tan^2\theta} = a|\tan\theta|$. The rearranged identity $\sec^2\theta - 1 = \tan^2\theta$ turns the difference of squares into a perfect square.

## 11.16 Why Trig Substitution Linearizes Square Roots

Q: What is the common structural reason all three trig substitutions work?
A: Each uses a Pythagorean identity ($\sin^2 + \cos^2 = 1$, $1 + \tan^2 = \sec^2$) to convert a two-term expression under a square root into a single squared term. Once the radicand is a perfect square, the root collapses to a single trig function, and the resulting integral in $\theta$ is a trig integral we can attack with techniques from Sections 11.11–11.12.

C: Trig substitution works because a [Pythagorean identity] converts the two-term radicand into a perfect square, eliminating the root.

## 11.17 Partial Fractions for Rational Functions

Q: What is the method of partial fractions, and what prerequisite must the integrand satisfy?
A: Partial fractions decomposes a rational function $P(x)/Q(x)$ into a sum of simpler fractions (each with a linear or irreducible quadratic denominator), which can be integrated one at a time. Prerequisite: $\deg P < \deg Q$ (proper rational function). If not, perform polynomial long division first.

C: The method of [partial fractions] decomposes a rational function into a sum of simpler fractions that integrate elementarily.

Q: Why is partial-fraction decomposition always possible (in principle) for a proper rational function with real coefficients?
A: Every real polynomial $Q(x)$ factors uniquely into a product of linear factors and irreducible quadratic factors (fundamental theorem of algebra over the reals). Each such factor contributes a known template of simple fractions, and matching coefficients always yields a solvable linear system.

## 11.18 Distinct Linear Factors

Q: How do you set up the partial-fraction decomposition when $Q(x)$ factors into distinct linear factors?
A: For each distinct linear factor $(x - r_i)$, include a term $\frac{A_i}{x - r_i}$ with an unknown constant $A_i$. So $\frac{P(x)}{(x-r_1)(x-r_2)\cdots(x-r_n)} = \frac{A_1}{x - r_1} + \frac{A_2}{x - r_2} + \cdots + \frac{A_n}{x - r_n}$. Each term integrates to $A_i \ln|x - r_i|$.

C: A distinct linear factor $(x - r)$ in the denominator contributes a term $[A/(x - r)]$ to the partial-fraction decomposition.

## 11.19 Repeated Linear Factors

Q: Why does a repeated linear factor $(x - r)^k$ require $k$ separate partial-fraction terms, not just one?
A: A single term $A/(x-r)^k$ cannot represent every numerator behavior — it has only one degree of freedom ($A$), but the repeated factor creates $k$ dimensions of possible numerators. We include all lower powers too: $\frac{A_1}{x - r} + \frac{A_2}{(x - r)^2} + \cdots + \frac{A_k}{(x - r)^k}$, giving $k$ constants to match $k$ equations.

C: A repeated linear factor $(x - r)^k$ contributes $k$ terms to the partial-fraction decomposition: $\frac{A_1}{x-r} + \frac{A_2}{(x-r)^2} + \cdots + [\frac{A_k}{(x-r)^k}]$.

## 11.20 Irreducible Quadratic Factors

Q: How do you handle an irreducible quadratic factor $ax^2 + bx + c$ (discriminant $< 0$) in partial fractions?
A: Include a term $\frac{Ax + B}{ax^2 + bx + c}$ with a linear numerator, not just a constant. Integration typically requires completing the square on the denominator and splitting into a logarithmic piece (from the $Ax$ part) and an arctangent piece (from the $B$ part).

C: An irreducible quadratic factor $ax^2 + bx + c$ contributes a term $[(Ax + B)/(ax^2 + bx + c)]$ — a linear numerator, not a constant.

Q: Why does the numerator need to be linear ($Ax + B$) rather than a constant for an irreducible quadratic factor?
A: The numerator must have one less degree than the denominator to span all possible proper rational functions with that denominator. A quadratic denominator has dimension 2 in its "proper numerator space," so we need two parameters $A$ and $B$, not one.

## 11.21 Polynomial Long Division

Q: When and why do you perform polynomial long division before applying partial fractions?
A: Do it whenever $\deg P \geq \deg Q$. Partial-fraction templates are derived only for proper rational functions, so we first split $P/Q = (\text{quotient polynomial}) + (\text{proper remainder})/Q$. The polynomial part integrates trivially, and partial fractions applies to the proper remainder.

C: If $\deg P \geq \deg Q$ in $P(x)/Q(x)$, you must first perform [polynomial long division] before partial fractions.

## 11.22 Strategy Flow

Q: What is a good general strategy when confronted with an unfamiliar integral?
A: Try techniques in roughly this order: (1) simple $u$-substitution to absorb any obvious inner function; (2) integration by parts if the integrand is a product of different function types (use LIATE); (3) trig substitution if a square root of $a^2 \pm x^2$ or $x^2 - a^2$ appears; (4) partial fractions if the integrand is a rational function (after long division if improper). Between steps, simplify algebraically or use trig identities.

C: The standard integration strategy flow is: try [substitution], then integration by parts, then trig substitution, then partial fractions.

Q: Why is $u$-substitution first in the strategy order?
A: It is the cheapest technique — a single change of variable — and it often exposes structure that makes the remaining work easier (or finishes the problem outright).

## 11.22a Pattern-Recognition Triggers

Q: You see $\int x \cos(x^2)\,dx$. What technique fires first?
A: $u$-substitution with $u = x^2$ — the derivative $2x$ is sitting in the integrand.

Q: You see $\int x e^x\,dx$ or $\int x \ln x\,dx$. What technique?
A: Integration by parts (polynomial × exponential or polynomial × log — LIATE chooses $u$).

Q: You see $\int \frac{1}{\sqrt{4 - x^2}}\,dx$. What technique?
A: Trig substitution $x = 2\sin\theta$ (radical of $a^2 - x^2$ form).

Q: You see $\int \frac{1}{x^2 + 9}\,dx$. What technique?
A: Trig substitution $x = 3\tan\theta$, OR recognize directly as $\frac{1}{3}\arctan(x/3) + C$.

Q: You see $\int \frac{3x + 5}{(x-1)(x+2)}\,dx$. What technique?
A: Partial fractions — proper rational function with distinct linear factors.

Q: You see $\int \sin^3 x \cos^2 x\,dx$ (one odd power). What technique?
A: Peel off one $\sin x$ for $du$, convert remaining $\sin^2 x = 1 - \cos^2 x$, substitute $u = \cos x$.

Q: You see $\int \sin^2 x\,dx$ (only even powers). What technique?
A: Power-reduction identity $\sin^2 x = (1 - \cos 2x)/2$.

Q: You see $\int e^x \sin x\,dx$. What technique?
A: Integration by parts twice — the integral loops back, solve algebraically.

Q: An integrand is a product but neither factor differentiates simpler than itself. Should you try IBP?
A: No — IBP only helps when one factor simplifies under differentiation. Look for $u$-sub or trig identities instead.

## 11.23 Worked Example: Substitution

P: Evaluate $\int x e^{x^2}\,dx$.

S:
**IDENTIFY**: Integrand is a product of $x$ and $e^{x^2}$. The exponent $x^2$ has derivative $2x$, which (up to a factor of $2$) is the other factor. This is a classic $u$-substitution setup.

**PLAN**:
- Let $u = x^2$ (the inner function of the exponential)
- Compute $du = 2x\,dx$, so $x\,dx = \tfrac{1}{2}\,du$
- Rewrite the integral in $u$ and integrate

**EXECUTE**:
1. $u = x^2 \Rightarrow du = 2x\,dx \Rightarrow x\,dx = \frac{1}{2}\,du$
2. $\int x e^{x^2}\,dx = \int e^{u} \cdot \frac{1}{2}\,du = \frac{1}{2}\int e^{u}\,du$
3. $= \frac{1}{2} e^{u} + C$
4. Back-substitute: $= \frac{1}{2} e^{x^2} + C$

**EVALUATE**: Differentiate: $\frac{d}{dx}\left[\frac{1}{2} e^{x^2}\right] = \frac{1}{2} e^{x^2} \cdot 2x = x e^{x^2}$ ✓. The answer recovers the original integrand, so the substitution is correct.

## 11.24 Worked Example: Partial Fractions

P: Evaluate $\int \frac{x + 1}{x^2 - 3x + 2}\,dx$ using partial fractions.

S:
**IDENTIFY**: Rational integrand with $\deg(\text{num}) = 1 < \deg(\text{denom}) = 2$, so it is proper — no long division needed. Factor the denominator and decompose.

**PLAN**:
- Factor $x^2 - 3x + 2 = (x - 1)(x - 2)$ (two distinct linear factors)
- Decompose $\frac{x+1}{(x-1)(x-2)} = \frac{A}{x-1} + \frac{B}{x-2}$
- Solve for $A, B$, then integrate term by term

**EXECUTE**:
1. Multiply both sides by $(x-1)(x-2)$: $x + 1 = A(x - 2) + B(x - 1)$
2. Set $x = 1$: $2 = A(-1) + B(0) \Rightarrow A = -2$
3. Set $x = 2$: $3 = A(0) + B(1) \Rightarrow B = 3$
4. Therefore $\frac{x+1}{(x-1)(x-2)} = \frac{-2}{x-1} + \frac{3}{x-2}$
5. Integrate: $\int \frac{x+1}{x^2-3x+2}\,dx = -2\ln|x-1| + 3\ln|x-2| + C$

**EVALUATE**: Check by combining logs: answer equals $\ln\!\left|\frac{(x-2)^3}{(x-1)^2}\right| + C$. Differentiating: $\frac{3}{x-2} - \frac{2}{x-1} = \frac{3(x-1) - 2(x-2)}{(x-1)(x-2)} = \frac{x + 1}{(x-1)(x-2)}$ ✓, the original integrand.
