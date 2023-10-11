## Definition
Recall the definition of [[Additive Category|additive categories]].

A **pre-Abelian category** is an additive category such that every [[Morphism|morphism]] $f\colon A\to B$ has a *kernel* $\mathrm{ker}(f)$ and a *cokernel* $\mathrm{coker}(f)$, which means there are [[Limit#Pullback|pullbacks]]
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	{\mathrm{ker}(f)} & 0 \\ A & B \arrow["\mathrm{Ker}(f)"',hook,from=1-1, to=2-1] \arrow[two heads, from=1-1, to=1-2] \arrow[hook, from=1-2, to=2-2] \arrow["f"', from=2-1, to=2-2] \arrow["\lrcorner"{anchor=center, pos=0.125}, draw=none, from=1-1, to=2-2]
\end{tikzcd}
\end{document}
```
and pushouts
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	A & 0 \\ B & {\mathrm{coker}(f)} \arrow["f"', from=1-1, to=2-1] \arrow[two heads, from=1-1, to=1-2] \arrow[hook, from=1-2, to=2-2] \arrow["\mathrm{Coker}(f)"',two heads, from=2-1, to=2-2] \arrow["\ulcorner"{anchor=center, pos=0.125}, draw=none, from=1-1, to=2-2]
\end{tikzcd}
\end{document}
```
Equivalently, it is an $\mathrm{Ab}$-[[Enriched Category#$ mathrm{Ab}$-enriched category|enriched category]] with all finite [[Limit|limits]] and colimits.

From here, we define the *image* of a morphism as $\mathrm{im}(f) = \mathrm{ker}(\mathrm{Coker}(f))$, and similarly the *co-image* $\mathrm{coim}(f)$. This induces a diagram
```tikz
\usepackage{tikz-cd}
\usetikzlibrary{calc}
\usepackage{amsmath}
\usepackage{amssymb}
\tikzset{curve/.style={settings={#1},to path={(\tikztostart)
    .. controls ($(\tikztostart)!\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
    and ($(\tikztostart)!1-\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
    .. (\tikztotarget)\tikztonodes}},
    settings/.code={\tikzset{quiver/.cd,#1}
        \def\pv##1{\pgfkeysvalueof{/tikz/quiver/##1}}},
    quiver/.cd,pos/.initial=0.35,height/.initial=0}
\begin{document}
\Large
\begin{tikzcd}
	{\mathrm{im}(f)} \\ & A & B \\ & 0 & {\mathrm{coker}(f)} \arrow[two heads, from=2-2, to=3-2] \arrow["f", from=2-2, to=2-3] \arrow[two heads, from=2-3, to=3-3] \arrow[hook, from=3-2, to=3-3] \arrow["\ulcorner"{anchor=center, pos=0.125}, draw=none, from=2-2, to=3-3] \arrow[curve={height=-24pt}, hook, from=1-1, to=2-3] \arrow[curve={height=24pt}, two heads, from=1-1, to=3-2] \arrow["\lrcorner"{anchor=center, pos=0.125}, draw=none, from=1-1, to=3-3]
\end{tikzcd}
\end{document}
```

**Proposition:** Every morphism $f\colon A\to B$ in a pre-Abelian category has a (canonical) decomposition
```tikz
\usepackage{tikz-cd}
\usetikzlibrary{calc}
\usepackage{amsmath}
\usepackage{amssymb}
\tikzset{curve/.style={settings={#1},to path={(\tikztostart)
    .. controls ($(\tikztostart)!\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
    and ($(\tikztostart)!1-\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
    .. (\tikztotarget)\tikztonodes}},
    settings/.code={\tikzset{quiver/.cd,#1}
        \def\pv##1{\pgfkeysvalueof{/tikz/quiver/##1}}},
    quiver/.cd,pos/.initial=0.35,height/.initial=0}
\begin{document}
\Large
\begin{tikzcd}
	A && {\mathrm{coker}(\mathrm{Ker}(f))} && {\mathrm{ker}(\mathrm{Coker}(f))} && B \arrow["{\bar{f}}", from=1-3, to=1-5] \arrow["{\mathrm{Ker}(\mathrm{Coker}(f))}", hook, from=1-5, to=1-7] \arrow["{\mathrm{Coker}(\mathrm{Ker}(f))}", two heads, from=1-1, to=1-3] \arrow["f"', curve={height=50pt}, from=1-1, to=1-7]
\end{tikzcd}
\end{document}
```
>[!proof]-
>Let us start with the cokernel and the kernel, giving rise to the following diagram:
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	{\mathrm{ker}(f)} & 0 \\ A & B \\ 0 & {\mathrm{coker}(f)} \arrow[hook, from=3-1, to=3-2] \arrow[hook, from=1-2, to=2-2] \arrow["{\mathrm{Coker}(f)}", two heads, from=2-2, to=3-2] \arrow[two heads, from=2-1, to=3-1] \arrow["f", from=2-1, to=2-2] \arrow["\ulcorner"{anchor=center, pos=0.125}, draw=none, from=2-1, to=3-2] \arrow["{\mathrm{Ker}(f)}"', hook, from=1-1, to=2-1] \arrow[two heads, from=1-1, to=1-2] \arrow["\lrcorner"{anchor=center, pos=0.125}, draw=none, from=1-1, to=2-2]
>\end{tikzcd}
>\end{document}
>```
>Notice now that the induced map $\mathrm{ker}(f)\to\mathrm{coker}(f)$ factors through $0$, and is therefore a zero morphism. This gives the following commutative diagram:
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	& A & B \\ {\mathrm{ker}(f)} &&& {\mathrm{coker}(f)} \\ & 0 & 0 \arrow["{1_0}"', from=3-2, to=3-3] \arrow[hook, from=3-3, to=2-4] \arrow[two heads, from=2-1, to=3-2] \arrow["{\mathrm{Ker}(f)}", hook, from=2-1, to=1-2] \arrow["f", from=1-2, to=1-3] \arrow["{\mathrm{Coker}(f)}", two heads, from=1-3, to=2-4]
>\end{tikzcd}
>\end{document}
>```
>Furthermore, the first commutative diagram allows us to add morphisms
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	& A & B \\ {\mathrm{ker}(f)} &&& {\mathrm{coker}(f)} \\ & 0 & 0 \arrow["{1_0}"', from=3-2, to=3-3] \arrow[hook, from=3-3, to=2-4] \arrow[two heads, from=2-1, to=3-2] \arrow["{\mathrm{Ker}(f)}", hook, from=2-1, to=1-2] \arrow["f", from=1-2, to=1-3] \arrow["{\mathrm{Coker}(f)}", two heads, from=1-3, to=2-4] \arrow[hook, from=3-2, to=1-3] \arrow[two heads, from=1-2, to=3-3]
>\end{tikzcd}
>\end{document}
>```
>Now recall that we have a pullback
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	{\mathrm{ker}(\mathrm{Coker}(f))} & 0 \\ B & {\mathrm{coker}(f)} \arrow[two heads, from=1-1, to=1-2] \arrow[hook, from=1-2, to=2-2] \arrow["{\mathrm{Ker}(\mathrm{Coker}(f))}"', hook, from=1-1, to=2-1] \arrow["\lrcorner"{anchor=center, pos=0.125}, draw=none, from=1-1, to=2-2] \arrow["{\mathrm{Coker}(f)}"', two heads, from=2-1, to=2-2]
>\end{tikzcd}
>\end{document}
>```
>and the previous diagram shows that A is a cone of the corresponding diagram, and so
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	& A & B \\ {\mathrm{ker}(f)} && {\mathrm{ker}(\mathrm{Coker}(f))} & {\mathrm{coker}(f)} \\ & 0 & 0 \arrow["{1_0}"', from=3-2, to=3-3] \arrow[hook, from=3-3, to=2-4] \arrow[two heads, from=2-1, to=3-2] \arrow["{\mathrm{Ker}(f)}", hook, from=2-1, to=1-2] \arrow["f", from=1-2, to=1-3] \arrow["{\mathrm{Coker}(f)}", two heads, from=1-3, to=2-4] \arrow[two heads, from=2-3, to=3-3] \arrow[hook, from=2-3, to=1-3] \arrow["{\exists !g}"', dashed, from=1-2, to=2-3] \arrow[hook, from=3-2, to=2-3]
>\end{tikzcd}
>\end{document}
>```
>but then, the pushout
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	{\mathrm{ker}(f)} & 0 \\ A & {\mathrm{coker}(\mathrm{Ker}(f))} \arrow[two heads, from=1-1, to=1-2] \arrow["{\mathrm{Ker}(f)}"', hook, from=1-1, to=2-1] \arrow["\ulcorner"{anchor=center, pos=0.125}, draw=none, from=1-1, to=2-2] \arrow["{\mathrm{Coker}(\mathrm{Ker}(f))}"', two heads, from=2-1, to=2-2] \arrow[hook, from=1-2, to=2-2]
>\end{tikzcd}
>\end{document}
>```
>shows that
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\Large
>\begin{tikzcd}
>	& A & B \\ {\mathrm{ker}(f)} & {\mathrm{coker}(\mathrm{Ker}(f))} & {\mathrm{ker}(\mathrm{Coker}(f))} & {\mathrm{coker}(f)} \\ & 0 & 0 \arrow["{1_0}"', from=3-2, to=3-3] \arrow[hook, from=3-3, to=2-4] \arrow[two heads, from=2-1, to=3-2] \arrow["{\mathrm{Ker}(f)}", hook, from=2-1, to=1-2] \arrow["f", from=1-2, to=1-3] \arrow["{\mathrm{Coker}(f)}", two heads, from=1-3, to=2-4] \arrow[two heads, from=2-3, to=3-3] \arrow[hook, from=2-3, to=1-3] \arrow["g"', from=1-2, to=2-3] \arrow[two heads,from=1-2, to=2-2] \arrow[hook, from=3-2, to=2-2] \arrow["{\exists !\bar{f}}"', dashed, from=2-2, to=2-3]
>\end{tikzcd}
>\end{document}
>```
>Hence, in particular, we find
>```tikz
>\usepackage{tikz-cd}
>\usetikzlibrary{calc}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\tikzset{curve/.style={settings={#1},to path={(\tikztostart)
>    .. controls ($(\tikztostart)!\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
 >   and ($(\tikztostart)!1-\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
 >   .. (\tikztotarget)\tikztonodes}},
 >   settings/.code={\tikzset{quiver/.cd,#1}
 >       \def\pv##1{\pgfkeysvalueof{/tikz/quiver/##1}}},
 >   quiver/.cd,pos/.initial=0.35,height/.initial=0}
>\begin{document}
>\Large
>\begin{tikzcd}
>	& A & B \\ {\mathrm{ker}(f)} & {\mathrm{coker}(\mathrm{Ker}(f))} & {\mathrm{ker}(\mathrm{Coker}(f))} & {\mathrm{coker}(f)} \arrow["{\mathrm{Ker}(f)}", hook, from=2-1, to=1-2] \arrow["f", from=1-2, to=1-3] \arrow["{\mathrm{Coker}(f)}", two heads, from=1-3, to=2-4] \arrow[hook, from=2-3, to=1-3] \arrow[two heads, from=1-2, to=2-2] \arrow["{\bar{f}}"', from=2-2, to=2-3] \arrow["0"', curve={height=50pt}, from=2-1, to=2-4]
>\end{tikzcd}
>\end{document}
>```
>This gives the canonical decomposition.

A pre-Abelian category in which $\bar{f}$ is an [[Morphism#Isomorphisms|isomorphism]] for all morphisms $f$ is called an **Abelian category**.
## Examples
### $R\mathrm{Mod}$
We already saw in [[Additive Category|the article on additive category]] that $R\mathrm{Mod}$ is additive. Moreover, it is quite easy to derive that kernels of morphisms $f\colon A\to B$ are given by submodules $\mathrm{ker}(f) = \{x\in A\ |\ f(x)=0\}$ and cokernels are given by $\mathrm{coker}(f) = B/fA$. Then $\mathrm{Ker}(f)$ is simply the inclusion and $\mathrm{Coker}(f)$ the projection onto the quotient.

Now, to determine the canonical decomposition. Notice first that $\mathrm{ker}(\mathrm{Coker}(f)) = \{x\in B\ |\ x \in 0 + fA\}  = fA$, the image of $f$. Then $g$ is simply the morphism $f$ with codomain restricted to the image (i.e., such that it is surjective). Secondly, $\mathrm{coker}(\mathrm{Ker}(f)) = A/\mathrm{ker}(f)$, such that $\bar{f}$ becomes $g$ restricted to the quotient, i.e., it is injective. This gives us a bijective map, which proves that it is an isomorphism. This proves that $R\mathrm{Mod}$ is an Abelian category.
## Propositions
**Theorem:** (*Freyd-Mitchell embedding theorem*) Every small Abelian category admits a fully faithful exact functor to $R\mathrm{Mod}$ for some ring $R$.
This also allows us to do diagram chasing on any Abelian category.