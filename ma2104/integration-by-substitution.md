# Integration by Substitution

## The Substitution Method

### Substitution Rule

If $u = g(x)$ is a differentiable function whose range is an interval $I$, and $f$ is continuous on $I$, then 

$$\int f(g(x)) \cdot g'(x) \; dx = \int f(u) \; du$$

### Substitution in Definite Integrals

If $g'$ is continuous on the interval $[a, b]$ and $f$ is continuous on the range of $g(x) = u$, then

$$\int^b_a f(g(x)) \cdot g'(x) \; dx = \int^{g(b)}_{g(a)} f(u) \; du$$

----------

Assume $g:[a, b] \rightarrow \R$ is continuously differentiable and injective and that $g([a, b]) = I$ is an interval in $\R^1$.

Let $f: I \rightarrow \R$ be continuous. Then 

$$\int^b_a (f \circ g) (x) \cdot g'(x) \; dx = \int^B_A f(u) \; du$$

## Jacobian

Let $U \subseteq \R^m$ be an open set.

Let $\Phi: Y \rightarrow \R^m$ be a differentiable function so we have the total derivative map $\Phi' : U \rightarrow \mathbb{M}_{m \times m}$

The **Jacobian of $\Phi$** is the function
$J_\Phi : U \rightarrow \R$ given by $J_\Phi(\vec x) := det(\Phi'(\vec x))$

ie. if $\vec x = (x_1, x_2, ..., x_m)$ and $\Phi(x) = (\Phi_1(\vec x), ...)^T$
then

$$J_\Phi(\vec x) = det \bigg [\frac{\partial \Phi_i}{\partial x_j}(\vec x) \bigg ]$$

## Change of Variable Theorem

Let $U \subseteq \R^m$ be an open set.

Let $\Phi : U \rightarrow \R^m$ be a function (change of variable map).

Suppose $\Phi$ is _continuously differentiable_ and _injective_ on $U$. 
Let $G \subseteq U$ be a compact rectangle in $U$.
and $R := \Phi(G)$ be its image.

Let $f: R \rightarrow \R$ be a _~~continuous~~ Riemann integrable_ function on $R$.
Then

$$\int_G (f \circ \Phi) (\vec x) \cdot \vert J_\Phi(\vec x) \vert \; d \vec x = \int_R f(\vec u) \; d\vec u $$

## Spherical Coordinates Map 

$$S: \R_{> 0} \times (0, \pi) \times (0, 2 \pi) \rightarrow \R^3 \setminus \{(x, 0, z) : x \geq 0 \} $$

$$( \rho, \phi, \theta ) \mapsto (\rho \sin \phi \cos \theta, \rho \sin \phi \sin \theta, \rho \cos \phi)$$

### Inverse Map given by

$$r = \sqrt{x^2 + y^2}$$

$$\theta = \tan^{-1}\frac{y}{x}$$

$$\rho = \sqrt{x^2 + y^2 + z^2}$$

$$\phi = \tan^{-1}\frac{r}{z}$$

### Change of Variable Formula

For any compact rectangle $G \subseteq (\rho, \phi, \theta)$-space
with spherical coordinate image $D = S(G) \subseteq (x, y, z)$-space

One has

$$\int_D f(x, y, z) \; d(x, y, z) = \int_G (f \circ S) (\rho, \phi, \theta) \cdot \rho^2 \sin \phi \; d(\rho, \phi, \theta)$$
