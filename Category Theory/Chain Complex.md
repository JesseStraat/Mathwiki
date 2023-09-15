---
aliases:
  - Homology
  - Cohomology
  - Exact Sequence
---
## Definition
Let $\mathcal{C}$ be an [[Abelian Category|Abelian category]]. A **chain complex** in $\mathcal{C}$ is a collection of [[Object|objects]] $\{A_n\}_{n\in\mathbb{Z}}$ and a collection of [[Morphism|morphisms]] $\{\partial_n\colon A_n\to A_{n-1}\}_{n\in\mathbb{Z}}$ such that $\partial_n\circ\partial_{n+1} = 0$. Set-theoretically, this means that the image of each morphism is contained within the kernel of the next.

There is a category of chain complexes over $\mathcal{C}$, with objects given by chain complexes $(\{A_n\}, \{\partial_n\})$, and morphisms $(\{A_n\}, \{\partial_n\})\to (\{B_n\}, \{\partial_n'\})$ are precisely a collection of morphisms $\{f_n\colon A_n\to B_n\}_{n\in\mathbb{Z}}$ such that $f_{n-1}\circ \partial_n = \partial_n'\circ f_n$, i.e., the following diagram commutes for all $n$:
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	\dots & {A_n} & {A_{n-1}} & \dots \\ \dots & {B_n} & {B_{n-1}} & \dots \arrow["{\partial_n}", from=1-2, to=1-3] \arrow["{f_n}"', from=1-2, to=2-2] \arrow["{f_{n-1}}", from=1-3, to=2-3] \arrow["{\partial_n'}"', from=2-2, to=2-3] \arrow[from=1-3, to=1-4] \arrow[from=1-1, to=1-2] \arrow[from=2-1, to=2-2] \arrow[from=2-3, to=2-4]
\end{tikzcd}
\end{document}
```
For each $n\in\mathbb{Z}$, we define the *$n$-cycle* $Z_n = \mathrm{ker}(\partial_n)$ and the $n$-boundary $B_n = \mathrm{im}(\partial_{n+1})$.

Now, there is a canonical monomorphism
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\usetikzlibrary{calc}
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
	{B_n} & {Z_n} \arrow["{g_n}", hook, from=1-1, to=1-2]
\end{tikzcd}
\end{document}
```
which in set-theoretic terms should be understood as the inclusion of the image of one map into the kernel of the next. See the info box below for an exact derivation of this map
>[!info]-
>Now, since $\partial_n\circ\partial_{n+1}=0$, we have that
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\usetikzlibrary{calc}
>\tikzset{curve/.style={settings={#1},to path={(\tikztostart)
>    .. controls ($(\tikztostart)!\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
>    and ($(\tikztostart)!1-\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
>    .. (\tikztotarget)\tikztonodes}},
>    settings/.code={\tikzset{quiver/.cd,#1}
>        \def\pv##1{\pgfkeysvalueof{/tikz/quiver/##1}}},
>    quiver/.cd,pos/.initial=0.35,height/.initial=0}
>\begin{document}
>\Large
>\begin{tikzcd}
>	{A_{n+1}} & {A_n} & {A_{n-1}} \\ 0 & {\mathrm{coker}(\partial_{n+1})} \arrow["{\partial_{n+1}}", from=1-1, to=1-2] \arrow["{\partial_n}", from=1-2, to=1-3] \arrow[two heads, from=1-1, to=2-1] \arrow[two heads, from=1-2, to=2-2] \arrow[hook, from=2-1, to=2-2] \arrow["\ulcorner"{anchor=center, pos=0.125}, draw=none, from=1-1, to=2-2] \arrow[curve={height=60pt}, hook, from=2-1, to=1-3] \arrow["{\exists!}", dashed, from=2-2, to=1-3]
>\end{tikzcd}
>\end{document}
>```
>In particular,
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\usetikzlibrary{calc}
>\tikzset{curve/.style={settings={#1},to path={(\tikztostart)
>    .. controls ($(\tikztostart)!\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
>    and ($(\tikztostart)!1-\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
>    .. (\tikztotarget)\tikztonodes}},
>    settings/.code={\tikzset{quiver/.cd,#1}
>        \def\pv##1{\pgfkeysvalueof{/tikz/quiver/##1}}},
>    quiver/.cd,pos/.initial=0.35,height/.initial=0}
>\begin{document}
>\Large
>\begin{tikzcd}
>	{B_n} \\ & {A_{n+1}} & {A_n} & {A_{n-1}} \\ & 0 & {\mathrm{coker}(\partial_{n+1})} \arrow["{\partial_{n+1}}", from=2-2, to=2-3] \arrow["{\partial_n}", from=2-3, to=2-4] \arrow[two heads, from=2-2, to=3-2] \arrow[two heads, from=2-3, to=3-3] \arrow[hook, from=3-2, to=3-3] \arrow["\ulcorner"{anchor=center, pos=0.125}, draw=none, from=2-2, to=3-3] \arrow[from=3-3, to=2-4] \arrow[curve={height=-24pt}, hook, from=1-1, to=2-3] \arrow[curve={height=24pt}, two heads, from=1-1, to=3-2] \arrow["\lrcorner"{anchor=center, pos=0.125}, draw=none, from=1-1, to=3-3]
>\end{tikzcd}
>\end{document}
>```
>now that we know that the morphism $B_n\to A_{n-1}$ factors through $0$, and therefore is a zero morphism, we have that
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\usetikzlibrary{calc}
>\tikzset{curve/.style={settings={#1},to path={(\tikztostart)
>    .. controls ($(\tikztostart)!\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
>    and ($(\tikztostart)!1-\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
>    .. (\tikztotarget)\tikztonodes}},
>    settings/.code={\tikzset{quiver/.cd,#1}
>        \def\pv##1{\pgfkeysvalueof{/tikz/quiver/##1}}},
>    quiver/.cd,pos/.initial=0.35,height/.initial=0}
>\begin{document}
>\Large
>\begin{tikzcd}
>	{B_n} & {Z_n} & 0 \\ {A_{n+1}} & {A_n} & {A_{n-1}} \arrow["{\partial_{n+1}}", from=2-1, to=2-2] \arrow["{\partial_n}", from=2-2, to=2-3] \arrow[curve={height=-30pt}, two heads, from=1-1, to=1-3] \arrow[hook, from=1-2, to=2-2] \arrow[two heads, from=1-2, to=1-3] \arrow[hook, from=1-3, to=2-3] \arrow["\lrcorner"{anchor=center, pos=0.125}, draw=none, from=1-2, to=2-3] \arrow["{\exists!g_n}", dashed, hook, from=1-1, to=1-2] \arrow[shift right, hook, from=1-1, to=2-2]
>\end{tikzcd}
>\end{document}
>```
>This $g_n$ is, of course, uniquely determined.

We then define the *chain homology of degree $n$* as $H_n = \mathrm{coker}(g_n)$. In particular, whenever it makes sense, it is the quotient $Z_n/B_n$.

Dually, one defines *cochain complexes* and *cohomology*.

An **exact sequence** is a chain complex such that the homology is $0$ at every degree.

We often abbreviate chain complexes by only concerning non-trivial parts, i.e., if we say that we have a chain complex
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\usetikzlibrary{calc}
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
	{A_n} & \dots & {A_0} \arrow["{\partial_n}"', from=1-1, to=1-2] \arrow["{\partial_1}"', from=1-2, to=1-3]
\end{tikzcd}
\end{document}
```
we actually mean the chain complex
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\usetikzlibrary{calc}
\tikzset{curve/.style={settings={#1},to path={(\tikztostart)
    .. controls ($(\tikztostart)!\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
    and ($(\tikztostart)!1-\pv{pos}!(\tikztotarget)!\pv{height}!270:(\tikztotarget)$)
    .. (\tikztotarget)\tikztonodes}},
    settings/.code={\tikzset{quiver/.cd,#1}
        \def\pv##1{\pgfkeysvalueof{/tikz/quiver/##1}}},
    quiver/.cd,pos/.initial=0.35,height/.initial=0}
\begin{document}
%\Large
\begin{tikzcd}
	\cdots & 0 & {\mathrm{ker}(\partial_n)} & {A_n} & \dots & {A_0} & {\mathrm{coker}(\partial_1)} & 0 & \dots \arrow["{\partial_n}"', from=1-4, to=1-5] \arrow["{\partial_1}"', from=1-5, to=1-6] \arrow[two heads, from=1-6, to=1-7] \arrow[two heads, from=1-7, to=1-8] \arrow[from=1-8, to=1-9] \arrow[hook, from=1-3, to=1-4] \arrow[hook, from=1-2, to=1-3] \arrow[from=1-1, to=1-2]
\end{tikzcd}
\end{document}
```
A *short exact sequence* is an exact sequence
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\usetikzlibrary{calc}
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
	{A_2} & {A_1} & {A_0} \arrow["{\partial_2}"', from=1-1, to=1-2] \arrow["{\partial_1}"', from=1-2, to=1-3]
\end{tikzcd}
\end{document}
```
## Propositions
**Lemma:** (*the snake lemma*) Given two short exact sequence $A\to B\to C$ and $A'\to B'\to C'$ and a chain morphism $\{\alpha\colon A\to A', \beta\colon B\to B', \gamma\colon C\to C'\}$, there is a morphism $s\colon \mathrm{ker}(\gamma)\to\mathrm{coker}(\alpha)$ such that the following diagram commutes
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\usetikzlibrary{calc}
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
	{\mathrm{ker}(\alpha)} & {\mathrm{ker}(\beta)} & {\mathrm{ker}(\gamma)} \\ A & B & C \\ {A'} & {B'} & {C'} \\ {\mathrm{coker}(\alpha)} & {\mathrm{coker}(\beta)} & {\mathrm{coker}(\gamma)} \arrow[from=2-1, to=2-2] \arrow[from=2-2, to=2-3] \arrow[from=3-1, to=3-2] \arrow[from=3-2, to=3-3] \arrow["\alpha"', from=2-1, to=3-1] \arrow["\beta"', from=2-2, to=3-2] \arrow["\gamma"', from=2-3, to=3-3] \arrow[hook, from=1-1, to=2-1] \arrow[hook, from=1-2, to=2-2] \arrow[hook, from=1-3, to=2-3] \arrow[two heads, from=3-1, to=4-1] \arrow[two heads, from=3-2, to=4-2] \arrow[two heads, from=3-3, to=4-3] \arrow["{\exists!}", dashed, from=1-1, to=1-2] \arrow["{\exists!}", dashed, from=1-2, to=1-3] \arrow["{\exists!}"', dashed, from=4-1, to=4-2] \arrow["{\exists!}"', dashed, from=4-2, to=4-3] \arrow["s", color={rgb,255:red,255;green,65;blue,51}, from=1-3, to=4-1]
\end{tikzcd}
\end{document}
```
and the sequence $\mathrm{ker}(\alpha)\to \dots \to \mathrm{coker}(\gamma)$ is exact.