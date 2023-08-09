---
aliases:
 - Yoneda Lemma
---
## Definition
Given a [[Smallness#Category theory|locally small]] [[Category|category]] $\mathcal{C}$, the **category of presheaves** on $\mathcal{C}$ is the [[Category#Functor category|functor category]] $[\mathcal{C}^{op},\mathrm{Set}] = \mathrm{Set}^{\mathcal{C}^{op}}$. Common notation for the presheaf category is $\hat{\mathcal{C}}$ or $\mathrm{Psh}(\mathcal{C})$. Hence, a **presheaf** is a functor $\mathcal{C}^{op}\to \mathrm{Set}$.

Let $F$ be a presheaf. Notice that objects $C$ in $\mathcal{C}$ are associated to a set $FC$, while morphisms $f\colon C\to C'$ are associated to a function $Ff\colon FC'\to FC$: the direction of morphisms is flipped.

Meanwhile, morphisms of the presheaf category are natural transformations $\mu\colon F\Rightarrow G$, i.e., $(Gf)\circ \mu_C = \mu_{C'}\circ (Ff)$.

## The Yoneda embedding
The **Yoneda embeddding** is the functor $Y\colon \mathcal{C}\to \hat{\mathcal{C}}$ with:
- For $C$ an object in $\mathcal{C}$, define $YC: \mathcal{C}^{op}\to\mathrm{Set}$ with $(YC)D = \mathcal{C}(D,C)$;
- For $f\colon D'\to D$ in $\mathcal{C}$, define $(YC)f\colon (YC)D\to (YC)D' = -\circ f$;
- For $g\colon C\to C'$ in $\mathcal{C}$, define $Yg\colon YC\Rightarrow YC'$ with $(Yg)_D = g\circ -$.

**Proposition:** The Yoneda embedding is well-defined and is a functor.
>[!proof]-
>To check well-definedness, we should check that $Yg$ is indeed a natural transformation. For any $f\colon D\to D'$ in $\mathcal{C}^{op}$ and $g\colon C\to C'$ in $\mathcal{C}$, we discover the following commutative diagram:
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	(YC)D \arrow[r,"(YC)f"]\arrow[d,swap,"(Yg)_D"]\arrow[rd,dashed,"g\circ -\circ f"] & (YC)D'\arrow[d,"(Yg)_D"]\\
>	(YC')D \arrow[r,swap,"(YC')f"] & (YC')D'
>\end{tikzcd}
>\end{document}
>```
>We recover the naturality square, and hence, $Yg$ is indeed a natural transformation.
>Now, we must show that $YC$ is a functor. Clearly, $(YC)(1_D) = 1_{(YC)D}$. Furthermore, $(YC)(g\circ f) = -\circ (f\circ g) = (-\circ f)\circ g = (YC)(g)\circ(YC)(f)$. We conclude that $YC$ is indeed a functor. Hence, $Y$ is well-defined.
>Now, to show that $Y$ is itself a functor, notice that, trivially, $Y(1_C) = 1_{YC}$. To conclude, $(Y(g\circ f))_D = (g\circ f)\circ- = (Yg)_D\circ(Yf)_D$. Hence, $Y$ is indeed a functor.
## The Yoneda Lemma
**Theorem:** Let $\mathcal{C}$ be locally small. For every presheaf $F$ and object $C$, we have a bijection $\eta_{C,F}\colon \hat{\mathcal{C}}(YC,F) \to FC$ defined by $\eta_{C,F}(\mu) = \mu_C1_C$ .
>[!proof]-
>Given any $\mu\in\hat{\mathcal{C}}(YC, F)$, we have the naturality square for all $f\colon D\to C$
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	(YC)C \arrow[r,"(YC)f"] \arrow[d,swap,"\mu_C"] & (YC)D \arrow[d,"\mu_C"]\\
>	FC \arrow[r,swap,"Ff"] & FD
>\end{tikzcd}
>\end{document}
>```
>Hence, we have $Ff(\eta_{C,F}(\mu)) = Ff\circ \mu_C (1_C) = \mu_D\circ (YC)f(1_C) = \mu_D(f)$. Therefore, every element $x\in FC$ has a unique natural transformation $\mu_x$ such that $\eta_{C,F}(\mu_x) = x$, defined by $(\mu_x)_Df = Ff(x)$. This proves bijectivity.
## Propositions
**Proposition:** The Yoneda embedding preserves limits.
>[!proof]-
>Given a diagram $D\colon \mathcal{I}\to\mathcal{C}$, assume that it has a limit $(X,\mu)$. Now, we also know that $\hat{\mathcal{C}}$ is complete, so we also know that it must have a limit of the diagram $Y\circ D$, defined object-wise by the limit of $Y\circ D(-)C = \mathcal{C}(C, D(-))$ in $\mathrm{Set}$. We know that the [[Functor#Hom-functor|Hom-functor]] [[Functor#Propositions|preserves limits]], so we know that this limit must be $\mathcal{C}(C,X)$. This therefore proves that the limit of $Y\circ D$ is $\mathcal{C}(-,X) = YX$.
