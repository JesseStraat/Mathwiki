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

Let $\mathcal{C}$ be some category with terminal object $1$. A **subobject classifier** is some object $\Omega$ together with a morphism $t\colon 1\to \Omega$, such that for any monomorphism $f\colon C\to D$ in $\mathcal{C}$, there is a unique morphism $\varphi_C\colon D\to \Omega$, such that we have a pullback
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