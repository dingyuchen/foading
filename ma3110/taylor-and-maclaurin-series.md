# Taylor and Maclaurin Series

We say that a function $f$ is **infinitely differentiable** on $(a, b)$ if $f^{(n)}(x)$ exists for all $x \in (a, b)$ and for all $n \in \N$.

Let $f$ be infinitely differentiable on $(x_0 - r, x_0 + r)$ for some $r > 0$.
The power series

$$\sum^\infty_{n = 0} \frac{f^{(n)}(x_0)}{n!} (x - x_0)^n$$

is called the **Taylor Series of $f$ about $x_0$**.

If $x_0 = 0$, the series becomes 

$$\sum^\infty_{n = 0} \frac{f^{(n)}(0)}{n!} x^n$$

called the **Maclaurin Series**.

## Theorem 9.3.1

Let $f$ be infinitely differentiable on $I = (x_0 - r, x_0 + r)$ and $x \in I$.
Then

$$f(x) = \sum^\infty_{n = 0} \frac{f^{(n)}(x_0)}{n!} (x - x_0)^n$$

iff 

$$\lim_{n \rightarrow \infty} R_n(x) = \lim_{n \rightarrow \infty} \frac{f^{(n+1)}(c_n)}{(n + 1)!} (x - x_0)^{n+1} = 0$$

where each $c_n$ (depending on $n, x, x_0$) is between $x$ and $x_0$.

## Analytic

A function $f$ is **analytic** on $(a, b)$ if 

1. $f$ is infinitely differentiable on $(a, b)$ and
2. for any $x_0 \in (a, b)$, the Taylor Series of $f$ about $x_0$ converges to $f$ in a neighborhood of $x_0$.

## Arithmetic Operations with Power Serieso

The **Cauchy product** of $\sum^\infty_{n = 0} a_n$ and $\sum^\infty_{n = 0} b_n$ is the series $\sum^\infty_{n = 0} c_n$, where for each $n \in \N$,

$$c_n = \sum^n_{k = 0} a_k b_{n-k} = a_0b_n + a_1b_{n - 1} + ... + a_n b_0 $$

> $c_n$ is the sum of all products where $i + j = n$.

## Merten's Theorem

If $\sum^\infty_{n = 0} a_n$ converges absolutely and $\sum^\infty_{n = 0} b_n$ converges, then the Cauchy product 
$\sum^\infty_{n = 0} c_n$ of these 2 series converges and 

$$\sum^\infty_{n = 0} c_n = \bigg ( \sum^\infty_{n = 0} b_n \bigg) \bigg(\sum^\infty_{n = 0} b_n \bigg )$$