## Modern Theory of Detection and Estimation <!-- omit in toc -->

# Classification Problems

*Academic year 2024-2025*  
*Telematics Engineering Department - Universidad Carlos III de Madrid*

$$
\global\def\E#1{\mathbb E \left\{#1\right\}}
\global\def\Var#1{\mathrm{Var} \left\{#1\right\}}
\global\def\Cov{\mathrm{Cov}}
\global\def\sgn{\mathrm{sgn}}
\global\def\declg#1#2{\enspace\overset{#1}{\underset{#2}{\lessgtr}}\enspace}
\global\def\decgl#1#2{\enspace\overset{#1}{\underset{#2}{\gtrless}}\enspace}
\global\def\est#1#2{\hat{#1}_{\text{#2}}}
\global\def\ML#1{\est{#1}{ML}}
\global\def\MAP#1{\est{#1}{MAP}}
\global\def\MAD#1{\est{#1}{MAD}}
\global\def\MSE#1{\est{#1}{MSE}}
\global\def\MMSE#1{\est{#1}{MMSE}}
$$

---

* [Exercise 2](#exercise-2)
    * [Question 2.a](#question-2a)
    * [Question 2.b](#question-2b)
    * [Question 2.c](#question-2c)
    * [Question 2.d](#question-2d)
* [Exercise 11 ✓](#exercise-11-)
    * [Question 11.a](#question-11a)
    * [Question 11.b](#question-11b)
    * [Question 11.c](#question-11c)
    * [Question 11.d](#question-11d)
* [Exercise 22 ✓](#exercise-22-)
    * [Question 11.a](#question-11a-1)
    * [Question 11.b](#question-11b-1)
    * [Question 11.c](#question-11c-1)
    * [Question 11.d](#question-11d-1)

---

## Exercise 2

### Question 2.a

> **Class notes**

$$
\begin{aligned}
\frac{p(\{x^{(k)}\}|1)}{p(\{x^{(k)}\}|0)} \overset{D_1}{\underset{D_0}{≶}} 1
\end{aligned}
$$

$$
p(\{x^{(k)}\}|0) = ∏_{k=1}^k \exp(-a x^{(k)}) \\
p(\{x^{(k)}\}|1) = ∏_{k=1}^k a \exp(-a x^{(k)})
$$

$$
\def\dec{\enspace\overset{D_1}{\underset{D_0}{≶}}\enspace}
\def\decr{\enspace\overset{D_0}{\underset{D_1}{≶}}\enspace}
\begin{aligned}
    ∑_{k=1}^k \ln a - a ∑_{k=1}^k x^{(k)} + ∑_{k=1}^k x^{(k)} &\dec 0 \\
    k \ln a - (a-1) ∑_{k=1}^k x^{(k)} &\dec 0 \\
    (a-1) ∑_{k=1}^k x^{(k)} &\decr k \ln a \\
    ∑_{k=1}^k x^{(k)} &\decr \frac{k \ln a}{a-1} \\
\end{aligned}
$$

$T = ∑_{k=1}^K X^{(k)}$ is a sufficient statistic

### Question 2.b

### Question 2.c

$$
\def\dec{\enspace\overset{D_1}{\underset{D_0}{≶}}\enspace}
\def\decr{\enspace\overset{D_0}{\underset{D_1}{≶}}\enspace}

t \dec η
$$

$$
P_M = ∫_η^∞ a^2 t \exp(-a t) dt = (aη + 1) \exp(-aη)
$$

### Question 2.d

## Exercise 11 ✓

We have a binary decision problem with likelihoods:

$$
p_{X_1,X_2|H}(x_1, x_2|0) = G \left(0, \begin{bmatrix}
    1 & ρ \\
    ρ & 1
\end{bmatrix}\right) \\[1em]
p_{X_1,X_2|H}(x_1, x_2|1) = G \left(m, \begin{bmatrix}
    1 & ρ \\
    ρ & 1
\end{bmatrix}\right) \\[1em]
$$

with $m = [m, m]^T$ , where $m > 0$, and $|ρ| < 1$.

### Question 11.a
Knowing that $P_H(0) = P_H(1)$, obtain the Bayes' decider incurring in a minimum
probability of error. Plot the obtained decision boundary on the plane $X_1 −
X_2$.

> **Answer** (class notes)
>
> The Bayes' decider is the MAP decider. Since both hypotheses are equally
> likely, it's the same as an ML decider. Additionally, since the distributions
> are identical gaussian distributions, we can further simplify it through a
> minimum distance decider, taking the distance to the mean of each distribution
> as the decision criterion.
>
> The boundary is given by $x_1 + x_2 = m$

### Question 11.b

For the classifier obtained in question a, verify that $Z = X_1 + X_2$ is a
sufficient statistic for the decision. Obtain the likelihoods of hypotheses $H =
0$ and $H = 1$ over random variable $Z$, $p_{Z|H}(z|0)$ and $p_{Z|H}(z|1)$.

> **Answer** (class notes)
>
> Let's check first for H=0
>
> $$
> \begin{aligned}
>     \E{Z|0} &= \E{X_1 + X_2 | 0} \\
>     &= \E{X_1|0} + \E{X_2|0} \\
>     &= 0 + 0 = 0 \\
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
>     \Var{Z|0} &= \Var{X_1 + X_2 | 0} \\
>     &= \Var{X_1|0} + \Var{X_2|0} + 2 \Cov(X_1, X_2 | 0)\\
>     &= 1 + 1 + 2ρ \\
>     &= 2(1+ρ)
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
>     E\{Z|1\} &= E\{X_1 + X_2 | 1\} \\
>     &= E\{X_1|1\} + E\{X_2|1\} \\
>     &= m + m = 2m \\
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
>     \Var{Z|1} &= \Var{X_1 + X_2 | 1} \\
>     &= \Var{X_1|1} + \Var{X_2|1} + 2 \Cov(X_1, X_2 | 1)\\
>     &= 1 + 1 + 2ρ \\
>     &= 2(1+ρ)
> \end{aligned}
> $$
>
> In the end,
>
> $$
> Z \decgl{D_1}{D_0} m
> $$

### Question 11.c
Calculate the false alarm, missing, and error probabilities of the previous decider, expressing them in terms of function

$$
F(x) = 1−Q(x) = ∫_{-∞}^x \frac{1}{\sqrt{2π}} \exp\left(-\frac{t^2}{2}\right) dt
$$

> **Answer** (class notes)
>
> $$
> \begin{aligned}
>     P_e &= P_H(0)⋅P_{FA} + P_H(1)⋅P_M \\
>     &= \frac{1}{2} ⋅ P_{FA} + \frac{1}{2} ⋅ P_M \\
>     &= P_{FA} = P_M
> \end{aligned}
> $$
>
> Where $P_{FA}$ is the probability of false alarm and $P_M$ is the probability of
> missing.
>
> $$
> \begin{aligned}
>     P_{FA} &= ∫_{D_1} p(z|0) dz \\
>     &= ∫_m^∞ \frac{1}{\sqrt{2π⋅2(1+ρ)}} \exp\left(\frac{-z^2}{2⋅2(1+ρ)}\right) dz \\
>     &= 1-∫_{-∞}^m \frac{1}{\sqrt{2π⋅2(1+ρ)}} \exp\left(\frac{-z^2}{2⋅2(1+ρ)}\right) dz \\
> \end{aligned}
> $$
>
> Let us do a change of variable: $t = \frac{z}{\sqrt{2(1+ρ)}}$
>
> $$
> \begin{aligned}
> z &= t \sqrt{2(1+ρ)} \\
> dz &= dt ⋅ \sqrt{2(1+ρ)} dt \\
> z = -∞ &⟹ t = -∞ \\
> z = m &⟹ t = \frac{m}{\sqrt{2(1+ρ)}}
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
>     P_{FA} &= 1 - ∫_{-∞}^{\frac{m}{\sqrt{2(1+ρ)}}} \frac{1}{\sqrt{2π}} \exp\left(\frac{-t^2}{2}\right) dt \\
>     &= 1 - Q\left(\frac{m}{\sqrt{2(1+ρ)}}\right)
> \end{aligned}
> $$
>
> As we stated before, this is the same as $P_M$.
>
> $$
> \boxed{P_e = P_m = P_{FA} = 1 - Q\left(\frac{m}{\sqrt{2(1+ρ)}}\right)}
> $$

### Question 11.d
Analyze how the probability of error changes with $ρ$; in order to do so,
consider cases $ρ = −1$, $ρ = 0$, and $ρ = 1$. Indicate, for each of these
values of $ρ$, how the likelihoods and decision boundary look like on the plane
with coordinate axis $X_1 − X_2$.

> **Answer** (class notes)
>
> Let's consider those cases:
>
> * $ρ=-1 ⟹ P_e = 1- F(∞) = 1-1 = \boxed{0 = P_e}$
> * $ρ=0 ⟹ P_e = 1- F\left(\frac{m}{\sqrt{2}}\right) = 1-F(0.70m) ⟹ P_{e0}<P_{e1}$
> * $ρ=1 ⟹ P_e = 1- F\left(\frac{m}{2}\right) = 1 - F(0.5m)$
>
> It seems that the probability of error increases with $ρ$.

## Exercise 22 ✓

Consider a binary decision problem described by

$$
\begin{aligned}
    p_{X|H}(x|0) &= a_0 x^2 & |x| < 1 \\
    p_{X|H}(x|1) &= a_1 (3 − |x|) & |x| < 3
\end{aligned}
$$

where $a_0$ and $a_1$ are constants, with the same a priori probabilities for
the two hypotheses, and where the following cost policy is used: $c_{00} =
c_{11} = 0, c_{10} = c_{01} = c$ with $c > 0$.

### Question 11.a
Calculate constants $a_0$ and $a_1$.

> **Answer** (class notes)

$a_0$

$$
\begin{aligned}
    ∫_{(x)} p(x|0) dx &= \\
    1∫_{-1}^1 a_0 x^2 dx &= 1 \\
    a_0 \frac{x^2}{3} \Big|_{x=-1}^1 &= 1 \\
    \boxed{a_0 = \frac{3}{2}}
\end{aligned}
$$

$a_1$

$$
\begin{aligned}
    ∫_{(x)} p(x|1) dx &= 1 \\
    ∫_{-3}^3 a_1 (3 - |x|) dx &= 1 \\
    2 ∫_{0}^3 a_1 (3 - x) dx &= 1 \\
    2 a_1 \left[3x - \frac{x^2}{2}\right] \Big|_{x=0}^3 &= 1 \\
    \boxed{a_1 = \frac{1}{9}}
\end{aligned}
$$

### Question 11.b
Determine the Bayes optimal classifier.

> **Answer** (class notes)
>
> MAP decider
>
> $$
> \begin{aligned}
>     \frac{p(x|1)}{p(x|0)} &\decgl{D_1}{D_0} \frac{c_{10} - c_{00}}{c_{01} - c_{11}} \frac{p_H(0)}{p_H(1)} \\
>     \frac{p(x|1)}{p(x|0)} &\decgl{D_1}{D_0} 1 \\
>     \frac{\frac{1}{9} (3-|x|)}{\frac{3}{2}x^2} &\decgl{D_1}{D_0} 1
> \end{aligned}
> $$
>
> For $0<x<1$
>
> $$
> \begin{aligned}
>     \frac{\frac{1}{9}(3-x)}{\frac{3}{2}x^2} &\decgl{D_1}{D_0} 1
>     \frac{2}{27}(3-x) &\decgl{D_1}{D_0} x^2
>     -x^2 - \frac{2}{27}x + \frac{6}{27} &\decgl{D_1}{D_0} 0
> \end{aligned}
> $$
>
> Solving the second degree equation
>
> $$
> \begin{aligned}
>     x &= \frac{-\frac{2}{27} ± \sqrt{\frac{4}{479}+ \frac{24}{27}}}{2} \\
>     &= 0.4358 \text{ or } \cancel{-0.3117}
> \end{aligned}
> $$
>
> So,
>
> $$
> \boxed{
> \begin{cases}
>     |x| < 1 & ⟹ |x| \decgl{D_0}{D_1} 0.4358 \\
>     1 < |x| < 3 & ⟹ D_1
> \end{cases}
> }
> $$

### Question 11.c
Calculate the probability of error of this decider.

> **Answer** (class notes)
>
> $$
> \begin{aligned}
>     P_e &= P_H(0) P_{FA} + P_H(1) P_M \\
>     &= \frac{1}{2} P_{FA} + \frac{1}{2} P_M
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
>     P_{FA} &= P_{D|H} (1|0) \\
>     &= 2 ∫_0^{0.4358} \frac{3}{2}x^2 dx \\
>     &= 2 ⋅ \frac{3}{2⋅3} x^3 \Big|_{x=0}^{0.4358} \\
>     &= 0.08276
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
>     P_M &= P_{D|H} (0|1) \\
>     &= 2 ∫_{0.4358}^1 \frac{1}{9} (3-x) dx \\
>     &= \frac{2}{9} \left(3x - \frac{x^2}{2}\right) \Big|_{x=0.4358}^1 \\
>     &= 0.2861
> \end{aligned}
> $$

### Question 11.d
Design the Neyman-Pearson decider that guarantees a PFA not larger than a
pre-established value

> **Answer** (class notes)
>
> Our constraint is:
>
> $$
> P_{FA} ≤ α
> $$
>
> For $|x| < 1$:
>
> $$
> \begin{aligned}
>     \frac{p(x|1)}{p(x|0)} &\decgl{D_1}{D_0} η \\
>     \frac{\frac{1}{9}(3-|x|)}{\frac{3}{2}x^2} &\decgl{D_1}{D_0} η \\
>     |x| &\decgl{D_0}{D_1} η'
> \end{aligned}
> $$
>
> Applying our constraint:
>
> $$
> \begin{aligned}
>     P_{FA} &= α
>     ∫_{D_1} p(x|0) dx &= α\\
>     2 ∫_0^{η'} \frac{3}{2}x^2 dx &= α \\
>     x^3 \Big|_{x=0}^{η'} &= α \\
>     η' &= \sqrt[3]{α}
> \end{aligned}
> $$
>
> Therefore,
>
> $$
> |x| \decgl{D_0}{D_1} \sqrt[3]{α}
> $$
>
> Finally:
>
> $$
> \begin{cases}
>     |x| < 1 & ⟹ |x| \decgl{D_0}{D_1} \sqrt[3]{α} \\
>     1 < |x| < 3 & ⟹ D_1
> \end{cases}
> $$
