## Definition
An **ordinal** is a [[Language of Sets|set]] $x$ such that $$\forall y(y\in x\Rightarrow \forall z(z\in y\Rightarrow z\in x)),$$ $$\forall y(y\in\mathcal{P}(x)\wedge y\neq\emptyset\Rightarrow \exists u\forall v(u\in y\wedge v\in y\wedge \neg(u=v)\Rightarrow u\in v)).$$
## Operations
### Successor function
Let $x$ be an ordinal. Then $x\cup\{x\}$ is also an ordinal. Indeed,
>[!proof]-
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\begin{tikzcd}
>	 && {^\dagger a\in x\Rightarrow \forall z(z\in a\Rightarrow z\in x)} & {^\dagger a=x} \\ {^\dagger a\in x\cup\{x\}} & {^\dagger a\in x} & {a\in x\Rightarrow \forall z(z\in a\Rightarrow z\in x\cup\{x\})} & {\forall z(z\in a\Rightarrow z\in x)} \\ {a\in x\vee a=x} && {\forall z(z\in a\Rightarrow z\in x\cup\{x\})} & {\forall z(z\in a\Rightarrow z\in x\cup\{x\})} \\ && {\forall z(z\in a\Rightarrow z\in x\cup\{x\})} \\ && {a\in x\cup\{x\}\Rightarrow \forall z(z\in a\Rightarrow z\in x\cup\{x\})} \arrow[no head, from=2-1, to=3-1] \arrow[no head, from=1-3, to=2-3] \arrow[no head, from=1-4, to=2-4] \arrow[no head, from=3-1, to=4-3] \arrow[no head, from=2-2, to=3-3] \arrow[no head, from=2-3, to=3-3] \arrow[no head, from=2-4, to=3-4] \arrow[no head, from=3-3, to=4-3] \arrow[no head, from=3-4, to=4-3] \arrow[no head,from=4-3, to=5-3] 
>\end{tikzcd}
>\end{document}
>```
>```tikz
>\usepackage{tikz-cd}
>\usepackage{amsmath}
>\usepackage{amssymb}
>\begin{document}
>\begin{tikzcd}
>	&& {^\dagger a=\emptyset} & {^\dagger\exists a(a\in\mathcal{P}(x)\wedge y=a\cup\{x\})} \\ &&& {y=\{x\}} \\ && {^\dagger v\in y\wedge \neg(x=v)} & {v\in y\Rightarrow v = x} & {^\dagger a\neq \emptyset} & {^\dagger a\in\mathcal{P}(x)} \\ &&& \perp & {^\dagger\forall a(a\in\mathcal{P}(x)\wedge a\neq\emptyset\Rightarrow \exists u\forall v(u\in a\wedge v\in a\wedge \neg(u=v)\Rightarrow u\in v))} & {a\in\mathcal{P}(x)\wedge a\neq\emptyset} & {^\dagger a\in\mathcal{P}(x)} & {^\dagger u\in a} \\ &&& {x\in v} && {\exists u\forall v(u\in a\wedge v\in a\wedge \neg(u=v)\Rightarrow u\in v)} & {u\in x} \\ &&& {\forall v(v\in y\wedge \neg(x=y)\Rightarrow x\in v)} && {\exists u\forall v(u\in a\wedge v\in a\cup\{x\}\wedge \neg(u=v)\Rightarrow u\in v)} & {^\dagger y=a\cup\{x\}} \\ &&& {\exists u\forall v(u\in y \wedge v\in y\wedge \neg(u=y)\Rightarrow u\in v)} && {\exists u\forall v(u\in a\wedge v\in y\wedge \neg(u=v)\Rightarrow u\in v)} & {^\dagger y=a\cup\{x\}} \\ {^\dagger y\neq \emptyset} & {^\dagger y\in\mathcal{P}(x)} &&&& {\exists u\forall v(u\in y\wedge v\in y\wedge \neg(u=v)\Rightarrow u\in v)} \\ & {y\in\mathcal{P}(x)\wedge y\neq \emptyset} & {^\dagger y\in\mathcal{P}(x)\wedge y\neq \emptyset\Rightarrow\exists u\forall v(u\in y\wedge v\in y\wedge \neg(u=v)\Rightarrow u\in v)} & {^\dagger y\in\mathcal{P}(x\cup\{x\})} & {^\dagger a=\emptyset \vee a\neq \emptyset} \\ && {\exists u\forall v(u\in y\wedge v\in y\wedge \neg(u=v)\Rightarrow u\in v)} & {y\in\mathcal{P}(x)\vee\exists a (a\in\mathcal{P}(x)\wedge y=a\cup\{x\})} & {\exists u\forall v(u\in y\wedge v\in y\wedge \neg(u=v)\Rightarrow u\in v)} \\ &&& {\exists u\forall v(u\in y\wedge v\in y\wedge \neg(u=v)\Rightarrow u\in v)} \\ &&& {y\in\mathcal{P}(x\cup\{x\})\wedge y\neq \emptyset\Rightarrow\exists u\forall v(u\in y\wedge v\in y\wedge \neg(u=v)\Rightarrow u\in v)} \\ &&& {\forall y(y\in\mathcal{P}(x\cup\{x\})\wedge y\neq \emptyset\Rightarrow\exists u\forall v(u\in y\wedge v\in y\wedge \neg(u=v)\Rightarrow u\in v))} \arrow[no head, from=12-4, to=13-4] \arrow[no head, from=9-3, to=10-3] \arrow[no head, from=8-1, to=9-2] \arrow[no head, from=8-2, to=9-2] \arrow[no head, from=9-2, to=10-3] \arrow[no head, from=9-4, to=10-4] \arrow[no head, from=1-4, to=2-4] \arrow[no head, from=1-3, to=2-4] \arrow[no head, from=2-4, to=3-4] \arrow[no head, from=3-4, to=4-4] \arrow[no head, from=3-3, to=4-4] \arrow[no head, from=5-4, to=6-4] \arrow[no head, from=6-4, to=7-4] \arrow[no head, from=3-6, to=4-6] \arrow[no head, from=3-5, to=4-6] \arrow[no head, from=4-5, to=5-6] \arrow[no head, from=4-6, to=5-6] \arrow[no head, from=5-6, to=6-6] \arrow[no head, from=4-7, to=5-7] \arrow[no head, from=4-8, to=5-7] \arrow[no head, from=5-7, to=6-6] \arrow[no head, from=6-7, to=7-6] \arrow[no head, from=6-6, to=7-6] \arrow[no head, from=7-7, to=8-6] \arrow[no head, from=7-6, to=8-6] \arrow[no head, from=7-4, to=10-5] \arrow[no head, from=8-6, to=10-5] \arrow[no head, from=9-5, to=10-5] \arrow[no head, from=10-5, to=11-4] \arrow[no head, from=10-3, to=11-4] \arrow[no head, from=10-4, to=11-4] \arrow[no head, from=11-4, to=12-4] \arrow[no head, from=4-4, to=5-4]
>\end{tikzcd}
>\end{document}
>```

This defines the successor function for ordinals $s(x) := x\cup \{x\}$.
## Natural numbers
We define the natural numbers as follows:
$0 = \emptyset$, $1 = s(0) = \{\emptyset\}$, $2 = s(1) = \{\emptyset,\{\emptyset\}\}$, and so on.
Now, we will show that the collection of all natural numbers forms a set. Indeed, let $N$ be the set postulated by the [[ZFC Set Theory|axiom of infinity]]. Then, define
$$\omega = \mathbb{N} = \{x\in N\ |\ \forall y(y\in\mathcal{P}(N) \Rightarrow [\emptyset\in y\wedge \forall z(z\in y\Rightarrow z\cup \{z\}\in y)] \Rightarrow x\in y)\}.$$
In other words, $\mathbb{N}$ is the intersection of all subsets of $N$ that contain $\emptyset$ and are closed under the succession function. Of course, this means that the set itself must contain $\emptyset$ and is closed under succession, therefore containing all the natural numbers.
This proves that every model of ZFC must contain the set of natural numbers.