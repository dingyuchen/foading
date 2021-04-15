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

#### Fact

The full set $z_i \otimes \zeta^j$ is a basis for $\mathcal{L}(V, V)$.

##### Proof

Let $T$ be any element of $\mathcal{L}(V, V)$ and think about $T(z_i)$. It's some vector in $V$, so for each $i$ we can express it as a linear combination, $T^j_i z_j$.

Now define $S = T^j_i z_j \otimes \zeta^i$. 
This is a linear combination of things in $\mathcal{L}(V, V)$ so it is an element of that vector space.

When $S$ acts on $z_k$ for any $k$

$$S z_k = T^j_i z_j \otimes \zeta^i (z_k) = T^j_i z_j I^i_k = T^j_k z_j$$

Which is exactly $T(z_k)$. 
Therefore by linearity, $T = S$.

> $dim(\mathcal{L}(V, V)) = dim(V)^2$

#### Extracting components

Let $\zeta^i$ be the dual basis of $z_j$. 
Then with $T(z_j) = T^k_j z_k$ we have

$$ \zeta^i(T(z_j)) = \zeta^i(T^k_j z_k) = T^k_j I^i_k = T^i_j$$

# The Matrix

An $n \times m$ **matrix**, where $m$ and $n$ are positive integers, 
is a list of $m$ vectors belonging to $\mathcal{F}^n$.

![](2021-03-20-15-07-10.png)

Convention
: **subscript** tell you which (column) vector you are talking about, while **superscripts** tell you which component of a given vector you are talking about

## Matrix Multiplication

$$M^i_jN^j_k = M^i_1 N^1_k + M^i_2 N^2_k + M^i_3 N^3_k + ... $$

This matches up with the normal definition of matrix multiplication 

### Algebras

A vector space with a multiplication that takes pairs of vectors back into the vector space is called an **algebra**.

Square matrices form an algebra.

### Linear Transformations as Matrices

If a linear transformation from $V$ to itself is expressed relative to some basis $z_i$ as $T^j_i z_j \otimes \zeta^i$, 
then the matrix $T^j_i$ is called the **matrix of $T$ relative to the basis $z_i$.**

### Duality Again

If $\hat T$ is the transpose transformation of $T$, then

$$\zeta^i (T(z_j)) = z_j(\hat T \zeta^i)$$

so the $(i, j)$ entry in the matrix of $T$ is the same as the $(j, i)$ entry in the matrix of $\hat T$ relative to the same basis.

# Linear Transformation into different Vector Spaces

Need to define tensor products of the form $x \otimes \alpha$, 
where $\alpha \in \hat V$ as before, but now $x \in W$.
if $v \in V$, then by definition

$$x \otimes \alpha(v) = \alpha (v) x$$

> $dim (\mathcal{L} (V, W)) = n \times m$

Any $T \in \mathcal{L}(V, W)$ can be expressed in the form $T^i_j x_i \otimes \zeta_j$, just as before, and the $T^i_j$ can be assembled into a matrix.
The only real difference is that this matrix is not a square.

## Summary

Given the bases for $V$ ($\hat V$) and $W$, you can map any linear transformation in $\mathcal{L}(V, W)$ to a matrix.

It is a mapping from $\mathcal{L}(V, W)$ to $M^{(m, n)}$, with $dim(V) = n$ and $dim(W) = m$ 
and it is a linear mapping.

# Multiplying Transformations Together

Let $U, V, W$ be vector spaces and let $S \in \mathcal{L}(U, V), T \in \mathcal{L}(V, W)$. 
The **composite mapping** $T \circ S$ is also a linear map from $U$ to $W$.

This means that for any $u \in U$, $TS(u) \equiv T(S(u))$. 
This products is associative and also respects the vector structure, that is $T(S_1 + S_2) = TS_1 + TS_2$

## Composite Tensors

Consider if $v, w \in V$, and $\alpha, \beta \in \hat V$, 
then 

$$v \otimes \alpha \; w \otimes \beta = \alpha (w) v \otimes \beta$$

## Matrix of a Product

Let $S \in \mathcal{L}(U, V), T \in \mathcal{L}(V, W)$, 
Then for any choice of bases,

$$ M(TS) = M(T)M(S)$$

The mapping $M$ is an algebra homomorphism.

Let $S \in \mathcal{L}(V, V), T \in \mathcal{L}(V, V)$.

So $S$ and $T$ can be expressed using square matrices $S = S^h_i z_h \otimes \zeta^i, T = T^j_k z_j \otimes \zeta^j$.
We now have

$$ST = S^h_i z_h \otimes \zeta^i T^j_k z_j \otimes \zeta^k = S^h_i T^j_k z_h \otimes \zeta^i z_j \otimes \zeta^k $$

by moving all the scalars to the left.

$z_h \otimes \zeta^j z_j \otimes \zeta^k = I^i_j z_h \otimes \zeta^k$ so 

$$ST = S^h_i T^i_k z_h \otimes \zeta^k$$

and the matrix on the right is exactly the product of $S^h_i$ and $T^i_k$ so we are done.

# Change of Basis

If $\zeta^j$ is the dual basis to $z_i$, and $\epsilon^j$ is the **dual** canonical basis of $\mathcal{F}^n$, then we have

$$\zeta^j = \epsilon^j \circ z^{-1}$$

To see that this is correct,

$$\zeta^j(z_i) = \epsilon^j \circ z^{-1} (z_i) = \epsilon^j(z^{-1}(z(e_i))) = \epsilon^j e_i = I^j_i$$

----------

The matrix of a linear map $T$ from $V$ to itself, relative to a basis $z$, is the same as the matrix of 

$$z^{-1} \circ T \circ z$$

relative to the canonical basis of $\mathcal{F}$.

