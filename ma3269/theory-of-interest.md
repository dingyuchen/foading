# Theory of Interest

## Interest

### Accumulation Function

When a principal of 1 dollar is deposited in an interest-paying account at time $t = 0$, it earns some interest over the time interval $[0, t]$. 
The accumulated value of 1 dollar at time $t \geq 0$, denoted by $a(t)$, is known as the **accumulation function**.

Clearly, $a(0) = 1$.

### Simple and Compound Interest

Let $r$ be the _annual_ rate of interest.

Based on the **simple-interest** method of calculating interest, 

$$a(t) = 1 + rt \text{ for } t \geq 0$$

If the **compound-interest** method is used, 

$$a(t) = (1 + r)^t \text{ for } t \geq 0$$

### Frequency of Compounding

When an interest of $r = r^{(p)}$ is said $p$ times a year (or equivalently, $r^{(p)}$ is convertible $p$thly or $r^{(p)}$ is compounded $p$ times a year),
we call $p$ the **frequency of compounding** and $r^{(p)}$ the **nominal** rate of interest.

The interest to be paid over one period, is $\frac{r^{(p)}}{p}$. 
Effectively, $\$1$ invested at time $t = 0$ will grow to $\Big( 1 + \frac{r^{(p)}}{p}\Big)$ over a period of length $\frac{1}{p}$,
so that the accumulated amount after one year is $\Big( 1 + \frac{r^{(p)}}{p}\Big)^p$

### Equivalent Interest Rates

Two nominal interest rates are said to be **equivalent** iff they yield the same accumulation amount over a year.
Hence, the nominal rates $r^{(p)}$ and $r^{(q)}$ are equivalent iff 

$$\Bigg (1 + \frac{r^{(p)}}{p} \Bigg)^p = \Bigg (1 + \frac{r^{(q)}}{q} \Bigg)^q$$

In particular, the **effective** annual interest rate (when $p = 1$),
denoted by $r_e$, is given by

$$1 + r_e = \Bigg ( 1 + \frac{r^{(p)}}{p} \Bigg)^p$$

It can be shown that for $p > 1$, the effective annual interest rate is always greater than the nominal rate $r^{(p)}$.
That is, for any positive integer $p$,

$$r_e := \Bigg ( 1 + \frac{r^{(p)}}{p} \Bigg)^p - 1 \geq r^{(p)}$$

> This can be shown with Bernoulli Inequality

### Continuous Compounding

We say that interest is compounded continuously when the frequency of compounding tends to infinity.
Let $r^{(\infty)}$ denote the nominal rate of interest under continuous compounding.
Then,

$$ a(1) = \lim_{p \rightarrow \infty}(1 + \frac{r^{(\infty)}}{p})^p = e^{r^{(\infty)}} $$

The number $r^{(\infty)}$ is known as the **continuously compounded rate of interest**.

It follows that compounding yields a _higher_ accumulated value than does compounding $p$ times a year, for any positive integer $p$.

$$ e^r > \Bigg ( 1 + \frac{r}{p} \Bigg)^p \; \text{ for any } \; r > 0 \text{ an for any } \; p \in \Z^+ $$

## Present Value and Time Value

Let $a(t)$ be the accumulation function.
Let $X$ be the amount that must be invested at time $t = 0$ to accumulate to $1$ dollar at $t = T$. 
Then

$$ X \cdot a(T) = 1$$

The amount $X = \frac{1}{a(T)}$ is the **present value** of 1 dollar paid at time $T$.

It follows that the present value of a single payment of $C$ at time $t = T$ is $\frac{C}{a(T)}$.

More generally, for a cash flow $\textbf{C} = \{(c_1, t_2), (c_2, t_2), ..., (c_n, t_n) \}$
the present value of this cash flow, denoted by $PV(\textbf{C})$, is defined by

$$PV(\textbf{C}) = \sum^n_{i = 1} \frac{c_i}{a(t_i)}$$

The **time value** of the cash flow $\textbf{C}$ at time $t \geq 0$, denoted by $TV_t(\textbf{C})$, is given by

$$TV_t(\textbf{C}) = PV(\textbf{C}) \times a(t)$$

### Principle of Equivalence

In an environment where both the interest rate and its method of accumulation remain the same over any time period, 
two cash flows streams are **equivalent** iff they have the same present value.
(iff they have the same time value at $t = T$ for any $T \geq 0$)

### Deferred Cash Flow

Let $k > 0$ and define the cash flow $\textbf{C}_{(k)} = \{(c_1, t_1 + k), (c_2, t_2 + k), ..., (c_n, t_n + k) \}$

If the _annual interest rate_ is $r$, then

$$ \frac{PV(\textbf{C})}{PV(\textbf{C}_{(k)})} = (1 + r)^k $$

> The deferment is consistent throughout the interval

### Equation of Value

Consider the cash flow stream $\textbf{C} = \{(c_1, t_1), (c_2, t_2), ..., (c_n, t_n) \}$.
The equation

$$PV(\textbf{C}) = \sum^n_{i = 1} \frac{c_i}{(1 + r)^{t_i}} = 0$$
### Internal Rate of Return

Any non-negative root $r$, of the equation of value is called the **yield**, or **internal rate of return (IRR)**, of the cash flow stream.

> In general, $r$ is not unique

> Although if first payment is negative and all subsequent payments are $\geq 0$, $r$ will be unique

## Newton Raphson Method

Numerical method to solve higher order polynomials

Let $\alpha$ be a root of the equation $f(x) = 0$,
where $f$ is differentiable on an interval containing $\alpha$.

The iterative formula is given by

$$\alpha_{n + 1} = \alpha_n - \frac{f(\alpha_n)}{f'(\alpha_n)}$$

provided $f'(\alpha_n) \neq 0$.

> It is better to multiply the denominator rather than substituting the denominator to create a polynomial
> As it would increase teh error when converting back to $r$

## Annuities

An annuity is a series of payments made a regular intervals.

An **annuity-due** is one for which payments are made at the _beginning_ of each period.

An **annuity immediate** is one for which payments are made _at the end of each period_.

### Perpetual Annuity (Perpetuity)

A perpetuity is an annuity with an infinite number of payments

## Loans


