# From Tangent Circles to Pi: A Geometric Construction and Square-Root Recurrence

> Research notes · November 19, 2026  
> Status: A mathematical exploration. The assumptions and limits of each result are stated explicitly for further work.

## 0. Motivation and key idea

Start with a large circle and a smaller circle whose **center \(C\) lies on the circumference of the large circle**. From the large circle's center \(O\), draw a tangent segment \(OT\) to the smaller circle and extend the line until it meets the large circle again at \(P\). Connecting \(OC\), \(TC\), and \(PC\) produces two right triangles.

Next, place \(n\) congruent small circles with their centers equally spaced on the circumference of the large circle, with adjacent small circles externally tangent. Connecting their centers creates an inscribed regular \(n\)-gon. As \(n\to\infty\), the small-circle radius \(r_n\to0\), and the sum of their diameters approaches the circumference of the large circle.

**Main result:** a recurrence based entirely on square roots and elementary arithmetic that approximates \(\pi\) without taking its numerical value as an input.

---

## 1. Geometric model: two circles, a tangent, and two right triangles

The following is a geometrically consistent scale drawing for one particular ratio of radii. The general formulas hold for any \(0<r<R\).

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 570 490" role="img" aria-label="A large circle centered at O, a smaller circle centered at C on the large circumference, tangent OT ending at T and extended to P, and lengths a, r, R, d, e.">
  <rect x="0" y="0" width="570" height="490" fill="#ffffff"/>
  <circle cx="215" cy="260" r="195" fill="#edf5fc" stroke="#5388be" stroke-width="2.4"/>
  <circle cx="410" cy="260" r="117" fill="#fff3df" fill-opacity="0.85" stroke="#d49336" stroke-width="2.4"/>
  <path d="M215 260 L339.8 166.4 L410 260 Z" fill="#55b3d7" fill-opacity="0.24"/>
  <path d="M339.8 166.4 L371 143 L410 260 Z" fill="#bd78ad" fill-opacity="0.21"/>
  <line x1="215" y1="260" x2="410" y2="260" stroke="#527db4" stroke-width="3.8"/>
  <line x1="215" y1="260" x2="339.8" y2="166.4" stroke="#08837c" stroke-width="4"/>
  <line x1="339.8" y1="166.4" x2="371" y2="143" stroke="#dd5252" stroke-width="5"/>
  <line x1="339.8" y1="166.4" x2="410" y2="260" stroke="#d5952d" stroke-width="4"/>
  <line x1="371" y1="143" x2="410" y2="260" stroke="#9f5299" stroke-width="4"/>
  <path d="M329.4 174.2 L337.2 184.6 L347.6 176.8" fill="none" stroke="#08837c" stroke-width="2"/>
  <path d="M349.4 159.2 L356.6 168.8 L347 176" fill="none" stroke="#dd5252" stroke-width="2"/>
  <g fill="#293649"><circle cx="215" cy="260" r="5"/><circle cx="410" cy="260" r="5"/><circle cx="339.8" cy="166.4" r="5"/><circle cx="371" cy="143" r="5"/></g>
  <g fill="#182739" font-family="Arial, sans-serif" font-size="19" font-weight="600"><text x="190" y="281">O</text><text x="416" y="282">C</text><text x="316" y="157">T</text><text x="377" y="129">P</text></g>
  <g font-family="Arial, sans-serif" font-size="21" font-weight="600"><text x="267" y="205" fill="#08837c">a</text><text x="350" y="219" fill="#ba7820">r</text><text x="305" y="285" fill="#527db4">R</text><text x="345" y="125" fill="#dd5252">d</text><text x="412" y="201" fill="#9f5299">e</text></g>
  <g font-family="sans-serif" font-size="17"><text x="100" y="110" fill="#5388be">Large circle</text><text x="448" y="147" fill="#b87a25">Small circle</text></g>
</svg>

### 1.1 Notation

| Symbol | Geometric meaning | Formula |
|---|---|---|
| \(O\) | Center of the large circle | — |
| \(C\) | Center of the small circle, on the large circumference | \(OC=R\) |
| \(T\) | Tangency point of \(OT\) with the smaller circle | \(TC\perp OT\) |
| \(P\) | Intersection of ray \(OT\) with the large circumference | \(O,T,P\) are collinear; \(T\) lies between \(O\) and \(P\) |
| \(a\) | Tangent segment \(OT\) | \(a=\sqrt{R^2-r^2}\) |
| \(r\) | Radius \(TC\) of the small circle | \(0<r<R\) |
| \(R\) | Radius \(OC=OP\) of the large circle | \(R>0\) |
| \(d\) | Extension segment \(TP\) | \(d=R-a\) |
| \(e\) | Segment \(PC\), a chord of the large circle | \(e=\sqrt{r^2+d^2}\) |

**Important distinctions:** \(a+d=R\), but neither \(a\) nor \(d\) is itself a radius of the large circle. Also, \(e=PC\) is a chord of the large circle, **not** the small-circle radius; the latter is \(r=TC\).

### 1.2 First right triangle: \(\triangle OTC\)

Because a tangent is perpendicular to the radius at the point of tangency,

\[
\angle OTC=90^\circ.
\]

Pythagoras gives

\[
a^2+r^2=R^2,
\qquad
\boxed{a=\sqrt{R^2-r^2}}.
\]

### 1.3 The extension segment

Since \(O,T,P\) are collinear and \(OP=R\),

\[
\boxed{a+d=R},
\qquad
\boxed{d=R-\sqrt{R^2-r^2}}.
\]

Rationalizing the expression gives an equivalent identity:

\[
\boxed{d=\frac{r^2}{R+\sqrt{R^2-r^2}}}.
\]

### 1.4 Second right triangle: \(\triangle PTC\)

Since \(PT\) lies on the same line as \(OT\),

\[
\angle PTC=90^\circ,
\qquad
d^2+r^2=e^2.
\]

Using \(r^2=R^2-a^2\) and \(d=R-a\),

\[
\begin{aligned}
e^2
&=d^2+r^2\\
&=d^2+R^2-a^2\\
&=d^2+(R-a)(R+a)\\
&=d(d+R+a)\\
&=2Rd.
\end{aligned}
\]

Therefore the following relation is **exact**, not asymptotic:

\[
\boxed{e^2=2Rd},
\qquad
\boxed{e=\sqrt{2R\left(R-\sqrt{R^2-r^2}\right)}}.
\]

The segment \(e\) becomes the central object in the recurrence derived below.

---

## 2. The infinitesimal-circle limit: \(r\to0^+\)

Hold the large-circle radius \(R>0\) fixed while shrinking the small-circle radius \(r\to0^+\).

### 2.1 Basic limits

\[
\lim_{r\to0^+}a=R,
\qquad
\lim_{r\to0^+}d=0,
\qquad
\lim_{r\to0^+}e=0.
\]

The more revealing question is **how quickly** each length approaches zero:

\[
\boxed{\lim_{r\to0^+}\frac{d}{r}=0},
\qquad
\boxed{\lim_{r\to0^+}\frac{d}{r^2}=\frac{1}{2R}},
\qquad
\boxed{\lim_{r\to0^+}\frac{e}{r}=1}.
\]

### 2.2 Asymptotic expansions

Expanding \(\sqrt{1-x}\) near \(x=0\) yields

\[
\begin{aligned}
a&=R-\frac{r^2}{2R}-\frac{r^4}{8R^3}
+O\!\left(\frac{r^6}{R^5}\right),\\[4pt]
d&=\frac{r^2}{2R}+\frac{r^4}{8R^3}
+O\!\left(\frac{r^6}{R^5}\right),\\[4pt]
e&=r+\frac{r^3}{8R^2}+\frac{7r^5}{128R^4}
+O\!\left(\frac{r^7}{R^6}\right).
\end{aligned}
\]

In particular,

\[
\boxed{\lim_{r\to0^+}\frac{e-r}{r^3}=\frac{1}{8R^2}}.
\]

**Interpretation:** \(r\) is a first-order infinitesimal, \(d\sim r^2/(2R)\) is second order, and \(e\sim r\). Their difference \(e-r\sim r^3/(8R^2)\) is third order.

Geometrically, the circle appears progressively closer to its tangent line when viewed at smaller scales; the coefficient \(1/R\) is related to circular curvature.

---

## 3. Approximating the large circumference with small circles

**Exact construction assumptions:**

1. The large circle has a fixed radius \(R\).
2. There are \(n\) congruent small circles, each of radius \(r_n\).
3. Their centers are equally spaced on the circumference of the large circle.
4. Every pair of adjacent small circles is externally tangent.

Connecting consecutive centers produces a **regular \(n\)-gon inscribed in the large circle**. The diagram shows \(n=12\).

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 540 430" role="img" aria-label="Twelve congruent mutually adjacent tangent small circles with centers on the large circle; joining centers forms an inscribed regular dodecagon.">
  <rect width="540" height="430" fill="#ffffff"/>
  <circle cx="250" cy="210" r="125" fill="#eef5fc" stroke="#5b8fc4" stroke-width="2.6"/>
  <g fill="#f5b361" fill-opacity="0.11" stroke="#db9c44" stroke-width="1.65">
    <circle cx="375" cy="210" r="32.352"/><circle cx="358.253" cy="147.5" r="32.352"/>
    <circle cx="312.5" cy="101.747" r="32.352"/><circle cx="250" cy="85" r="32.352"/>
    <circle cx="187.5" cy="101.747" r="32.352"/><circle cx="141.747" cy="147.5" r="32.352"/>
    <circle cx="125" cy="210" r="32.352"/><circle cx="141.747" cy="272.5" r="32.352"/>
    <circle cx="187.5" cy="318.253" r="32.352"/><circle cx="250" cy="335" r="32.352"/>
    <circle cx="312.5" cy="318.253" r="32.352"/><circle cx="358.253" cy="272.5" r="32.352"/>
  </g>
  <polygon points="375,210 358.253,147.5 312.5,101.747 250,85 187.5,101.747 141.747,147.5 125,210 141.747,272.5 187.5,318.253 250,335 312.5,318.253 358.253,272.5" fill="none" stroke="#117e77" stroke-width="3"/>
  <g fill="#1b6c66">
    <circle cx="375" cy="210" r="3.3"/><circle cx="358.253" cy="147.5" r="3.3"/>
    <circle cx="312.5" cy="101.747" r="3.3"/><circle cx="250" cy="85" r="3.3"/>
    <circle cx="187.5" cy="101.747" r="3.3"/><circle cx="141.747" cy="147.5" r="3.3"/>
    <circle cx="125" cy="210" r="3.3"/><circle cx="141.747" cy="272.5" r="3.3"/>
    <circle cx="187.5" cy="318.253" r="3.3"/><circle cx="250" cy="335" r="3.3"/>
    <circle cx="312.5" cy="318.253" r="3.3"/><circle cx="358.253" cy="272.5" r="3.3"/>
  </g>
  <circle cx="250" cy="210" r="4" fill="#243448"/>
  <line x1="250" y1="210" x2="375" y2="210" stroke="#5b8fc4" stroke-width="2" stroke-dasharray="5 5"/>
  <g font-family="Arial, sans-serif" font-size="16" fill="#26364b"><text x="237" y="198">O</text><text x="302" y="203">R</text><text x="405" y="148">12 small circles</text><text x="405" y="173">Each radius r</text><text x="170" y="400">Green dodecagon: each side = 2r</text></g>
</svg>

The distance between adjacent small-circle centers is \(2r_n\), so the polygon perimeter is

\[
\boxed{P_n=2nr_n}.
\]

This is the **sum of the small-circle diameters**, not the sum of their circumferences or the perimeter of their combined outer boundary.

For every finite \(n\ge3\), the inscribed polygon is shorter than the large-circle circumference:

\[
2nr_n<2\pi R.
\]

The central angle subtended by each polygon side is \(2\pi/n\), hence

\[
2r_n=2R\sin\left(\frac{\pi}{n}\right).
\]

It follows that

\[
\boxed{\lim_{n\to\infty}2nr_n=2\pi R},
\qquad
\boxed{\pi=\lim_{n\to\infty}\frac{nr_n}{R}}.
\]

**Avoiding circular reasoning:** The trigonometric identity above is useful to **prove convergence**. It would be circular to treat \(\sin(\pi/n)\) as a numerical input when trying to compute an unknown \(\pi\). Instead, the next section obtains all successive \(r_n\) values from geometry and square roots alone.

---

## 4. Deriving a pi recurrence directly from the original segment \(e\)

Let \(C\) and \(C'\) be adjacent vertices of the inscribed regular \(n\)-gon, so that \(CC'=2r_n\). Let \(O\) be the large-circle center.

Draw a tangent from \(O\) to the small circle centered at \(C\) with radius \(r_n\), meeting the small circle at \(T\). Extend the ray through \(T\) to the large circle, meeting it at \(P\).

Because \(OT\perp CT\), we have

\[
\sin\angle POC=\frac{r_n}{R}.
\]

The isosceles triangle \(OCC'\) has base \(CC'=2r_n\), so its half-central angle has the same sine \(r_n/R\). With the appropriate choice of tangent on the minor-arc side, the ray \(OP\) bisects \(\angle COC'\). Consequently, **\(P\) is the midpoint of the minor arc from \(C\) to \(C'\)**.

The original two-triangle construction gives the distance from the old vertex \(C\) to the new midpoint vertex \(P\):

\[
PC=e=\sqrt{2R\left(R-\sqrt{R^2-r_n^2}\right)}.
\]

If every arc is bisected, a regular \(n\)-gon becomes a regular \(2n\)-gon. Its new side length is \(e\). To place the next family of mutually tangent small circles, their diameter must equal that new side:

\[
2r_{2n}=e.
\]

Hence the **primary radius recurrence**:

\[
\boxed{
r_{2n}
=\sqrt{\frac{R\left(R-\sqrt{R^2-r_n^2}\right)}{2}}
}.
\tag{1}
\]

### 4.1 Numerically stable version

For very small \(r_n/R\), directly subtracting \(R-\sqrt{R^2-r_n^2}\) causes floating-point cancellation. Rationalization yields the mathematically identical but computationally more stable formula

\[
\boxed{
r_{2n}
=r_n\sqrt{\frac{R}{2\left(R+\sqrt{R^2-r_n^2}\right)}}
}.
\tag{2}
\]

Define the dimensionless quantity \(x_n=r_n/R\). Then

\[
\boxed{
x_{2n}
=\frac{x_n}{\sqrt{2\left(1+\sqrt{1-x_n^2}\right)}}
}.
\tag{3}
\]

### 4.2 Starting with a regular hexagon

Each side of a regular hexagon equals the radius of its circumcircle. Therefore,

\[
2r_6=R,
\qquad
\boxed{x_6=\frac12}.
\]

Let \(n_k=6\cdot2^k\), with \(k=0,1,2,\ldots\). Compute \(x_{12},x_{24},x_{48},\ldots\) using equation (3), and define the lower approximation

\[
\boxed{p_{n_k}=n_kx_{n_k}=\frac{n_kr_{n_k}}{R}},
\qquad
\boxed{\lim_{k\to\infty}p_{n_k}=\pi}.
\]

It is even possible to update \(p_n\) without separately storing the radius. Substituting \(x_n=p_n/n\) into equation (3) gives

\[
\boxed{
p_{2n}=p_n\sqrt{\frac{2}{1+\sqrt{1-(p_n/n)^2}}}
},
\qquad
\boxed{p_6=3}.
\tag{4}
\]

This update uses only the current approximation, the integer \(n\), basic arithmetic, and square roots. No numerical value of the true \(\pi\) appears on the right-hand side.

---

## 5. Numerical results, error bounds, and convergence

Set \(R=1\) and start with \(n=6\), doubling \(n\) at every step.

The lower approximation is

\[
L_n=\frac{nr_n}{R}.
\]

An upper approximation, derived from the regular \(n\)-gon circumscribed about the large circle, is

\[
U_n=\frac{nr_n}{\sqrt{R^2-r_n^2}}.
\]

| Number of small circles \(n\) | Lower bound \(L_n\) | Upper bound \(U_n\) |
|---:|---:|---:|
| 6 | 3.000000000 | 3.464101615 |
| 12 | 3.105828541 | 3.215390309 |
| 24 | 3.132628613 | 3.159659942 |
| 48 | 3.139350203 | 3.146086215 |
| 96 | 3.141031951 | 3.142714600 |
| 192 | 3.141452472 | 3.141873050 |
| 384 | 3.141557608 | 3.141662747 |
| 768 | 3.141583892 | 3.141610177 |
| 1,536 | 3.141590463 | 3.141597034 |
| 3,072 | 3.141592106 | 3.141593749 |

Reference value:

\[
\pi\approx3.141592653589793\ldots
\]

### 5.1 Why the bounds are valid

The **inscribed regular polygon** has perimeter \(2nr_n\), smaller than the circle circumference:

\[
\boxed{\frac{nr_n}{R}<\pi}.
\]

For the **circumscribed regular polygon**, half a tangent-side length equals \(R\tan(\pi/n)\). Since

\[
\tan\left(\frac{\pi}{n}\right)
=\frac{r_n}{\sqrt{R^2-r_n^2}},
\]

its half-perimeter divided by \(R\) gives

\[
\boxed{\pi<\frac{nr_n}{\sqrt{R^2-r_n^2}}}.
\]

Thus each iteration yields an interval enclosing \(\pi\):

\[
\boxed{
\frac{nr_n}{R}
<\pi<
\frac{nr_n}{\sqrt{R^2-r_n^2}}
}.
\tag{5}
\]

For example, with \(n=3072\) the rounded results give

\[
3.141592106<\pi<3.141593749.
\]

### 5.2 Convergence rate

The theoretical relation \(r_n/R=\sin(\pi/n)\) gives

\[
\frac{nr_n}{R}
=n\sin\left(\frac{\pi}{n}\right)
=\pi-\frac{\pi^3}{6n^2}+O(n^{-4}).
\]

Thus doubling the polygon size reduces the leading lower-bound error by roughly a factor of four. Again, this expression is used to **analyze** error; the actual numeric algorithm is based solely on equations (2)–(4).

---

## 6. Pseudocode

This version uses the dimensionless radius \(x=r/R\) and the stable recurrence:

~~~text
n = 6
x = 0.5                 # Starting radius: r_6 = R/2

repeat:
    lower = n * x
    upper = n * x / sqrt(1 - x*x)
    print(n, lower, upper)

    if upper - lower < tolerance:
        stop

    x = x / sqrt(2 * (1 + sqrt(1 - x*x)))
    n = 2*n
~~~

The two printed values are theoretical bounds for \(\pi\). Ordinary floating-point output may not rigorously enclose \(\pi\) at extremely high precision; for a formally certified computation, use outward-rounded interval arithmetic.

---

## 7. Summary of formulas

| Topic | Formula |
|---|---|
| Tangent length | \(a=\sqrt{R^2-r^2}\) |
| Tangent extension | \(d=R-\sqrt{R^2-r^2}=r^2/(R+\sqrt{R^2-r^2})\) |
| New chord | \(e=\sqrt{2R(R-\sqrt{R^2-r^2})}\) |
| First right triangle | \(a^2+r^2=R^2\) |
| Second right triangle | \(d^2+r^2=e^2\) |
| Collinearity | \(a+d=R\) |
| Exact identity | \(e^2=2Rd\) |
| Small-radius limit | \(d\sim r^2/(2R)\), \(e\sim r\) |
| Sum of small diameters | \(2nr_n\to2\pi R\) |
| Stable radius recurrence | \(r_{2n}=r_n\sqrt{R/[2(R+\sqrt{R^2-r_n^2})]}\) |
| Initial radius | \(r_6=R/2\) |
| Limit defining pi | \(\pi=\lim_{k\to\infty}n_kr_{n_k}/R\), \(n_k=6\cdot2^k\) |
| Certified mathematical enclosure | \(nr_n/R<\pi<nr_n/\sqrt{R^2-r_n^2}\) |

---

## 8. Mathematical significance and possible next steps

1. **Validity:** The method converges to \(\pi\) and admits explicit upper and lower bounds without using its numerical value as an input.
2. **Historical classification:** The underlying method is geometrically equivalent to the classical Archimedean approximation using inscribed and circumscribed regular polygons. The current derivation is not sufficient to claim a historically new pi algorithm.
3. **Distinctive explanatory route:** It begins with two tangent-circle right triangles and \(e^2=2Rd\), then recognizes \(e\) as the new polygon chord after angle bisection. This may be a useful construction for teaching geometry and limits.
4. **Practical efficiency:** Its error decreases by approximately a factor of four per polygon doubling. It is conceptually elegant but substantially slower than modern high-precision pi algorithms.
5. **Research directions:** Sharper error estimates from the two right triangles; curvature and local tangent limits; different starting polygons; improved convergence acceleration; and alternative square-root-only recurrences.

### Final logical chain

The finite-\(n\) identity is **not** \(2nr_n=2\pi R\). The rigorous route is

\[
\boxed{
\text{tangent geometry}
\;\longrightarrow\;
e^2=2Rd
\;\longrightarrow\;
r_{2n}=\frac e2
\;\longrightarrow\;
\pi=\lim_{n\to\infty}\frac{nr_n}{R}
}.
\]

This links the geometric model, Pythagoras, an implementable recurrence, and the limiting circumference in one coherent argument.
