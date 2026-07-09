+++
order = 9
subject = "Math"
tags = ["math", "calculus", "antiderivative", "indefinite-integral", "initial-value-problem"]
+++

# Calculus — Antiderivatives and Indefinite Integrals

## 9.1 Motivating Problem: Reversing Differentiation

Q: What new question motivates the study of antiderivatives?
A: So far we have started with a function $f$ and computed its derivative $f'$. The reverse question is: given a function $f$, can we find a function $F$ whose derivative equals $f$? This is called "antidifferentiation," and it is the gateway to integral calculus.

Q: Why is reversing differentiation an important problem in applications?
A: Many physical laws describe rates of change ($f'$) — velocity, growth rate, force per unit area. To recover the underlying quantity (position, population, total force), we must reverse differentiation. Antidifferentiation is how we go from a rate back to an accumulated total.

C: The operation that undoes differentiation is called [antidifferentiation].

## 9.2 Definition of an Antiderivative

Q: What is an antiderivative of a function $f$ on an interval $I$?
A: A function $F$ is called an antiderivative of $f$ on $I$ if $F'(x) = f(x)$ for every $x$ in $I$. In other words, $F$ is a function whose derivative is $f$ everywhere on $I$.

C: $F$ is an [antiderivative] of $f$ on an interval $I$ if $F'(x) = f(x)$ for every $x \in I$.

Q: Give a simple example of an antiderivative.
A: $F(x) = x^2$ is an antiderivative of $f(x) = 2x$, because $F'(x) = 2x = f(x)$. Equally, $G(x) = x^2 + 5$ is also an antiderivative of $f$, since the constant $5$ differentiates to zero.

## 9.3 Family of Antiderivatives

Q: If $F$ is one antiderivative of $f$, what does the full family of antiderivatives look like?
A: Every antiderivative has the form $F(x) + C$, where $C$ is an arbitrary real constant. Thus antiderivatives come in an infinite one-parameter family, all parallel vertical shifts of the same "shape."

C: If $F$ is an antiderivative of $f$ on an interval, every antiderivative of $f$ has the form [$F(x) + C$], where $C$ is a real constant.

Q: Why is the constant $C$ called the "constant of integration"?
A: It is the one undetermined parameter that arises whenever we reverse differentiation. Because constants vanish under $\frac{d}{dx}$, no amount of differentiating can tell us which vertical shift produced $f$, so $C$ remains as a free parameter until an extra condition pins it down.

## 9.4 Why Adding a Constant Doesn't Change the Derivative

Q: Why does adding a constant to an antiderivative produce another antiderivative?
A: Differentiation is linear, and the derivative of any constant is zero: $\frac{d}{dx}(F(x) + C) = F'(x) + 0 = f(x)$. So shifting $F$ vertically leaves its slope function untouched.

C: For any constant $C$, $\frac{d}{dx}[F(x) + C] = $ [$F'(x)$], because the derivative of a constant is zero.

## 9.5 Why EVERY Antiderivative Differs by Only a Constant

Q: Why is every antiderivative of $f$ on an interval of the form $F(x) + C$ — not some more exotic function?
A: Suppose $F$ and $G$ are both antiderivatives of $f$ on an interval $I$. Then $(G - F)'(x) = f(x) - f(x) = 0$ on $I$. By a corollary of the Mean Value Theorem, a function with zero derivative on an interval is constant, so $G(x) - F(x) = C$, i.e. $G = F + C$.

Q: Which earlier theorem guarantees that a function with zero derivative on an interval must be constant?
A: The Mean Value Theorem. If $h'(x) = 0$ on $I$, then for any two points $a < b$ in $I$, the MVT gives some $c$ with $h(b) - h(a) = h'(c)(b-a) = 0$. Hence $h$ takes the same value everywhere on $I$.

C: By a corollary of the [Mean Value Theorem], any function with zero derivative on an interval is constant on that interval.

Q: Why must the domain be an interval in the "differ by a constant" theorem?
A: The MVT argument requires connecting two points by a path lying inside the domain. On a disconnected set (e.g. two separate intervals), the "constants" on each piece could be different, and $G - F$ need not equal the same $C$ everywhere.

## 9.6 Notation of the Indefinite Integral

Q: What is the indefinite integral notation, and what does it mean?
A: We write $\int f(x)\,dx = F(x) + C$, meaning "the family of all antiderivatives of $f$ with respect to $x$." The symbol $\int$ is the integral sign, $f(x)$ is the integrand, $dx$ indicates the variable of integration, and $C$ is the constant of integration.

C: The notation $\int f(x)\,dx$ denotes the [family of all antiderivatives] of $f$ with respect to $x$.

Q: Why do we call $\int f(x)\,dx$ the "indefinite" integral?
A: "Indefinite" signals that the answer is not a single function but an entire family, $F(x) + C$, with the constant $C$ left undetermined. This contrasts with the "definite" integral, which produces a specific number.

## 9.7 Meaning of the $dx$

Q: What role does the $dx$ play inside $\int f(x)\,dx$?
A: The $dx$ is a differential that names the variable of integration — the variable with respect to which $f$ is being anti-differentiated. It distinguishes, e.g., $\int xt\,dx = \tfrac{1}{2}x^2 t + C$ from $\int xt\,dt = \tfrac{1}{2}xt^2 + C$, where $t$ is treated as a constant in the first and $x$ as a constant in the second.

C: In $\int f(x)\,dx$, the $dx$ signals that $x$ is the [variable of integration].

Q: Why is the $dx$ not just decorative notation?
A: It anchors the integral to a specific variable, which matters when the integrand has several symbols. It also foreshadows the substitution rule, where $dx$ transforms like a genuine differential under a change of variable.

## 9.8 Power Rule for Integration

Q: What is the power rule for integration?
A: For any real exponent $n \ne -1$, $\int x^n\,dx = \dfrac{x^{n+1}}{n+1} + C$, where $x$ is the variable, $n$ is a constant exponent, and $C$ is the constant of integration. The rule is verified by differentiating the right side and recovering $x^n$.

C: For $n \ne -1$, $\int x^n\,dx = $ [$\dfrac{x^{n+1}}{n+1} + C$].

Q: Why does the power rule for integration look like the reverse of the power rule for differentiation?
A: Differentiation drops the exponent by 1 and multiplies by the old exponent: $\frac{d}{dx}x^{n+1} = (n+1)x^n$. To reverse this, we raise the exponent by 1 and divide by the new exponent, producing $\frac{x^{n+1}}{n+1}$.

## 9.9 Why $n = -1$ Is Excluded

Q: Why is $n = -1$ excluded from the integration power rule?
A: The formula $\dfrac{x^{n+1}}{n+1}$ has $n+1$ in the denominator, which becomes $0$ at $n = -1$, giving $\dfrac{x^0}{0}$ — undefined. So the power rule breaks down exactly for $f(x) = x^{-1} = 1/x$, and we need a different antiderivative.

C: The power rule fails at $n = -1$ because [$n+1 = 0$] would produce division by zero.

Q: What kind of function should we expect to be the antiderivative of $1/x$?
A: Since $\frac{d}{dx}(\ln x) = 1/x$, the natural logarithm must appear. So the antiderivative of $1/x$ is built from $\ln$, not from a power of $x$.

## 9.10 Integral of $1/x$

Q: What is $\int \dfrac{1}{x}\,dx$?
A: $\int \dfrac{1}{x}\,dx = \ln|x| + C$, valid on any interval not containing $0$. The absolute value lets the formula cover both $x > 0$ and $x < 0$ in a single expression.

C: $\int \dfrac{1}{x}\,dx = $ [$\ln|x| + C$].

Q: Why does $\ln|x|$ — with an absolute value — appear instead of just $\ln x$?
A: $\ln x$ is only defined for $x > 0$, but $1/x$ is defined for all $x \ne 0$. For $x < 0$, $\frac{d}{dx}\ln(-x) = \frac{-1}{-x} = \frac{1}{x}$, so $\ln(-x)$ is the antiderivative there. Using $\ln|x|$ stitches both cases together with one formula.

## 9.11 Integrals of Trigonometric Functions

C: $\int \sin x\,dx = $ [$-\cos x + C$].

C: $\int \cos x\,dx = $ [$\sin x + C$].

C: $\int \sec^2 x\,dx = $ [$\tan x + C$].

C: $\int \csc^2 x\,dx = $ [$-\cot x + C$].

C: $\int \sec x \tan x\,dx = $ [$\sec x + C$].

C: $\int \csc x \cot x\,dx = $ [$-\csc x + C$].

Q: Why is $\int \sin x\,dx = -\cos x + C$ rather than $+\cos x + C$?
A: Because $\frac{d}{dx}\cos x = -\sin x$, not $+\sin x$. To get $\sin x$ back upon differentiation, we must differentiate $-\cos x$: $\frac{d}{dx}(-\cos x) = \sin x$. The minus sign is forced by the sign in the derivative of cosine.

Q: How can you remember the trig antiderivative table without memorizing it?
A: Just differentiate the "co" and "non-co" trig functions and read the table backwards. The minus signs attach to antiderivatives whose "forward" derivative produced a minus — namely $\cos$, $\cot$, and $\csc$.

## 9.12 Integrals of Exponential Functions

C: $\int e^x\,dx = $ [$e^x + C$].

C: For $a > 0$ with $a \ne 1$, $\int a^x\,dx = $ [$\dfrac{a^x}{\ln a} + C$].

Q: Why is $e^x$ its own antiderivative?
A: Because $\frac{d}{dx}e^x = e^x$. Since differentiating leaves it unchanged, anti-differentiating must also leave it unchanged (up to the $+C$). $e^x$ is the unique function (up to scalar) with this self-reproducing property.

Q: Why does $\int a^x\,dx = \dfrac{a^x}{\ln a} + C$ — where does $\ln a$ come from?
A: Because $\frac{d}{dx}a^x = a^x \ln a$, where $a$ is the base and $\ln a$ is the natural log of the base. To kill the extra factor of $\ln a$ under differentiation, we must divide by $\ln a$ in the antiderivative, giving $\frac{a^x}{\ln a}$.

Q: Why must we require $a \ne 1$ in $\int a^x\,dx = \dfrac{a^x}{\ln a} + C$?
A: $\ln 1 = 0$, making the denominator zero. But also $a = 1$ gives the trivial integrand $1^x = 1$, whose antiderivative is simply $x + C$ — no special formula needed.

## 9.13 Integrals Giving Inverse Trig Functions

C: $\int \dfrac{1}{\sqrt{1-x^2}}\,dx = $ [$\arcsin x + C$].

C: $\int \dfrac{1}{1+x^2}\,dx = $ [$\arctan x + C$].

C: $\int \dfrac{1}{|x|\sqrt{x^2-1}}\,dx = $ [$\operatorname{arcsec}|x| + C$].

Q: Why do inverse trig functions arise naturally as antiderivatives?
A: Differentiating $\arcsin x$, $\arctan x$, and $\operatorname{arcsec}|x|$ produces exactly the algebraic expressions $\frac{1}{\sqrt{1-x^2}}$, $\frac{1}{1+x^2}$, and $\frac{1}{|x|\sqrt{x^2-1}}$. Since those algebraic integrands contain no visible inverse trig, the connection would be invisible without knowing the derivative formulas.

Q: How can you tell at a glance that $\int \frac{1}{1+x^2}\,dx$ should be an inverse trig function rather than a logarithm?
A: The denominator is $1 + x^2$, a sum of squares, which never factors over the reals. Sums of squares are the fingerprint of $\arctan$, while differences (like $1/(1-x^2)$) factor and lead to logs via partial fractions.

## 9.14 Linearity of Integration

Q: What are the two linearity properties of the indefinite integral?
A: (1) Sum rule: $\int [f(x) + g(x)]\,dx = \int f(x)\,dx + \int g(x)\,dx$. (2) Constant multiple rule: $\int k\,f(x)\,dx = k\int f(x)\,dx$ for any constant $k$. Together these mean $\int$ is a linear operator on functions.

C: The sum rule for integrals: $\int [f(x)+g(x)]\,dx = $ [$\int f(x)\,dx + \int g(x)\,dx$].

C: The constant multiple rule: for a constant $k$, $\int k\,f(x)\,dx = $ [$k\int f(x)\,dx$].

Q: Why is linearity of integration automatic once we know linearity of differentiation?
A: If $F' = f$ and $G' = g$, then $(F + G)' = f + g$ and $(kF)' = kf$. So $F + G$ is an antiderivative of $f + g$, and $kF$ is an antiderivative of $kf$. Linearity transfers from $\frac{d}{dx}$ to $\int$ verbatim.

Q: Is there a product rule or quotient rule for integrals analogous to those for derivatives?
A: No — $\int fg\,dx \ne (\int f\,dx)(\int g\,dx)$ in general, and similarly for quotients. Integration of products requires techniques like substitution or integration by parts, developed in later chapters.

## 9.15 Initial Value Problems (IVPs)

Q: What is an initial value problem (IVP) in the context of antiderivatives?
A: An IVP specifies a derivative equation $F'(x) = f(x)$ together with a single condition $F(x_0) = y_0$ at some point $x_0$. The condition pins down the constant $C$ in the general antiderivative, selecting one specific function from the family $F(x) + C$.

C: An [initial value problem] combines a derivative equation $F'(x) = f(x)$ with a condition $F(x_0) = y_0$ to determine the constant $C$ uniquely.

Q: Why is exactly one initial condition needed to determine the constant in a first-order IVP?
A: The general antiderivative contains one free parameter $C$. Plugging $x = x_0$ into $F(x) + C = y_0$ yields one linear equation in one unknown ($C$), which has a unique solution. More conditions would over-determine the problem.

## 9.16 Applications: Kinematics

Q: How do you recover position $s(t)$ from velocity $v(t)$?
A: Since $s'(t) = v(t)$ by definition, $s(t) = \int v(t)\,dt + C$, where $t$ is time. The constant $C$ is determined by an initial position $s(t_0) = s_0$, which gives one specific position function.

Q: How do you recover velocity $v(t)$ from acceleration $a(t)$?
A: Since $v'(t) = a(t)$, $v(t) = \int a(t)\,dt + C$, where $C$ is fixed by the initial velocity $v(t_0) = v_0$. Iterating once more recovers position: $s(t) = \int v(t)\,dt$ with another initial condition.

C: From acceleration $a(t)$ to position $s(t)$ requires [two integrations], each introducing a constant fixed by one initial condition (initial velocity and initial position).

Q: Why do kinematics problems always need two initial conditions when starting from acceleration?
A: Each integration introduces one constant of integration. Going from $a(t)$ to $v(t)$ introduces one, and going from $v(t)$ to $s(t)$ introduces another. Two unknowns require two independent conditions — typically $v(t_0) = v_0$ and $s(t_0) = s_0$.

## 9.17 Reverse Chain Rule (Preview of Substitution)

Q: The chain rule says $\frac{d}{dx}F(g(x)) = F'(g(x))\,g'(x)$. What does reading it backwards tell us about integration?
A: $\int F'(g(x))\,g'(x)\,dx = F(g(x)) + C$. So when an integrand looks like "a function of $g(x)$ times $g'(x)$," its antiderivative is just $F$ composed with $g$. This observation powers the method of substitution.

Q: What pattern should you scan an integrand for to spot that the reverse chain rule applies?
A: Look for a composite function $F'(g(x))$ multiplied by the derivative $g'(x)$ of its inner function. For example, $\int 2x\,\cos(x^2)\,dx$ fits with $g(x) = x^2$ and $g'(x) = 2x$, giving $\sin(x^2) + C$.

C: Reversing the chain rule: $\int F'(g(x))\,g'(x)\,dx = $ [$F(g(x)) + C$].

## 9.18 Worked Example — Linearity and the Power Rule

P: Find $\int (3x^2 - 4\sin x)\,dx$.

S:
**IDENTIFY**: An indefinite integral of a linear combination of two basic functions: a power ($x^2$) and a trig function ($\sin x$). No composition, no product — straight linearity + table lookups.

**PLAN**:
- Apply the sum rule and constant multiple rule to split into two simpler integrals.
- Use the power rule on $\int x^2\,dx$ and the trig table on $\int \sin x\,dx$.
- Combine and write a single $+C$ at the end.

**EXECUTE**:
1. Split: $\int (3x^2 - 4\sin x)\,dx = 3\int x^2\,dx - 4\int \sin x\,dx$.
2. Power rule with $n = 2$: $\int x^2\,dx = \dfrac{x^3}{3}$.
3. Trig table: $\int \sin x\,dx = -\cos x$.
4. Assemble: $3 \cdot \dfrac{x^3}{3} - 4(-\cos x) = x^3 + 4\cos x$.
5. Add the constant: $\int (3x^2 - 4\sin x)\,dx = x^3 + 4\cos x + C$.

**EVALUATE**:
- Differentiate to check: $\frac{d}{dx}(x^3 + 4\cos x + C) = 3x^2 - 4\sin x$. ✓
- One constant $C$ suffices (combining constants from both pieces).

## 9.19 Worked Example — Solving an IVP

P: Solve the IVP $f'(x) = \dfrac{1}{x} + \sec^2 x$ with $f(\pi/4) = 2$.

S:
**IDENTIFY**: First-order IVP. We must antidifferentiate $f'$ to get the general antiderivative $f(x) + C$, then use the condition at $x = \pi/4$ to pin down $C$.

**PLAN**:
- Antidifferentiate each term: $1/x \to \ln|x|$, $\sec^2 x \to \tan x$ (from the trig table).
- Write the general solution with one constant $C$.
- Substitute $x = \pi/4$ and set equal to $2$ to solve for $C$.

**EXECUTE**:
1. General antiderivative: $f(x) = \int \left(\dfrac{1}{x} + \sec^2 x\right)dx = \ln|x| + \tan x + C$.
2. Apply the initial condition $f(\pi/4) = 2$: $\ln(\pi/4) + \tan(\pi/4) + C = 2$.
3. Evaluate $\tan(\pi/4) = 1$: $\ln(\pi/4) + 1 + C = 2$.
4. Solve for $C$: $C = 1 - \ln(\pi/4)$.
5. Final solution: $f(x) = \ln|x| + \tan x + 1 - \ln(\pi/4)$.

**EVALUATE**:
- Differentiate: $f'(x) = \frac{1}{x} + \sec^2 x$. ✓
- Check the condition: $f(\pi/4) = \ln(\pi/4) + 1 + 1 - \ln(\pi/4) = 2$. ✓
- Domain check: $\pi/4 > 0$, so $\ln|x|$ behaves as $\ln x$ in a neighborhood; $\tan x$ is smooth there too. Solution is valid on $(0, \pi/2)$.
