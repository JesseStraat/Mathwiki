Given two [[Differentiable Manifold|smooth manifolds]] $M, N$, a [[Continuous Function|continuous function]] $f\colon M\to N$ is called **smooth** if for all charts $\phi\colon U\to\mathbb{R}^m$ of $M$ and $\psi\colon V\to\mathbb{R}^n$ of $N$, the function $$f^\psi_\phi := \psi\circ f\circ \phi^{-1}\colon \phi(U\cap f^{-1}V)\to \psi(fU\cap V)$$is smooth in the Euclidean sense.

In the [[Category|category]] of smooth manifolds $\mathrm{Diff}$, smooth functions are the morphisms.
## Differential
Let $M,N$ be manifolds, and $f\colon M\to N$ smooth. Then, the **differential** of $f$ at some point $p$ is the linear mapping $(\mathrm{d}f)_p\colon T_pM\to T_{f(p)}N$ between [[Tangent Space|tangent spaces]] such that for any $X_p\in T_pM$ and $g\in \mathcal{C}_N(f(p))$,
$$((\mathrm{d}f)_pX_p)g = X_p(g\circ f).$$
If $N=\mathbb{R}$, $\mathrm{d}f$ is a [[Tangent Space#1-forms|1-form]]. A $1$-form that can be written as a differential is called an **exact differential**, while a $1$-form that cannot is called an **inexact differential**.
## Special smooth functions
### Diffeomorphisms
**Diffeomorphisms** are bijective smooth functions, i.e., bijections in $\mathrm{Diff}$.
### Immersions
A smooth function $f\colon M\to N$ is an **immersion** at some point $p\in M$ if its differential $(\mathrm{d}f)_p$ is injective.
### Submersions
A smooth function $f\colon M\to N$ is an **immersion** at some point $p\in M$ if its differential $(\mathrm{d}f)_p$ is surjective.
### Embedding
A smooth function $f\colon M\to N$ is a **(smooth) embedding** if $f(M)$ is an [[Differentiable Manifold#Submanifolds|embedded submanifold]] of $N$ and $f\colon M\to f(M)$ is a diffeomorphism.
## Propositions
**Proposition:** (Embedding theorem) Let $f\colon M\to N$ be some smooth function between manifolds. If $q\in N$ is a regular value of $f$, the preimage of $q$, $f^{-1}\{q\}$, is an embedded submanifold of $M$ with dimension $\mathrm{dim}\ M - \mathrm{dim}\ N$.
Moreover, the tangent space of $f^{-1}\{q\}$ at a point $p$ is given by $T_p(f^{-1}\{q\}) = \mathrm{ker}(\mathrm{d}f)_p$.
https://en.wikipedia.org/wiki/Preimage_theorem