## Definition
Let $\mathcal{A}$ be a [[Monoidal Category|monoidal category]]. A $\mathcal{A}$-enriched category $\mathcal{C}$ is then
- A collection of objects $\mathrm{Ob}(\mathcal{C})$;
- For each $A,B\in\mathrm{Ob}(\mathcal{C})$ an [[Object|object]] $\mathcal{C}(A,B)$ of $\mathcal{A}$ called a *hom-object*;
- For each triple $(A,B,C)$ in $\mathrm{Ob}(\mathcal{C})$ a [[Morphism|morphism]] $\circ_{A,B,C}\colon \mathcal{C}(B,C)\otimes\mathcal{C}(A,B)\to\mathcal{C}(A,C)$ called *composition*;
- For each object $A$ a morphism $1_A\colon 1\to \mathcal{C}(A,A)$;
such that the following axioms hold:
1. Associativity of composition:
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	(\mathcal{C}(C,D)\otimes \mathcal{C}(B,C))\otimes \mathcal{C}(A,B) \arrow[d,swap,"\circ_{B,C,D}\otimes 1"] \arrow[rr,"a"] && \mathcal{C}(C,D)\otimes (\mathcal{C}(B,C)\otimes \mathcal{C}(A,B))\arrow[d,"1\otimes\circ_{A,B,C}"]\\
	\mathcal{C}(B,D)\otimes \mathcal{C}(A,B) \arrow[rd,swap,"\circ_{A,B,D}"] && \mathcal{C}(C,D)\otimes \mathcal{C}(A,C) \arrow[ld,"\circ_{A,C,D}"]\\
	& \mathcal{C}(A,D) &
\end{tikzcd}
\end{document}
```
2. Unitality of composition:
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	1\otimes \mathcal{C}(A,B) \arrow[rd,"\lambda"]\arrow[d,swap,"\eta_B\otimes 1"] && \mathcal{C}(A,B)\otimes 1 \arrow[ld,swap,"\rho"]\arrow[d,"1\otimes\eta_A"]\\
	\mathcal{C}(B,B)\otimes\mathcal{C}(A,B)\arrow[r,swap,"\circ_{A,B,B}"] & \mathcal{C}(A,B) & \mathcal{C}(A,B)\otimes \mathcal{C}(A,A) \arrow[l,"\circ_{A,A,B}"]
\end{tikzcd}
\end{document}
```

Note that if there exists an interpretation of objects of $\mathcal{A}$ as collections, morphisms as maps, $1$ has a single element and the tensor product produces quotients of the Cartesian product, then $\mathcal{A}$-enriched categories are in particular [[Category|categories]].
Conversely, a category is $\mathcal{A}$-enriched iff its hom-sets are objects of $\mathcal{A}$ and the composition operator is a morphism in $\mathcal{A}$, since the axioms hold trivially.
## Examples
### $\mathrm{Set}$-enriched category
Quite trivially, a $\mathrm{Set}$-enriched category is a [[Smallness#Category theory|locally small]] category.
### $\mathrm{Ab}$-enriched category
[[Monoidal Category#$ mathrm{Ab}$|Recall that Abelian groups form a monoidal category]]. Let us work explicitly through $\mathrm{Ab}$-enriched categories. In particular, notice that $\mathrm{Ab}$-enriched categories are categories, through the reasoning above.
A category is $\mathrm{Ab}$-enriched if and only if its hom-sets have the structure of an Abelian group and composition is bilinear.