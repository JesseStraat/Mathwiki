---
aliases:
 - Fiber Bundle
 - Section
---
## Definition
Let $\mathcal{C}$ be any [[Category|category]] with a terminal object $1$. A **fibre bundle** with fibre $F$ is then some morphism $\pi\colon E\to A$, such that for any morphism $x\colon 1\to A$,  we have a [[Limit#Pullback|pullback]]
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
A **section** over a fibre bundle $\pi\colon E\to A$ is a morphism $s\colon A\to E$ such that $\pi\circ s = 1_A$.