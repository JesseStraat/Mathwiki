---
aliases:
  - Ab-enriched Category
---
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
A category is $\mathrm{Ab}$-enriched if and only if its hom-sets have the structure of an Abelian group and composition is bilinear. The unit of the hom-set is called the *zero morphism*, denoted by $0$. In particular, all hom-sets must contain a zero morphism and is therefore non-empty.
$\mathrm{Ab}$-enriched categories are sometimes called *ringoids*, although this term may be reserved for small $\mathrm{Ab}$-enriched categories.

**Proposition:** Let $\mathcal{C}$ be an $\mathrm{Ab}$-enriched category. Any object $A$ is a zero object (i.e., both [[Limit#Terminal object|terminal]] and initial) if and only if its identity morphism $1_A$ is the unit of the Abelian group $\mathcal{C}(A,A)$.
>[!proof]-
>Assuming that $A$ is a zero object, then $\mathcal{C}(A,A)$ may only have one object, and hence is the trivial group. Therefore, $1_A$ must be the unit.
>
>Now assume that $1_A$ is the unit element. Then, we know in particular that for any $f\colon A\to B$ we have $f = f\circ 1_A = 0$ in $\mathcal{C}(A,B)$ and so it is unique. This proves that $A$ is initial. Analogously, one shows that it is terminal, and hence, a zero object.

**Proposition:** Any initial or terminal object in an $\mathrm{Ab}$-enriched category $\mathcal{C}$ is a zero object.
>[!proof]-
>Let $A$ be initial in $\mathcal{C}$. Then there is exactly one morphism in $\mathcal{C}(A,A)$, which then implies that $1_A$ is the unit. Therefore, it is a zero object.
>The same claim for terminal objects follows by the duality principle, concluding the proof.

In any $\mathrm{Ab}$-enriched category, we will denote any zero object by $0$. Note that any morphism into a zero object is epi, and any morphism out of a zero object is mono.

**Proposition:** Let $A,B$ denote any two objects in an $\mathrm{Ab}$-enriched category with zero object $0$. Then the zero morphism between the two is given precisely by the unique map
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	A & 0 & B \arrow[two heads, from=1-1, to=1-2] \arrow[hook, from=1-2, to=1-3]
\end{tikzcd}
\end{document}
```
In other words, zero morphisms factor through $0$.
>[!proof]-
>Due to the unicity of the zero morphism, it is sufficient to show that the given map is a zero morphism. Due to the necessary bilinearity of composition, we find that any composition with a zero morphism must also be a zero morphism. Furthermore, since both morphisms in the proposed composition are unique, and hence the zero morphism, we find that their composition must then also be a zero morphism between $A$ and $B$. This concludes the proof.

**Proposition:** If we have any finite [[Limit#Binary product|product]], then the finite coproduct also exists and they are equal. Moreover, the dual holds by the duality principle. Since they coincide, we call them a *biproduct*.
>[!proof]-
>We already proved that this holds for the empty (co-)product, so we only have to show that this holds for the binary product.
>Let $A,B$ be objects. Due to the non-emptiness of hom-sets, we know that there must be a zero map $0\colon A\to B$, inducing a unique morphism $i_A\colon A\to A\times B$ such that $\pi_Ai_A = 1_A$ and $\pi_Bi_A = 0$ (and similarly an $i_B$). In fact, we will write $i_A = (1_A,0)$ and $i_B = (0,1_B)$, as we usually do. This gives us a coproduct cone.
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	A\arrow[rd,swap,"{(1_A,0)}"] && B\arrow[ld,"{(0,1_B)}"]\\
>	& A\times B &
>\end{tikzcd}
>\end{document}
>```
>As we will use later, notice that $1_{A\times B} = (1_A,0)\pi_A + (0,1_B)\pi_B$.
>Now, we only have to show universality. Assume that there is some object $C$ with maps $f_A\colon A\to C$ and $f_B\colon B\to C$. Then, in particular, $g := f_A\pi_A + f_B\pi_B\colon A\times B\to C$ and also $gi_A = f_A$ and $gi_B = f_B$.
>We only need to show that $g$ is unique. Indeed, assume that $h$ is a morphism with $hi_A = f_A$ and $hi_B = f_B$, then
>$$h = h\circ 1_{A\times B} = h((1_A,0)\pi_A + (0,1_B)\pi_B) = f_A\pi_A + f_B\pi_B = g.$$
>Hence, we find that $A\times B$ is also the coproduct of $A$ and $B$.
