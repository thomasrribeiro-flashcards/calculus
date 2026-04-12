+++
order = 4
tags = ["math", "calculus", "derivative", "trig", "exponential", "logarithm", "inverse-trig"]
+++

# Calculus — Derivatives of Transcendental Functions

## 4.1 What "Transcendental" Means

Q: What distinguishes a transcendental function from an algebraic function?
A: An algebraic function can be built from finitely many additions, multiplications, divisions, and roots applied to the variable (e.g., $x^2$, $\sqrt{x}$, $\frac{x+1}{x^2-3}$). A transcendental function cannot — it "transcends" algebra. Examples include $\sin x$, $\cos x$, $e^x$, $\ln x$, and $\arctan x$.

Q: Why do we study the derivatives of transcendental functions as a separate topic?
A: The power rule and basic algebraic rules from Chapter 3 do not apply to them — $\frac{d}{dx}\sin x$ is not $x\cdot(\text{something})^{-1}$. Each family (trig, exponential, logarithmic, inverse trig) has its own derivative rule that must be derived from the limit definition or from an inverse relationship.

C: Functions like $\sin x$, $e^x$, and $\ln x$ are called [transcendental] because they cannot be expressed using finitely many algebraic operations on $x$.

C: The three main families of transcendental functions in elementary calculus are trigonometric, [exponential], and logarithmic (plus their inverses).

## 4.2 Derivative of Sine

Q: What is $\frac{d}{dx}\sin x$, and what does the answer mean geometrically?
A: $\frac{d}{dx}\sin x = \cos x$. Geometrically, the slope of the sine curve at any point $x$ equals the height of the cosine curve at that same $x$. Where $\sin x$ peaks ($x=\pi/2$), its slope is zero — which is exactly $\cos(\pi/2)=0$.

C: $\frac{d}{dx}\sin x = [\cos x]$, valid for $x$ measured in radians.

Q: Why does the formula $\frac{d}{dx}\sin x = \cos x$ require $x$ to be in radians?
A: The derivation depends on $\lim_{h\to 0}\frac{\sin h}{h} = 1$, which is only true when $h$ is in radians. In degrees, the limit equals $\frac{\pi}{180}$, introducing an unwanted constant factor into every derivative.

## 4.3 Deriving $\frac{d}{dx}\sin x$ from the Limit Definition

Q: Why is the limit $\lim_{h\to 0}\frac{\sin h}{h} = 1$ the crucial ingredient in deriving $\frac{d}{dx}\sin x$?
A: Applying the limit definition produces a term $\sin x\cdot\frac{\cos h - 1}{h}$ and a term $\cos x\cdot\frac{\sin h}{h}$. These two special trig limits ($\to 0$ and $\to 1$) collapse the messy expression into the clean answer $\cos x$. Without them the derivative would remain an unevaluated limit.

C: The small-angle limit $\lim_{h\to 0}\frac{\sin h}{h} = [1]$ is essential for differentiating trigonometric functions.

C: The companion limit $\lim_{h\to 0}\frac{\cos h - 1}{h} = [0]$, which allows the $\sin x$ term to vanish during the derivation of $\frac{d}{dx}\sin x$.

Q: Sketch the derivation: how does $\frac{\sin(x+h)-\sin x}{h}$ become $\cos x$?
A: Expand with the angle-addition formula: $\sin(x+h)=\sin x\cos h + \cos x\sin h$. Subtracting $\sin x$ and dividing by $h$ gives $\sin x\cdot\frac{\cos h - 1}{h} + \cos x\cdot\frac{\sin h}{h}$. As $h\to 0$, the first term $\to \sin x\cdot 0 = 0$ and the second $\to \cos x\cdot 1 = \cos x$.

## 4.4 Derivative of Cosine

C: $\frac{d}{dx}\cos x = [-\sin x]$.

Q: How can you derive $\frac{d}{dx}\cos x$ without redoing a limit argument from scratch?
A: Use the cofunction identity $\cos x = \sin(\pi/2 - x)$ and apply the chain rule: $\frac{d}{dx}\sin(\pi/2 - x) = \cos(\pi/2 - x)\cdot(-1) = -\sin x$. The identity converts cosine into a sine, so the sine derivative rule transfers directly.

## 4.5 Why the Negative Sign in $\frac{d}{dx}\cos x$

Q: Why is $\frac{d}{dx}\cos x$ negative, not positive?
A: Because cosine is decreasing on $(0,\pi)$, where most early examples live. At $x=0$ the cosine curve is at its maximum ($y=1$) with zero slope, then tilts downward — slopes on this interval are negative. The function $-\sin x$ captures that: it starts at $0$ and becomes negative as $x$ grows from $0$.

Q: How does the unit-circle picture explain the sign difference between $\frac{d}{dx}\sin x$ and $\frac{d}{dx}\cos x$?
A: Moving counterclockwise on the unit circle, the $y$-coordinate ($\sin x$) rises when $x$ is in the right half, while the $x$-coordinate ($\cos x$) shrinks. Motion advances sine but retreats cosine, producing the $+\cos x$ for sine's rate of change and $-\sin x$ for cosine's.

## 4.6 Derivative of Tangent via Quotient Rule

Q: Derive $\frac{d}{dx}\tan x$ using the quotient rule.
A: Write $\tan x = \frac{\sin x}{\cos x}$. The quotient rule gives $\frac{\cos x\cdot\cos x - \sin x\cdot(-\sin x)}{\cos^2 x} = \frac{\cos^2 x + \sin^2 x}{\cos^2 x} = \frac{1}{\cos^2 x} = \sec^2 x$. The Pythagorean identity $\sin^2 x + \cos^2 x = 1$ collapses the numerator.

C: $\frac{d}{dx}\tan x = [\sec^2 x]$, where $\sec x = 1/\cos x$.

Q: Why is $\frac{d}{dx}\tan x$ always positive on each interval where tangent is defined?
A: Because $\sec^2 x = 1/\cos^2 x$ is a square of a real number, it is always non-negative, and never zero (since $\cos x$ would have to be infinite). So tangent is strictly increasing on every interval $(-\pi/2 + k\pi,\ \pi/2 + k\pi)$.

## 4.7 Derivatives of Cotangent, Secant, Cosecant

C: $\frac{d}{dx}\cot x = [-\csc^2 x]$, where $\csc x = 1/\sin x$.

C: $\frac{d}{dx}\sec x = [\sec x\tan x]$.

C: $\frac{d}{dx}\csc x = [-\csc x\cot x]$.

Q: What pattern ties together the derivatives of $\cos x$, $\cot x$, and $\csc x$?
A: They all carry a negative sign and involve the "co-" named trig function or its relatives. The mnemonic is: functions starting with "co-" ($\cos$, $\cot$, $\csc$) differentiate to negative expressions, while $\sin$, $\tan$, $\sec$ differentiate to positive ones.

Q: How do you derive $\frac{d}{dx}\sec x$?
A: Rewrite $\sec x = (\cos x)^{-1}$ and apply the chain rule: $-1\cdot(\cos x)^{-2}\cdot(-\sin x) = \frac{\sin x}{\cos^2 x} = \frac{1}{\cos x}\cdot\frac{\sin x}{\cos x} = \sec x\tan x$.

## 4.8 Summary Table of Six Trig Derivatives

C: Trig derivative: $\frac{d}{dx}\sin x = [\cos x]$.

C: Trig derivative: $\frac{d}{dx}\cos x = [-\sin x]$.

C: Trig derivative: $\frac{d}{dx}\tan x = [\sec^2 x]$.

C: Trig derivative: $\frac{d}{dx}\cot x = [-\csc^2 x]$.

C: Trig derivative: $\frac{d}{dx}\sec x = [\sec x\tan x]$.

C: Trig derivative: $\frac{d}{dx}\csc x = [-\csc x\cot x]$.

Q: What is the fastest sanity check that a student has memorized the six trig derivatives correctly?
A: Check the sign pattern: the three "co-" functions ($\cos$, $\cot$, $\csc$) give negative derivatives; the other three give positive ones. Then check that each derivative uses functions "of the same family" (e.g., tangent differentiates to secant-squared, secant differentiates to secant-tangent).

## 4.9 Trig Derivatives with the Chain Rule

Q: How do you differentiate $\sin(3x^2)$?
A: Apply the chain rule: $\frac{d}{dx}\sin(u) = \cos(u)\cdot u'$, where $u = 3x^2$ and $u' = 6x$. Result: $\cos(3x^2)\cdot 6x = 6x\cos(3x^2)$. The outer function (sine) differentiates first, evaluated at the inner function, then multiplied by the inner derivative.

Q: What is $\frac{d}{dx}\tan(e^x)$?
A: Let $u = e^x$, so $u' = e^x$. Then $\frac{d}{dx}\tan(u) = \sec^2(u)\cdot u' = e^x\sec^2(e^x)$.

C: $\frac{d}{dx}\cos(u(x)) = [-\sin(u(x))\cdot u'(x)]$ by the chain rule, where $u(x)$ is any differentiable inner function.

Q: Why does chain rule practice matter so much for trig derivatives specifically?
A: In applied problems (oscillations, waves, rotations), the argument of a trig function is almost never just $x$ — it's $\omega t$, $kx$, or $f(t)$. Forgetting the inner derivative is the single most common source of error in physics and engineering calculus.

## 4.10 Derivative of the Natural Exponential

C: $\frac{d}{dx}e^x = [e^x]$ — the exponential function is its own derivative.

Q: What does the equation $\frac{d}{dx}e^x = e^x$ tell you about the graph of $y = e^x$?
A: At every point $(x, e^x)$ on the curve, the slope of the tangent line equals the $y$-coordinate. So where the curve is at height $1$, the slope is $1$; at height $10$, the slope is $10$. The function's growth rate equals its current value.

## 4.11 Why $e$ Is the Special Base

Q: Why is $e \approx 2.71828$ singled out as the base of the "natural" exponential?
A: Among all bases $a > 0$, the base $e$ is the unique one for which $\frac{d}{dx}a^x = a^x$ (no extra constant factor). For any other base, the derivative introduces a multiplier $\ln a$. This self-derivative property makes $e$ the natural choice for modeling continuous growth, decay, and compounding.

Q: How can you think of $e$ as being defined by its derivative property?
A: Define $e$ as the unique positive number such that the function $f(x) = e^x$ satisfies $f'(0) = 1$ — i.e., the tangent at $x=0$ has slope $1$. Equivalently, $\lim_{h\to 0}\frac{e^h - 1}{h} = 1$. This single property forces the full $\frac{d}{dx}e^x = e^x$ rule.

C: The base $e$ is the unique positive number for which $\frac{d}{dx}a^x$ equals [the function itself] with no additional multiplicative constant.

## 4.12 Derivative of a General Exponential

C: $\frac{d}{dx}a^x = [a^x\ln a]$, where $a > 0$ is a constant base.

Q: Where does the extra factor $\ln a$ in $\frac{d}{dx}a^x$ come from?
A: Rewrite $a^x = e^{x\ln a}$. By the chain rule, $\frac{d}{dx}e^{x\ln a} = e^{x\ln a}\cdot\ln a = a^x\ln a$. The constant $\ln a$ appears because $x\ln a$ has derivative $\ln a$, and this gets carried along the chain.

Q: Why does $\frac{d}{dx}2^x$ not equal $x\cdot 2^{x-1}$?
A: The power rule $\frac{d}{dx}x^n = nx^{n-1}$ applies only when the base is the variable and the exponent is a constant. In $2^x$ the base is constant and the exponent is the variable, so it is an exponential function. Its derivative is $2^x\ln 2$, not a power-rule expression.

## 4.13 Derivative of the Natural Logarithm

C: $\frac{d}{dx}\ln x = [\frac{1}{x}]$, valid for $x > 0$.

Q: Why is the derivative of $\ln x$ equal to $1/x$, and why the domain restriction $x>0$?
A: Since $\ln x$ is the inverse of $e^x$, differentiate $y = \ln x \Leftrightarrow e^y = x$ implicitly: $e^y\cdot y' = 1$, so $y' = 1/e^y = 1/x$. The restriction $x>0$ comes from the domain of $\ln x$ itself — the natural log is only defined for positive reals.

Q: Why does the graph of $\ln x$ have steep slope near $x=0^+$ and nearly flat slope for large $x$?
A: Because $\frac{d}{dx}\ln x = 1/x$. As $x\to 0^+$, $1/x\to\infty$ (very steep); as $x\to\infty$, $1/x\to 0$ (nearly horizontal). The logarithm's growth rate decays like $1/x$.

## 4.14 Derivative of a General Logarithm

C: $\frac{d}{dx}\log_a x = [\frac{1}{x\ln a}]$, where $a > 0$, $a\neq 1$, $x > 0$.

Q: Derive $\frac{d}{dx}\log_a x$ from $\frac{d}{dx}\ln x = 1/x$.
A: Use the change-of-base formula: $\log_a x = \frac{\ln x}{\ln a}$. Since $\ln a$ is a constant, differentiate to get $\frac{1}{\ln a}\cdot\frac{1}{x} = \frac{1}{x\ln a}$. The base $a$ contributes only the constant denominator $\ln a$.

## 4.15 Logarithmic Differentiation

Q: When should you reach for logarithmic differentiation?
A: Use it when the function is (1) a messy product or quotient of many factors, (2) has the variable in both base and exponent (like $x^x$ or $(\sin x)^x$), or (3) involves products raised to powers. Taking $\ln$ converts products into sums and exponents into multipliers, making differentiation tractable.

Q: Why can't you differentiate $y = x^x$ using the power rule or the exponential rule directly?
A: The power rule $\frac{d}{dx}x^n = nx^{n-1}$ needs a constant exponent. The exponential rule $\frac{d}{dx}a^x = a^x\ln a$ needs a constant base. In $x^x$ both base and exponent are the variable, so neither rule applies — you need logarithmic differentiation (or rewrite as $e^{x\ln x}$).

C: Logarithmic differentiation is especially useful when the variable appears in both the [base] and the exponent of an expression.

## 4.16 Derivative of $\arcsin x$

C: $\frac{d}{dx}\arcsin x = [\frac{1}{\sqrt{1 - x^2}}]$, for $-1 < x < 1$.

Q: Derive $\frac{d}{dx}\arcsin x$ using implicit differentiation.
A: Let $y = \arcsin x$, so $\sin y = x$ with $y\in[-\pi/2,\pi/2]$. Differentiate: $\cos y\cdot y' = 1$, so $y' = 1/\cos y$. Since $\cos y = \sqrt{1 - \sin^2 y} = \sqrt{1 - x^2}$ (positive on this branch), $y' = 1/\sqrt{1 - x^2}$.

## 4.17 Derivative of $\arccos x$

C: $\frac{d}{dx}\arccos x = [-\frac{1}{\sqrt{1 - x^2}}]$, for $-1 < x < 1$.

Q: Why is $\frac{d}{dx}\arccos x$ the negative of $\frac{d}{dx}\arcsin x$?
A: Because $\arcsin x + \arccos x = \pi/2$ for all $x\in[-1,1]$. Differentiating both sides gives $\frac{d}{dx}\arcsin x + \frac{d}{dx}\arccos x = 0$, so $\frac{d}{dx}\arccos x = -\frac{d}{dx}\arcsin x$.

## 4.18 Derivative of $\arctan x$

C: $\frac{d}{dx}\arctan x = [\frac{1}{1 + x^2}]$, valid for all real $x$.

Q: Why doesn't the derivative of $\arctan x$ have a square root, unlike $\arcsin x$ and $\arccos x$?
A: Let $y = \arctan x$, so $\tan y = x$. Differentiating gives $\sec^2 y\cdot y' = 1$, so $y' = 1/\sec^2 y$. The identity $\sec^2 y = 1 + \tan^2 y = 1 + x^2$ is a clean polynomial — no square root is ever introduced, because the identity is algebraic rather than coming from $\cos y = \sqrt{1-\sin^2 y}$.

Q: Why is $\frac{d}{dx}\arctan x$ defined for every real $x$, while $\frac{d}{dx}\arcsin x$ is not?
A: Arctangent is defined on all of $\mathbb{R}$ with range $(-\pi/2, \pi/2)$, and its derivative $1/(1+x^2)$ has denominator $\geq 1$ everywhere — never zero, never undefined. Arcsine is only defined on $[-1,1]$, and its derivative blows up at the endpoints $x=\pm 1$ where $\sqrt{1-x^2} = 0$.

## 4.19 Procedural: Differentiate $y = x^x$

P: Differentiate $y = x^x$ using logarithmic differentiation, for $x > 0$.

S:
**IDENTIFY**: Variable appears in both base and exponent — neither power rule nor exponential rule applies directly. Logarithmic differentiation is the right tool.

**PLAN**:
- Take the natural log of both sides to move the exponent down as a coefficient.
- Differentiate implicitly, using the product rule on the right.
- Solve for $y'$ and substitute $y = x^x$ back in.

**EXECUTE**:
1. Take $\ln$ of both sides: $\ln y = \ln(x^x) = x\ln x$.
2. Differentiate both sides with respect to $x$. Left side: $\frac{1}{y}\cdot y'$ (chain rule). Right side: product rule gives $1\cdot\ln x + x\cdot\frac{1}{x} = \ln x + 1$.
3. So $\frac{y'}{y} = \ln x + 1$, giving $y' = y(\ln x + 1)$.
4. Substitute $y = x^x$: $y' = x^x(\ln x + 1)$.

**EVALUATE**:
- Check at $x = 1$: $y = 1^1 = 1$, and $y' = 1\cdot(\ln 1 + 1) = 1$. Tangent slope equals $1$ at that point — plausible for a rapidly growing function just past its minimum near $x = 1/e$.
- Units/form check: the result $x^x(\ln x + 1)$ has the expected structure — original function times a correction term involving $\ln x$.

## 4.20 Procedural: Differentiate $y = \arctan(\sqrt{x})$

P: Differentiate $y = \arctan(\sqrt{x})$ using the chain rule, for $x > 0$.

S:
**IDENTIFY**: Composition of arctangent (outer) with $\sqrt{x}$ (inner). Chain rule applies: $\frac{d}{dx}\arctan(u) = \frac{1}{1+u^2}\cdot u'$.

**PLAN**:
- Let $u = \sqrt{x} = x^{1/2}$, so $u' = \frac{1}{2\sqrt{x}}$.
- Apply the arctangent derivative rule with this $u$.
- Simplify the resulting expression.

**EXECUTE**:
1. Identify inner function: $u(x) = \sqrt{x}$, with $u'(x) = \frac{1}{2\sqrt{x}}$.
2. Apply the chain rule: $y' = \frac{1}{1 + u^2}\cdot u' = \frac{1}{1 + (\sqrt{x})^2}\cdot\frac{1}{2\sqrt{x}}$.
3. Simplify $(\sqrt{x})^2 = x$: $y' = \frac{1}{1+x}\cdot\frac{1}{2\sqrt{x}} = \frac{1}{2\sqrt{x}\,(1+x)}$.

**EVALUATE**:
- Domain check: formula requires $x > 0$ (from $\sqrt{x}$ in the denominator), matching the natural domain of $\arctan(\sqrt{x})$ as a differentiable function.
- Sign check: for $x > 0$, both factors in the denominator are positive, so $y' > 0$. This matches the fact that $\arctan(\sqrt{x})$ is strictly increasing on $(0,\infty)$.
- Limiting behavior: as $x\to 0^+$, $y'\to\infty$ (vertical tangent at the origin); as $x\to\infty$, $y'\to 0$ (curve flattens as it approaches the horizontal asymptote $y = \pi/2$). Both are consistent with the known shape of arctangent of a square root.
