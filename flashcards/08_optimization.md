+++
order = 8
tags = ["math", "calculus", "optimization", "extrema", "constraints", "newton-method"]
+++

# Calculus — Optimization

## 8.1 What Optimization Means

Q: In calculus, what does "optimization" mean?
A: Finding the input values in the domain that make a function attain its largest or smallest output. We turn a real-world "best/worst" question into "find the global maximum or minimum of $f(x)$," then use derivatives to locate candidate points.

Q: Why is calculus the natural tool for optimization?
A: At a smooth interior extremum, the tangent is horizontal, so $f'(x) = 0$. The derivative converts a global search over infinitely many points into solving a single equation, which narrows the problem to a finite list of candidates.

C: An optimization problem in calculus asks for the [global maximum or minimum] of a real-valued function on a specified domain.

## 8.2 Absolute vs Local Extrema

Q: What is the difference between an absolute (global) extremum and a local (relative) extremum?
A: A global max/min is the largest/smallest value of $f$ anywhere in the domain. A local max/min is only largest/smallest within some open neighborhood of that point. Every global extremum is local, but not every local extremum is global.

C: A point $c$ is a [local maximum] of $f$ if $f(c) \ge f(x)$ for all $x$ in some open interval around $c$.

C: A point $c$ is an [absolute maximum] of $f$ on a domain $D$ if $f(c) \ge f(x)$ for every $x \in D$.

Q: Why does the distinction between local and global matter when optimizing?
A: Calculus techniques ($f'(x)=0$) locate local extrema, but the real-world answer usually asks for the global best. You must compare all local candidates plus boundary behavior to be sure you have the global optimum.

## 8.3 Closed-Interval Method

Q: What is the closed-interval method for finding absolute extrema of a continuous $f$ on $[a, b]$?
A: (1) Find all critical points of $f$ in $(a, b)$, where $f'(x) = 0$ or $f'$ is undefined. (2) Evaluate $f$ at those critical points and at the endpoints $a$ and $b$. (3) The largest value is the absolute max, the smallest is the absolute min.

Q: Why do you only need to check critical points and endpoints, and not other points?
A: A continuous function on a closed interval attains its max/min at a point that is either interior (forcing $f'=0$ or undefined, i.e. a critical point) or on the boundary. Those are the only places an extremum can hide.

C: On a closed interval $[a,b]$ with continuous $f$, absolute extrema occur at [critical points or endpoints].

## 8.4 Extreme Value Theorem

Q: What does the Extreme Value Theorem (EVT) guarantee?
A: If $f$ is continuous on a closed, bounded interval $[a, b]$, then $f$ attains both an absolute maximum and an absolute minimum somewhere on $[a, b]$. Existence is guaranteed before you even start looking.

Q: Why are closedness and continuity both essential in the EVT?
A: Without closedness, extrema can "escape" through an open endpoint (e.g. $f(x)=x$ on $(0,1)$ has no max). Without continuity, a jump can skip over the supremum. Both conditions ensure the function cannot approach an extreme value without reaching it.

C: The Extreme Value Theorem requires $f$ to be [continuous] on a [closed] and bounded interval.

## 8.5 Open Intervals and Unbounded Domains

Q: Why does the closed-interval method fail on open or unbounded domains?
A: There are no endpoints to plug in, and $f$ may not attain a maximum at all (e.g. $f(x)=x$ on $\mathbb{R}$). You must instead examine limiting behavior as $x$ approaches the missing endpoints or $\pm\infty$.

Q: How do you optimize $f$ on an open or unbounded domain?
A: Find all critical points, then compute the one-sided limits at excluded endpoints and $\lim_{x\to\pm\infty} f(x)$ as needed. Compare the critical-point values to those limits; if a limit is larger than every critical value, no maximum exists on that domain.

C: On an unbounded domain, absolute extrema may fail to exist; you must check [limits at infinity] alongside critical points.

## 8.6 General Optimization Strategy

P: What is the general strategy for solving an applied optimization problem?

S:
**IDENTIFY**: An applied max/min question — some quantity $Q$ must be optimized subject to a real-world setup (geometric, physical, or economic).

**PLAN**:
- Draw a picture and label every variable.
- Write the quantity to optimize, $Q$, in terms of those variables.
- Use constraints to eliminate variables until $Q$ is a function of a single variable on a specific domain.

**EXECUTE**:
1. Compute $\dfrac{dQ}{dx}$ and solve $\dfrac{dQ}{dx} = 0$ for critical points.
2. Classify each critical point as max, min, or neither (second derivative or sign-change test).
3. If the domain has endpoints, compare $Q$ there as well.

**EVALUATE**:
- Check units and reasonableness (lengths positive, within feasible range).
- Confirm the classification matches the problem (asking for max vs min).

## 8.7 Using a Constraint

Q: In a constrained optimization problem, why must we reduce the objective to a single variable before applying $f'(x)=0$?
A: Single-variable calculus only locates extrema via one-variable derivatives. The constraint equation (e.g. $2x+2y = P$) lets us solve for one variable in terms of the other and substitute, turning $Q(x,y)$ into $Q(x)$ alone.

C: A [constraint equation] relates the variables of an optimization problem, letting us express the objective as a function of one variable.

Q: How do you choose which variable to eliminate using a constraint?
A: Pick whichever substitution produces the algebraically simplest single-variable objective. Often one variable appears linearly in the constraint, making it trivial to isolate and substitute.

## 8.8 Maximizing Area Given Perimeter

P: A farmer has 100 m of fence. What rectangular pen maximizes the enclosed area?

S:
**IDENTIFY**: Constrained max problem — maximize area $A$ subject to fixed perimeter $P = 100$. Variables: width $x$, length $y$, both $> 0$.

**PLAN**:
- Objective: $A = xy$.
- Constraint: $2x + 2y = 100 \Rightarrow y = 50 - x$.
- Reduce to $A(x) = x(50-x)$ on $(0, 50)$.

**EXECUTE**:
1. $A(x) = 50x - x^2$, so $A'(x) = 50 - 2x$.
2. $A'(x) = 0 \Rightarrow x = 25$.
3. $A''(x) = -2 < 0$, so $x=25$ is a local max.
4. Then $y = 50 - 25 = 25$, giving $A = 625 \text{ m}^2$.

**EVALUATE**:
- The optimal pen is a $25 \times 25$ square — consistent with the general result that among rectangles of fixed perimeter, the square maximizes area.
- Endpoints $x \to 0^+$ or $x \to 50^-$ give $A \to 0$, confirming the interior point is the global max.

## 8.9 Minimizing Surface Area for Given Volume

P: A closed cylindrical can must hold a fixed volume $V$. What radius $r$ minimizes its surface area?

S:
**IDENTIFY**: Constrained min problem — minimize surface area $S$ subject to fixed volume $V$. Variables: radius $r > 0$, height $h > 0$.

**PLAN**:
- Objective: $S = 2\pi r^2 + 2\pi r h$ (two circular ends plus lateral wall).
- Constraint: $V = \pi r^2 h \Rightarrow h = \dfrac{V}{\pi r^2}$.
- Substitute: $S(r) = 2\pi r^2 + \dfrac{2V}{r}$ on $(0, \infty)$.

**EXECUTE**:
1. $S'(r) = 4\pi r - \dfrac{2V}{r^2}$.
2. Set $S'(r) = 0$: $4\pi r^3 = 2V$, so $r^3 = \dfrac{V}{2\pi}$ and $r = \left(\dfrac{V}{2\pi}\right)^{1/3}$.
3. Then $h = \dfrac{V}{\pi r^2} = 2r$ — the optimal height equals the diameter.
4. $S''(r) = 4\pi + \dfrac{4V}{r^3} > 0$, confirming a minimum.

**EVALUATE**:
- As $r \to 0^+$, $S \to \infty$ (thin tall can has huge lateral area); as $r \to \infty$, $S \to \infty$ (flat disk has huge endcaps). The interior critical point is therefore the global min.
- Result $h = 2r$ matches the classic can-design rule of thumb.

## 8.10 Minimizing Distance From Point to Curve

Q: When minimizing the distance from a fixed point to a curve, why do we usually minimize the squared distance $D^2$ instead of $D$?
A: Since $D \ge 0$ and squaring is monotonic on $[0,\infty)$, $D$ and $D^2$ attain their minimum at the same point. Working with $D^2$ avoids the square root, giving a simpler derivative without changing the location of the minimizer.

C: Minimizing distance and minimizing [squared distance] yield the same optimal point, because squaring is monotonic on non-negative values.

Q: Geometrically, at the point on a smooth curve closest to an external point $P$, what is true about the line from $P$ to that point?
A: It is perpendicular to the tangent of the curve at that point. Any non-perpendicular direction would allow a small move along the curve that decreases the distance, contradicting minimality.

## 8.11 Economic Applications: MR = MC

Q: In economics, why does profit maximization require marginal revenue to equal marginal cost, $MR = MC$?
A: Profit $\pi(q) = R(q) - C(q)$, so $\pi'(q) = R'(q) - C'(q) = MR - MC$. Setting $\pi'(q) = 0$ gives $MR = MC$. At higher $q$, cost rises faster than revenue; at lower $q$, an extra unit still adds more revenue than cost — balance occurs where they're equal.

C: A profit-maximizing firm produces the quantity where [marginal revenue equals marginal cost], i.e. $MR = MC$.

Q: At the profit-maximizing quantity, what second-order condition must hold?
A: $\pi''(q) < 0$, equivalently $MR'(q) < MC'(q)$: marginal cost must be rising faster than marginal revenue at that point. Otherwise $MR=MC$ would identify a profit minimum, not a maximum.

## 8.12 Fermat's Principle and Snell's Law

Q: What does Fermat's principle of least time state, and how is it an optimization problem?
A: Light travels between two points along the path that minimizes total travel time. Parameterizing the path by a single variable (e.g. the point of refraction on an interface) gives a function $T(x)$ to minimize — a standard calculus optimization.

Q: How does applying $T'(x) = 0$ to light crossing from medium 1 to medium 2 yield Snell's law?
A: Writing $T(x) = \dfrac{\sqrt{a^2+x^2}}{v_1} + \dfrac{\sqrt{b^2+(d-x)^2}}{v_2}$ and setting $T'(x)=0$ gives $\dfrac{\sin\theta_1}{v_1} = \dfrac{\sin\theta_2}{v_2}$, i.e. $n_1\sin\theta_1 = n_2\sin\theta_2$, where $\theta_i$ are angles from the normal and $v_i$ are wave speeds in each medium.

C: [Snell's law] $n_1 \sin\theta_1 = n_2 \sin\theta_2$ follows from minimizing light's travel time (Fermat's principle), where $n_i$ is the refractive index and $\theta_i$ the angle from the normal in medium $i$.

## 8.13 Verifying a Critical Point Is a Max or Min

Q: What is the second derivative test for classifying a critical point $c$ where $f'(c)=0$?
A: If $f''(c) < 0$, $c$ is a local max (concave down). If $f''(c) > 0$, $c$ is a local min (concave up). If $f''(c) = 0$, the test is inconclusive and you must use a sign-change (first derivative) test or higher analysis.

Q: What is the first derivative sign test, and when is it preferable to the second derivative test?
A: Check the sign of $f'$ on intervals just left and right of $c$. If $f'$ changes $+ \to -$, $c$ is a local max; $- \to +$, a local min; no change means neither. Preferred when $f''$ is hard to compute or $f''(c)=0$.

C: If $f'(c) = 0$ and $f''(c) < 0$, then $c$ is a [local maximum] by the second derivative test.

## 8.14 Closed-Interval Method vs Monotonicity Argument

Q: When is the closed-interval method the right tool, and when is a monotonicity argument better?
A: Use the closed-interval method when the domain is a closed bounded interval and $f$ has multiple critical points or unclear behavior. Use a monotonicity argument (show $f'$ never changes sign) when $f$ is clearly increasing or decreasing throughout, making the extremum occur at a boundary or limit without needing to evaluate candidates.

Q: Why does a monotonicity argument alone sometimes suffice, with no need to find critical points?
A: If $f'(x) > 0$ on the entire domain, $f$ is strictly increasing, so its min is at the left end and max at the right end (or via limits at open ends). No interior critical point can be extremum-relevant because none exists.

## 8.15 Newton's Method

C: [Newton's Method] for finding a root of $f(x)=0$ uses the iteration $x_{n+1} = x_n - \dfrac{f(x_n)}{f'(x_n)}$, where $x_n$ is the current estimate.

Q: Geometrically, what does one step of Newton's Method do?
A: It replaces $f$ by its tangent line at $x_n$ and takes the next estimate $x_{n+1}$ to be the tangent line's $x$-intercept. Each iteration solves a linear approximation rather than the nonlinear equation directly.

Q: Why does the Newton iteration formula include division by $f'(x_n)$?
A: The tangent line at $x_n$ is $y = f(x_n) + f'(x_n)(x - x_n)$. Setting $y=0$ and solving for $x$ gives $x = x_n - f(x_n)/f'(x_n)$. The derivative $f'(x_n)$ is the slope converting a vertical correction $-f(x_n)$ into a horizontal step.

## 8.16 Quadratic Convergence of Newton's Method

Q: What is meant by quadratic convergence of Newton's Method?
A: Near a simple root $r$ where $f'(r) \ne 0$, the error roughly squares each step: $|x_{n+1} - r| \le C|x_n - r|^2$ for some constant $C$. The number of correct digits approximately doubles every iteration.

Q: Why does Newton's Method converge so quickly near a simple root?
A: Taylor-expanding $f$ around $r$ shows the linear term cancels in the Newton update, leaving the error governed by the quadratic term $f''(r)/(2 f'(r))$ times $(x_n-r)^2$. Linear approximations introduce only quadratic-order error when $f'\ne 0$ at the root.

C: Near a simple root, Newton's Method exhibits [quadratic] convergence — the error approximately squares each iteration.

## 8.17 Failure Modes of Newton's Method

Q: What happens if $f'(x_n) = 0$ during Newton iteration?
A: The tangent line is horizontal and never crosses the $x$-axis, so the formula divides by zero and the method fails. In practice, a nearly horizontal tangent causes huge, wild jumps even without exact failure.

Q: How can Newton's Method enter a cycle instead of converging?
A: For certain starting points, $x_{n+1}$ maps back to a previously visited value, producing a periodic orbit that never approaches any root. Classic example: $f(x) = x^3 - 2x + 2$ starting at $x_0 = 0$ alternates between $0$ and $1$.

Q: Why might Newton's Method diverge even when a root exists?
A: If the starting point is far from the root or in a region where $f$ is highly nonlinear, the tangent-line approximation is poor and iterates can fly off to infinity or toward a different root than intended. Quadratic convergence is only a *local* guarantee.

C: Newton's Method can fail by [division by zero when $f'(x_n)=0$], by cycling, or by diverging from a poor initial guess.

## 8.18 Worked Problem: Rectangle With Fixed Perimeter

P: Find the dimensions of a rectangle with perimeter 100 that maximizes its area.

S:
**IDENTIFY**: Constrained optimization — maximize area subject to a perimeter constraint. Unknowns: width $x > 0$, length $y > 0$.

**PLAN**:
- Objective: $A(x,y) = xy$.
- Constraint: $2x + 2y = 100$, so $y = 50 - x$, with $x \in (0, 50)$.
- Reduce to one variable: $A(x) = x(50-x) = 50x - x^2$.

**EXECUTE**:
1. $A'(x) = 50 - 2x$.
2. Set $A'(x)=0$: $x = 25$.
3. Verify max: $A''(x) = -2 < 0$, so $x=25$ is a local (and global interior) max.
4. Compute $y = 50 - 25 = 25$; area $A = 25 \cdot 25 = 625$.

**EVALUATE**:
- Dimensions $25 \times 25$ (a square); area $625$ square units.
- Boundary check: $A(0) = A(50) = 0$, so the interior critical point beats the endpoints — it is the global maximum.
- Matches the general theorem: among all rectangles with fixed perimeter, the square has the greatest area.

## 8.19 Worked Problem: Closest Point on a Parabola

P: Find the point on the parabola $y = x^2$ closest to the point $(0, 1)$.

S:
**IDENTIFY**: Unconstrained min problem — minimize distance from $(0,1)$ to a point $(x, x^2)$ on the curve, where $x \in \mathbb{R}$.

**PLAN**:
- Distance squared: $D^2(x) = (x-0)^2 + (x^2 - 1)^2$.
- Minimize $D^2$ instead of $D$ since squaring is monotonic on $[0,\infty)$.
- Expand: $D^2(x) = x^2 + (x^2-1)^2 = x^4 - x^2 + 1$.

**EXECUTE**:
1. $\dfrac{d}{dx}(D^2) = 4x^3 - 2x = 2x(2x^2 - 1)$.
2. Set to zero: $x = 0$ or $x^2 = \tfrac{1}{2}$, i.e. $x = \pm\tfrac{1}{\sqrt{2}}$.
3. Evaluate $D^2$ at each:
   - $x=0$: $D^2 = 0 + 1 = 1$.
   - $x = \pm\tfrac{1}{\sqrt{2}}$: $D^2 = \tfrac{1}{4} - \tfrac{1}{2} + 1 = \tfrac{3}{4}$.
4. Minimum is $D^2 = \tfrac{3}{4}$ at $x = \pm\tfrac{1}{\sqrt{2}}$, giving points $\left(\pm\tfrac{1}{\sqrt{2}}, \tfrac{1}{2}\right)$.

**EVALUATE**:
- Two symmetric closest points at distance $D = \tfrac{\sqrt{3}}{2} \approx 0.866$.
- The vertex $(0,0)$ is a *local max* of $D^2$ along the curve (saddle between the two minima), consistent with $D^2(0)=1 > \tfrac{3}{4}$.
- Geometric check: the line from $(0,1)$ to $\left(\tfrac{1}{\sqrt{2}}, \tfrac{1}{2}\right)$ has slope $\tfrac{1/2 - 1}{1/\sqrt{2}} = -\tfrac{1}{\sqrt{2}}$, while the tangent to $y=x^2$ there has slope $2x = \sqrt{2}$; product $= -1$, so they are perpendicular — confirming the minimum-distance geometric condition.
