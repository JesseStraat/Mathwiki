---
aliases:
  - Monoid
---

## Definition
A **monoidal category** consists of:
- A [[Category|category]] $\mathcal{C}$;
- A *tensor product*, being a [[Functor|functor]] $\otimes\colon \mathcal{C}\times\mathcal{C}\to\mathcal{C}$;
- A *unit [[Object|object]]* $1$ in $\mathcal{C}$;
- An *associator*, a [[Natural Transformation|natural isomorphism]] between the following functors $\mathcal{C}\times\mathcal{C}\times\mathcal{C}\to\mathcal{C}$:
$$a\colon (-\otimes-)\otimes- \Rightarrow -\otimes (-\otimes -);$$
- A *left unitor*, a natural isomorphism $\lambda\colon 1\otimes - \Rightarrow -$;
- A *right unitor*, a natural isomorphism $\rho\colon -\otimes 1\Rightarrow -$;
such that the following axioms hold:
1. The *triangle identity*, for all objects $A,B$, the following diagram commutes:
   ```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	(A\otimes 1)\otimes B \arrow[rr,"a_{A,1,B}"]\arrow[rd,swap,"\rho_A\otimes 1_B"] && A\otimes (1\otimes B) \arrow[ld,"1_A\otimes \lambda_B"]\\
	& A\otimes B &
\end{tikzcd}
\end{document}
```
2. The *pentagon identity*, for all objects $A,B,C,D$, the following diagram commutes:
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	& (A\otimes B)\otimes (C\otimes D) \arrow[ld,swap,"a_{A,B,C\otimes D}"] &\\
	A\otimes (B\otimes (C\otimes D)) & & ((A\otimes B)\otimes C)\otimes D \arrow[dd,"a_{A,B,C}\otimes 1_D"] \arrow[lu,swap,"a_{A\otimes B,C,D}"]\\
	&&\\
	A\otimes ((B\otimes C)\otimes D) \arrow[uu,"1_A\otimes a_{B,C,D}"] & & (A\otimes (B\otimes C))\otimes D \arrow[ll,"a_{A,B\otimes C,D}"]
\end{tikzcd}
\end{document}
```
## Examples
### Category closed under finite products
Any category closed under [[Limit#Binary product|finite products]] is monoidal. Indeed, the tensor product is then none other than the binary product $\times$, the unit object is the [[Limit#Terminal object|terminal object]] $1$ (i.e., the empty product), it is associative (so the associator is the identity) and $1\times X = X = X\times 1$, so the unitors are also simply the identity. The identities then hold trivially.
### $\mathrm{Ab}$
The category of Abelian groups is a monoidal category, under the tensor product $A\otimes B$ defined as the quotient of the free group on the (set-theoretic) product $A\times B$, $\mathbb{Z}[A\times B]$, by relations $(a,b)+(a',b) \sim (a+a',b)$ and $(a,b)+(a,b')\sim (a,b+b')$.
The unit object is the trivial group $0$, under which $A\otimes 0 = A = 0\otimes A$, which gives that the unitors are simply identities.
The tensor product inherits the associativity of the direct product, proving that the associator is the identity. The identities then hold trivially.
### $R\mathrm{Mod}$
Let $R$ be a [[Ring|ring]], and $R\mathrm{Mod}$ the category of modules over $R$ and take any two objects $M,N$. In particular, all modules are Abelian groups under addition, so we can take the Abelian tensor product $M\otimes N$. The tensor product over $R$ is then defined as the Abelian tensor product modulo the action of $R$ on either side of $A\otimes B$, i.e., $A\otimes_R B = A\otimes B/(a,rb)\sim (ar,b)$.
We inherit associativity and the unit object from Abelian tensor product, which proves that we have a monoidal category. The identities then hold trivially.
### The category of endofunctors
Let $\mathcal{C}$ be any category, and let $[\mathcal{C},\mathcal{C}]$ be its [[Category#Functor category|category of endofunctors]]. Now define our tensor product as composition. This is by definition associative, and the unit object is the identity functor. This once again gives associators and unitors that are identities, and the axioms follow trivially. Hence, this forms a monoidal category.
## Monoids
In a monoidal category $(\mathcal{C},\otimes,1,a,\lambda,\rho)$, we define a **monoid** as an object $M$ together with morphisms $\mu\colon M\otimes M\to M$ (*multiplication*) and $\eta\colon 1\to M$ (*unit*), such that the associative law
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	(M\otimes M)\otimes M \arrow[r,"a_{M,M,M}"]\arrow[dd,swap,"\mu\otimes 1_M"] & M\otimes (M\otimes M)\arrow[r,"1_M\otimes\mu"] & M\otimes M \arrow[dd,"\mu"]\\
	&&\\
	M\otimes M\arrow[rr,swap,"\mu"] && M
\end{tikzcd}
\end{document}
```
and the unit law
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	1\otimes M \arrow[r,"\eta\otimes 1_M"] \arrow[rd,swap,"\lambda"] & M\otimes M \arrow[d,"\mu"] & M\otimes 1 \arrow[l,swap,"1_M\otimes \eta"]\arrow[ld,"\rho"]\\
	& M &
\end{tikzcd}
\end{document}
```
hold.
### Examples
 - An (algebraic) monoid is a monoid in the monoidal category $\mathrm{Set}$ under the Cartesian product.
 - A ring is a monoid in the category of Abelian groups.
 - A [[Monad|monad]] is a monoid in the category of endofunctors.