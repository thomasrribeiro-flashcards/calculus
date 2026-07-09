+++
order = 6
subject = "Math"
tags = ["math", "calculus", "mean-value-theorem", "rolles-theorem", "lhopital", "indeterminate-forms"]
+++

# Calculus — Mean Value Theorem and L'Hôpital's Rule

## 6.1 Why Foundational Theorems Matter

Q: Why do we need theorems like the Mean Value Theorem (MVT) and Rolle's Theorem in calculus?
A: They form the logical bridge between local information (the derivative $f'(c)$ at a point $c$) and global behavior (how $f$ changes over an interval $[a,b]$). Without them, we could compute derivatives but couldn't justify conclusions like "if $f' > 0$ then $f$ is increasing" or "L'Hôpital's Rule works." They turn calculus from a collection of formulas into a deductive system.

Q: Before studying MVT, predict: if a car's average speed over a trip is 60 mph, must the speedometer ever read exactly 60 mph?
A: Yes — if speed varies continuously, the instantaneous speed must equal the average speed at some moment. This is exactly the physical content of the Mean Value Theorem: the instantaneous rate $f'(c)$ equals the average rate $\frac{f(b)-f(a)}{b-a}$ somewhere.

Q: What does it mean to say a theorem connects "local slope" to "average behavior"?
A: "Local slope" refers to the derivative $f'(c)$, which is defined at a single point $c$. "Average behavior" refers to quantities like $\frac{f(b)-f(a)}{b-a}$, which summarize how $f$ changes across an entire interval $[a,b]$. MVT-type theorems guarantee that these two viewpoints must agree at some interior point.

C: The Mean Value Theorem links a [local] rate of change (the derivative at a point) to an [average] rate of change over an interval.

## 6.2 Extreme Value Theorem

Q: What does the Extreme Value Theorem (EVT) state?
A: If $f$ is continuous on a closed, bounded interval $[a,b]$, then $f$ attains both an absolute maximum value $M$ and an absolute minimum value $m$ somewhere on $[a,b]$. That is, there exist points $c_1, c_2 \in [a,b]$ with $f(c_1) = M$ and $f(c_2) = m$.

Q: Why are BOTH hypotheses of EVT (continuity AND closed interval) essential?
A: Without continuity, $f$ could jump to avoid reaching a max — e.g., $f(x)=x$ for $x<1$ and $f(1)=0$ on $[0,1]$ has no maximum. Without a closed interval, $f$ can approach but never attain a value — e.g., $f(x)=x$ on $(0,1)$ has supremum $1$ but no maximum. Both conditions trap the function so extrema must exist.

C: The [Extreme Value Theorem] guarantees that a continuous function on a closed bounded interval attains its absolute maximum and minimum.

Q: Why is EVT needed before proving Rolle's Theorem?
A: Rolle's proof finds an interior point where $f'=0$ by locating an extremum of $f$ on $[a,b]$. EVT guarantees such an extremum exists in the first place — without EVT, there would be nothing to differentiate and set equal to zero.

## 6.3 Fermat's Theorem

Q: What does Fermat's theorem say about extrema and derivatives?
A: If $f$ has a local extremum at an interior point $c$ (meaning $c$ is not an endpoint) and $f'(c)$ exists, then $f'(c) = 0$. A local extremum means $f(c)$ is the largest or smallest value in some open neighborhood around $c$.

Q: Why must $f'(c) = 0$ at an interior local extremum where $f'(c)$ exists?
A: If $f'(c) > 0$, then $f$ is strictly increasing near $c$, so $f(c)$ isn't a local max or min. If $f'(c) < 0$, $f$ is strictly decreasing near $c$, same conclusion. The only remaining option for a local extremum with a defined derivative is $f'(c) = 0$.

Q: Does Fermat's theorem say every point with $f'(c) = 0$ is a local extremum?
A: No — it's a one-way implication. $f(x) = x^3$ has $f'(0) = 0$ but no extremum at $0$ (it's an inflection point). Fermat says extremum $\Rightarrow f'=0$, not the reverse.

C: Fermat's theorem: if $f$ has a local extremum at an interior point $c$ and $f'(c)$ exists, then $f'(c) = [0]$.

Q: Why does Fermat's theorem require $c$ to be an interior point?
A: At an endpoint, $f$ has only a one-sided neighborhood, so a local max can occur without the derivative vanishing — e.g., $f(x)=x$ on $[0,1]$ has a max at $x=1$ but $f'(1)=1 \neq 0$. Interior points require $f$ to "turn around," forcing $f'=0$.

## 6.4 Critical Points

C: A [critical point] of $f$ is an interior point $c$ in the domain where either $f'(c) = 0$ or $f'(c)$ does not exist.

Q: Why include points where $f'$ is undefined as critical points?
A: Extrema can occur where the derivative fails to exist — e.g., $f(x)=|x|$ has a minimum at $x=0$ even though $f'(0)$ doesn't exist. To capture ALL candidate extrema (per Fermat's theorem), we must include these non-differentiable points.

Q: What is the relationship between critical points and local extrema?
A: Every interior local extremum of $f$ is a critical point (by Fermat's theorem plus the non-differentiable case). However, not every critical point is an extremum — some are inflection points or "cusp" points where no extremum occurs.

Q: If you're searching for absolute extrema of a continuous $f$ on $[a,b]$, which points must you check?
A: Three types: (1) critical points in $(a,b)$ where $f'=0$ or $f'$ is undefined, (2) the endpoints $a$ and $b$. EVT guarantees extrema exist, and they can only occur at these locations.

## 6.5 Rolle's Theorem

Q: State Rolle's Theorem precisely.
A: If $f$ is continuous on $[a,b]$, differentiable on $(a,b)$, and $f(a) = f(b)$, then there exists at least one $c \in (a,b)$ with $f'(c) = 0$. Here $a < b$ are real numbers, and the conclusion places $c$ strictly between them.

Q: Why does Rolle's Theorem require all three hypotheses?
A: Continuity on $[a,b]$ invokes EVT to guarantee extrema exist. Differentiability on $(a,b)$ lets us apply Fermat's theorem at an interior extremum. Equal endpoint values $f(a)=f(b)$ ensure the extremum is interior (not merely at the endpoints), so Fermat gives $f'(c)=0$.

Q: Sketch the proof of Rolle's Theorem.
A: By EVT, $f$ attains max $M$ and min $m$ on $[a,b]$. Case 1: $M = m$, so $f$ is constant and $f'(c)=0$ everywhere. Case 2: $M \neq m$, so at least one of $M, m$ differs from $f(a)=f(b)$, meaning it's attained at an interior point $c \in (a,b)$. By Fermat's theorem, $f'(c)=0$.

C: Rolle's Theorem requires $f$ continuous on $[a,b]$, differentiable on $(a,b)$, and $f(a) = [f(b)]$.

## 6.6 Geometric Interpretation of Rolle's Theorem

Q: What does Rolle's Theorem look like geometrically?
A: If the graph of $f$ starts and ends at the same height over $[a,b]$ (i.e., $f(a)=f(b)$) and is smooth, then somewhere strictly between $a$ and $b$ the tangent line must be horizontal. Intuitively, the graph must "turn around" at least once, and where it turns, the slope is zero.

Q: Why is Rolle's conclusion intuitive if you imagine a hiker walking from altitude $h$ back to altitude $h$?
A: If the hiker starts and ends at the same altitude along a smooth path, they must at some moment be at a highest (or lowest) point — and at that moment their altitude is momentarily not changing, corresponding to zero instantaneous slope.

## 6.7 Mean Value Theorem (MVT)

Q: State the Mean Value Theorem.
A: If $f$ is continuous on $[a,b]$ and differentiable on $(a,b)$, then there exists $c \in (a,b)$ such that $f'(c) = \frac{f(b) - f(a)}{b - a}$. Here $a < b$, and the right-hand side is the average rate of change of $f$ over $[a,b]$.

Q: Why is MVT a generalization of Rolle's Theorem?
A: Rolle's is the special case of MVT when $f(a) = f(b)$: then $\frac{f(b)-f(a)}{b-a} = 0$, so MVT's conclusion becomes $f'(c) = 0$ — exactly Rolle's conclusion. MVT drops the requirement that endpoints match and replaces $0$ with the average slope.

C: The Mean Value Theorem concludes $f'(c) = \frac{f(b) - f(a)}{[b - a]}$ for some $c \in (a,b)$.

Q: What does MVT guarantee about a car trip of 150 miles in 3 hours on a smooth journey?
A: The average speed is $150/3 = 50$ mph. MVT (applied to position $s(t)$, continuous and differentiable) guarantees that at some instant $c$ in the 3-hour interval, the instantaneous speed $s'(c)$ was exactly 50 mph.

## 6.8 Geometric Interpretation of MVT

Q: What is the geometric meaning of MVT?
A: The slope of the secant line connecting $(a, f(a))$ to $(b, f(b))$ equals $\frac{f(b)-f(a)}{b-a}$. MVT says that somewhere in $(a,b)$, the tangent to the graph of $f$ is parallel to this secant. There's a point where the instantaneous slope matches the average slope.

Q: Why does "tangent parallel to secant" capture the essential content of MVT?
A: The secant slope is the average rate of change — a global summary. The tangent slope is the instantaneous rate at a point — a local quantity. MVT asserts these geometric objects (secant and tangent) must be parallel at some interior point, connecting the global average to a local instant.

## 6.9 Proving MVT from Rolle's Theorem

Q: How do we derive MVT from Rolle's Theorem using an auxiliary function?
A: Define $g(x) = f(x) - L(x)$, where $L(x)$ is the secant line through $(a,f(a))$ and $(b,f(b))$: $L(x) = f(a) + \frac{f(b)-f(a)}{b-a}(x-a)$. Then $g(a) = g(b) = 0$, and $g$ inherits continuity and differentiability from $f$. Rolle's gives $c$ with $g'(c)=0$, i.e., $f'(c) = \frac{f(b)-f(a)}{b-a}$.

Q: Why do we subtract the secant line $L(x)$ from $f(x)$ when proving MVT?
A: Subtracting $L$ "tilts" the graph of $f$ so that its new endpoints match: $g(a) = f(a) - L(a) = 0$ and $g(b) = f(b) - L(b) = 0$. This reduces MVT to Rolle's Theorem, which we've already proved.

C: To prove MVT via Rolle's, define $g(x) = f(x) - [L(x)]$, where $L$ is the secant line; this forces $g(a) = g(b)$.

## 6.10 Corollaries of MVT

Q: Why does MVT imply that if $f'(x) = 0$ on an interval $I$, then $f$ is constant on $I$?
A: For any two points $a < b$ in $I$, MVT gives $c$ with $f(b) - f(a) = f'(c)(b-a) = 0 \cdot (b-a) = 0$, so $f(b) = f(a)$. Since $a,b$ were arbitrary, $f$ takes the same value everywhere on $I$.

Q: Why does MVT imply that if $f'(x) > 0$ on $(a,b)$, then $f$ is strictly increasing on $[a,b]$?
A: Pick any $x_1 < x_2$ in $[a,b]$. MVT gives $c \in (x_1, x_2)$ with $f(x_2) - f(x_1) = f'(c)(x_2 - x_1)$. Since $f'(c) > 0$ and $x_2 - x_1 > 0$, the right side is positive, so $f(x_2) > f(x_1)$. This makes $f$ strictly increasing.

Q: Why does MVT imply that two functions with the same derivative differ by a constant?
A: If $f'(x) = g'(x)$ on an interval $I$, then $(f-g)'(x) = 0$ on $I$. By the previous corollary, $f-g$ is constant on $I$, so $f(x) = g(x) + C$ for some constant $C$. This is the logical foundation for the "$+C$" in indefinite integrals.

C: By MVT, if $f'(x) = 0$ on an interval, then $f$ is [constant] on that interval.

C: By MVT, if $f'(x) > 0$ on $(a,b)$, then $f$ is strictly [increasing] on $[a,b]$.

## 6.11 Cauchy's Mean Value Theorem

Q: State Cauchy's Mean Value Theorem (the generalized MVT).
A: If $f$ and $g$ are continuous on $[a,b]$, differentiable on $(a,b)$, and $g'(x) \neq 0$ on $(a,b)$, then there exists $c \in (a,b)$ such that $\frac{f'(c)}{g'(c)} = \frac{f(b) - f(a)}{g(b) - g(a)}$.

Q: Why is Cauchy's MVT a genuine generalization of the ordinary MVT?
A: Taking $g(x) = x$ gives $g'(c) = 1$ and $g(b) - g(a) = b - a$, so Cauchy's conclusion becomes $f'(c) = \frac{f(b)-f(a)}{b-a}$ — the ordinary MVT. Cauchy's version handles two functions simultaneously, which is essential for proving L'Hôpital's Rule.

C: Cauchy's MVT concludes $\frac{f'(c)}{g'(c)} = \frac{f(b)-f(a)}{[g(b)-g(a)]}$ under its hypotheses.

## 6.12 Indeterminate Forms

Q: What is an "indeterminate form" in the context of limits?
A: An expression like $\frac{0}{0}$ or $\frac{\infty}{\infty}$ whose value cannot be determined by the forms of the numerator and denominator alone — the actual limit depends on HOW the pieces approach those values. These forms signal that more analysis (e.g., L'Hôpital's Rule) is needed.

Q: Why is $\frac{0}{0}$ called indeterminate rather than just undefined?
A: Different $\frac{0}{0}$ limits can equal any value. $\lim_{x\to 0}\frac{x}{x}=1$, $\lim_{x\to 0}\frac{x^2}{x}=0$, $\lim_{x\to 0}\frac{x}{x^3}=\infty$. All are "$0/0$" in form, but the limits differ — so the form alone is indeterminate.

C: The seven classical indeterminate forms are $\frac{0}{0}$, $\frac{\infty}{\infty}$, $0\cdot\infty$, $\infty - \infty$, $0^0$, $1^\infty$, and $[\infty^0]$.

Q: Why is $1^\infty$ indeterminate even though $1$ to any finite power is $1$?
A: In a limit $1^\infty$, the base approaches $1$ but isn't exactly $1$. Tiny deviations like $(1 + \frac{1}{n})^n \to e$ show that the infinite exponent can amplify the deviation into a nontrivial limit. The "$1$" is a limit, not a true $1$.

## 6.13 L'Hôpital's Rule

Q: State L'Hôpital's Rule for the $\frac{0}{0}$ form.
A: Suppose $f$ and $g$ are differentiable near $a$ (except possibly at $a$), $g'(x) \neq 0$ near $a$, and $\lim_{x\to a} f(x) = \lim_{x\to a} g(x) = 0$. If $\lim_{x\to a}\frac{f'(x)}{g'(x)}$ exists (or is $\pm\infty$), then $\lim_{x\to a}\frac{f(x)}{g(x)} = \lim_{x\to a}\frac{f'(x)}{g'(x)}$.

Q: Does L'Hôpital's Rule also apply to $\frac{\infty}{\infty}$ forms?
A: Yes. If $\lim_{x\to a} f(x) = \pm\infty$ and $\lim_{x\to a} g(x) = \pm\infty$ (with $g'(x) \neq 0$ near $a$), and $\lim \frac{f'(x)}{g'(x)}$ exists or is $\pm\infty$, then $\lim \frac{f(x)}{g(x)} = \lim \frac{f'(x)}{g'(x)}$. The limit point $a$ can also be $\pm\infty$.

C: L'Hôpital's Rule says that for an indeterminate $\frac{0}{0}$ or $\frac{\infty}{\infty}$, $\lim \frac{f(x)}{g(x)} = \lim \frac{f'(x)}{[g'(x)]}$ when the latter limit exists.

Q: Why must we verify the form is indeterminate BEFORE applying L'Hôpital's Rule?
A: L'Hôpital's hypotheses require $\frac{0}{0}$ or $\frac{\infty}{\infty}$. Applying it to, say, $\lim_{x\to 0}\frac{\cos x}{x+1}$ (which is $\frac{1}{1}=1$) incorrectly gives $\lim \frac{-\sin x}{1} = 0$. The rule silently gives wrong answers if the precondition fails.

## 6.14 Why L'Hôpital Works

Q: Why does L'Hôpital's Rule work? (Sketch the idea via Cauchy's MVT.)
A: Near $a$ with $f(a)=g(a)=0$, Cauchy's MVT gives some $c_x$ between $x$ and $a$ with $\frac{f(x)}{g(x)} = \frac{f(x)-f(a)}{g(x)-g(a)} = \frac{f'(c_x)}{g'(c_x)}$. As $x\to a$, $c_x\to a$ too, so $\frac{f(x)}{g(x)} \to \lim \frac{f'(x)}{g'(x)}$. L'Hôpital is Cauchy's MVT taken to the limit.

Q: Intuitively, why should $\lim \frac{f}{g} = \lim \frac{f'}{g'}$ when both $f, g \to 0$?
A: Near $a$, the linear approximations are $f(x) \approx f'(a)(x-a)$ and $g(x) \approx g'(a)(x-a)$. The ratio of these approximations is $\frac{f'(a)(x-a)}{g'(a)(x-a)} = \frac{f'(a)}{g'(a)}$ — the $(x-a)$ factors cancel. L'Hôpital captures this cancellation rigorously.

## 6.15 When L'Hôpital Does NOT Apply

Q: When does L'Hôpital's Rule NOT apply, and what goes wrong if you force it?
A: It doesn't apply when the limit is NOT in an indeterminate $\frac{0}{0}$ or $\frac{\infty}{\infty}$ form. Forcing it on a determinate form (e.g., $\frac{2}{3}$ as $x\to a$) replaces a well-defined limit with the ratio of derivatives, which can be anything — producing wrong answers.

Q: Why can repeated application of L'Hôpital's Rule fail even when each step is indeterminate?
A: If $\lim \frac{f'(x)}{g'(x)}$ oscillates and doesn't exist (not even $\pm\infty$), the rule's conclusion doesn't apply — the original limit might still exist via other methods. Example: $\lim_{x\to\infty}\frac{x+\sin x}{x}=1$, but $\lim \frac{1+\cos x}{1}$ doesn't exist.

C: L'Hôpital's Rule does not apply to limits that are already in [determinate] form (such as $\frac{1}{2}$ or $\frac{0}{5}$).

## 6.16 Converting Other Indeterminate Forms

Q: Why must forms like $0\cdot\infty$, $\infty-\infty$, $0^0$, $1^\infty$, $\infty^0$ be converted before L'Hôpital's Rule applies?
A: L'Hôpital's Rule is stated only for $\frac{0}{0}$ and $\frac{\infty}{\infty}$. Other indeterminate forms must be algebraically rewritten as a quotient (for $0\cdot\infty$ or $\infty-\infty$) or converted via logarithms (for $0^0$, $1^\infty$, $\infty^0$) to match the rule's required form.

Q: What is the general strategy for attacking any indeterminate form?
A: (1) Identify which of the seven indeterminate forms it is. (2) Use algebra or logarithms to convert to $\frac{0}{0}$ or $\frac{\infty}{\infty}$. (3) Apply L'Hôpital's Rule. (4) If the result is still indeterminate, repeat; if determinate, you have the limit.

## 6.17 Specific Conversion Techniques

Q: How do you convert a $0\cdot\infty$ limit to a $\frac{0}{0}$ or $\frac{\infty}{\infty}$ form?
A: Rewrite $f(x)\cdot g(x)$ as a quotient: either $\frac{f(x)}{1/g(x)}$ (giving $\frac{0}{0}$) or $\frac{g(x)}{1/f(x)}$ (giving $\frac{\infty}{\infty}$). Choose whichever makes the subsequent derivatives simpler. Example: $\lim_{x\to 0^+} x\ln x = \lim \frac{\ln x}{1/x}$ ($\frac{-\infty}{\infty}$ form).

Q: How do you handle $1^\infty$, $0^0$, or $\infty^0$ indeterminate forms?
A: Let $y = f(x)^{g(x)}$, then $\ln y = g(x) \ln f(x)$, which is a $0\cdot\infty$ form you can convert to a quotient. Find $L = \lim \ln y$ using L'Hôpital, then the original limit is $e^L$. Taking logs turns exponential indeterminates into multiplicative ones.

Q: How do you handle $\infty - \infty$ indeterminate forms?
A: Combine the two terms into a single fraction using a common denominator, algebraic manipulation, or a conjugate trick. The result is typically $\frac{0}{0}$ or $\frac{\infty}{\infty}$, to which L'Hôpital's Rule applies. Example: $\lim_{x\to 0}\left(\frac{1}{\sin x} - \frac{1}{x}\right) = \lim \frac{x - \sin x}{x\sin x}$.

C: To attack $1^\infty$, set $y = f(x)^{g(x)}$ and first evaluate $\lim [\ln y] = \lim g(x)\ln f(x)$.

## 6.18 Applying MVT: Lipschitz Bound for Sine

P: Use the Mean Value Theorem to prove that $|\sin b - \sin a| \leq |b - a|$ for all real $a, b$, where $a$ and $b$ are real numbers.

S:
**IDENTIFY**: Bound the difference of function values using the derivative — a classic MVT application (Lipschitz-type inequality).

**PLAN**:
- $f(x) = \sin x$ is continuous and differentiable everywhere.
- By MVT, $\frac{\sin b - \sin a}{b - a} = f'(c) = \cos c$ for some $c$ between $a$ and $b$.
- Use the bound $|\cos c| \leq 1$.

**EXECUTE**:
1. WLOG assume $a < b$ (if $a=b$, both sides are $0$; if $a>b$, swap).
2. $f(x) = \sin x$ is continuous on $[a,b]$ and differentiable on $(a,b)$.
3. By MVT, $\exists c \in (a,b)$ with $\sin b - \sin a = \cos c \cdot (b - a)$.
4. Take absolute values: $|\sin b - \sin a| = |\cos c| \cdot |b - a|$.
5. Since $|\cos c| \leq 1$ for all $c$: $|\sin b - \sin a| \leq 1 \cdot |b - a| = |b - a|$.

**EVALUATE**:
- The inequality holds with equality only when $|\cos c|=1$ everywhere between $a$ and $b$, which fails generically — so usually strict inequality.
- This shows $\sin$ is "Lipschitz continuous" with Lipschitz constant $1$.
- Sanity check: for $a = 0, b = \pi$: $|\sin \pi - \sin 0| = 0 \leq \pi$. ✓

## 6.19 Applying L'Hôpital: Classic $0/0$ Limit

P: Evaluate $\displaystyle\lim_{x \to 0} \frac{e^x - 1 - x}{x^2}$ using L'Hôpital's Rule.

S:
**IDENTIFY**: Limit of the form $\frac{0}{0}$ (substituting $x=0$: numerator $= 1 - 1 - 0 = 0$, denominator $= 0$). L'Hôpital's Rule applies.

**PLAN**:
- Verify the form is indeterminate.
- Differentiate numerator and denominator separately.
- If still $\frac{0}{0}$, apply L'Hôpital again.
- Continue until a determinate form appears.

**EXECUTE**:
1. Check indeterminate form: numerator $\to 1 - 1 - 0 = 0$; denominator $\to 0$. Form is $\frac{0}{0}$. ✓
2. Differentiate: $\frac{d}{dx}(e^x - 1 - x) = e^x - 1$; $\frac{d}{dx}(x^2) = 2x$.
3. New limit: $\displaystyle\lim_{x\to 0}\frac{e^x - 1}{2x}$. Check form: numerator $\to 1 - 1 = 0$; denominator $\to 0$. Still $\frac{0}{0}$.
4. Apply L'Hôpital again: $\frac{d}{dx}(e^x - 1) = e^x$; $\frac{d}{dx}(2x) = 2$.
5. New limit: $\displaystyle\lim_{x\to 0}\frac{e^x}{2} = \frac{e^0}{2} = \frac{1}{2}$. Determinate — done.

**EVALUATE**:
- Answer: $\lim_{x\to 0}\frac{e^x - 1 - x}{x^2} = \frac{1}{2}$.
- Sanity check via Taylor series: $e^x = 1 + x + \frac{x^2}{2} + O(x^3)$, so $e^x - 1 - x = \frac{x^2}{2} + O(x^3)$, giving $\frac{e^x - 1 - x}{x^2} = \frac{1}{2} + O(x) \to \frac{1}{2}$. ✓
- Two applications of L'Hôpital matches the fact that the numerator vanishes to second order at $x=0$.
