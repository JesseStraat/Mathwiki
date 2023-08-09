---
aliases:
 - Fiber Bundle
---
## Definition
Let $\mathcal{C}$ be any [[Category|category]]. A **bundle** over some [[Object|object]] $A$ is an object $E$ together with a [[Morphism|morphism]] $\pi\colon E\to A$. A **section** on a bundle is some map $s\colon A\to E$ such that $\pi\circ s = 1_A$.
Now assume that $\mathcal{C}$ has a terminal object $1$. A **fibre bundle** with fibre $F$ is then some bundle $\pi\colon E\to A$, such that for any morphism $x\colon 1\to A$,  we have a [[Limit#Pullback|pullback]]
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	F\arrow[d]\arrow[r]\arrow[dr, phantom, "\lrcorner" , very near start, color=black] & E\arrow[d,"\pi"]\\
	1\arrow[r,swap,"x"] & A
\end{tikzcd}
\end{document}
```