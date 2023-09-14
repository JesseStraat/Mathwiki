---
aliases:
 - Subobject Classifier
---
## Definition
Let $\mathcal{C}$ be a [[Category|category]], and choose some [[Object|object]] $C$. The [[Morphism#Monomorphisms|monomorphisms]] with codomain $C$ are a [[Category#Pre-orders|pre-order]] in the sense that $(f\colon A\to C)\leq (g\colon B\to C)$ whenever the following diagram commutes
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	A \arrow[rd,swap,"f"]\arrow[rr,dashed,"\exists h"] && B\arrow[ld,"g"]\\
	& C & 
\end{tikzcd}
\end{document}
```
If we now impose the equivalence $f\sim g$ if $f\leq g$ and $g\leq f$, i.e., we have the following diagram:
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	A \arrow[rd,swap,"f"]\arrow[rr,dashed,bend right=10,swap,"\exists h"] && B\arrow[ld,"g"]\arrow[ll,dashed,bend right=10,swap,"\exists k"]\\
	& C & 
\end{tikzcd}
\end{document}
```
(which implies that $k,h$ are each other's inverses), then the pre-order of monomorphisms restricted to the equivalence classes under $\sim$ is called the **subobject category**, denoted $\mathrm{Sub}(C)$.

Let $\mathcal{C}$ be some category with [[Object#Terminal object|terminal object]] $1$. A **subobject classifier** is some object $\Omega$ together with a [[Morphism|morphism]] $t\colon 1\to \Omega$, such that for any monomorphism $f\colon C\to D$ in $\mathcal{C}$, there is a unique morphism $\varphi_C\colon D\to \Omega$, such that we have a [[Limit#Pullback|pullback]]
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	C \arrow[r]\arrow[d,swap,"f"]\arrow[dr, phantom, "\lrcorner" , very near start, color=black] & 1 \arrow[d,"t"]\\
	D \arrow[r,swap,dashed,"\exists !\varphi_C"] & \Omega
\end{tikzcd}
\end{document}
```
In other words, we have a subobject $[t]$ such that every subobject $[f]$ can be written as $\varphi_C^*[t]$ for a unique $\varphi_C$.
## Examples
### $\mathrm{Set}$
Let us think about what subobjects in $\mathrm{Set}$ are. An injection $f\colon A\to X$ can be thought of as a subset inclusion (albeit not unique). Indeed, a second injection $g\colon B\to X$ is known to represent the same subset of $X$ whenever $fA = gB$. In other words, there exists an isomorphism $h\colon A\to B$ such that $g\circ h = f$. But this is exactly the subobject equivalence! Hence, subobjects correspond exactly to subsets of a set.

$\mathrm{Set}$ also has a subobject classifier, being $\Omega = \{\mathrm{True},\mathrm{False}\}$, and $t(*) = \mathrm{True}$. Indeed, given any injection $f\colon X\to Y$, we have $$\varphi_X(y) = \begin{cases} \mathrm{True}\quad&\text{if $y\in fX$,}\\ \mathrm{False}\quad&\text{otherwise.}\end{cases}$$
For this reason, $\Omega$ is sometimes called the **object of truth values**.