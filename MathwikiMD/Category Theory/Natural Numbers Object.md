## Definition
Given a [[Category|category]] $\mathcal{C}$ with a [[Object#Terminal object|terminal object]] $1$ , the **natural numbers object** in $\mathcal{C}$ is an [[Object|object]] $N$ with [[Morphism|morphisms]] $0\colon 1\to N$ and $s\colon N\to N$ (dubbed the *successor morphism*) such that for any object $X$ and morphisms $x\colon 1\to X$ and $f\colon X\to X$, there is a unique morphism $g\colon N\to X$ such that the following diagram commutes:
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
    & N\arrow[r,"s"]\arrow[dd,dashed,"\exists!g"] & N\arrow[dd,dashed,"\exists!g"]\\
    1\arrow[ur,"0"]\arrow[dr,swap,"x"]&&\\
    & X\arrow[r,swap,"f"] & X
\end{tikzcd}
\end{document}
```
## Examples
### $\mathrm{Set}$
In $\mathrm{Set}$, the the terminal object is the set $\{*\}$, and the natural numbers object is $\mathbb{N}$ with $0(*) = 0$ and $s(n) = n+1$. Indeed, for any set $X$, $x\in X$ (equivalent to a $x\colon 1\to X$) and $f\colon X\to X$, the commutative diagram gives $g(0) = x$ and $g(n+1) = g(s(n)) = f(g(n))$, which inductively defines $g$ uniquely.