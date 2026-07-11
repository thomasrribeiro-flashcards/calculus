+++
order = 2
subject = "mathematics"
tags = ["math", "calculus", "derivative", "tangent-line", "rate-of-change", "differentiability"]
+++

# Calculus — The Derivative

## 2.1 Motivating Problem: Slope of a Tangent Line

Q: Why is finding the slope of a tangent line to a curve $y = f(x)$ at a point $P = (a, f(a))$ not a straightforward algebra problem?
A: Slope classically requires two distinct points, via $\frac{\Delta y}{\Delta x}$. A tangent line touches the curve at only one point $P$, so we have no second point to form a slope ratio. This forces us to use a limiting process: pick a nearby point $Q$ on the curve, compute the slope of the secant line $PQ$, and then let $Q$ slide toward $P$. The tangent slope is defined as the limit of these secant slopes, which is exactly the idea that gives birth to the derivative.

Q: What is a secant line, and how does it approximate the tangent line at a point $(a, f(a))$?
A: A secant line through $(a, f(a))$ and a nearby point $(a+h, f(a+h))$ on the graph of $f$ has slope $\frac{f(a+h) - f(a)}{h}$, where $h$ is the horizontal separation of the two points. As $h \to 0$, the second point slides toward $(a, f(a))$, and the secant line rotates into the tangent line. The tangent line is therefore the limiting position of secant lines, and its slope is the limit of the secant slopes.

C: The slope of the [secant line] through $(a, f(a))$ and $(a+h, f(a+h))$ on the graph of $f$ is $\frac{f(a+h) - f(a)}{h}$.

## 2.2 Motivating Problem: Instantaneous Rate of Change

Q: Why does a moving particle have a well-defined "instantaneous velocity" even though velocity is classically defined as displacement over a time interval?
A: Classical velocity $\frac{\Delta s}{\Delta t}$ needs a nonzero time interval $\Delta t$, so at a single instant $t = a$ the ratio is $\tfrac{0}{0}$ and undefined. But physically, a car's speedometer reads a definite value at each instant. We recover this mathematically by computing average velocities over shorter and shorter intervals $[a, a+h]$ and taking the limit as $h \to 0$. This limit, when it exists, is the instantaneous velocity and is again a derivative.

Q: If $s(t)$ gives the position of a particle at time $t$, what does $\frac{s(a+h) - s(a)}{h}$ represent, and what is its unit?
A: It is the average velocity of the particle over the time interval from $t = a$ to $t = a+h$, where $s$ is position and $h > 0$ is the elapsed time. Its unit is (units of position) / (units of time), e.g., meters per second. Sending $h \to 0$ turns this average velocity into the instantaneous velocity at time $a$.

## 2.3 Average Rate of Change

C: The [average rate of change] of $f$ over $\lbrack a, b\rbrack $ is $\frac{f(b) - f(a)}{b - a}$, where $f(a)$ and $f(b)$ are the output values at the endpoints and $b - a$ is the length of the interval.

Q: Why is the average rate of change $\frac{f(b) - f(a)}{b - a}$ geometrically equal to the slope of a secant line?
A: The graph points $(a, f(a))$ and $(b, f(b))$ lie on the curve $y = f(x)$. The line through them is the secant line over $[a, b]$, and its slope by the two-point formula is $\frac{f(b) - f(a)}{b - a}$. So "average rate of change of $f$ over $[a, b]$" and "slope of the secant line from $a$ to $b$" are two names for the same number, tying algebra (averages) to geometry (slopes).

Q: Predict: as $b \to a$ in the expression $\frac{f(b) - f(a)}{b - a}$, what geometric object does the secant line become, and what number does its slope approach?
A: The two points $(a, f(a))$ and $(b, f(b))$ merge, so the secant line pivots about $(a, f(a))$ and approaches the tangent line there. Its slope therefore approaches the slope of the tangent line at $a$, which is the derivative $f'(a)$.

## 2.4 Definition of the Derivative at a Point

C: The [derivative of $f$ at $a$] is $f'(a) = \lim_{h \to 0} \frac{f(a+h) - f(a)}{h}$, where $f$ is a function defined near $a$ and $h$ is the horizontal increment from $a$.

Q: Why does the definition $f'(a) = \lim_{h\to 0}\frac{f(a+h) - f(a)}{h}$ require a two-sided limit rather than just $h \to 0^+$?
A: A tangent line exists only if the curve is smoothly approached from both sides. If left-hand and right-hand limits of the difference quotient disagree, the secants approach two different lines and no single tangent slope is defined. Requiring the full two-sided limit therefore enforces that $f$ has matching secant behavior on both sides of $a$, which is what "differentiable at $a$" means.

Q: When does the derivative $f'(a)$ fail to exist, based purely on the definition $f'(a) = \lim_{h\to 0}\frac{f(a+h) - f(a)}{h}$?
A: It fails whenever that limit does not exist as a finite number: the one-sided limits disagree (a corner), the limit is $\pm\infty$ (a vertical tangent), or the difference quotient oscillates without settling. In all such cases we say $f$ is not differentiable at $a$, even though $f(a)$ itself may still be perfectly defined.

## 2.5 Alternate Form of the Derivative

C: An equivalent form of the derivative at a point is [$f'(a) = \lim_{x \to a} \frac{f(x) - f(a)}{x - a}$], where $x$ approaches $a$ through values near (but not equal to) $a$.

Q: Why are the two forms $\lim_{h\to 0}\frac{f(a+h) - f(a)}{h}$ and $\lim_{x\to a}\frac{f(x) - f(a)}{x - a}$ equal?
A: Let $x = a + h$, so $h = x - a$. As $h \to 0$, $x \to a$, and the numerator $f(a+h) - f(a)$ becomes $f(x) - f(a)$ while the denominator $h$ becomes $x - a$. The substitution is a bijection of nonzero $h$ with $x \ne a$ near $a$, so the two limits describe exactly the same difference quotients approaching the same value, $f'(a)$.

Q: When is the $x \to a$ form of the derivative often more convenient than the $h \to 0$ form?
A: When the function is already written in terms of $x$ and the algebra simplifies nicely if we factor $x - a$ out of $f(x) - f(a)$—for example, polynomials and rational functions, where $f(x) - f(a)$ has $x - a$ as a root. The $h$ form is handier when we need to expand $f(a+h)$ around a fixed $a$, e.g., for $\sqrt{a+h}$ or $\sin(a+h)$.

## 2.6 Geometric Interpretation

Q: Geometrically, what does $f'(a)$ represent on the graph of $y = f(x)$?
A: $f'(a)$ is the slope of the tangent line to the graph of $f$ at the point $(a, f(a))$. Intuitively, if you zoom in on the graph near that point, the curve looks more and more like a straight line, and $f'(a)$ is the slope of that limiting line. A positive $f'(a)$ means the curve is sloping upward there; a negative value means downward; zero means horizontal tangent.

Q: Why can't $f'(a)$ be interpreted as the slope of the graph "at" a single point without the limiting construction?
A: Slope is fundamentally a two-point concept: rise over run. A single point has no "run" to speak of, so "slope at a point" is meaningless until we define it via a limit of secant slopes. The derivative's limiting definition is the machinery that turns the intuitive idea of "steepness at an instant" into a rigorous number.

## 2.7 Physical Interpretation

C: If $s(t)$ is the position of a particle at time $t$, then $s'(a)$ is its [instantaneous velocity] at time $t = a$, measured in (position units)/(time units).

Q: Why does $s'(a)$ deserve the name "instantaneous velocity" rather than "average velocity at $a$"?
A: The ratio $\frac{s(a+h) - s(a)}{h}$ is literally the average velocity over $[a, a+h]$. Taking $h \to 0$ shrinks this interval to the single instant $t = a$, so the limit measures the rate of change at exactly that instant—no averaging window remains. This matches the speedometer reading at an instant, which is why $s'(a)$ models instantaneous velocity.

Q: Beyond velocity from position, give two other physical interpretations of a derivative $f'(a)$.
A: If $T(t)$ is temperature, $T'(a)$ is the rate of heating/cooling at time $a$ (degrees per unit time). If $Q(t)$ is charge on a capacitor, $Q'(a)$ is the electric current at time $a$. More generally, $f'(a)$ is the instantaneous rate at which the output $f$ changes per unit change in the input near $a$.

## 2.8 Derivative Function vs Derivative at a Point

Q: What is the distinction between the derivative at a point $f'(a)$ and the derivative function $f'(x)$?
A: $f'(a)$ is a single number—the slope of $f$ at the one input $a$. The derivative function $f'$ is a new function whose value at each input $x$ is $f'(x) = \lim_{h\to 0}\frac{f(x+h) - f(x)}{h}$ whenever that limit exists. So $f'(a)$ is the value of $f'$ evaluated at $x = a$; $f'$ packages the slope information at every differentiable point into one function.

C: The [domain] of the derivative function $f'$ consists of all inputs $x$ in the domain of $f$ at which the limit $\lim_{h\to 0}\frac{f(x+h) - f(x)}{h}$ exists as a finite number.

Q: Why can the derivative function $f'$ have a smaller domain than $f$ itself?
A: $f$ only needs to be defined at a point for $f(a)$ to exist, but $f'(a)$ additionally requires the difference quotient to approach a finite limit as $h \to 0$. Corners, cusps, and vertical tangents leave $f$ defined but kill the limit, so those inputs drop out of $f'$'s domain. For example, $f(x) = |x|$ is defined at $0$, but $f'(0)$ does not exist.

## 2.9 Notation

C: Lagrange's prime notation writes the derivative of $y = f(x)$ as [$f'(x)$], emphasizing that $f'$ is a new function obtained from $f$.

C: Leibniz notation writes the derivative as [$\frac{dy}{dx}$], suggesting the limit of the ratio $\frac{\Delta y}{\Delta x}$ of output change to input change; it is excellent for the chain rule and for tracking which variable we differentiate with respect to.

C: The operator notation [$\frac{d}{dx} f$] treats $\frac{d}{dx}$ as an action applied to the function $f$, emphasizing differentiation as a process/operator rather than a completed function.

C: The compact operator notation [$Df$] also treats differentiation as an operator $D$ acting on a function $f$, and is useful when writing abstract operator equations like $(D^2 + 1)y = 0$ in differential equations.

Q: When is Leibniz notation $\frac{dy}{dx}$ especially helpful compared to prime notation $f'(x)$?
A: Leibniz notation makes the input variable explicit, which matters when several variables are in play (e.g., $\frac{dy}{dx}$ vs $\frac{dy}{dt}$), when applying the chain rule ($\frac{dy}{dx} = \frac{dy}{du}\frac{du}{dx}$), or when units matter (meters per second literally reads off $\frac{ds}{dt}$). Prime notation is more compact but hides what the independent variable is.

## 2.10 Tangent Line Equation

C: The [tangent line] to $y = f(x)$ at $x = a$ has equation $y - f(a) = f'(a)(x - a)$, where $(a, f(a))$ is the point of tangency and $f'(a)$ is the slope.

Q: Why is the tangent line written in point-slope form $y - f(a) = f'(a)(x - a)$ rather than slope-intercept form?
A: Point-slope form uses exactly the two pieces of information the derivative gives us: the point on the curve $(a, f(a))$ and the slope $f'(a)$ at that point. Converting to $y = mx + b$ would require computing the $y$-intercept separately, which adds work and obscures the natural "anchored at $(a, f(a))$" structure that makes tangent lines useful for local approximation.

Q: A curve passes through $(2, 5)$ with $f'(2) = 3$. Write the equation of the tangent line at that point.
A: Using $y - f(a) = f'(a)(x - a)$ with $a = 2$, $f(a) = 5$, $f'(a) = 3$: $y - 5 = 3(x - 2)$, i.e., $y = 3x - 1$. The tangent line has slope $3$ and passes through $(2, 5)$, and it is the best linear approximation to $f$ near $x = 2$.

## 2.11 Linear Approximation / Linearization

C: The [linearization] of $f$ at $a$ is $L(x) = f(a) + f'(a)(x - a)$, where $L$ is the linear function whose graph is the tangent line to $f$ at $(a, f(a))$.

Q: Why is the linearization $L(x) = f(a) + f'(a)(x - a)$ a good approximation to $f(x)$ for $x$ near $a$?
A: Near $a$, the graph of $f$ is nearly indistinguishable from its tangent line, because zooming in makes smooth curves look linear. Algebraically, the error $f(x) - L(x)$ goes to zero faster than $x - a$ itself, so for small $|x - a|$ the tangent line captures both the value and slope of $f$ at $a$. This is why physicists and engineers routinely replace complicated functions by their linearizations in small-perturbation analyses.

Q: Use linearization to estimate $\sqrt{4.1}$ from the known value $\sqrt{4} = 2$.
A: Let $f(x) = \sqrt{x}$, $a = 4$. Then $f(a) = 2$ and $f'(x) = \frac{1}{2\sqrt{x}}$, so $f'(4) = \tfrac{1}{4}$. The linearization is $L(x) = 2 + \tfrac{1}{4}(x - 4)$, where $x$ is the input and $L(x)$ approximates $\sqrt{x}$ near $4$. Thus $\sqrt{4.1} \approx L(4.1) = 2 + \tfrac{1}{4}(0.1) = 2.025$ (true value $\approx 2.02485$).

## 2.12 Differentiability Implies Continuity

Q: State and prove (sketch) the theorem: if $f$ is differentiable at $a$, then $f$ is continuous at $a$.
A: Statement: $f'(a)$ exists $\Rightarrow$ $\lim_{x \to a} f(x) = f(a)$. Sketch: write $f(x) - f(a) = \frac{f(x) - f(a)}{x - a} \cdot (x - a)$ for $x \ne a$. As $x \to a$, the first factor tends to $f'(a)$ (a finite number by assumption) and the second factor tends to $0$. By limit laws, the product tends to $f'(a) \cdot 0 = 0$, so $\lim_{x \to a}[f(x) - f(a)] = 0$, i.e., $\lim_{x \to a} f(x) = f(a)$, which is continuity at $a$.

Q: Why is the contrapositive of "differentiable $\Rightarrow$ continuous" a useful diagnostic tool?
A: The contrapositive says: if $f$ is not continuous at $a$, then $f$ is not differentiable at $a$. So as soon as you spot a jump, removable hole, or infinite discontinuity, you can immediately rule out differentiability there without computing any limits of difference quotients. This often saves work on problems that ask whether $f'(a)$ exists.

## 2.13 Continuity Does Not Imply Differentiability

Q: Give four ways a function can be continuous at $a$ yet fail to be differentiable there.
A: (1) **Corner**: left and right tangent slopes disagree, e.g., $f(x) = |x|$ at $0$. (2) **Cusp**: both one-sided slopes are infinite but with opposite signs, e.g., $f(x) = x^{2/3}$ at $0$. (3) **Vertical tangent**: difference quotient $\to +\infty$ or $-\infty$ from both sides, e.g., $f(x) = x^{1/3}$ at $0$. (4) **Wild oscillation**: difference quotient oscillates without limit, e.g., $f(x) = x\sin(1/x)$ at $0$.

Q: Show directly from the definition that $f(x) = |x|$ is not differentiable at $0$, even though it is continuous there.
A: Continuity at $0$ is clear since $\lim_{x\to 0}|x| = 0 = |0|$. For differentiability we compute $\lim_{h \to 0}\frac{|0 + h| - |0|}{h} = \lim_{h \to 0}\frac{|h|}{h}$, where $h$ is the increment. For $h > 0$ this ratio is $+1$; for $h < 0$ it is $-1$. The one-sided limits disagree, so the two-sided limit does not exist and $f'(0)$ is undefined.

C: A [corner] on the graph of a continuous function $f$ at $x = a$ is a point where the left-hand and right-hand limits of $\frac{f(a+h) - f(a)}{h}$ both exist but are unequal.

C: A [vertical tangent] occurs at $x = a$ when $f$ is continuous at $a$ and $\lim_{h \to 0}\frac{f(a+h) - f(a)}{h} = \pm\infty$, with the same sign from both sides.

## 2.14 Higher-Order Derivatives

C: The [second derivative] of $f$ is the derivative of the derivative: $f''(x) = (f')'(x) = \frac{d}{dx}\!\left(\frac{df}{dx}\right) = \frac{d^2 f}{dx^2}$, where $f'$ is the first derivative function.

C: The [$n$th derivative] of $f$, denoted $f^{(n)}(x)$ or $\frac{d^n f}{dx^n}$, is obtained by differentiating $f$ a total of $n$ times, with $f^{(0)} = f$ by convention; here $n \ge 1$ is a positive integer.

Q: Why do we use $f^{(n)}$ notation with parentheses instead of just $f^n$ for the $n$th derivative?
A: Without parentheses, $f^n(x)$ is ambiguous: it could mean repeated composition $f \circ f \circ \cdots \circ f$, or the $n$th power $[f(x)]^n$. The parentheses in $f^{(n)}(x)$ signal "differentiation applied $n$ times" and distinguish it from powers and compositions. For small $n$ we often write $f', f'', f'''$, then switch to $f^{(4)}, f^{(5)}, \ldots$ for clarity.

## 2.15 Physical Meaning of the Second Derivative

C: If $s(t)$ is position as a function of time, then $s''(t)$ is the [acceleration], i.e., the instantaneous rate of change of velocity $v(t) = s'(t)$ with respect to time.

Q: Why is acceleration naturally represented as a second derivative of position rather than a first derivative of something else?
A: Velocity is the rate of change of position: $v(t) = s'(t)$. Acceleration is the rate of change of velocity: $a(t) = v'(t)$. Composing these, $a(t) = (s')'(t) = s''(t)$. So acceleration sits "two derivatives away" from position because it describes how the rate of motion itself is changing, not just how position is changing.

Q: On a position-time graph, what does a positive second derivative $s''(t) > 0$ tell you visually?
A: $s'(t)$ is increasing, so velocity is growing over time; the graph of $s$ is concave up (bowl-shaped). Physically this can mean speeding up in the positive direction or slowing down while moving in the negative direction—in both cases the rightward/positive velocity component is growing.

## 2.16 Computing Derivatives from the Limit Definition

Q: What is the general recipe for computing $f'(x)$ directly from the limit definition?
A: (1) Write the difference quotient $\frac{f(x+h) - f(x)}{h}$, where $h$ is a nonzero increment. (2) Expand $f(x+h)$ and subtract $f(x)$ in the numerator. (3) Algebraically simplify so the $h$ in the denominator cancels (factoring, conjugates, common denominators, trig identities). (4) Take $\lim_{h \to 0}$ of the simplified expression; this limit is $f'(x)$.

Q: Why is it essential that the $h$ in the denominator cancels before taking the limit?
A: Before simplification, the difference quotient has the indeterminate form $\tfrac{0}{0}$ as $h \to 0$, since numerator and denominator both vanish. Cancelling $h$ algebraically reveals the finite value the ratio is approaching. If $h$ won't cancel, either your algebra is incomplete or the derivative does not exist (the limit is genuinely indeterminate or infinite).

## 2.17 Worked Example: Derivative of $f(x) = x^2$ from the Definition

P: Use the limit definition of the derivative to find $f'(x)$ for $f(x) = x^2$.

S:
**IDENTIFY**: We need the derivative function of a polynomial via the definition $f'(x) = \lim_{h\to 0}\frac{f(x+h) - f(x)}{h}$, where $x$ is the input and $h$ is the increment approaching $0$.

**PLAN**:
- Substitute $f(x) = x^2$ into the difference quotient.
- Expand $(x+h)^2$ using the binomial formula.
- Factor $h$ out of the numerator and cancel with the denominator.
- Take $\lim_{h \to 0}$ of the simplified expression.

**EXECUTE**:
1. Difference quotient: $\dfrac{f(x+h) - f(x)}{h} = \dfrac{(x+h)^2 - x^2}{h}$.
2. Expand numerator: $(x+h)^2 - x^2 = x^2 + 2xh + h^2 - x^2 = 2xh + h^2 = h(2x + h)$.
3. Cancel $h$ (valid since $h \ne 0$ in the limit): $\dfrac{h(2x + h)}{h} = 2x + h$.
4. Take the limit: $f'(x) = \lim_{h \to 0}(2x + h) = 2x$.

**EVALUATE**:
- Units/dimensions: if $x$ is length, $x^2$ is area, and $\frac{d}{dx}(x^2) = 2x$ is again length, consistent with "area per unit length."
- Spot-check: at $x = 0$, $f'(0) = 0$ matches the horizontal tangent of the parabola at its vertex; at $x = 1$, $f'(1) = 2$ matches the visibly steep rightward slope.
- This also verifies the power rule $\frac{d}{dx}x^n = nx^{n-1}$ in the special case $n = 2$.

## 2.18 Worked Example: Tangent Line to $f(x) = \sqrt{x}$ at $x = 4$

P: Find the equation of the tangent line to $f(x) = \sqrt{x}$ at the point where $x = 4$.

S:
**IDENTIFY**: We need a tangent line, so we need (i) the point $(a, f(a))$ on the curve and (ii) the slope $f'(a)$, then plug into $y - f(a) = f'(a)(x - a)$, where $a = 4$.

**PLAN**:
- Compute $f(4)$ to get the point of tangency.
- Compute $f'(x)$ from the limit definition by rationalizing the numerator with a conjugate.
- Evaluate $f'(4)$ for the slope.
- Assemble the point-slope equation and optionally simplify.

**EXECUTE**:
1. Point: $f(4) = \sqrt{4} = 2$, so the curve passes through $(4, 2)$.
2. Difference quotient: $\dfrac{\sqrt{x+h} - \sqrt{x}}{h}$, where $h$ is the increment from $x$.
3. Multiply by the conjugate $\dfrac{\sqrt{x+h} + \sqrt{x}}{\sqrt{x+h} + \sqrt{x}}$: the numerator becomes $(x + h) - x = h$, giving $\dfrac{h}{h(\sqrt{x+h} + \sqrt{x})} = \dfrac{1}{\sqrt{x+h} + \sqrt{x}}$.
4. Take the limit: $f'(x) = \lim_{h \to 0}\dfrac{1}{\sqrt{x+h} + \sqrt{x}} = \dfrac{1}{2\sqrt{x}}$.
5. Slope at $a = 4$: $f'(4) = \dfrac{1}{2\sqrt{4}} = \dfrac{1}{4}$.
6. Tangent line: $y - 2 = \tfrac{1}{4}(x - 4)$, equivalently $y = \tfrac{1}{4}x + 1$.

**EVALUATE**:
- Sanity check the point: plug $x = 4$ into $y = \tfrac{1}{4}x + 1$ to get $y = 2$, matching $(4, 2)$.
- Slope reasonableness: $\sqrt{x}$ grows slowly for large $x$, and $\tfrac{1}{4}$ is a gentle positive slope, consistent with the shallow rise of $\sqrt{x}$ near $x = 4$.
- Linearization check: $L(4.1) = \tfrac{1}{4}(4.1) + 1 = 2.025$, a close approximation to $\sqrt{4.1} \approx 2.02485$, confirming the tangent line hugs the curve nearby.
