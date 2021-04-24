# Random Variables

A **random variable** $X$ is a mapping from the sample space to real numbers.

## Sum of Outcomes


## Discrete Random Variables

A random variable is said to be **discrete** if the range of $X$ is either finite or countably infinite.

Suppose that a random variable $X$ is discrete, taking values $x_1, x_2, ...$ then the **probability mass function** of $X$, denoted by $p_x$, is defined as 

$$p_x(x) = \begin{cases}
P(X = x), & \text{if } x = x_1, x_2, ...\\
0 & \text{otherwise}
\end{cases}$$

## Binomial Random Variable

We perform the experiment (under identical conditions and independently) $n$ times and define
$X =$ **number of successes** in $n$ Bernoulli($p$) trials.

$$P(X = k) = \binom{n}{k} p^k (1-p)^{n - k}$$

$$E(X) = np$$

$$var(X) = np(1-p)$$

## Geometric Random Variable

Define the random variable $X =$ **number of Bernoulli(p) trials** required to obtain the first success.

$$P(X = k) = pq^{k-1}$$

$$E(X) = \frac{1}{p}$$

$$var(X) = \frac{1-p}{p^2}$$

## Negative Binomial

Define random variable $X =$ **number of Bernoulli(p) trials** required to obtain $r$ successes.

$$P(X = k) = \binom{k-1}{r -1}p^r q^{k - r}$$

$$E(X) = \frac{r}{p}$$

$$var(X) = \frac{r(1-p)}{p^2}$$

> Note that $Geom(p) = NB(1, p)$.

## Poisson Random Variable

A random variable $X$ is said to have a **Poisson** distribution with parameter $\lambda$ if $X$ takes non-negative integer values with probability

$$P(X = k) = \frac{e^{-\lambda} \lambda^k}{k!}$$

$$E(X) = \lambda$$

$$var(X) = \lambda$$

### Approximation

For large values of $n$ and small values of $p$ so that $np$ is of moderate size, let $\lambda = np$.

A Binomial distribution $B(n, p) \approx Po(lambda)$

## Hypergeometric Random Variable

Suppose that we have a set of $N$ balls, of which $m$ are red and $N -m$ are blue. 
We choose $n$ of these balls, **without replacement**, and define $X$ to be the number of red balls in our sample.

$$P(X = x) = \frac{\binom{m}{x} \binom{N - m}{n - x}}{\binom{N}{n}}$$

$$E(X) = \frac{nm}{N}$$

$$var(X) = \frac{nm}{N}(\frac{(n-1)(m - 1)}{N -1} + 1 - \frac{mn}{N})$$
