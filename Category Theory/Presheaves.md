---
aliases:
 - Yoneda Lemma
---
## Definition
Given a [[Smallness#Category theory|small]] [[Category|category]] $\mathcal{C}$, the **category of presheaves** on $\mathcal{C}$ is the [[Category#Functor category|functor category]] $[\mathcal{C}^{op},\mathrm{Set}] = \mathrm{Set}^{\mathcal{C}^{op}}$. Common notation for the presheaf category is $\hat{\mathcal{C}}$ or $\mathrm{Psh}(\mathcal{C})$. Hence, a **presheaf** is a functor $\mathcal{C}^{op}\to \mathrm{Set}$.

Let $F$ be a presheaf. Notice that objects $C$ in $\mathcal{C}$ are associated to a set $FC$, while morphisms $f\colon C\to C'$ are associated to a function $Ff\colon FC'\to FC$: the direction of morphisms is flipped.

Meanwhile, morphisms of the presheaf category are natural transformations $\mu\colon F\Rightarrow G$, i.e., $(Gf)\circ \mu_C = \mu_{C'}\circ (Ff)$.

## The Yoneda embedding
The **Yoneda embeddding** is the functor $Y\colon \mathcal{C}\to \hat{\mathcal{C}}$ with:
- For $C$ an object in $\mathcal{C}$, define $YC: \mathcal{C}^{op}\to\mathrm{Set}$ with $(YC)D = \mathcal{C}(D,C)$;
- For $f\colon D\to D'$ in $\mathcal{C}^{op}$, define $(YC)f\colon (YC)D\to (YC)D' = -\circ f$;
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
