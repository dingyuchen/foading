# Linear Mappings

Let $V$ and $W$ be vector spaces.

A mapping $T : V \rightarrow W$ is called a **linear** mapping if it _preserves the vector structure_.
That is,

- $T(u + v) = T(u) + T(v) \; \forall u, v \in V$
- $T(au + v) = aT(u) + T(v) \; \forall a \in \mathcal{F}, \forall u \in V$

The set of linear mappings from $V$ to $W$ is denoted $\mathcal{L}(V, W)$.

> Not every element of $\mathcal{L}$ is a basis, because not all of them are bijections.

## Everything is a Vector

The vector space $\mathcal{L}(V, \mathcal{F})$ is called the **dual** space to the space $V$, denoted as $\hat V$.
So if $\alpha \in \hat V$, then for any $u \in V$, $\alpha(u)$ is just a number.

This means that vectors are linear transformations.

Define $aT$ where $a$ is a scalar and $T$ is a linear maping from $V$ to $W$ as

$$ (aT)u \equiv a(Tu) \; \forall u \in V$$

and since

$$ (T_1 + T_2)(u) = T_1(u) + T_2(u) \; \forall u \in V$$

So the set of linear transformations from $V$ to $W$ is a vector space.

### Zero Vector of Transformations

The mapping that takes every element of a vector space to its zero vector is an element of $\mathcal{L}(V, V)$, which is the zero vector in the vector space $\mathcal{L}(V, V)$.

## Kernel

If $T \in \mathcal{L}(V, W)$, then the **kernel** of $T$, $\ker(T)$, is the set of elements in $V$ that are mapped to the zero vector in $W$.

- $\ker(T)$ is a subspace of $V$.

The dimension of $\ker(T)$ is traditionally called the **nullity** of $T$, $Null(T)$.

- $T$ is injective iff $\ker(T)$ consists of the zero vector only. ($Null(T) = 0$)

## Range

The **range** of $T$, $\text{Rang}(T)$, is defined as for any mapping: it is the set of vectors in $W$ which can be expressed as $Tv$ for some $v \in V$.

> $\text{Rang}(T)$ is as subspace of $W$.

The dimension of $\text{Rang}(T)$ is called the **rank** of T, $\text{Rank}(T)$

### Fundamental Theorem of Linear Transformations

$$dim(V) = Null(T) + Rank(T)$$

> For linear maps from $V$ to itself, bijectivity <=> injectivity <=> surjectivity

## Duality

Given any basis $z_i$ of a vector space $V$, we define dual vectors, denoted $\zeta^i$ as:

For any $v \in V$, write $v = a^iz_i$, where $a^i$ are the components of $v$ relative to this basis.

By definition, $\zeta^i(v) \equiv a^i$.

$I^i_j = 1$ if $i = j$.
> We see that $\zeta^i(z_j) = I^i_j$.

### Dual Vectors

Given a basis $z_i$ of a vector space $V$, the set of all $\zeta^i \in \hat V$ that satisfies $\zeta^i(z_j) = I^i_j$ is called the **dual basis** of $z_i$.

> All of the $\zeta^i$ are linear mappings.

Suppose $\alpha$ is any dual vector, and consider the dual vector $\beta \equiv (\alpha z_i) \zeta^i$,
that is, the components of this dual vector are just defined to be the numbers $\alpha z_i$.

Let this dual vector act on $z_j$, then

$$\beta (z_j) = \alpha (z_i) \zeta^i (z_j) = \alpha (z_i) I^i_j = \alpha (z_j)$$

By linearity, this means that $\alpha = \beta$ for all $v \in V$.
The set of dual vectors $\zeta^i$ is a basis for $\hat V$.

#### Dual Spaces

Given any finite dimensional vector space $V$, the dual space $\hat V$ is another vector space of the same dimension as $V$.
Every basis $z_i$ for $V$ defines a dual basis $\zeta^i$ for $\hat V$.

#### Finding $p$

Let $p_i \zeta^i$ act on the vectors $z_i$.
Note that

$$ p_i \zeta^i (z_j) = p_i I^i_j = p_j$$

So this is how you extract components of dual vectors.

### Symmetry

We normally think of $T$ as acting on $V$, mapping its elements back to $V$.
But since $\hat V$ is so closely tied to $V$, we expect that doing something to $V$ should result in something happening to $\hat V$.

### Transpose 

Let $\alpha \in \hat V$ and let $v \in V$.
Then for each linear transformation $T$, define $\hat T$, a mapping from $\hat V$ to itself, as follows:

$$\hat T(\alpha) (v) = \alpha (T v)$$

$\hat T$ is called the **transpose** of $T$.
In fact, $\hat T \in \mathcal{L}(\hat V, \hat V)$.

## Tensor Products

Let $V$ be a vector space, and let $\hat V$ be its dual.
For each $v \in V, \alpha \in \hat V$, define their **tensor product** $v \otimes \alpha$ to be the element of $\mathcal{L}(V, V)$ which acts on vectors $w \in V$ as follows

$$(v \otimes \alpha) (w) \equiv \alpha (w)v$$

> From definition, the tensor product is linear in both "slots".
> That is, it is linear on the left and right.

### Composites

Let $\beta$ be a dual vector. 
Then the composite map $\beta \circ (v \otimes \alpha)$ makes sense, and in fact it is a dual vector.
The mapping $\beta \rightarrow \beta \circ (v \otimes \alpha)$ is linear.

So in this way, $\alpha \otimes v$ generates a linear map from $\hat V$ to itself - in fact this is the transpose of $v \otimes \alpha$.

Let the composite map act on a vector $w$,

$$\beta \circ (v \otimes \alpha) (w) = \beta(\alpha(w)v) = \beta(v) \alpha (w)$$

which, since $w$ could be anything, means that

$$\beta \circ (v \otimes \alpha) = \beta(v) \alpha$$

### Building Linear Transformations

Let $z_i$ be a basis of $V$ and let $\zeta^j$ be the dual basis.

> For each pair of indices $(i, j)$, $z_i \otimes \zeta_j$ is a linear transformation from $V$ to itself

> The full set $z_i \otimes \zeta^j$ is a basis for $\mathcal{L}(V, V)$.
