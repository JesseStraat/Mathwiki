---
aliases:
---
## Definition
A **(smooth) fibre bundle** is a [[Fibre Bundle|fibre bundle]] in the category of smooth [[Manifold|manifolds]] $\mathrm{Diff}$.
In other words, a smooth fibre bundle consists of smooth manifolds $E,M,F$ and a map $\pi\colon E\to M$ such that $\pi^{-1}\{x\}\cong F$ for all $x\in M$ (which also implies surjectivity).

If $F$ now has the structure of a [[Vector Space|vector space]] $V$, we say that the fibre bundle is a **(smooth) vector bundle** if for every point $p\in M$, there is a neighbourhood $U$ such that we have a fibrewise linear isomorphism $\varphi\colon \pi^{-1}U \to U\times V$ such that we have a commutative diagram
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	\pi^{-1}U\arrow[rr,"\varphi"]\arrow[rd,"\pi"] && U\times V\arrow[ld,"\pi_U"]\\
	& U &
\end{tikzcd}
\end{document}
```
## Tangent bundle
An important vector bundle is the **tangent bundle** of some manifold $M$, which is the bundle induced by the manifold's [[Tangent Space|tangent spaces]]. It is defined as the bundle $(TM,M,\mathbb{R}^m,\pi)$, with $m$ the dimension of $M$, $TM = \coprod_{p\in M} T_pM$ and $\pi\colon TM\to M$ through $\pi(X) = p$ whenever $X\in T_pM$. A section of this bundle is a [[Tangent Space#Vector Field|vector field]].