# Series of Functions

Given a sequence of functions, construct a new sequence of functions.

If $(f_n)$ is a sequence of functions on $E$, 
then $\sum^\infty_{n = 1} f_n$ is an infinite series of functions.

For each $n \in \N$, the **nth partial sum** of $\sum^\infty_{n = 1} f_n$ is the function

$$S_n(x) = \sum^n_{i = 1} f_i(x), \; x \in E$$

- The series $\sum f_n$ is said to **converge pointwise** to a function $S$ on $E$ if the sequence $(S_n)$ of functions converges pointwise to $S$ on $E$.
- The series is said to **converge uniformly** to a function $S$ on $E$ if the sequence $(S_n)$ of functions converges uniformly to $S$ on $E$.
- The series is said to **converge absolutely** on $E$ if the series $\sum^\infty_{n = 1} \vert f_n \vert$ converges pointwise on $E$.

## Cauchy Criterion for Uniform Convergence

Let $(f_n)$ be a sequence of functions on $E$. 
Then the series $\sum^\infty_{n = 1} f_n$ converges uniformly on $E$ if and only if for every $\epsilon > 0$, there exists $K \in \N$ such that

$$n > m \geq K \Rightarrow \Vert f_{m + 1} + f_{m + 2} + ... + f_n\Vert_E < \epsilon$$

or alternatively:

$$n > m \geq K \Rightarrow \vert f_{m + 1}(x) + f_{m + 2}(x) + ... + f_n(x) \vert < \epsilon \; \forall x \in E$$

### Corollary 8.3.1

If $\sum^\infty_{n = 1} f_n$ converges uniformly on $E$, then

$f_n \rightarrow 0$ uniformly on $E$.

> Contrapositive

#### Proof

## Weierstrass M-test

Let $(f_n)$ be a sequence of functions on $E$ and let $(M_n)$ be a sequence of positive real numbers such that $\forall n \in \N$,

$$\Vert f_n \Vert_E \leq M_n$$

i.e.,

$$\vert f_n(x) \vert \leq M_n \; \forall x \in E, \forall n \in \N$$

If the series $\sum M_n$ converges, then $\sum f_n$ converges uniformly on $E$.

## Theorem 8.3.2

If $\sum^\infty_{n = 1} f_n$ converges uniformly to $f$ on an interval $I$ and each $f_n$ is continuous at $x_0 \in I$, then $f$ is continuous at $x_0$.

### Corollary 8.3.3

If $\sum^\infty_{n = 1} f_n$ converges uniformly to $f$ on an interval $I$ and each $f_n$ is continuous on $I$, then $f$ is continuous on $I$.

## Theorem 8.3.4

If $\sum^\infty_{n = 1} f_n$ converges uniformly to $f$ on $[a, b]$ and each $f_n$ is integrable on $[a, b]$, then 

1. $f$ is integrable on $[a, b]$ and
2. for every $x \in [a, b]$,

$$ \sum^\infty_{n = 1} \int^x_a f_n(t) \; dt = \int^x_a f(t) \; dt = \int^x_a \sum^\infty_{n = 1} f_n(t) \; dt$$

where the convergence is uniform on [a, b].

## Theorem 8.3.5

Suppose that

1. $\sum^\infty_{n = 1} f_n(x_0)$ converges for some $x_0 \in [a, b]$ and
2. $\sum^\infty_{n = 1} f'_n$ converges uniformly on $[a, b]$

Then $\sum^\infty_{n = 1} f_n$ converges uniformly on $[a, b]$ to a differentiable function $f$ and

$$\sum^\infty_{n = 1} f_n'(x) = f'(x)$$

ie,

$$\sum^\infty_{n = 1} \frac{d}{dx} f_n(x) = \frac{d}{dx} \Bigg (\sum^\infty_{n = 1} f_n(x) \Bigg)$$

## Theorem 8.3.6

There exists a function $f: \R \rightarrow \R$ such that

1. $f$ is continuous on $\R$
2. $f$ is not differentiable at any point of $\R$

### Proof

Construct $f$ using uniform convergence of a series.

Let $\phi(x) = \vert x \vert$
