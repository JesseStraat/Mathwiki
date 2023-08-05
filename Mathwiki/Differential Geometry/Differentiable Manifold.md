## Definition
An **$n$-dimensional $C^k$-differentiable manifold** is
- A [[Topological Manifold|topological manifold]] $(M, \mathscr{T})$, i.e., a [[Topological space|topological space]] that is locally Euclidean, [[Hausdorff]] and [[Second countable|second countable]];
- A collection of local *charts* $\mathscr{A} = \{(U, \varphi)\ |\ U\in \mathscr{T}, \varphi\colon U\to \mathbb{R}^n\text{ is injective and continuous}\}$,
such that
1. $\cup_{(U,\varphi)\in\mathscr{A}}U = M$;
2. Each pair $(U,\varphi), (V, \psi)$ is *$C^k$-compatible*, i.e., $\varphi\circ \psi^{-1}\colon \psi(U\cap V)\to \phi(U\cap V)$ is a $C^k$ function in $\mathbb{R}^n$ (we then say that $\mathscr{A}$ is an *atlas* of $M$);
3. $\mathscr{A}$ is *maximal*, which means that if $(U,\varphi)$, with $U\in\mathscr{T}$ and $\varphi\colon U\to\mathbb{R}^n$ injective and continuous, is $C^k$-compatible with all charts in $\mathscr{A}$, then $(U,\varphi)\in\mathscr{A}$.
We say that $\mathscr{A}$ is the *differentiable structure* of the manifold $M$ (the topology is neglected).
## Morphisms
A map between two $C^k$-differentiable manifolds $M$ and $N$ $f\colon M\to N$ is said to be $C^k$-differentiable if for any charts $(U,\varphi)$ of $M$ and $(V,\psi)$ of $N$, the map
$$\psi\circ f\circ\varphi^{-1}\colon \varphi(U\cap f^{-1}V) \to \psi(fU\cap V)$$
is $C^k$-differentiable in the Euclidean sense.
In the [[Category|category]] of $C^k$-differentiable manifolds, $C^k$-differentiable maps are their [[Morphism|morphisms]]. [[Morphism#Isomorphisms|Isomorphisms]] in this category are called *diffeomorphisms*.