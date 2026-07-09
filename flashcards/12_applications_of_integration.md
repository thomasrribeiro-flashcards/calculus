+++
order = 12
subject = "Math"
tags = ["math", "calculus", "integration", "area", "volume", "arc-length", "work", "average-value"]
+++

# Calculus — Applications of Integration

## 12.1 Why Integration Has So Many Applications

Q: Why does a single integration technique apply to areas, volumes, work, arc length, and averages?
A: Each of these quantities is built by accumulating infinitely many infinitesimal contributions. If a small slice contributes $dQ = f(x)\,dx$, then the total $Q = \int_a^b f(x)\,dx$. The integral is the universal tool for "sum up infinitely many small pieces."

Q: What is the general recipe for setting up an integral in an application problem?
A: (1) Slice the quantity into infinitesimal pieces. (2) Write the contribution of one slice as $dQ = (\text{something})\,dx$. (3) Identify the limits that cover the whole region. (4) Integrate to sum the pieces.

C: Any quantity that can be built by summing infinitesimal contributions $dQ = f(x)\,dx$ can be computed as [$\int_a^b f(x)\,dx$].

Q: Why is "think about one typical slice" the most important step in applied integration?
A: Because once you write $dQ$ correctly for a single slice, the integral $\int dQ$ is automatic. Most errors come from a wrong $dQ$, not from wrong antidifferentiation.

## 12.2 Area Between Two Curves

Q: Why is the area between $y = f(x)$ and $y = g(x)$ on $[a,b]$ given by $\int_a^b [f(x) - g(x)]\,dx$ when $f \geq g$?
A: A vertical strip at $x$ has height $f(x) - g(x)$ (top minus bottom) and width $dx$, so its area is $[f(x) - g(x)]\,dx$. Summing over $[a,b]$ gives $\int_a^b [f(x) - g(x)]\,dx$.

C: The area between curves $y = f(x)$ and $y = g(x)$ on $\lbrack a,b\rbrack $ with $f \geq g$ is [$\int_a^b \lbrack f(x) - g(x)\rbrack \,dx$], where $f$ is the upper curve and $g$ is the lower curve.

Q: What happens if $f$ and $g$ cross on $[a,b]$?
A: You must split the integral at each crossing point and use $|f - g|$ on each subinterval, since area is always positive. The sign of $f - g$ flips where the curves cross.

Q: Why must we take top minus bottom rather than just $f - g$?
A: If $g > f$ on some interval, $\int (f - g)\,dx$ would be negative, but geometric area is nonnegative. Always subtract the lower function from the upper.

## 12.3 Finding Intersection Points to Set Bounds

Q: Why do we usually need to solve $f(x) = g(x)$ before setting up an area integral?
A: Because the natural bounds of the enclosed region are the $x$-values where the curves meet. Without the intersection points, you don't know where the "top" curve switches or where the region ends.

P: Find the intersection points of $y = x^2$ and $y = 2x$ to set up an area integral.

S:
**IDENTIFY**: Intersection points are where both curves share the same $(x,y)$.

**PLAN**: Set $f(x) = g(x)$ and solve for $x$.

**EXECUTE**:
1. $x^2 = 2x \Rightarrow x^2 - 2x = 0 \Rightarrow x(x-2) = 0$.
2. Solutions: $x = 0$ and $x = 2$.
3. Corresponding points: $(0,0)$ and $(2,4)$.

**EVALUATE**: On $(0,2)$, test $x=1$: $2x = 2 > x^2 = 1$, so $y = 2x$ is on top. Bounds are $a=0$, $b=2$.

C: To find the limits for an area-between-curves integral, solve [$f(x) = g(x)$] for the $x$-values where the curves intersect.

## 12.4 Horizontal vs Vertical Slicing

Q: When should you integrate with respect to $y$ instead of $x$?
A: When the region is more naturally described as "left curve $x = g(y)$ to right curve $x = f(y)$" for each $y$. This happens when one curve is not a single-valued function of $x$ (e.g., a sideways parabola) or when vertical strips would require splitting the region.

C: Slicing horizontally gives strips of height $dy$ and width $\lbrack x_{\text{right}}(y) - x_{\text{left}}(y)\rbrack $, with total area [$\int_c^d \lbrack x_{\text{right}}(y) - x_{\text{left}}(y)\rbrack \,dy$], where $c$ and $d$ are the minimum and maximum $y$-values of the region.

Q: Why does switching from $dx$ to $dy$ sometimes avoid splitting the integral into two pieces?
A: A vertical strip may have a top curve that changes midway through the region, forcing two integrals. A horizontal strip may see the same left and right curves throughout, needing only one integral.

Q: What is the rule of thumb for choosing the slicing direction?
A: Choose the direction in which a typical slice crosses the region without changing which two curves bound it. If vertical strips hit different curves on different subintervals, try horizontal.

## 12.5 Volume by the Disk Method

Q: Why does rotating a region about an axis that forms its edge produce solid disks rather than rings?
A: Because the region touches the axis, each cross section perpendicular to the axis is a full circle (no hole in the middle). The radius of the disk is the function value $f(x)$.

C: The disk method volume for rotating $y = f(x)$ on $\lbrack a,b\rbrack $ about the $x$-axis is [$V = \int_a^b \pi \lbrack f(x)\rbrack ^2\,dx$], where $f(x)$ is the radius of the disk at position $x$ and $dx$ is the disk's thickness.

Q: Why does the disk method formula contain $\pi [f(x)]^2$?
A: Each disk has area $\pi r^2$ with $r = f(x)$, and its volume is $(\text{area})(\text{thickness}) = \pi [f(x)]^2\,dx$. Summing these gives the integral.

Q: What condition must the region satisfy for the disk method (no washer) to apply?
A: The axis of rotation must be an edge of the region — the region must touch the axis. If there's a gap, you get washers, not disks.

## 12.6 Volume by the Washer Method

Q: Why do we subtract $\pi r_{\text{inner}}^2$ from $\pi r_{\text{outer}}^2$ in the washer method?
A: When the axis of rotation lies outside the region, each cross section is a ring (washer). Its area is the outer disk area minus the inner disk area: $\pi R^2 - \pi r^2$, where $R$ is the outer radius and $r$ is the inner radius.

C: The washer method gives $V = \int_a^b \pi\big(\lbrack R(x)\rbrack ^2 - \lbrack r(x)\rbrack ^2\big)\,dx$, where [$R(x)$] is the outer radius (distance from axis to far edge) and $r(x)$ is the inner radius (distance from axis to near edge).

Q: How do you compute inner and outer radii when the axis of rotation is $y = k$ rather than the $x$-axis?
A: The radius at $x$ is the distance from the curve to the line $y = k$, namely $|f(x) - k|$. The outer radius uses the curve farther from $y=k$, and the inner radius uses the curve closer to $y=k$.

Q: Why is the washer method really just the disk method applied twice?
A: The washer's volume equals the volume of the big solid of revolution (outer curve) minus the volume of the hole (inner curve). Each piece is a disk-method integral.

## 12.7 Volume by the Shell Method

Q: Why does the shell method use $2\pi \cdot \text{radius} \cdot \text{height}$?
A: A thin vertical strip at distance $r$ from the axis, when rotated, sweeps out a cylindrical shell. Unroll the shell: it becomes a thin rectangle of length $2\pi r$ (circumference), height $h$, and thickness $dx$. Its volume is $2\pi r h\,dx$.

C: The shell method volume is [$V = \int_a^b 2\pi\,(\text{radius})(\text{height})\,dx$], where the radius is the distance from the strip to the axis of rotation and the height is the length of the strip parallel to the axis.

Q: When using shells for rotation about the $y$-axis with strips at position $x$, what are the radius and height of each shell?
A: For the region between $y = f(x)$ and $y = g(x)$ with $f \geq g$ on $[a,b]$: radius $= x$ (distance to $y$-axis), height $= f(x) - g(x)$. Volume: $\int_a^b 2\pi x [f(x) - g(x)]\,dx$.

Q: Why does rotating a vertical strip give a cylindrical shell rather than a disk?
A: Because the strip is parallel to the axis of rotation, not perpendicular. A strip perpendicular to the axis sweeps a disk; a strip parallel to it sweeps a shell around the axis.

## 12.8 Choosing Disk/Washer vs Shell

Q: How do you decide between shells and disks/washers for a volume of revolution?
A: Use disks/washers when slices are perpendicular to the axis (the integration variable matches the axis). Use shells when slices are parallel to the axis. If solving for the curve in the "wrong" variable is hard (e.g., $x$ as a function of $y$), that's often a hint to use shells instead.

C: When slices perpendicular to the axis of rotation are easier to describe, use the [disk or washer] method; when slices parallel to the axis are easier, use the [shell] method.

Q: Why might shells be necessary even when disks seem possible?
A: If the curves can't be easily inverted (e.g., $y = x + \sin x$ has no closed-form inverse), you can't write the outer/inner radius as a function of $y$ for disk/washer. Shells let you keep $x$ as the integration variable.

## 12.9 Volume by Known Cross-Sectional Area

Q: Why is $V = \int_a^b A(x)\,dx$ the volume of a solid with known cross-section $A(x)$?
A: Slice the solid into thin slabs perpendicular to the $x$-axis. Each slab has face area $A(x)$ and thickness $dx$, so its volume is $A(x)\,dx$. Summing over $[a,b]$ gives the total volume.

C: For a solid with cross-sectional area $A(x)$ perpendicular to the $x$-axis on $\lbrack a,b\rbrack $, the volume is [$V = \int_a^b A(x)\,dx$], where $A(x)$ is the area of the cross section at position $x$ and $dx$ is the slab's thickness.

Q: Why do disks, washers, and cross-section volumes all share the same underlying idea?
A: They're all $\int A(x)\,dx$ — disks have $A = \pi r^2$, washers have $A = \pi(R^2 - r^2)$, and general cross-sections allow squares, triangles, semicircles, or anything else. The method is one idea; the cross-section shape changes.

P: A solid has a circular base of radius $1$. Cross sections perpendicular to the $x$-axis are squares. Set up its volume.

S:
**IDENTIFY**: Volume by known cross-section (squares).

**PLAN**: Find side length of the square at position $x$, then use $V = \int A(x)\,dx$.

**EXECUTE**:
1. Base circle: $x^2 + y^2 = 1$, so at position $x$, the chord has length $2\sqrt{1-x^2}$.
2. Square with that side length has area $A(x) = [2\sqrt{1-x^2}]^2 = 4(1-x^2)$.
3. $V = \int_{-1}^{1} 4(1-x^2)\,dx$.

**EVALUATE**: The integrand is positive on $(-1,1)$, so $V > 0$. Computing: $V = 4[x - x^3/3]_{-1}^{1} = 4\cdot(4/3) = 16/3$.

## 12.10 Arc Length

C: The arc length of $y = f(x)$ on $\lbrack a,b\rbrack $ is [$L = \int_a^b \sqrt{1 + \lbrack f'(x)\rbrack ^2}\,dx$], where $f'(x)$ is the derivative of $f$ and $\lbrack a,b\rbrack $ is the interval over which the curve runs.

Q: Why does the arc length formula involve $f'(x)$ rather than $f(x)$?
A: Because length depends on how fast the curve rises, not on its height. A steep curve (large $|f'|$) covers more arc per unit of horizontal distance than a flat one.

Q: What is the arc length element $ds$?
A: $ds = \sqrt{1 + [f'(x)]^2}\,dx$ for $y = f(x)$, or equivalently $ds = \sqrt{[dx]^2 + [dy]^2}$. It represents the infinitesimal length along the curve.

## 12.11 Why the Arc Length Formula Works

Q: How does the Pythagorean theorem produce the arc length formula?
A: A tiny piece of curve is nearly straight, with horizontal leg $dx$ and vertical leg $dy$. Its length is $ds = \sqrt{dx^2 + dy^2}$. Factor out $dx$: $ds = \sqrt{1 + (dy/dx)^2}\,dx = \sqrt{1 + [f'(x)]^2}\,dx$. Integrating sums these lengths.

Q: Why can we treat a tiny arc as a straight line segment when deriving arc length?
A: For smooth curves, as $dx \to 0$ the arc becomes indistinguishable from the chord (up to higher-order infinitesimals). This is the same "linearization" idea that justifies differentials everywhere in calculus.

C: Arc length derivation: on an infinitesimal scale, $(ds)^2 = (dx)^2 + (dy)^2$ from the [Pythagorean theorem], leading to $ds = \sqrt{1 + (dy/dx)^2}\,dx$.

## 12.12 Surface Area of Revolution

C: The surface area generated by rotating a curve about an axis is [$S = \int 2\pi r\,ds$], where $r$ is the distance from the arc element to the axis and $ds$ is the arc length element along the curve.

Q: Why does the surface area formula use $2\pi r\,ds$?
A: Rotating an arc element $ds$ at distance $r$ from the axis sweeps out a thin band — essentially the lateral surface of a tiny frustum with circumference $2\pi r$ and slant height $ds$. Its area is $2\pi r \cdot ds$.

Q: For $y = f(x)$ rotated about the $x$-axis, what is the explicit surface area integral?
A: $S = \int_a^b 2\pi f(x) \sqrt{1 + [f'(x)]^2}\,dx$, where $r = f(x)$ is the radius and $ds = \sqrt{1 + [f'(x)]^2}\,dx$ is the arc length element.

Q: Why use $ds$ rather than $dx$ in surface area but $dx$ is fine in volume by disks?
A: Volume by disks stacks thin perpendicular slabs, whose thickness is $dx$. Surface area wraps a ribbon along the curve, whose width is the actual arc length $ds$ — the curve's slope matters.

## 12.13 Work Done by a Variable Force

C: The work done by a variable force $F(x)$ moving an object from $x=a$ to $x=b$ along the $x$-axis is [$W = \int_a^b F(x)\,dx$], where $F(x)$ is the force at position $x$.

Q: Why is work an integral rather than just force times distance?
A: Force $\times$ distance only works when the force is constant. For a variable force, break the path into tiny pieces $dx$ where $F$ is nearly constant; the work on each piece is $F(x)\,dx$, and the total is the integral.

Q: Why does stretching a spring obey $W = \int_0^x kx'\,dx' = \frac{1}{2}kx^2$?
A: By Hooke's law, the restoring force is $F(x') = kx'$, where $k$ is the spring constant and $x'$ is the displacement from equilibrium. Integrating $F$ from $0$ to $x$ gives $\frac{1}{2}kx^2$ — the classic spring potential energy.

Q: How do you set up pumping-out-a-tank work problems?
A: Slice the liquid horizontally at height $y$ with thickness $dy$. The slab's weight is $\rho g \cdot A(y)\,dy$, and it must be lifted a distance $d(y)$ to reach the top. Work $dW = \rho g\,A(y)\,d(y)\,dy$; integrate over the liquid's depth.

## 12.14 Hydrostatic Force

Q: Why is hydrostatic force an integral of pressure times area over depth?
A: Pressure $P = \rho g h$ depends on depth $h$ (where $\rho$ is fluid density and $g$ is gravitational acceleration), so it varies across a submerged surface. Slice the surface into thin horizontal strips at depth $h$ with area $dA$; the force on a strip is $dF = P\,dA = \rho g h\,dA$, and total force is $F = \int \rho g h\,dA$.

C: Hydrostatic force on a submerged vertical surface: $F = \int \rho g h(y)\,w(y)\,dy$, where [$\rho$] is the fluid density, $g$ is gravitational acceleration, $h(y)$ is the depth of strip $y$, and $w(y)$ is its horizontal width.

Q: Why does pressure at depth $h$ equal $\rho g h$?
A: Because the weight of a column of fluid above area $A$ at depth $h$ is $\rho g h A$. Dividing by $A$ (force per area) gives pressure $\rho g h$ — pressure grows linearly with depth.

Q: Why must hydrostatic force be computed strip-by-strip rather than as "pressure at center times area"?
A: Pressure varies continuously with depth. Using the center pressure is only exact for rectangular surfaces (by symmetry); for triangles, circles, or other shapes, you must integrate.

## 12.15 Average Value of a Function

C: The average value of $f$ on $\lbrack a,b\rbrack $ is [$\bar{f} = \frac{1}{b-a}\int_a^b f(x)\,dx$], where $b-a$ is the length of the interval and $\int_a^b f(x)\,dx$ is the "total accumulation" of $f$.

Q: Why does dividing the integral by $(b-a)$ give an average?
A: The integral $\int_a^b f\,dx$ is the area under $f$ on $[a,b]$. Spreading that same area uniformly over the interval gives a rectangle of width $(b-a)$ and height $\bar{f}$, so $\bar{f} = \frac{\text{area}}{\text{width}}$.

Q: How does the Mean Value Theorem for integrals relate to the average value?
A: It guarantees that for continuous $f$ on $[a,b]$, there exists $c \in [a,b]$ with $f(c) = \bar{f}$. The function actually attains its average somewhere on the interval.

Q: Why is "average value" useful in physics?
A: Average velocity, average force, average power, and average temperature are all $\frac{1}{T}\int_0^T (\text{quantity})\,dt$. Converting a time-varying process to a single equivalent constant enables back-of-envelope estimates.

## 12.16 Center of Mass / Centroids

Q: Why is the centroid $\bar{x}$ of a lamina given by $\frac{1}{A}\int x\,dA$?
A: The centroid is the mass-weighted average of position. For uniform density, mass is proportional to area, so $\bar{x} = \frac{\int x\,dA}{\int dA} = \frac{1}{A}\int x\,dA$, where $A$ is the total area.

C: For a region with uniform density, the centroid coordinates are $\bar{x} = \frac{1}{A}\int x\,dA$ and $\bar{y} = \frac{1}{A}\int y\,dA$, where [$A$] is the total area of the region.

Q: Why does symmetry help locate centroids without computing integrals?
A: If a region is symmetric about a line, its centroid lies on that line — contributions from symmetric pairs of points cancel in the moment integral. This often determines $\bar{x}$ or $\bar{y}$ for free.

## 12.17 Probability Density Functions

Q: Why is probability computed as an integral of a density rather than a simple count?
A: For continuous random variables, any exact value has probability zero; probability is meaningful only over intervals. A probability density function $f(x)$ encodes probability per unit $x$, so $P(a \leq X \leq b) = \int_a^b f(x)\,dx$ — the area under $f$.

C: For a probability density function $f$ on $\mathbb{R}$: [$\int_{-\infty}^{\infty} f(x)\,dx = 1$], meaning the total probability over all outcomes equals 1.

Q: What is the expected value of a continuous random variable with density $f$?
A: $E[X] = \int_{-\infty}^{\infty} x f(x)\,dx$, the "average" value of $X$ weighted by its density. It's the continuous analog of $\sum x_i p_i$.

Q: Why must a probability density function satisfy $f(x) \geq 0$ and $\int f\,dx = 1$?
A: $f \geq 0$ because probabilities can't be negative, and the integral equals $1$ because the random variable must take some value — the total probability is 100%.

## 12.18 Worked Problem: Area Enclosed by $y = x^2$ and $y = 2x$

P: Find the area enclosed by $y = x^2$ and $y = 2x$.

S:
**IDENTIFY**: Area-between-curves problem. Need to find intersection points and determine which curve is on top.

**PLAN**:
- Solve $x^2 = 2x$ for bounds.
- Determine upper curve by testing a point.
- Integrate $\int [\text{top} - \text{bottom}]\,dx$.

**EXECUTE**:
1. $x^2 = 2x \Rightarrow x(x-2) = 0 \Rightarrow x = 0, 2$. Bounds: $a=0$, $b=2$.
2. Test $x=1$: $2x = 2$, $x^2 = 1$. So $y = 2x$ is the upper curve.
3. Area $A = \int_0^2 (2x - x^2)\,dx = \left[x^2 - \frac{x^3}{3}\right]_0^2 = 4 - \frac{8}{3} = \frac{4}{3}$.

**EVALUATE**: On $(0,2)$, $2x > x^2$, so the integrand is positive and the answer is positive — a good sanity check. Units are square units; magnitude $\frac{4}{3}$ looks reasonable for a region bounded by curves on $[0,2]$.

## 12.19 Worked Problem: Volume by Disks for $y = \sqrt{x}$ on $[0,4]$ about $x$-axis

P: Find the volume of the solid obtained by rotating the region under $y = \sqrt{x}$ on $[0,4]$ about the $x$-axis.

S:
**IDENTIFY**: Volume of revolution about the $x$-axis; the region touches the axis ($y=0$ at $x=0$), so use the disk method.

**PLAN**:
- Radius at $x$: $r = f(x) = \sqrt{x}$.
- Disk area: $A(x) = \pi r^2 = \pi x$.
- $V = \int_0^4 A(x)\,dx$.

**EXECUTE**:
1. $A(x) = \pi (\sqrt{x})^2 = \pi x$.
2. $V = \int_0^4 \pi x\,dx = \pi \cdot \frac{x^2}{2}\Big|_0^4 = \pi \cdot \frac{16}{2} = 8\pi$.

**EVALUATE**: Units are cubic units; $8\pi \approx 25.13$. As a rough check, the region is a curvy triangle fitting in a $4 \times 2$ box rotated into a solid; $8\pi$ is well below the enclosing cylinder's volume $\pi(2)^2(4) = 16\pi$, which makes sense because the region is below the top of the box.
