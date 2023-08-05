## Definition
Let $D\colon \mathcal{I}\to\mathcal{C}$ be any [[Functor|functor]] (called a *diagram* of shape $\mathcal{I}$, known as the *index category*). A **cone** for $D$ is some [[Object|object]] $C$ in $\mathcal{C}$ (called the cone's *vertex*), together with a [[Natural Transformation|natural transformation]] $\mu\colon \Delta_C\Rightarrow F$, with $\Delta_C i = C$ for any $i$ in $\mathcal{I}$ and $\Delta_Cf = 1_C$ for any [[Morphism|morphism]] $f$. In other words, the following diagram commutes for any $\alpha\colon i\to i'$:
```tikz
\usepackage{tikz-cd}
\begin{document}
\Large
\begin{tikzcd}
 & C \arrow[dl,swap,"\mu_i"]\arrow[dr,"\mu_{i'}"] & \\
 Di\arrow[rr,"D\alpha"] & & Di'
\end{tikzcd}
\end{document}
```
We construct morphisms $f\colon (C,\mu)\to (C',\mu')$ between cones as morphisms $f\colon C\to C'$ such that for all $i$ in $\mathcal{I}$, we have that the following diagram commutes:
```tikz
\usepackage{tikz-cd}
\begin{document}
\Large
\begin{tikzcd}
 C \arrow[rr,"f"]\arrow[dr,swap,"\mu_i"] & & C' \arrow[dl,"\mu'_i"]\\
  & Di &
\end{tikzcd}
\end{document}
```
From the identity and composition of $\mathcal{C}$, we find that we get a [[Category|category]] of cones, called $\mathrm{Cone}(D)$.
A [[Object#Terminal objects|terminal object]] of the cone category is called a **limit** of $D$.

A limit is called a *finite limit* if the index category is finite, and it is called a *small limit* if the index category is [[Smallness#Category theory|small]].

The [[Category#The duality principle|dual concepts]] of a cone and a limit are called a **co-cone** and a **co-limit**, respectively.

If a category has all small limits, then it is called [[Category#Special categories|complete]].
## Inducing cones
Given categories $\mathcal{C},\mathcal{D}$, a functor $F\colon\mathcal{C}\to\mathcal{D}$, an index category $\mathcal{I}$ and a diagram $D\colon \mathcal{I}\to\mathcal{C}$, we induce a functor $\hat{F}\colon\mathrm{Cone}(D)\to\mathrm{Cone}(F\circ D)$ through
$$\hat{F}(X,\mu) = (FX,F\mu),\qquad \hat{F}f = Ff.$$
If $\hat{F}$ preserves terminal objects, we say that $F$ *preserves the limit of the diagram $D$*.
Note: a functor that preserves a terminal object may send it to any terminal object, so $F(X\times Y) \neq FX\times FY$ in general.
## Examples
### Terminal object
For $0$ the empty category, there is a unique functor $D\colon 0\to \mathcal{C}$. Then, $\mathrm{Cone}(D)$ is none other than $\mathcal{C}$. Hence, a cone of this functor is an object in $\mathcal{C}$, and a limit is a [[Object#Terminal objectterminal object]] in $\mathcal{C}$.

**Proposition:** Terminal objects are unique up to unique isomorphism.
>[!proof]-
>Let $X,Y$ be terminal objects. Then there are unique $f\colon X\to Y$ and $g\colon Y\to X$. Since $fg\colon Y\to Y$ and $gf\colon X\to X$, we find that they must both be identities. Hence, $f$ is an isomorphism. It is unique from the fact that $Y$ is a terminal object.
### Binary product
For $2 = \begin{CD}\bullet & \bullet\end{CD}$ the trivial $2$-object category, a diagram $D\colon 2\to\mathcal{C}$ is the same as a collection of two objects $A, B$ in $\mathcal{C}$. Cones are then objects $X$ together with morphisms $\pi_A\colon X\to A$ and $\pi_B\colon X\to B$, i.e.,
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\begin{document}
\Large
\begin{tikzcd}
    & X \arrow[rd,"\pi_B"] \arrow[ld,swap,"\pi_A"] &\\
    A & & B
\end{tikzcd}
\end{document}
```
The limit of this diagram is called a **binary product** of $A$ and $B$, denoted $A\times B$. The morphisms $\pi_A, \pi_B$ are called the *projection morphisms*.

In particular, given an object $C$ with morphisms $f\colon C\to A$ and $g\colon C\to B$, we find that there must be a unique $h\colon C\to X$ such that $\pi_A\circ h = f$ and $\pi_B\circ h = g$. We denote this map by $h = (f,g)$.
### Equaliser
For $\mathcal{I}$ the following category:
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\begin{document}
%\Large
\begin{tikzcd}\bullet \arrow[r,shift right]\arrow[r,shift left] & \bullet\end{tikzcd}
\end{document}
```
cones for a diagram $D\colon \mathcal{I}\to\mathcal{C}$ are characterised by commutative diagrams
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\begin{document}
\Large
\begin{tikzcd}
    & X \arrow[dl,swap,"\mu_A"]\arrow[dr,"\mu_B"] &\\
    A\arrow[rr,"f",shift left]\arrow[rr,"g",shift right,swap] & & B
\end{tikzcd}
\end{document}
```
the limit of which is called an **equaliser** of $f$ and $g$.

Usually, we do not explicitly write the map $\mu_B$, and instead we explicitly say that we have an equaliser cone.

### Pullback
For $\mathcal{I}$ the following category:
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\begin{document}
%\Large
\begin{tikzcd}
    &\bullet\arrow[d]\\
    \bullet\arrow[r]&\bullet
\end{tikzcd}
\end{document}
```
cones for a diagram $D\colon \mathcal{I}\to\mathcal{C}$ are characterised by commutative diagrams
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\begin{document}
\Large
\begin{tikzcd}
    X\arrow[r]\arrow[d] & A\arrow[d,"f"]\\
    B\arrow[r,swap,"g"] & C
\end{tikzcd}
\end{document}
```
the limit of which is called the **pullback** of $f$ and $g$. In the case of a pullback, we write
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
    X\arrow[r,"f^*g"]\arrow[d,swap,"g^*f"]\arrow[dr, phantom, "\lrcorner" , very near start, color=black] & A\arrow[d,"f"]\\
    B\arrow[r,swap,"g"] & C
\end{tikzcd}
\end{document}
```
The dual of a pullback is called a **pushout**.

**Lemma:** (*Pullback lemma*) Consider the following commutative diagrams:
>[!info]- Commutative Diagrams
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\begin{document}
>\Large
>\begin{tikzcd}
>    A \arrow[r,"f"]\arrow[d,swap,"g"] & C\arrow[d,"h"] & \arrow[d,phantom,"{(1)}"]\\
>    B \arrow[r,swap,"k"] & D & \hphantom{\bullet}
>\end{tikzcd}
>\end{document}
>```
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\begin{document}
>\Large
>\begin{tikzcd}
>    C \arrow[r,"\alpha"]\arrow[d,swap,"h"] & E\arrow[d,"\gamma"] & \arrow[d,phantom,"{(2)}"]\\
>    D \arrow[r,swap,"\beta"] & F & \hphantom{\bullet}
>\end{tikzcd}
>\end{document}
>```
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\begin{document}
>\Large
>\begin{tikzcd}
>    A \arrow[r,"\alpha\circ f"]\arrow[d,swap,"g"] & E\arrow[d,"\gamma"] & \arrow[d,phantom,"{(3)}"]\\
>    B \arrow[r,swap,"\beta\circ k"] & F & \hphantom{\bullet}
>\end{tikzcd}
>\end{document}
>```

If diagram (2) is a pullback, then (1) is a pullback if and only if (3) is a pullback.
>[!proof]-
>Assume that (1) is a pullback. Now assume that there is some $X$ with $m\colon X\to B$ and $n\colon X\to E$ such that $\beta\circ k\circ m = \gamma\circ n$. In particular, then, there is a unique map $\xi\colon X\to C$ such that $h\circ\xi = k\circ m$ and $\alpha\circ\xi = n$:
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	X \arrow[drr,bend left,"n"]\arrow[ddr,bend right,swap,"k\circ m"]\arrow[dr,dashed,"\exists !\xi"] &&\\
>    &C \arrow[dr, phantom, "\lrcorner" , very near start, color=black]\arrow[r,"\alpha"]\arrow[d,swap,"h"] & E\arrow[d,"\gamma"]\\
>    &D \arrow[r,swap,"\beta"] & F
>\end{tikzcd}
>\end{document}
>```
>There then also exists a unique $\chi\colon X\to A$ such that $f\circ\chi = \xi$ and $g\circ\chi = m$:
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	X \arrow[drr,bend left,"\xi"]\arrow[ddr,bend right,swap,"m"]\arrow[dr,dashed,"\exists !\chi"] &&\\
>    &A \arrow[dr, phantom, "\lrcorner" , very near start, color=black]\arrow[r,"f"]\arrow[d,swap,"g"] & C\arrow[d,"h"]\\
>    &B \arrow[r,swap,"k"] & D
>\end{tikzcd}
>\end{document}
>```
>Hence, the following diagram commutes
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	X \arrow[drr,bend left,"n"]\arrow[ddr,bend right,swap,"m"]\arrow[dr,dashed,"\exists\chi"] &&\\
>    &A \arrow[r,"\alpha\circ f"]\arrow[d,swap,"g"] & E\arrow[d,"\gamma"]\\
>    &B \arrow[r,swap,"\beta\circ k"] & F
>\end{tikzcd}
>\end{document}
>```
>The unicity of $\chi$ follows from the unicity of $\xi$ and the unicity of $\chi$ in its original pullback diagram. We conclude that (3) is a pullback.
>
>Assume that (3) is a pullback. Now assume that there is some $X$ with $m\colon X\to B$ and $n\colon X\to C$ such that $k\circ m = h\circ n$. In particular, then, there is a unique map $\xi\colon X\to A$ such that $\alpha\circ f\circ\xi = \alpha\circ n$ and $g\circ\xi = m$:
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	X \arrow[drr,bend left,"\alpha\circ n"]\arrow[ddr,bend right,swap,"m"]\arrow[dr,dashed,"\exists !\xi"] &&\\
>    &A \arrow[dr, phantom, "\lrcorner" , very near start, color=black]\arrow[r,"\alpha\circ f"]\arrow[d,swap,"g"] & E\arrow[d,"\gamma"]\\
>    &B \arrow[r,swap,"\beta\circ k"] & F
>\end{tikzcd}
>\end{document}
>```
>There then also exists a unique $\chi\colon X\to C$ such that $\alpha\circ f\circ\xi = \alpha\circ\chi$ and $h\circ f\circ\xi = h\circ \chi$:
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	X \arrow[drr,bend left,"\alpha\circ f\circ\xi"]\arrow[ddr,bend right,swap,"h\circ f\circ\xi"]\arrow[dr,dashed,"\exists !\chi"] &&\\
>    &C \arrow[dr, phantom, "\lrcorner" , very near start, color=black]\arrow[r,"\alpha"]\arrow[d,swap,"h"] & E\arrow[d,"\gamma"]\\
>    &D \arrow[r,swap,"\beta"] & F
>\end{tikzcd}
>\end{document}
>```
>But since this commutation relation holds for both $\chi = n$ and $\chi = f\circ\xi$, we conclude that $f\circ\xi = n$. Hence, the following diagram commutes
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	X \arrow[drr,bend left,"n"]\arrow[ddr,bend right,swap,"m"]\arrow[dr,dashed,"\exists\chi"] &&\\
>    &A \arrow[r,"f"]\arrow[d,swap,"g"] & C\arrow[d,"h"]\\
>    &B \arrow[r,swap,"k"] & D
>\end{tikzcd}
>\end{document}
>```
>The unicity of $\chi$ follows from the unicity of $\xi$ and the unicity of $\chi$ in its original pullback diagram. We conclude that (1) is a pullback.
## Propositions
**Proposition:** If a category $\mathcal{C}$ has binary products and equalisers, then it has pullbacks.
>[!proof]-
>Given morphisms $f\colon A\to B$ and $g\colon C\to B$, we take the binary product
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\begin{document}
>\Large
>\begin{tikzcd}
>    & A\times C \arrow[dl,"\pi_A",swap]\arrow[dr,"\pi_B"] &\\
>    A & & C
>\end{tikzcd}
>\end{document}
>```
>Now, we take the equaliser
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\begin{document}
>\Large
>\begin{tikzcd}
>    D \arrow[r,"h"] & A\times C \arrow[r,shift left,"f\circ\pi_A"]\arrow[r,shift right,swap,"g\circ\pi_C"] & B
>\end{tikzcd}
>\end{document}
>```
>In particular, we find the commutative diagram
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\begin{document}
>\Large
>\begin{tikzcd}
>    D \arrow[r,"\pi_C\circ h"]\arrow[d,"\pi_A\circ h",swap] & C \arrow[d,"g"]\\
>    A \arrow[r,swap,"f"] & B
>\end{tikzcd}
>\end{document}
>```
>Hence, there exist cones for the pullback diagram. Assume now that there exists another such cone
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\begin{document}
>\Large
>\begin{tikzcd}
>    E \arrow[r,"\beta"]\arrow[d,"\alpha",swap] & C \arrow[d,"g"]\\
>    A \arrow[r,swap,"f"] & B
>\end{tikzcd}
>\end{document}
>```
>then we induce the morphism $(\alpha,\beta)\colon E\to A\times C$ such that we have an equaliser cone
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\begin{document}
>\Large
>\begin{tikzcd}
>    E \arrow[r,"{(\alpha,\beta)}"] & A\times C \arrow[r,shift left,"f\circ\pi_A"]\arrow[r,shift right,swap,"g\circ\pi_C"] & B
>\end{tikzcd}
>\end{document}
>```
>and hence, there exists a unique $k\colon E\to D$ such that $h\circ k = (\alpha,\beta)$. In particular, this means that $k$ is a morphism in the category of pullback cones.
>To finalise this proof, we need to show that $k$ is unique in the context of the category of pullback cones. Indeed, assume that there exists a $k'\colon E\to D$ such that $\pi_A\circ h\circ k' = \alpha$ and $\pi_C\circ h\circ k' = \beta$, and therefore $h\circ k' = (\alpha,\beta)$. However, the equaliser then guarantees that $k = k'$. Therefore, we have generated a pullback for $f$ and $g$.

**Proposition:** If a category $\mathcal{C}$ has a [[Object#Terminal objects|terminal object]] $1$ and pullbacks, then it has binary products and equalisers.
>[!proof]-
>Given any two objects $A,B$ in $\mathcal{C}$, we construct the following pullback diagram:
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>    A\times B \arrow[r]\arrow[d] \arrow[dr, phantom, "\lrcorner" , very near start, color=black] & B\arrow[d]\\
>    A\arrow[r] & 1
>\end{tikzcd}
>\end{document}
>```
>This is, in particular, the binary product.
>Now, for morphisms $f,g\colon A\to B$, we take the pullback square
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>    E \arrow[r]\arrow[d,"h"] \arrow[dr, phantom, "\lrcorner" , very near start, color=black] & B\arrow[d,"{(1_B,1_B)}"]\\
>    A\arrow[r,swap,"{(f,g)}"] & B\times_1 B
>\end{tikzcd}
>\end{document}
>```
>where $E$ together with $h$ forms the equaliser of $f$ and $g$.

**Theorem:** If a category has all small products and equalisers, then it is complete.
>[!proof]-
>Suppose $\mathcal{C}$ has all small products and equalisers, and presume we have some small category $\mathcal{I}$ and a diagram $D\colon\mathcal{I}\to\mathcal{C}$. Now, consider the following equaliser diagram:
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>    E\arrow[r,"\mu"] & \prod_{i\in \mathrm{Ob}(\mathcal{I})} Di \arrow[r,"f",shift left]\arrow[r,swap,"g",shift right] & \prod_{\alpha\in\mathrm{Mor}(\mathcal{I})}\mathrm{cod}(\alpha)
>\end{tikzcd}
>\end{document}
>```
>where $f = (\pi_{\mathrm{cod}(\alpha)})_{\alpha\in\mathrm{Mor}(\mathcal{I})}$ and $g = (D\alpha\circ \pi_{\mathrm{dom}(\alpha)})_{\alpha\in\mathrm{Mor}(\mathcal{I})}$, for $\pi_{j}\colon \prod_{i\in \mathrm{Ob}(\mathcal{I})} Di\to Dj$ the projection map.
>We see that $f\circ \mu = g\circ \mu$ is equivalent to $\pi_{\mathrm{cod}(\alpha)}\circ \mu = D\alpha\circ \pi_{\mathrm{dom}(\alpha)}\circ\mu$ for all morphisms $\alpha$, which tells us that equaliser diagrams are equivalent to cones of $D$ with projection maps $\mu_i = \pi_{i}\circ\mu$.
>Hence, if $(E,\mu)$ is the equaliser of the diagram, we find that it is also the limit of $D$. Due to the existence of all equalisers, we therefore find that all small limits exist, and hence, $\mathcal{C}$ is complete.