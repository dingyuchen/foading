# Surface Integrals

## Surface Integral of (scalar-valued) Functions

### Parametrized Surface

A **parametrized surface** in $\R^n$ is a function 
$\vec r : R \rightarrow \R^n$ from a region $R \in \R^2$ to Euclidean n-space $\R^n$.

The parametrized surface given by $\vec r$ is "smooth" iff $\vec r$ is continuously differentiable (partial derivatives components exists and are continuous)

## Special case of $\R^3$

Let $S$ be a smooth surface in $\R^3$.

Let $G: S \rightarrow \R$ be a (scalar-valued) function on $S$.

The surface integral of $G$ over $S$ is $\int_S G \; d\sigma$ is defined as follows:

- Choose any **bijective smooth** parametrization $\vec r : R \rightarrow S$.

$$\int_S G \; d \sigma := \int_R G (\vec r(u, v)) \vert \vec r_u (u, v) \times \vec r_v (u, v) \vert \; d(u, v)$$

(if the RHS exists)

> This is well-defined, independent of choice of parameter $\vec r$

### Additivity

If a piecewise smooth surface $S$ is obtained by joining a finite number of smooth surfaces $S_1, S_2, ..., S_n$ along boundary curves which are themselves piecewise smooth curves,
then

$$\int_S f \; d \sigma = \int_{S_1} f \; d \sigma + ... + \int_{S_n} f \; d \sigma$$

## Surface Integral of a Vector Field

$$\int_S \vec F \cdot \vec n \; d \sigma := \int_R \vec F(\vec r (u, v)) \cdot \vec r_u (u, v) \times \vec r_v (u, v) \; d(u, v)$$

> Make use of triple product, which gives us a scalar valued function that we can easily integrate iteratively over region $R$.

- This depends on the chosen parameter $\vec r$ of $S$ but only up to orientation.

If $\vec \rho : \Omega \rightarrow S$ is another parameterization, then there exists some composed function $\Phi$ that is continuously differentiable and invertible.

If $J_\Phi = det(\Phi') : R \rightarrow \R$ always takes $>0$ values then $\vec r$ and $\vec p$ are said to be parametrizing $S$ in the **same orientation**.

### The Normal Vector

> Comparable to the case of curves $\int_C \vec F \cdot \vec T \; ds$

The normal vector $\vec n$ is a unit vector on the positive side of the surface defined by parameterization.
Setting $\vec n(p)$ as the normalized $\vec r_u(u, v) \times \vec r_v(u, v)$.

$$ \vec n (p) := \frac{\vec r_u (u, v) \times \vec r_v (u, v)}{\vert \vec r_u (u, v) \times \vec r_v (u, v) \vert}$$

### Flow and Flux

In terminology, flux of $\vec F$ is a surface integral

and flow of $\vec F$ over $C$ is a curve integral.

