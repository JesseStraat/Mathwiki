---
aliases:
 - Oriented Manifold
 - Orientable Manifold
 - Volume Form
---
## Definition
Let $(M,\mathscr{A})$ be some [[Differentiable Manifold|manifold]] with an atlas $\mathscr{O}$. We say that $\mathscr{O}$ is an **oriented atlas** if for any two charts $(U,\varphi)$, $(V,\psi)$, with $U\cap V$ non-empty, the diffeomorphism $\psi\circ\varphi^{-1}\colon \phi(U\cap V)\to \psi(U\cap V)$ is **orientation preserving**, i.e., its Jacobian determinant is everywhere strictly positive.
If $\mathcal{O}$ is not contained in any other oriented atlases, we say that it is an **orientation**. If an orientation is contained within the smooth structure of a manifold, we say that it is an **orientable manifold**.
A chart is **positively oriented** if it is contained in the orientation.

Let $M$ be some $m$-dimensional manifold. We call $m$-forms **volume forms**.

**Theorem:** There is a unique linear map $\int_M\colon \Omega_c^m(M)\to \mathbb{R}$, with $\Omega_c^m(M)$ the compactly supported $m$-forms on $M$, such that for positively oriented charts $\varphi\colon U\to \mathbb{R}^m$ and volume forms $\omega$ with $\mathrm{supp}(\omega)\subseteq U$, $$\int_M\omega = \int_{\varphi(U)}(\varphi^{-1})^*\omega\ \mathrm{d}x.$$
>[!proof] TO DO

## Propositions
**Theorem:** (Stokes' theorem) For $M$ a manifold with boundary, and $d\omega$ an exact volume form on $M$,
$$\int_{\partial M}\omega = \int_M\mathrm{d}\omega$$
>[!proof] TO DO