## Definition
Given [[Category|categories]] $\mathcal{C}$ and $\mathcal{D}$, a **functor** $F\colon \mathcal{C}\to \mathcal{D}$ consists of
- An operation $F\colon \mathrm{Ob}(\mathcal{C}) \to \mathrm{Ob}(\mathcal{D})$;
- For each pair of [[Object|objects]] $X,Y$ in $\mathcal{C}$, a map $F\colon \mathcal{C}(X,Y) \to \mathcal{D}(FX, FY)$,
such that the following axioms hold:
1. Given objects $X,Y,Z$ in $\mathcal{C}$, and [[Morphism|morphisms]] $f\colon X\to Y$ and $g\colon Y\to Z$, we have $F(g\circ f) = Fg\circ Ff$;
2. For all objects $X$ in $\mathcal{C}$, we have $F(1_X) = 1_{FX}$.

Notice that property 1 does not necessarily imply property 2. Indeed, it is true that $Ff \circ F1_X = F(f\circ 1_X) = Ff$ for any $f$ with $\mathrm{dom}(f) = X$, but this gives no guarantee for all other morphisms in $\mathcal{D}$ without a preimage in $\mathcal{C}$.

Sometimes, functors are called **forgetful**. This means that, in some way, the functor "forgets" certain properties. An example of such a forgetful functor is the functor $F\colon \mathrm{Grp}\to \mathrm{Set}$, which maps a group to its constituent set, and maps homomorphisms to themselves. It "forgets" the group structure of its domain.
## Special functors
### Faithful and full functors
A functor $F\colon \mathcal{C}\to\mathcal{D}$ is **faithful** if for each $X,Y\in\mathcal{C}$, the hom-map $F\colon \mathcal{C}(X,Y)\to\mathcal{D}(FX,FY)$ is injective. It is **full** if the hom-map is surjective, and it is **fully faithful** if the hom-map is bijective.
### Equivalences
A functor $F\colon\mathcal{C}\to\mathcal{D}$ is an **equivalence** if there exists a $G\colon\mathcal{D}\to\mathcal{C}$ such that $F\circ G \cong 1_\mathcal{D}$ and $G\circ F\cong 1_\mathcal{C}$ (in the sense of natural isomorphy). We then say that $\mathcal{C}$ and $\mathcal{D}$ are **equivalent**, or $\mathcal{C}\simeq\mathcal{D}$.

**Proposition:** A functor $F\colon\mathcal{C}\to\mathcal{D}$ is an equivalence if and only if it is [[Functor#Faithful and full functors|fully faithful]] and essentially surjective (for all $D$ in $\mathcal{D}$, there exists a $C$ in $\mathcal{C}$ such that $FC \cong D$).
>[!proof]-
>Assume $F$ is an equivalence. Let $G$ be the functor such that $FG\cong 1_\mathcal{D}$ and $GF\cong 1_\mathcal{C}$. Then, for any $D\in\mathcal{D}$, we know that $FGD \cong D$ with $GD\in\mathcal{C}$, which proves essential surjectivity.
>Given $f,g\colon X\to Y$ in $\mathcal{C}$ with $Ff = Fg$, then, of course, $GFf = GFg$. If $\mu\colon 1_\mathcal{C}\Rightarrow GF$ is the natural isomorphism, we know that $f = \mu_Y^{-1} (GFf) \mu_X = \mu_Y^{-1} (GFg) \mu_X = g$. Hence, $F$ is faithful.
>Given any morphism $h\colon FX\to FY$ in $\mathcal{D}$, we have $f := \mu_Y^{-1}(Gh)\mu_X \colon X\to Y$. Now, the following diagram commutes:
>```tikz
>\usepackage{tikz-cd}
>\begin{document}
>\Large
>\begin{tikzcd}
>X \arrow[r,"f"]\arrow[d,"\mu_X"] & Y\arrow[d,"\mu_Y"]\\
>GFX \arrow[r,swap,"GFf"] & GFY
>\end{tikzcd}
>\end{document}
>```
>Hence, $Gh = GF\mu_Y^{-1}(Gh)\mu_X$, and due to faithfulness of $G$, we have $h = F\mu_Y^{-1}(Gh)\mu_X$. Therefore, $F$ is full, since $h$ has pre-image $\mu_Y^{-1}(Gh)\mu_X$.
>
>Now, we assume that $F$ is fully faithful and essentially surjective. Through essential surjectivity, we know that for all $D$ in $\mathcal{D}$ there is a $GD$ in $\mathcal{C}$ such that there is an isomorphism $\epsilon_D\colon FGD \to D$. Moreover, for all $D,D'$, we have the bijection $F_{D,D'}\colon \mathcal{C}(GD,GD')\to\mathcal{D}(FGD,FGD')$ through $f\mapsto Ff$.
>Similarly, we can construct a bijection $\alpha_{D,D'}\colon \mathcal{D}(FGD,FGD')\to \mathcal{D}(D,D')$ through $f\mapsto \epsilon_{D'}f\epsilon_D^{-1}$.
>We get a bijection $\alpha_{D,D'}F_{D,D'}\colon \mathcal{C}(GD,GD')\to \mathcal{D}(D,D')$. We then define for $f\colon D\to D'$ the morphism $Gf = (\alpha_{D,D'}F_{D,D'})^{-1}f\colon GD\to GD'$. In particular,
>$$G1_D = F_{D,D}^{-1}\alpha_{D,D}^{-1}1_D = F_{D,D}^{-1}1_{FGD} = 1_{GD},$$
>$$G(g\circ f) = F_{D,D''}^{-1}\alpha_{D,D''}^{-1}(g\circ f) = F_{D,D''}^{-1}(\alpha_{D',D''}^{-1}g\circ\alpha_{D,D'}^{-1}f) = Gg\circ Gf.$$
>Hence, $G$ is a functor.
>Now, we would like to show that $\epsilon\colon FG\Rightarrow 1_\mathcal{D}$ is a natural isomorphism. To this end, we only need to show that for any $f\colon D\to D'$, we have $FGf = \epsilon_{D'}^{-1}f\epsilon_D = \alpha_{D,D'}^{-1}f$. Indeed, $FGf = F_{D,D'}(\alpha_{D,D'}F_{D,D'})^{-1}f = \alpha_{D,D'}^{-1}f$, which confirms that this is a natural isomorphism.
>For every $C$ in $\mathcal{C}$, we know that there is a unique $\eta_C\colon GFC\to C$ such that $F\eta_C = \epsilon_{FC}$. Then, for any $f\colon C\to C'$, we have the commutative diagram
>```tikz
>\usepackage{tikz-cd}
>\begin{document}
>\Large
>\begin{tikzcd}
>FGFC \arrow[r,"FGFf"]\arrow[d,"F\eta_C"] & FGFC'\arrow[d,"F\eta_{C'}"]\\
>FC \arrow[r,swap,"Ff"] & FC'
>\end{tikzcd}
>\end{document}
>```
>i.e., $Ff\circ F\eta_C = F\eta_{C'}\circ FGFf$, and bijectivity implies that $f\circ\eta_C = \eta_{C'}\circ GFf$. Therefore, $\eta\colon GF\Rightarrow 1_\mathcal{C}$ is a natural transformation. Furthermore, fully faithful functions reflect isomorphy, so $\eta$ is a natural isomorphism.
>We conclude that $F$ is an equivalence.
## Examples
### Hom-functor
**Proposition:** Let $\mathcal{C}$ be [[Smallness#Category theory|locally small]]. Then the map $\mathrm{Hom}\colon \mathcal{C}^{op}\times \mathcal{C}\to \mathrm{Set}$ sending objects $(C,D)$ to $\mathcal{C}(C,D)$ and morphisms $(f,g)$ to $g\circ -\circ f$ is a functor.
>[!proof]-
>First, notice that $\mathrm{Hom}(1_C,1_D) = 1_D\circ -\circ 1_C = 1_{\mathcal{C}(C,D)}$. Moreover, $\mathrm{Hom}(f\circ f',g\circ g') = (g\circ g')\circ - \circ (f'\circ f) = \mathrm{Hom}(f,g)\circ\mathrm{Hom}(f',g')$. This proves that we have a functor.

We can also restrict the Hom-functor to either of its arguments by fixing an object $C$ and defining $\mathrm{Hom}(C,f) = f\circ -$, and $\mathrm{Hom}(f,C) = -\circ f$.
## Propositions
**Proposition:** Functors preserve isomorphisms: given $F\colon\mathcal{C}\to\mathcal{D}$ and $f\colon X\to Y$ isomorphic in $\mathcal{C}$, $Ff$ is isomorphic in $\mathcal{D}$.
>[!proof]-
>Choose $g\colon Y\to X$ such that $f\circ g = 1_Y$ and $g\circ f = 1_X$. Now, $Fg\circ Ff = F(g\circ f) = F1_X = 1_{FX}$. Similarly, $Ff\circ Fg = 1_{FY}$. Therefore, $Ff$ is an isomorphism.

**Proposition:** Faithful functors reflect epimorphisms and monomorphisms. Fully faithful functors reflect isomorphisms.
>[!proof]-
>Let $F\colon\mathcal{C}\to\mathcal{D}$ be faithful and $f\colon X\to Y$ in $\mathcal{C}$ such that $Ff$ is epimorphic. Assume we have $g,h\colon Y\to Z$ such that $g\circ f = h\circ f$. Then $Fg\circ Ff = Fh\circ Ff$, which implies $Fg = Fh$, and through injectivity, $g = h$. Hence, $f$ is epimorphic.
>A similar proof holds for monomorphisms.
>Now assume $F$ is fully faithful and $f$ is isomorphic. Then there exists a (unique) $g\colon Y\to X$ that is its inverse. Therefore, $F(f\circ g) = 1_{FY}$, which implies that $f\circ g = 1_Y$. Similarly, we show that $g\circ f = 1_X$, which proves that $f$ is an isomorphism.

**Proposition:** Given categories $\mathcal{C},\mathcal{D}$ and for each object $C$ in $\mathcal{C}$ a functor $G_C^\mathcal{C}\to\mathcal{E}$ and for each object $D$ in $\mathcal{D}$ a functor $H_D\colon\mathcal{C}\to\mathcal{E}$, assume that $G_C(D) = H_D(C) =: \tilde{F}(C,D)$ for all $C,D$, and that for any morphisms $f\colon C\to C'$ in $\mathcal{C}$ and $g\colon D\to D'$ in $\mathcal{D}$, the following diagram commutes,
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	\tilde{F}(C,D) \arrow[r,"H_C(g)"]\arrow[d,"G_C(f)"] & \tilde{F}(C,D') \arrow[d,"G_{D'}(f)"]\\
	\tilde{F}(C',D) \arrow[r,"H_{C'}(g)"] & \tilde{F}(C',D')
\end{tikzcd}
\end{document}
```
there is a unique functor $F\colon \mathcal{C}\times\mathcal{D}\to\mathcal{E}$ such that:
1. $F(C,D) = \tilde{F}(C,D)$;
2. $F(f,1_D) = G(f)$;
3. $F(1_C,f) = H(f)$.
>[!proof]-
>To finish defining the functor, we only need to define $F(f,g)$ for arbitrary morphisms $f\colon C\to C'$, $g\colon D\to D'$. We find that
>$$F(f,g) = F((1_{C'}, g) \circ (f, 1_D)) = H_{C'}(g) \circ G_D(f),$$
>diagrammatically,
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	F(C,D) \arrow[r,"G_D(f)"]\arrow[d,dashed,swap,"{F(f,g)}"] & F(C',D)\arrow[dl,"H_{C'}(g)"]\\
>	F(C',D') &
>\end{tikzcd}
>\end{document}
>```
>which, of course, uniquely defines $F$. Now we only need to check the functor axioms. By construction, it is trivial that $F(1_C,1_D) = 1_{F(C,D)}$. As for composition, given morphisms
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	C \arrow[r,"f"] & C'\arrow[r,"f'"] & C''\\
>	D \arrow[r,"g"] & D' \arrow[r,"g'"] & D''
>\end{tikzcd}
>\end{document}
>```
>we see that we have the following commutative diagram,
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	F(C,D) \arrow[dd,bend right=80,swap,dashed,"{F(f'\circ f,g'\circ g)}"]\arrow[r,"G_D(f)"]\arrow[d,dashed,swap,"{F(f,g)}"] & F(C',D) \arrow[r,"G_D(f')"]\arrow[dl,"H_{C'}(g)"] & F(C'',D) \arrow[dl,"H_{C''}(g)"]\\
>	F(C',D') \arrow[d,dashed,swap,"{F(f',g')}"]\arrow[r,swap,"G_{D'}(f')"] & F(C'', D') \arrow[dl, "H_{C''}(g')"] & \\
>	F(C'',D'') &&
>\end{tikzcd}
>\end{document}
>```
>which proves that $F$ is indeed a functor.

**Proposition:** The Hom-functor preserves limits in its second argument.
>[!proof]-
>Let $D\colon\mathcal{I}\to\mathcal{C}$ be any diagram with a limit $(C,\mu)$. Fix an $A$ in $\mathcal{C}$. Let now $(X,\nu)$ denote any cone of the diagram $\mathrm{Hom}(A,-)\circ D$ in $\mathrm{Set}$. Now, given $x\in X$, this tells us that we get a collection of morphisms $\nu_i(x)\colon A\to Di$. The universality property of the limit then gives us a unique $f(x)\colon A\to C$ such that
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	A \arrow[rr,dashed,"\exists ! f(x)"]\arrow[rd,swap,"\nu_i(x)"] && C \arrow[ld,"\mu_i"]\\
>	& Di &
>\end{tikzcd}
>\end{document}
>```
>This now induces the commutative diagram
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	X \arrow[rr,"f"]\arrow[rd,swap,"\nu_i"] && \mathcal{C}(A,C) \arrow[ld,"{\mathrm{Hom}(A,\mu_i) = \mu_i\circ -}"]\\
>	& \mathcal{C}(A,Di) &
>\end{tikzcd}
>\end{document}
>```
>In fact, the unicity of $f$ follows directly from the unicity of each $f(x)$. Hence, we have proven that $\mathcal{C}(A,C)$ is the limit of $\mathcal{C}(A,-)\circ D$.
