# Power Series

A series of functions of the form

$$\sum^\infty_{n = 0} a_n (x - x_0)^n = a_0 + a_1(x - x_0) + ... + a_n(x - x_0)^n + ...$$

where $x_0, a_1, a_2, ...$ are constants, is called a **power series** in $x - x_0$.

So 

$$\sum^\infty_{n = 0} a_n (x - x_0)^n = \sum^\infty_{n = 0} f_n(x)$$

where for each $n = 0, 1, 2, ...$

$$f_n : \R \rightarrow \R, f_n(x) = a_n(x - x_0)^n$$

> Power series will always at least converge at the center

## Ratio Test

Suppose that all the terms of the series $\sum^\infty_{n = 1} a_n$ are nonzero and the limit

$$\rho = \lim_{n \rightarrow \infty} \bigg \vert \frac{a_n + 1}{a_n} \bigg \vert$$

exists.

1. If $\rho < 1$, then the series converges absolutely
2. If $\rho > 1$, then the series diverges.
3. No conclusion if $\rho = 1$.

## Alternating Series Test

Suppose that we have a series $\sum a_n$ and either $a_n = (-1)^n b_n$ or $a_n = (-1)^{n + 1} b_n$ where $b_n \geq 0$ for all $n$.
Then if

1. $\lim_{n \rightarrow 0} b_n = 0$
2. $(b_n)$ is a decreasing sequence

the series $\sum a_n$ is convergent.

## Theorem 9.1.1

Let $\sum^\infty_{n = 0} a_n(x - x_0)^n$ be a power series.

1. If it converges at $x = x_1$, then it is absolutely convergent for all values of $x$ for which $\vert x - x_0 \vert < \vert x_1 - x_0 \vert$
2. If it diverges for $x = x_2$, then it diverges for all values of $x$ such that $\vert x - x_0 \vert > \vert x_2 - x_0 \vert$.

> By Theorem 9.1.1, every power series converges either at only one point or in an interval.

### Proof

Using comparison test and sum of geometric series.

Prove part 2 using contradiction

## Radius of Convergence

Given a power series $\sum^\infty_{n = 0} a_n(x - x_0)^n$, let

$$ S = \{ \vert x - x_0 \vert : x \in \R \text{ and } \sum^\infty_{n = 0} a_n(x - x_0)^n \text{ converges } \}$$

The **radius of convergence** of the series is defined as

$$R = \sup S$$

1. $R = 0$, if power series converges only for $x = x_0$.
2. $R = \infty$, if power series converges for all $x \in \R$.

## Theorem 9.1.2

A power series $\sum^\infty_{n = 0} a_n(x - x_0)^n$

- converges absolutely for all $x \in (x_0 - F, x_0 + R)$
- diverges for all $x$ with $\vert x - x_0\vert > R$.

> The theorem makes not statement about the end points $x = x_0 \pm R$
>
> A power series may converge or diverge at each of the points.

## Theorem 9.1.3

Suppose that $a_n \neq 0 \forall n$

1. If the limit $\rho = \lim_{n \rightarrow \infty} \vert \frac{a_{n + 1}}{a_n} \vert$ exists, then the radius of convergence of $\sum^\infty_{n = 0} a_n(x - x_0)^n$ is given by

$$R = \frac{1}{\rho}$$

2. If $\rho = \infty$, then $R = 0$.
