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
