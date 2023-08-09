---
aliases:
 - Subobject Classifier
---
## Definition
Let $\mathcal{C}$ be some category with terminal object $1$. A **subobject classifier** is some object $\Omega$ together with a morphism $t\colon 1\to \Omega$, such that for any monomorphism $f\colon C\to D$ in $\mathcal{C}$, there is a unique morphism $\varphi_C\colon D\to \Omega$, such that we have a pullback
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	C \arrow[r]\arrow[d,swap,"f"]\arrow[dr, phantom, "\lrcorner" , very near start, color=black] & 1 \arrow[d,"t"]\\
	D \arrow[r,swap,"\varphi_C"] & \Omega
\end{tikzcd}
\end{document}
```
If a category $\mathcal{C}$ has finite limits, is Cartesian closed and has a subobject classifier, then it is called an **(elementary) topos**.
## Examples
### $\mathrm{Set}$ as a topos
We already know that $\mathrm{Set}$ is Cartesian closed and complete. However, it also has a subobject classifier, being $\Omega = \{\mathrm{True},\mathrm{False}\}$, and $t(*) = \mathrm{True}$. Indeed, given any injection $f\colon X\to Y$, we have $$\varphi_X(y) = \begin{cases} \mathrm{True}\quad&\text{if $y\in fX$,}\\ \mathrm{False}\quad&\text{otherwise.}\end{cases}$$
For this reason, $\Omega$ is sometimes called the **object of truth values**.