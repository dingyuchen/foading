# Sequences of Functions

## Sequence of Functions

Let $E \subseteq \R$

Suppose for each $n \in \N$, we have a function $f_n : E \rightarrow \R$.
Put these functions together to form a sequence

$$(f_n) = (f_1, f_2, ..., f_n)$$

We say that **$(f_n)$ is a sequence of functions on $E$**.

> Think of functions in an array

> Use this to create new functions ($e$)

### Questions

How well does pointwise convergence preserve the properties of the sequence\ of functions?

- If $f_n \rightarrow f$ pointwise, and each $f_n$ is continuous on $I$, is $f$ continuous on $I$?
- If $g_n \rightarrow g$ pointwise on $[a, b]$, and each $g_n$ is integrable on $[a, b]$, then
  - is $g$ necessarily integrable on $[a, b]$?
  - does $\int^b_a g_n \rightarrow \int^b_a g$?
- Is $h_n' \rightarrow h'$ pointwise?

> All no

### Uniform Convergence

A sequence $(f_n)$ of functions **converges uniformly** to $f$ on $E$ iff $\forall \epsilon > 0, \exists K \in \N$ such that

$$n \geq K \Rightarrow \vert f_n(x) - f(x) \vert < \epsilon \; \forall x \in E$$

> The convergence speed is roughly the same for all $x$.

We say that $(f_n)$ **converges uniformly on** $E$ if there exists a function $f$ such that $(f_n)$ converges to $f$ uniformly on $E$.

### Uniform Norm

Let $E \subseteq \R$ and let $\varphi: E \rightarrow \R$ be a bounded function.
The **uniform norm** of $\varphi$ on $E$ is defined as 

$$\Vert \varphi \Vert_E := \sup \{ \vert \varphi(x) \vert : x \in E\} $$

Note that $\vert \varphi (x) \vert \leq \Vert \varphi \Vert_E$ for all $x \in E$.

### Lemma 8.1.1

A sequence $(f_n)$ of functions converges to $f$ uniformly on $E$ iff $\Vert f_n - f \Vert_E \rightarrow 0$

#### Proof

Assume that $f_n \rightarrow f$ uniformly. 
Let $\epsilon > 0$.

Then let there be some $K \in \N$, we see that both expressions are $< \epsilon$.

Similar in the converse direction.

### Cauchy Criterion for Uniform Convergence

A sequence $(f_n)$ of functions convergences uniformly on $E$ iff for each $\epsilon > 0$,
there exists $K \in \N$ such that

$$\Vert f_n - f_m \Vert_E < \epsilon \; \forall n, m \geq K$$ 

### Lemma 8.1.3

A sequence $(f_n)$ **does not** converge uniformly to $f$ on $E$ iff for some $\epsilon_0 > 0$, there is a subsequence $(f_{n_k})$ of $(f_n)$ and a sequence $(x_k)$ in $E$ such that

$$\vert f_{n_k}(x_k) - f(x_k) \vert \geq \epsilon_0, \forall k \in \N$$

## Properties Preserved by Uniform Convergence

### Theorem 8.2.1

If $(f_n)$ converges uniformly to $f$ on an interval $I$ and each $f_n$ is continuous at $x_0 \in I$, then $f$ is continuous at $x_0$.

> Uniform convergence preserves continuity.

#### Proof

Let $\epsilon > 0$.

We have $\vert f_k(x) - f(x) \vert < \frac{\epsilon}{3}$ for all $x$ in $I$.

Since $f_k$ is continuous at $x_0$,
$\exists \delta > 0$ such that $\vert x - x_0 \vert < \delta \Rightarrow \vert f_k(x) - f(x) \vert < \frac{\epsilon}{3}$

$$\vert f(x) - f(x_0) \vert \leq \vert f(x) - f_k(x) \vert + \vert f_k(x) - f_k(x_0) \vert + \vert f_k(x_0) - f(x_0) \vert < \epsilon$$

> The 3-$\epsilon$ argument

### Corollary 8.2.2

If $(f_n)$ converges uniformly to $f$ on an interval $I$ and each $f_n$ is continuous on $I$, then $f$ is continuous on $I$.

### Remarks

> Uniform convergence allows us to interchange the order of limits.

#### Method 3

If $f_n \rightarrow f$ pointwise on $I$, $f_n$ is continuous but $f$ is not continuous on $I$, then $f_n$ does not converge uniformly to $f$ on $I$.

# Integrability

## Theorem 8.2.3

Suppose that $f_n \rightarrow f$ uniformly on $[a, b]$ and each $f_n$ is integrable on $[a, b]$. Then:

1. $f$ is integrable on $[a, b]$ and 
2. for each $x_0 \in [a, b]$, the sequence $F_n(x) := \int^x_{x_0} f_n(t) \; dt$ converges uniformly to $F(x) := \int^x_{x_0} f(t) \; dt$ on $[a, b]$.

Hence 

$$\lim_{n \rightarrow \infty} \int^x_{x_0} f_n(t) \; dt = \int^x_{x_0} \lim_{n \rightarrow \infty} f_n(t) \; dt$$

In particular,

$$\lim_{n \rightarrow \infty} \int^b_a f_n(t) \; dt = \int^b_a f(t) \; dt$$

> Uniform convergence preserves the integrability

> Uniform convergence allows us to interchange the order of taking limits and integration

# Differentiability

Does uniform convergence preserve differentiability?

> no.

## Theorem 8.2.4

Suppose that $(f_n)$ is a sequence of differentiable functions on $[a, b]$ such that 

1. $(f_n(x_0))$ converges for some $x_0 \in [a, b]$
2. $(f_n')$ converges uniformly on $[a, b]$

> $(f_n')$ must also be uniformly convergent

Then $(f_n)$ converges uniformly on $[a, b]$ to a differentiable function $f$, and

$$\lim_{n \rightarrow \infty} f_n'(x) = f'(x)$$

i.e.,

$$\lim_{n \rightarrow \infty} \Bigg ( \frac{d}{dx} f_n(x) \Bigg ) = \frac{d}{dx} \Bigg ( \lim_{n \rightarrow \infty} f_n(x) \Bigg) $$

### Proof

See page 250 of text.

## 

