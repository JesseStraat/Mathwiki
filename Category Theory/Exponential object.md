## Definition
Given a [[Category|category]] $\mathcal{C}$ with [[Limit#Binary product|binary products]], and [[Object|objects]] $X,Y$, the **exponential object** is an object $X^Y$ in $\mathcal{C}$ equipped with an evaluation [[Morphism|morphism]] $ev\colon X^Y\times Y\to X$ that is universal, i.e., for every object $Z$ and morphism $f\colon Z\times Y\to X$, there exists a unique map $\hat{f}\colon Z\to X^Y$ such that the following diagram commutes:
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
    X^Y\times Y\arrow[r,"ev"] & X\\
    Z\times Y\arrow[u,"{(\hat{f},1_Y)}"]\arrow[ru,swap,"f"]
\end{tikzcd}
\end{document}
```
A category is **cartesian closed** if the exponential exists for all objects.
## Examples
### $\mathrm{Set}$
In $\mathrm{Set}$, the exponential object is given by $X^Y = \mathrm{Set}(Y,X)$ with $ev(f,y) = f(y)$. Indeed, for any $f\colon Z\times Y\to X$, we define $\hat{f}(z) = f(z,\cdot)$, such that $ev\circ (\hat{f},1_Y) = f$.
$\mathrm{Set}$ is cartesian closed.