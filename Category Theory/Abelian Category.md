## Definition
Recall the definition of [[Additive Category|additive categories]].

A **pre-Abelian category** is an additive category such that every morphism $f\colon A\to B$ has a *kernel* $\mathrm{ker}(f)$ and a *cokernel* $\mathrm{coker}(f)$, which means there are pullbacks
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
Equivalently, it is an $\mathrm{Ab}$-enriched category with all finite limits and colimits.

**Proposition:** Every morphism $f\colon A\to B$ in a pre-Abelian category has a decomposition
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
>[!proof]
>TODO

A pre-Abelian category in which $\bar{f}$ is an isomorphism for all morphisms $f$ is called an **Abelian category**.