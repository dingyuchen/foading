# Determinants

## Multilinear Form

A **multilinear form** of degree $m$ on an $n$-dimensional vector space $V$ is a mapping from $V \times V \times ... \times V$ ($m$ times) to $\mathcal{F}$ which is linear in every slot.

## Two Form

A bilinear form $\Psi$ on a real finite-dimensional vector space $V$ is called a **two form** if it is antisymmetric.

That is, for any pair of vectors $u, v$

$$\Psi(u, v) = - \Psi(v, u)$$

> The set of two-forms on $V$ is a vector space

## Wedge Product

The **wedge product** of 2 dual vectors is defined

$$\alpha \wedge \beta = \frac{1}{2} (\alpha \otimes \beta - \beta \otimes \alpha)$$

Note that $\alpha \wedge \beta = - \beta \wedge alpha$ and $\alpha \wedge \alpha = 0$.

### Expressing a Two form

Let $z$ be a basis for $V$ and let $\zeta$ be the dual basis.
Then the collection of all two-forms of the form $\zeta^i \wedge \zeta^j$ gives a basis for the space of two-forms on $V$.

That is, any two-forms can be expressed as $\Psi = \psi_{ij} \zeta^i \wedge \zeta^j$.

## Three-Form

A **three-form** is a trilinear form $\Psi$ that is anti-symmetric in all 3 slots

$$\Psi(u, v, w) = - \Psi(v, u, w) = -\Psi(u, w, v) = ...$$

## Dimensionality

In general, the space of $m$-forms on an $n$-dimensional vector space is a vector space of dimension $\binom{n}{m}$.

Therefore the dimension of $n$-forms on an $n$-dimensional vector space is one-dimensional.


