## Definition
Given [[Category|categories]] $\mathcal{C}, \mathcal{D}$ and [[Functor|functors]] $F,G\colon\mathcal{C}\to\mathcal{D}$, a **natural transformation** from $F$ to $G$, denoted $\mu\colon F\Rightarrow G$, is a family of [[Morphism|morphisms]] $(\mu_C\colon FC\to GC)_{C\in\mathrm{Ob}(\mathcal{C})}$ such that for all $f\colon C\to D$, the following diagram commutes:
```tikz
\usepackage{tikz-cd}
\begin{document}
\Large
\begin{tikzcd}
FC \arrow[r, "Ff"]\arrow[d, "\mu_C"] & FD \arrow[d, "\mu_D"]\\
GC \arrow[r, "Gf"] & GD
\end{tikzcd}
\end{document}
```
This diagram is called the *naturality square*.

A *natural isomorphism* is a natural transformation that is an [[Morphism#Isomorphisms|isomorphism]] in the [[Category#Functor category|functor category]]. A natural transformation $\mu\colon F\Rightarrow G$ is isomorphic if and only if $\mu_C$ is isomorphic for all $C$.
## Composition
There are two kinds of composition of natural transformations.
### Vertical composition
Given functors $F,G,H\colon\mathcal{C}\to\mathcal{D}$ and $\mu\colon F\Rightarrow G$ and $\nu\colon G\Rightarrow H$, we define $\nu\circ\mu\colon F\Rightarrow H$ as $(\nu\circ\mu)_C := \nu_C\circ \mu_C$. This is called *vertical composition*. To prove that this defines a natural transformation, consider the following commutative diagram:
```tikz
\usepackage{tikz-cd}
\begin{document}
\Large
\begin{tikzcd}
FC \arrow[r, "Ff"]\arrow[d, "\mu_C"]\arrow[bend right=60,swap,dd,"(\nu\circ\mu)_C"] & FD \arrow[d, "\mu_D"]\arrow[bend left=60,dd,"(\nu\circ\mu)_D"]\\
GC \arrow[r, "Gf"]\arrow[d, "\nu_C"] & GD \arrow[d, "\nu_D"]\\
HC \arrow[r, "Hf"] & HD
\end{tikzcd}
\end{document}
```
### Horizontal composition
Given functors and natural transformations
```tikz
\usepackage{tikz-cd}
\begin{document}
\Large
\begin{tikzcd}
\mathcal{C}
\arrow[r,bend left,"F"{name=F}]
\arrow[r,swap,bend right,"G"{name=G}]
\arrow[from=F.south-|G,to=G,Rightarrow,shorten=2pt,"\mu"]
& \mathcal{D}
\arrow[r,bend left,"H"{name=H}]
\arrow[r,swap,bend right,"K"{name=K}]
\arrow[from=H.south-|K,to=K,Rightarrow,shorten=2pt,"\nu"]
& \mathcal{E}
\end{tikzcd}
\end{document}
```
we define a natural transformation $\nu*\mu\colon H\circ F\Rightarrow K\circ G$ such that
```tikz
\usepackage{tikz-cd}
\begin{document}
\Large
\begin{tikzcd}
	HFC \arrow[r,"\nu_{FC}"]\arrow[d,swap,"H\mu_C"]\arrow[rd,dashrightarrow,"(\nu*\mu)_C"] & KFC\arrow[d,"K\mu_C"]\\
	HGC \arrow[r,swap,"\nu_{GC}"] & KGC
\end{tikzcd}
\end{document}
```
commutes. Commutativity follows from the fact that this is a naturality square for $\nu$ at $\mu_C$. To show that it is a natural transformation, take any $f\colon C\to D$, and notice that the following diagram commutes:
```tikz
\usepackage{tikz-cd}
\begin{document}
\Large
\begin{tikzcd}
KFC \arrow[dd,swap,bend right=60,"(\nu*\mu)_C"]\arrow[r, "KFf"]\arrow[d, "\nu_{FC}"] & KFD \arrow[d, "\nu_{FD}"]\arrow[dd,bend left=60,"(\nu*\mu)_D"]\\
LFC \arrow[d, "L\mu_C"]\arrow[r, "LFf"] & LFD\arrow[d, "L\mu_D"]\\
LGC \arrow[r, "LGf"] & LGD
\end{tikzcd}
\end{document}
```