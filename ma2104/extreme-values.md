# Extreme Values

Basic Facts

Let $R \subseteq \R^n$ be a region in Euclidean space

Let $f: R \rightarrow \R$ be a function

If $R$ is compact (close & bounded) and $f$ is continuous
then there exists $p \in \R$ such that 
$f(p)$ is the global maximum value of $f$ over $R$.

## Local Maximum

Let $f(x, y)$ be defined on a region $R$ containing the point $(a, b)$.
Then

1. $f(a, b)$ is a **local maximum** value of $f$ if $f(a, b) \geq f(x, y)$ for all domain points $(x, y)$ in an open disk centered at $(a, b)$.
2. $f(a, b)$ is a **local minimum** value of $f$ if $f(a, b) \leq f(x, y)$ for all domain points $(x, y)$ in an open disk centered at $(a, b)$.


$p \in R$ is a **local maximum point** for $f$ iff

$\exists \epsilon \in \R_{> 0}$ s.t. $\forall q \in R$ with $\vert q - p \vert < \epsilon$, one has $f(q) \leq f(p)$.

When this is so, $f(p) \in \R$ is a **local maximum value** of $f$.

## First Derivative Test for Local Extreme Values

Suppose $f: R \rightarrow \R$ is differentiable and $p \in R$ is an interior point of $R$ which is local max/min point of $f$.
Then

$$(\nabla f)(\vec p) = \vec 0$$

## Critical Point

A **critical point** of $f: R \rightarrow \R$ is an interior point $p \in R$ of $R$ such that 

$$(\nabla f)(\vec p) = \vec 0$$

when this is so, $f(p) \in \R$ is a **critical value** of $f$

Thus, by the first derivative test, all local max/min points of $f$ which are interior points of $R$ must be among the critical points of $f$.

## Absolute Maxima and Minima on Closed Bounded Regions

We organize the search for the absolute extrema of a continuous function $f(x, y)$ on a closed bounded region $R$ into 3 steps

1. List the _interior points_ of $R$ where $f$ may have local maxima and minima and evaluate $f$ at these points. These are the critical points of $f$.
2. List the _boundary points_ of $R$ where $f$ has local maxima and minima and evaluate $f$ at these points.
3. Look through the lists for the maximum and minimum values of $f$. These will be the absolute maximum and minimum values of $f$ on $R$.

## Saddle Point

$p \in R$ is a **saddle point** for $f$ iff
$p$ is a critical point for $f$ but $p$ is not a local maximum and local minimum for $f$.

## Second Derivative Test for Local Extreme Values

Suppose that $f(x, y)$ and its first and second derivatives are continuous throughout a disk centered at $(a, b)$ and that $f_x(a, b) = f_y(a, b) = 0$. 
Then

1. $f$ has a **local maximum** at $(a, b)$ if $f_{xx} < 0$ and $f_{xx}f_{yy} - f_{xy}^2 > 0$ at $(a, b)$.
2. $f$ has a **local minimum** at $(a, b)$ if $f_{xx} > 0$ and $f_{xx}f_{yy} - f_{xy}^2 > 0$ at $(a, b)$.
3. $f$ has a **saddle point** at $(a, b)$ if $f_{xx}f_{yy} - f_{xy}^2 < 0$ at $(a, b)$.
4. **test is inconclusive** at $(a, b)$ if $f_{xx}f_{yy} - f_{xy}^2 = 0$ at $(a, b)$. In this case, we must find some other way to determine the behavior of $f$ at $(a, b)$.

### Hessian

Determinant of square matrix of partial derivatives.


