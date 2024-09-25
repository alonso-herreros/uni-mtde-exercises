# Review of Statistics - Problems

## Example 1

Let

$$
X → p_X(x) = U[0,1] \\
Y → Y = 3X + 2
$$

The target is to find $p_Y(y)$

> **Answer**
>
> The PDF is given by
>
> $$
> p_Y(y) = p_X(x(y)) \left| \frac{∂}{∂y} x(y) \right|
> $$
>
> We'll figure out the components of this equation individually
>
> For a uniform distribution, the PDF is
>
> $$
> \begin{aligned}
> p_X(x) &= \frac{1}{1-0},\quad 0<x<1 \\
> &= 1,\quad 0<x<1
> \end{aligned}
> $$
>
> The expression of X in terms of Y is
>
> $$
> Y = 3X + 2 ⇒ X = \frac{Y-2}{3}\\
> $$
>
> $$
> \begin{aligned}
> p_Y(y) &= p_X(x(y)) \left| \frac{∂}{∂y} x(y) \right| \\
> &= 1 · \frac{1}{3} = \frac{1}{3} ,\quad 2<y<5
> \end{aligned}
> $$

## Example 2

Let $X ∼ G(x | 0,1)$ and $Y = 3X + 2$

Find $p_Y(y)$

> **Answer**
>
> $$
> X ∼ G(x|0,1) ⇒ p_X(x) = \frac{1}{\sqrt{2π · 1}} \exp \left(\frac{-x^2}{2·1}\right)
> $$
>
> $$
> X = \frac{Y-2}{3}
> $$
>
> $$
> p_Y(y) = \frac{1}{2π} \exp \left(-\frac{(y-2)^2}{2 · 3^2}\right) · \frac{1}{3}
> $$
>
> You can also use the fact that Y must be a Gaussian distribution, with mean $E\{Y\} = 2$, $Var\{Y\}
> = 9$, and apply the formula for the PDF of a Gaussian distribution.
>
> $$
> p_Y(y) = \frac{1}{\sqrt{2π·9}} \exp \left(-\frac{(y-2)^2}{2·9}\right)
> $$

## Example 3

Let $X ∼ U[-1,1]$, $Y = X^2$. Find $p_Y(y)$

> **Answer**
>
> We'll use the same procedure as before to complete the expression
>
> $$
> p_Y(y) = p_X(x(y)) \left| \frac{∂}{∂y} x(y) \right|
> $$
>
> First the PDF of X
>
> $$
> p_X(x) = \frac12,\quad -1<x<1
> $$
>
> Then, the expression of X in terms of Y
>
> $$
> Y = X^2 ⇒ X = ± \sqrt{Y}
> $$
>
> As we can see, the original function was not one-to-one, so the the expression of X in terms of Y is
> not unique. We'll have to split this, taking one of the branches at a time, and calculate the PDF of
> Y for each case.
>
> $$
> \begin{aligned}
> p_Y(y)\big|_{x=+\sqrt{y}} = \frac12 · \frac{1}{2\sqrt{y}} \\
> p_Y(y)\big|_{x=-\sqrt{y}} = \frac12 · \frac{1}{2\sqrt{y}} \\
> \end{aligned}
> $$
>
> Now we have two results (which just hapen to be the same). What we'll have to do to get the global
> $p_Y(y)$ is to calculate the **sum** of both branches:
>
> $$
> p_Y(y) = \frac{1}{2\sqrt{y}}
> $$

## Example 4

Let $X ∼ U[-1,2]$, $Y = X^2$. Find $p_Y(y)$

> **Answer**
>
> This case is similar to the previous example, but with an addition to the range of X. It will mostly
> be the same, but we'll have to split the calculation further, as the expression of X in terms of Y
> in the added range is unambiguous.
>
> $$
> p_Y(y) = \begin{cases}
>     \frac{1}{3\sqrt{y}} & 0<y<1 \\
>     \frac{1}{6\sqrt{y}} & 1<y<4 \\
>     0 & \text{otherwise}
> \end{cases}
> $$

## Example 5 (from exam)

1. Let $X ∼ U[0,1]$, $Y = X^r$ where $r$ is a constant $r>0$. Find $p_Y(y)$

    > **Answer**
    >
    > Once again, we'll use the same procedure
    >
    > $$
    > p_Y(y) = p_X(x(y)) \left| \frac{∂}{∂y} x(y) \right|
    > $$
    >
    > The PDF of X is trivial
    >
    > $$
    > p_X(x) = 1,\quad 0<x<1
    > $$
    >
    > Now, the expression of X in terms of Y
    >
    > $$
    > Y = X^r ⇒ X = Y^{1/r}
    > $$
    >
    > Since $X$ is never negative, we don't have to worry about negative roots.
    >
    > $$
    > p_Y(y) = 1 · \left|\frac{1}{r} y^{1/r - 1}\right|,\quad 0≤y≤1
    > $$

2. Let $X ∼ U[0,1]$, $Y = -2 \ln X$

    > **Answer**
    >
    > Same song and dance
    >
    > $$
    > p_X(x) = 1,\quad 0<x<1
    > $$
    >
    > $$
    > X = \exp \left(\frac{-Y}{2}\right)
    > $$
    >
    > The support can be found by analyzing the support of X: when $X=0$, $Y=∞$; when $X=1$, $Y=0$.
    >
    > $$
    > \begin{aligned}
    > p_Y(y) &= 1 · \left|-\frac{1}{2} · \exp\left(-\frac{Y}{2}\right)\right|,\quad 0<y<∞ \\
    > &= \frac12 \exp\left(-\frac{y}{2}\right),\quad 0<y<∞
    > \end{aligned}
    > $$

3. Let $p_R(r) = \exp (-r) u(r)$, $X = R/S$, $S>0$. Find $p_{X|S}(x|s)$

    > **Answer**
    >
    > Since the PDF we are looking for is conditional on $S$, we can treat it as a given constant.
    >
    > Instead of $X$ and $Y$, in this problem we're dealing with $R$ and $S$. We'll modify the formula
    > like so
    >
    > $$
    > p_{X|S}(x|s) = p_R(r(x|s)) · \left|\frac{∂}{∂x} r(x|s)\right|
    > $$
    >
    > We'll have to find the expression of $R$ in terms of $X$ (and $S$).
    >
    > $$
    > R = X·S \\
    > \left|\frac{∂}{∂x} r(x|s)\right| = |s| = s
    > $$
    >
    > $$
    > p_{X|S} (x|s) = \exp(-x·s) ·s ,\quad 0<x<∞
    > $$

4. (Jan '21)

    Let $p_X(x) = x·\exp \left(-\frac{x^2}{2}\right) ·u(x)$

    ```mermaid
    %%{init: {'forceLegacyMathML':'true'} }%%
    graph LR
    x(("$$x$$")) --> box["$$\frac{x^2}{2a}$$"] --> y(("$$y$$"))
    ```

    > **Answer**
    >
    > The graph can be interpreted as follows: $Y=\frac{X^2}{2a}$
    >
    > The procedure is the same as before
    >
    > $$
    > p_Y(y) = p_X(x(y)) \left|\frac{∂}{∂y} x(y)\right|
    > $$
    >
    > Since $X$ is always positive, the expression of $X$ in terms of $Y$ is
    >
    > $$
    > X = + \sqrt{2ay}
    > \left|\frac{∂}{∂y} x(y)\right| = \left|\sqrt{2a} \frac{1}{1\sqrt{y}}\right| = \sqrt{\frac{a}{2y}}
    > $$
    >
    > And finally,
    >
    > $$
    > \begin{aligned}
    > p_Y(y) &= \sqrt{2ay} · \exp \left(\frac{-2ay}{2}\right) · \sqrt{\frac{a}{2y}} \\
    > &= a \exp(-ay)
    > \end{aligned}
    > $$

## Two-dimensional random variables

## Example 6

Let

$$
p_{X_1, X_2} ∼ G\left(
    \begin{bmatrix}
        x_1 \\
        x_2
    \end{bmatrix}
    \middle|
    \begin{bmatrix}
        μ_1 \\
        μ_2
    \end{bmatrix}
    \begin{bmatrix}
        1 & ρ \\
        ρ & 1
    \end{bmatrix}
\right)
$$

Let $Y = X_1 + X_2$

> **Answer**
>
> We can find the parameters for the new RV $Y$:
>
> $$
> E\{Y\} = E\{X_1 + X_2\} = μ_1 + μ_2
> $$
>
> $$
> \begin{aligned}
> Var\{Y\} &= Var\{X_1 + X_2\} = Var\{X_1\} + Var \{X_2\} + 2Cov\{X_1, X_2\}
> &= 1 + 1 + 2ρ
> \end{aligned}
> $$
>
> $$
> p_Y(y) = \frac{1}{\sqrt{2π · 2(1+ρ)}} \exp \left(-\frac{(y-μ_1-μ_2)^2}{2·2(1+ρ)}\right)
> $$

## Example 7

Let

$$
X_1, X_2 ∼ G\left(
    \begin{bmatrix}
        x_1 \\
        x_2
    \end{bmatrix}
    \middle|
    \begin{bmatrix}
        1 \\
        0
    \end{bmatrix}
    \begin{bmatrix}
        2 & 1 \\
        1 & 5
    \end{bmatrix}
\right)
$$

> **Answer**
>
> $$
> Y = 3X_1 - X_2
> $$
>
> $$
> E\{Y\} = 3μ_1 - μ_2 = 3
> $$
>
> $$
> Var\{Y\} = Var\{3X_1\} + Var\{X_2\} - 3·2·Cov\{X_1, X_2\} = 3^2·2 + 5 - 6 · 1 = 17
> $$

## Example 8

Let

$$
p_{X,Y}(x,y) = \begin{cases}
    10x^2y & \begin{aligned}
        0<y<x \\
        0<x<1
    \end{aligned} \\
    0 & \text{otherwise}
\end{cases}
$$

> **Answer**
>
> $$
> p_Y(y) = ∫_y^1 10x^2 y dx
> $$
>
> $$
> p_X(x) = ∫_0^x 10x^2 y dy
> $$
