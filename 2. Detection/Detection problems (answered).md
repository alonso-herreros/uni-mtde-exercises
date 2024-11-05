## Modern Theory of Detection and Estimation

# Problemas de Detección

*Academic year 2024-2025*  
*Telematics Engineering Department - Universidad Carlos III de Madrid*

---

* [Modern Theory of Detection and Estimation](#modern-theory-of-detection-and-estimation)
* [Ejemplo 2.8](#ejemplo-28)
* [Ejemplo 2.9](#ejemplo-29)

---

## Ejemplo 2.8

Dadas las verosimilitudes:

$$
\begin{aligned}
p_{X|H}(x|1) &= 2x & 0 ≤ x ≤ 1 \\
p_{X|H}(x|0) &= 2(1 − x) \quad& 0 ≤ x ≤ 1
\end{aligned}
$$

diseñar el decisor NP dado por la cota $α = 0,1$ ($P_{FA} ≤ α$)

> **Respuesta** (apuntes)
>
> $$
> P_{FA} = P_{D|H}(1|0) = ∫_{D_1} p(x|0) dx = 0.1
> $$
>
> $$
> \begin{aligned}
>     \frac{p(x|1)}{p(x|0)} &\overset{D_1}{\underset{D_0}{≶}} η \\[1em]
>     \frac{2x}{2(1-x)} &\overset{D_1}{\underset{D_0}{≶}} η \\[1em]
>     x &\overset{D_1}{\underset{D_0}{≶}} η(1-x) \\[1em]
>     x &\overset{D_1}{\underset{D_0}{≶}} \frac{η}{1+η} = η' \\[1em]
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
>     P_{FA} &= ∫_{D_1} p(x|0) dx \\
>     &= ∫_{η'}^1 2(1-x) dx = 0.1 \\
>     &= 2x-x^2 \big|_{η'}^1 = 0.1 \\
>     &= 2-1-2η' + η'^2 = 0.1 \\
>     &⇓ \\
>     η' &= \begin{cases}
>         \cancel{1.3168} \\
>         \boxed{0.6838}
>     \end{cases}
> \end{aligned}
> $$

## Ejemplo 2.9

Dadas las verosimilitudes:

$$
\begin{aligned}
p_{X|H}(x|1) &= 2x & 0 ≤ x ≤ 1 \\
p_{X|H}(x|0) &= 2(1 − x) \quad& 0 ≤ x ≤ 1
\end{aligned}
$$

diseñar el decisor Minimax

> **Respuesta** (apuntes de clase)
>
> $$
> \begin{aligned}
>     η'^2 - 2` +1 &= η'^2 \\
>     η' &= \frac{1}{2}
> \end{aligned}
> $$
>
> Como en el apartado anterior,
>
> $$
> \begin{aligned}
>     x &\overset{D_1}{\underset{D_0}{≶}} \frac{η}{1+η} = η' \\[1em]
>     x &\overset{D_1}{\underset{D_0}{≶}} \frac{1}{2}
> \end{aligned}
> $$
