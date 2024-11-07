## Modern Theory of Detection and Estimation <!-- omit in toc -->

# Classification Problems

*Academic year 2024-2025*  
*Telematics Engineering Department - Universidad Carlos III de Madrid*

* [Exercise 2](#exercise-2)
    * [Question 2.a](#question-2a)
    * [Question 2.b](#question-2b)
    * [Question 2.c](#question-2c)
    * [Question 2.d](#question-2d)

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
