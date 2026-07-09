+++
order = 3
subject = "Math"
tags = ["math", "calculus", "derivative", "power-rule", "product-rule", "quotient-rule", "chain-rule"]
+++

# Calculus — Differentiation Rules

## 3.1 Why We Need Rules

Q: Why do we need differentiation rules when the limit definition $f'(x) = \lim_{h\to 0}\frac{f(x+h) - f(x)}{h}$ already defines the derivative?
A: The limit definition is mechanically correct but slow and error-prone for complex functions. Computing $\frac{d}{dx}(x^5 \sin x / (x^2+1))$ from scratch would require pages of algebra. Rules let us decompose complex expressions into simpler parts and differentiate each piece mechanically, turning calculus into a symbolic procedure rather than a limit computation.

Q: What is the strategic role of differentiation rules in calculus?
A: They provide a compositional toolkit: once you know derivatives of basic functions (powers, sines, exponentials) and a handful of combining rules (sum, product, quotient, chain), you can differentiate almost any expression by pattern-matching. This turns derivatives from a theoretical object into a routine symbolic skill.

C: The limit definition of the derivative is always [valid], but using it directly for complex functions is inefficient.

## 3.2 The Constant Rule

C: The constant rule states that $\frac{d}{dx}(c) = [0]$ for any real constant $c$.

Q: Why is the derivative of a constant function zero?
A: A derivative measures the instantaneous rate of change. A constant function $f(x) = c$ has the same output everywhere, so its output never changes as $x$ changes. The rate of change is therefore zero everywhere, regardless of the value of $c$.

Q: Using the limit definition, why does $\frac{d}{dx}(c) = 0$?
A: Apply $f'(x) = \lim_{h\to 0}\frac{f(x+h) - f(x)}{h}$ with $f(x) = c$. The numerator is $c - c = 0$, so the quotient is $0/h = 0$ for every $h \neq 0$, and the limit is $0$.

## 3.3 The Power Rule

C: The power rule states that $\frac{d}{dx}(x^n) = [nx^{n-1}]$ for every real number $n$, where $x$ is the independent variable.

Q: What is the power rule, and why is it remarkable?
A: The power rule says $\frac{d}{dx}(x^n) = nx^{n-1}$ for ALL real $n$ — not just positive integers, but also negatives, fractions, and irrationals like $\pi$. This single rule collapses differentiation of an entire family of functions into one pattern: multiply by the exponent, then decrement the exponent.

Q: Apply the power rule to $\frac{d}{dx}\left(\sqrt{x}\right)$. Define all variables.
A: Rewrite $\sqrt{x} = x^{1/2}$, where $x > 0$ is the input. By the power rule with $n = 1/2$: $\frac{d}{dx}(x^{1/2}) = \frac{1}{2}x^{-1/2} = \frac{1}{2\sqrt{x}}$.

Q: Apply the power rule to $\frac{d}{dx}\left(\frac{1}{x^3}\right)$.
A: Rewrite $1/x^3 = x^{-3}$. By the power rule with $n = -3$: $\frac{d}{dx}(x^{-3}) = -3x^{-4} = -\frac{3}{x^4}$.

## 3.4 Why the Power Rule Works for Integer n

Q: Predict: using the limit definition on $f(x) = x^3$, what factor should emerge that yields $3x^2$?
A: Expanding $(x+h)^3 = x^3 + 3x^2 h + 3xh^2 + h^3$, the $x^3$ cancels with $-x^3$. Dividing by $h$ gives $3x^2 + 3xh + h^2$. All terms with $h$ vanish as $h \to 0$, leaving $3x^2$.

Q: Why does the power rule $\frac{d}{dx}(x^n) = nx^{n-1}$ work for any positive integer $n$?
A: By the binomial theorem, $(x+h)^n = x^n + nx^{n-1}h + \binom{n}{2}x^{n-2}h^2 + \cdots + h^n$. In the difference quotient $[(x+h)^n - x^n]/h$, the $x^n$ cancels and every remaining term has at least one factor of $h$. Dividing by $h$, only $nx^{n-1}$ has no leftover $h$; all higher-order terms vanish as $h \to 0$.

C: In the binomial expansion of $(x+h)^n$, the linear-in-$h$ term is $[nx^{n-1}h]$, which produces the power rule after dividing by $h$ and taking the limit.

## 3.5 The Constant Multiple Rule

C: The constant multiple rule states $\frac{d}{dx}[cf(x)] = [cf'(x)]$, where $c$ is any real constant and $f$ is differentiable.

Q: Why does scaling a function by a constant scale its derivative by the same constant?
A: Scaling $f$ by $c$ vertically stretches or compresses its graph by factor $c$. The slope at every point is stretched by the same factor because the rise is multiplied by $c$ while the run is unchanged. Formally, the limit defining the derivative is linear: pulling $c$ out of $\lim_{h\to 0}\frac{cf(x+h) - cf(x)}{h}$ gives $c \cdot f'(x)$.

Q: Differentiate $g(x) = 7x^4$ using the constant multiple and power rules.
A: By the constant multiple rule, $g'(x) = 7 \cdot \frac{d}{dx}(x^4)$. By the power rule, $\frac{d}{dx}(x^4) = 4x^3$. So $g'(x) = 7 \cdot 4x^3 = 28x^3$.

## 3.6 The Sum and Difference Rule

C: The sum/difference rule states $\frac{d}{dx}[f(x) \pm g(x)] = [f'(x) \pm g'(x)]$, where $f$ and $g$ are differentiable functions of $x$.

Q: Why does the derivative distribute over addition?
A: The derivative is defined by a limit, and limits distribute over sums when each part has its own limit. Rates of change add independently: if $f$ is rising at 3 units/sec and $g$ is rising at 5 units/sec, then $f+g$ rises at $3+5 = 8$ units/sec. There is no interaction between independent addends.

Q: Differentiate $h(x) = 5x^3 - 2x^2 + 7x - 9$.
A: Apply the sum/difference, constant multiple, power, and constant rules term-by-term. $h'(x) = 15x^2 - 4x + 7 + 0 = 15x^2 - 4x + 7$.

## 3.7 The Product Rule

C: The product rule states $(fg)'(x) = [f'(x)g(x) + f(x)g'(x)]$, where $f$ and $g$ are differentiable functions of $x$.

Q: State the product rule in words.
A: The derivative of a product is the derivative of the first factor times the second, plus the first factor times the derivative of the second. Symmetrically: differentiate each factor in turn, holding the other fixed, then add.

Q: Differentiate $h(x) = x^2 \sin x$ using the product rule, treating $\frac{d}{dx}(\sin x) = \cos x$ as known.
A: Let $f(x) = x^2$ and $g(x) = \sin x$, so $f'(x) = 2x$ and $g'(x) = \cos x$. By the product rule, $h'(x) = f'g + fg' = 2x\sin x + x^2\cos x$.

## 3.8 Why the Product Rule Is NOT f'g'

Q: Predict: if you had never seen the product rule, what would you naively guess $(fg)'$ equals? Why is that guess wrong?
A: The naive guess is $(fg)' = f'g'$, by analogy with the sum rule. It fails: try $f(x) = g(x) = x$. Then $fg = x^2$, so $(fg)' = 2x$. But $f'g' = 1 \cdot 1 = 1 \neq 2x$. A product changes whenever EITHER factor changes, so both contributions must be tracked.

Q: Derive the product rule from the limit definition.
A: Start with $(fg)'(x) = \lim_{h\to 0}\frac{f(x+h)g(x+h) - f(x)g(x)}{h}$. Add and subtract $f(x)g(x+h)$ in the numerator: $f(x+h)g(x+h) - f(x)g(x+h) + f(x)g(x+h) - f(x)g(x)$. Factor: $g(x+h)[f(x+h)-f(x)] + f(x)[g(x+h)-g(x)]$. Divide by $h$ and take the limit: $g(x)f'(x) + f(x)g'(x)$.

Q: Intuitively, why does $(fg)' = f'g + fg'$ instead of $f'g'$?
A: Think of $fg$ as the area of a rectangle with sides $f$ and $g$. When both sides grow, the area grows by a thin strip on top ($f \cdot \Delta g$) plus a thin strip on the side ($\Delta f \cdot g$) plus a tiny corner ($\Delta f \cdot \Delta g$). The corner is second-order small and vanishes in the limit, leaving exactly $f'g + fg'$.

## 3.9 The Quotient Rule

C: The quotient rule states $\left(\frac{f}{g}\right)'(x) = \left[\frac{f'(x)g(x) - f(x)g'(x)}{[g(x)]^2}\right]$, where $f, g$ are differentiable and $g(x) \neq 0$.

Q: Why does the quotient rule have a minus sign while the product rule has a plus?
A: In a quotient $f/g$, increasing $g$ (the denominator) DECREASES the output, so $g$'s rate of change contributes negatively. Increasing $f$ (the numerator) increases the output, contributing positively. The product rule has no denominator, so both factors contribute positively.

Q: Differentiate $h(x) = \frac{x}{x+1}$ using the quotient rule, where $x \neq -1$.
A: Let $f(x) = x$ and $g(x) = x+1$, so $f'(x) = 1$ and $g'(x) = 1$. Then $h'(x) = \frac{f'g - fg'}{g^2} = \frac{1\cdot(x+1) - x\cdot 1}{(x+1)^2} = \frac{1}{(x+1)^2}$.

## 3.10 Mnemonic for the Quotient Rule

Q: State the classic mnemonic for the quotient rule and decode it.
A: "Low d-high minus high d-low, over low-low." Here "high" = numerator $f$, "low" = denominator $g$, "d-high" = $f'$, "d-low" = $g'$. So $\left(\frac{f}{g}\right)' = \frac{g \cdot f' - f \cdot g'}{g \cdot g} = \frac{f'g - fg'}{g^2}$.

C: In the quotient rule mnemonic "low d-high minus high d-low, over low-squared," "low" refers to the [denominator] and "high" refers to the numerator.

Q: Why is the ORDER of terms in the quotient rule numerator important?
A: Because subtraction is not commutative: $f'g - fg' \neq fg' - f'g$. Swapping the order flips the sign of the entire derivative. The mnemonic enforces the correct order: "low d-high" ($gf'$) comes FIRST, then minus "high d-low" ($fg'$).

## 3.11 The Chain Rule

C: The chain rule states $(f \circ g)'(x) = [f'(g(x)) \cdot g'(x)]$, where $g$ is differentiable at $x$ and $f$ is differentiable at $g(x)$.

Q: What is the chain rule, in words?
A: To differentiate a composition $f(g(x))$, take the derivative of the OUTER function $f$ evaluated at the INNER function $g(x)$, then multiply by the derivative of the inner function. The inner function is NOT differentiated before being plugged into $f'$.

Q: Differentiate $h(x) = \sin(x^2)$ using the chain rule.
A: The outer function is $\sin$; the inner is $g(x) = x^2$. So $f'(u) = \cos u$ and $g'(x) = 2x$. By the chain rule, $h'(x) = \cos(x^2) \cdot 2x = 2x\cos(x^2)$.

## 3.12 Chain Rule in Leibniz Notation

C: In Leibniz notation, the chain rule reads $\frac{dy}{dx} = \left[\frac{dy}{du} \cdot \frac{du}{dx}\right]$, where $y$ depends on $u$ and $u$ depends on $x$.

Q: Why is Leibniz notation $\frac{dy}{dx} = \frac{dy}{du}\frac{du}{dx}$ so suggestive of the chain rule?
A: Because it looks like ordinary fraction cancellation: the $du$ symbols appear to cancel, leaving $\frac{dy}{dx}$. This is a useful mnemonic but not a proof — $\frac{dy}{du}$ is a limit, not a fraction. Still, the symbolism mirrors the true rate-of-rate structure faithfully.

Q: If $y = u^5$ and $u = 3x+1$, find $\frac{dy}{dx}$ using Leibniz chain rule. Define all variables.
A: Here $y$ is a function of $u$, and $u$ is a function of $x$. Compute $\frac{dy}{du} = 5u^4$ and $\frac{du}{dx} = 3$. Then $\frac{dy}{dx} = \frac{dy}{du}\cdot\frac{du}{dx} = 5u^4 \cdot 3 = 15(3x+1)^4$.

## 3.13 Why the Chain Rule Works

Q: Predict: if $y$ changes twice as fast as $u$, and $u$ changes three times as fast as $x$, how fast does $y$ change with respect to $x$?
A: Six times as fast. Rates of change multiply through a chain: if $u$ moves 3 units per unit of $x$, and $y$ moves 2 units per unit of $u$, then a single unit of $x$ causes 3 units of $u$, which causes $3 \times 2 = 6$ units of $y$.

Q: Why does the chain rule multiply derivatives instead of adding or composing them?
A: The chain rule expresses how rates of change transmit through a composition. A change $\Delta x$ produces a change $\Delta u \approx g'(x)\Delta x$. That $\Delta u$ then produces a change $\Delta y \approx f'(u)\Delta u = f'(g(x))g'(x)\Delta x$. Dividing by $\Delta x$ and taking the limit gives $f'(g(x))\cdot g'(x)$. Multiplication captures the amplification of rates through the chain.

C: Intuitively, the chain rule works because rates of change [multiply] when passed through a composition of functions.

## 3.14 Extended Chain Rule for Multiple Compositions

Q: How does the chain rule extend to three-level compositions like $y = f(g(h(x)))$?
A: Each link in the chain contributes a factor: $\frac{dy}{dx} = f'(g(h(x))) \cdot g'(h(x)) \cdot h'(x)$. Equivalently in Leibniz form, if $y$ depends on $u$, $u$ on $v$, and $v$ on $x$: $\frac{dy}{dx} = \frac{dy}{du}\cdot\frac{du}{dv}\cdot\frac{dv}{dx}$. Each factor is the next function's derivative evaluated at the appropriate argument.

Q: Differentiate $y = \sin^2(3x)$ using the extended chain rule. Identify the three layers.
A: Layers: outermost $u^2$, middle $\sin v$, innermost $3x$. So $y = [\sin(3x)]^2$, with derivatives $2u$, $\cos v$, and $3$. Composing: $\frac{dy}{dx} = 2\sin(3x)\cdot\cos(3x)\cdot 3 = 6\sin(3x)\cos(3x)$.

## 3.15 Strategy for Applying the Chain Rule

Q: What is the strategic first step when applying the chain rule to a composite function?
A: Identify the OUTER and INNER functions. Ask: "If I had to compute this function's value at a specific $x$, what would I do LAST?" That final operation is the outer function; everything inside it is the inner function. The chain rule then peels operations off in reverse order.

Q: For $h(x) = \sqrt{7x^3 - 2}$, identify the outer and inner functions.
A: Outer function: $\sqrt{\ \cdot\ }$, i.e., $f(u) = u^{1/2}$. Inner function: $g(x) = 7x^3 - 2$. The "last thing you do" to compute $h(x)$ is take a square root — that is the outer function. Everything under the radical is the inner function.

C: When applying the chain rule, the outer function is identified as the [last] operation you would perform when evaluating the composite function at a point.

## 3.16 Combining Rules on Complicated Expressions

Q: When differentiating a complicated expression, in what order should you apply the rules?
A: Work outside-in, matching the structure: identify whether the TOP-LEVEL operation is a sum, product, quotient, or composition, apply that rule first, then recursively differentiate the resulting sub-expressions. Plan on paper before writing anything — identifying structure prevents algebra errors.

Q: Differentiate $h(x) = x^2\sin(x^3)$. Which rules are needed and in what order?
A: Top-level operation is a PRODUCT of $f(x) = x^2$ and $g(x) = \sin(x^3)$, so start with the product rule: $h' = f'g + fg' = 2x\sin(x^3) + x^2 g'(x)$. Now compute $g'(x)$ using the chain rule on $\sin(x^3)$: outer $\sin$, inner $x^3$, giving $\cos(x^3)\cdot 3x^2$. Final answer: $h'(x) = 2x\sin(x^3) + 3x^4\cos(x^3)$.

## 3.17 Worked Example — Chain Rule on a Power

P: Differentiate $f(x) = (3x^2 + 1)^5$ using the chain rule.

S:
**IDENTIFY**: Composite function — a power of a polynomial. Top-level operation is "raise to the 5th power," so this is a composition $f = \text{outer} \circ \text{inner}$, not a product or quotient.

**PLAN**:
- Outer function: $F(u) = u^5$, where $u$ is a placeholder for whatever is inside.
- Inner function: $g(x) = 3x^2 + 1$.
- Apply chain rule: $f'(x) = F'(g(x)) \cdot g'(x)$.
- Use the power rule for $F'$ and $g'$.

**EXECUTE**:
1. Differentiate outer: $F'(u) = 5u^4$ (power rule with $n=5$).
2. Evaluate at inner: $F'(g(x)) = 5(3x^2 + 1)^4$. Do NOT expand $(3x^2+1)^4$ — leave it factored.
3. Differentiate inner: $g'(x) = 6x$ (power rule on $3x^2$ plus constant rule on $1$).
4. Multiply: $f'(x) = 5(3x^2 + 1)^4 \cdot 6x = 30x(3x^2 + 1)^4$.

**EVALUATE**:
- Check structure: outer-evaluated-at-inner, times inner-derivative. ✓
- Sanity check at $x = 0$: $f(x) = 1^5 = 1$ is at a local minimum (since $3x^2 + 1 \geq 1$), so $f'(0) = 0$. Our formula gives $30 \cdot 0 \cdot 1^4 = 0$. ✓
- Units of structure preserved: power of polynomial → same-power polynomial times a linear piece. ✓

## 3.18 Worked Example — Quotient Rule

P: Differentiate $f(x) = \dfrac{x^2 + 1}{x^2 - 1}$ using the quotient rule, where $x \neq \pm 1$.

S:
**IDENTIFY**: Quotient of two polynomials. Top-level operation is division, so the quotient rule applies directly. Restrict domain to $x \neq \pm 1$ so the denominator is nonzero.

**PLAN**:
- Let numerator $f_1(x) = x^2 + 1$, denominator $g_1(x) = x^2 - 1$.
- Apply quotient rule: $f'(x) = \dfrac{f_1'(x)g_1(x) - f_1(x)g_1'(x)}{[g_1(x)]^2}$.
- Use power and sum rules for $f_1'$ and $g_1'$.

**EXECUTE**:
1. Differentiate numerator: $f_1'(x) = 2x$.
2. Differentiate denominator: $g_1'(x) = 2x$.
3. Assemble numerator of the derivative: $f_1'g_1 - f_1 g_1' = 2x(x^2 - 1) - (x^2 + 1)(2x) = 2x[(x^2 - 1) - (x^2 + 1)] = 2x(-2) = -4x$.
4. Square the denominator: $[g_1(x)]^2 = (x^2 - 1)^2$.
5. Combine: $f'(x) = \dfrac{-4x}{(x^2 - 1)^2}$.

**EVALUATE**:
- Sign check: at $x = 2$, $f(2) = 5/3$, and a slightly larger $x$ gives a slightly smaller $f$ (numerator and denominator both increase, but denominator grows faster since $x^2 - 1 < x^2 + 1$... wait, check: numerator grows like $2x$, denominator like $2x$, but quotient decreases because... ). More robustly: $f'(2) = -8/9 < 0$, consistent with $f$ decreasing on $(1, \infty)$.
- Symmetry: $f$ is even (replace $x \to -x$), so $f'$ should be odd. $-4x/(x^2-1)^2$ is indeed odd. ✓
- At $x = 0$: $f(0) = -1$ is a local extremum (symmetry axis), so $f'(0) = 0$. Our formula: $-4(0)/1 = 0$. ✓
