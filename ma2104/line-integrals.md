# Line Integrals

## Line Integral of (scalar-valued) functions

A parametrized curve in $\R^n$ is a function
$\vec r : I \rightarrow \R^n$ from an interval $I \subseteq \R$ to Euclidean n-space $\R^n$.

The parametrized curve given by $\vec r$ is _smooth_ iff
$\vec r$ is _continuously differentiable_ and has _non-vanishing derivative_. $(\vec r (t) \neq 0) \forall t in I$.

Geometrically, we think of the image set $C := \vec r (I) \subseteq \R^n$ as a smooth "curve" in $\R^n$ and the function $\vec r : I \rightarrow C$ as a (auxiliary) parametrization.

### Smooth curve

A smooth curve in $\R^n$ is a subset $C \subseteq \R^n$ such that there exists a bijective smooth parametrization $\vec r : I \rightarrow C$, where $I \subseteq \R$ is an interval

----------
Suppose $\vec r : I \rightarrow C, \vec s : J \rightarrow C$ are bijective smooth parametrizations.

Then there exists a bijective _continuously differentiable_ map $\Phi : I \rightarrow J$ such that $\vec r = \vec s \circ \Phi$.

----------
Let $C$ be a smooth curve in $\R^n$.
Let $f : C \rightarrow \R$ be a scalar valued function on $C$.

The line integral of $f$ over $C$ is $\int_C f \; ds \in \R$ defined as follows

Choose any bijective smooth parametrization $\vec r : I \rightarrow C$.
Set

$$\int_C f \; ds := \int_I f(\vec r(t)) \vert \vec r'(t) \vert \; dt$$

This is well-defined, independent of choice of parameter $\vec r$

#### Proof

If $\vec s : J \rightarrow C$ is another, then by _fact^_, there exists $\Phi : I \rightarrow J$ such that $\vec r = \vec s \circ \Phi$

Thus by change of variable $u = \Phi(t)$.

$$ \int_I f(\vec r (t)) \vert \vec r'(t) \vert \; dt 
= \int_I f(\vec s (\Phi(t))) \cdot \vert \vec s'(\Phi(t)) \vert \vert \Phi'(t) \vert \; dt
= \int_J f(\vec s(u)) \cdot \vert \vec s'(u) \vert \; du $$

## Additivity

Line integrals have the useful property that if a piecewise smooth curve $C$ is made by joining a finite number of smooth curves $C_1, C_2, .., C_n$ end to end,
then the integral of a function over $C$ is the sum of the integrals over the curves that make it up.

$$\int_C f \; ds = \int_{C_1} f \; ds + \int_{C_2} f \; ds + ... + \int_{C_n} f \; ds $$

# Vector Fields

- gradient of a function
- line integral of a vector field

Let $X$ be any subset of $\R^n$.
A **vector field** on $X$ is a vector-valued function $\vec F : X \rightarrow \R^n$ from $X$ to $\R^n$.
The vector field $\vec F : X \rightarrow \R^n$ is continuous / smooth iff $\vec F$ (as a vector-valued function) is continuous / smooth

> Same as vector-valued function, just that output dimension is the same as input

## Types

### Constant Vector Field

Fix any vector $\vec v_0 \in \R^n$

Set $\vec F : X \rightarrow \R^n$ to be $\vec F (\vec p) := \vec v_0$

### "Position" Vector Field

$\vec F : X \rightarrow \R^n$ to be $\vec F (\vec p) := \vec p$.

## Gradient Field

Let $U \subseteq \R^n$ be an open set,
and $f: U \rightarrow \R$ be a scalar-valued differentiable function

The gradient $\nabla f$ of $f$ is the total derivative map of $f' : U \rightarrow \mathbb{M}_{1 \times n}(\R) = \R^n$ (regarded as a vector field on $U$)

Explicitly, $\nabla f: U \rightarrow \R^n$ is given by
for each $\vec p \in U$, partial differentiation on each component.

Thus $\nabla f$ is a vector field on $U$, 

is continuous vector field iff $f$ is continuously differentiable.

A **gradient vector field** on $U$ is a vector field $\vec F : U \rightarrow \R^n$
such that there exists a scalar-valued differentiable function $f: U \rightarrow \R$ such that $\vec F = \nabla f$.

When this is so, the function $f$ is called a **potential function** of (the vector field) $\vec F$.

### Algebra Rules for Gradients

1. Sum Rule
2. Difference Rule 
3. Constant Multiple Rule 
4. Product Rule 
5. Quotient Rule

> Similar to single variate differentiation

## Line Integral of Vector Field over a Curve

Let $C$ be a smooth curve in $\R^n$ given with a bijective smooth parameterization $\vec r : I \rightarrow C$

Let $\vec F : C \rightarrow \R$ be a continuous vector field on $C$.

The **line integral of $\vec F$ over $C$ with respect to $\vec r$ is defined as

$$\int_C \vec F \cdot d \vec r := \int_I \vec F(\vec r (t)) \cdot \vec r '(t) \; dt$$

> This depends on the chosen parameter $\vec r$ of $C$ but only up to orientation:

If $\vec s : J \rightarrow C$ is another parameterization 
then there exists $\Phi : I \rightarrow J$ that is a contin differentiable bijection
such that $\vec r = \vec s \circ \Phi$.

If $\Phi' I \rightarrow \R$ always takes $>0$ values
then $\vec r$ and $\vec s$ are said to be parameterizing $C$ in the _same orientation_.

When this is so,

$$\int_C \vec F \cdot d \vec r = \int_I \vec F(\vec r (t)) \cdot \vec r'(t) \; dt$$
$$= \int_I \vec F(\vec s(\Phi(t))) \cdot \vec s'(\Phi(t)) \Phi'(t) \; dt$$
$$= \int_I \vec F(\vec s(u)) \cdot \vec s'(u) \; ds$$
$$= \int_C \vec F \cdot \; ds$$

If the orientation is negative, then we get exactly the negative of the above.

# Integral Theorems

## Fundamental Theorem of Line Integrals

Let $C$ be a smooth curve in $\R^n$, say from $A$ to $B$ given with a bijective smooth parameterization
$\vec r : I \rightarrow C$. 
Let $D \subseteq \R^n$ be an open set with $C \subseteq D$ and 
let $f: D \rightarrow \R$ be a continuously differentiable (scalar-valued) function.
Then

$$ \int_C \nabla f \cdot d \vec r = f(B) - f(A)$$

Note that this works for a _piecewise smooth function_ as well as the summation is telescopic.

## Remarks and Questions

1. Suppose we have to compute some line integral
   - How do we know whether $\vec F$ is a gradient vector field?
   - When we do know that $\vec F$ is a gradient vector field, how do we find $f$ such that $\vec F = \nabla f$?
2. If $\vec F$ is a gradient vector field on an open set $D$, then for any smooth curve $C$ in $D$, $\int_C F \cdot d \vec r$ depends only on the end points.

> Any other smooth curve $C'$ will give the same answer.

## Conservative Fields

Let $\vec F$ be a vector field defined on an open region $D$ in space, 
and suppose that for any two points $A$ and $B$ in $D$ the line integral $\int_C \vec F \cdot d \vec r$ along a path $C$ from $A$ to $B$ in $D$ is the same over all paths from $A$ to $B$.

Then the integral $\int_C \vec F \cdot d \vec r$ is **path independent** in $D$ and the field $\vec F$ is **conservative** on $D$.

> If $\vec F$ is a gradient vector field, then it is conservative

## Connected Sets

A subset $X \subseteq \R^n$ is **connected** iff for any open subsets $U, V$ of $\R^n$ such that $U \cap V \cap X = \varnothing$,
one has $U \cap X = \phi$ or, $V \cap X = \varnothing$.

### Proposition

Let $D \subseteq \R^n$ be an _open_ set.

Then $D$ is connected iff $D$ is path connected ($D$ can be expressed as a piecewise smooth curve)

## Loop Property of Conservative Fields

Let $D \subseteq \R^n$ be a _connected_ open set, $\vec F : D \rightarrow \R^n$ be a continuous vector field on $D$.

Then $\vec F$ is conservative iff for any closed curve $C \in D$,
one has

$$\oint_c \vec F \cdot d \vec r = 0$$

## Criterion for Gradient Vector Field

Component Test for Conservative Fields

Let $D \subseteq \R^n$ be an open set,
$\vec F : D \rightarrow \R^n$ be a continuously differentiable vector field on $D$.

Write $\vec F = (F_1, F_2, ..., F_n)$ with each $F_j : D \rightarrow \R$ a scalar valued function on $D$.

If $\vec F$ is a gradient vector field,
then $\forall i, j \in \{1, ..., n\}$, one has

$$\frac{\partial F_i}{\partial x_j} = \frac{\partial F_j}{\partial x_i}$$ 

on $D$.

> will see that the converse holds whenever $D$ is _connected_ and _simply connected_.


