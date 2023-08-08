## Definition
A **ring** is a [[Set|set]] $R$ with binary operations $+$ and $\cdot$ such that:
1. $(R,+)$ is an [[Group#Abelian Group|Abelian group]];
2. $(R,\cdot)$ is a [[Monoid|monoid]];
3. $\cdot$ is distributive with respect to $+$: $$a\cdot(b+c) = (a\cdot b) + (a\cdot c),$$$$(a+b)\cdot c = a\cdot c + b\cdot c.$$
We say that a ring is **commutative** if $\cdot$ commutes.
## Unit
In a ring $R$, a **unit** is some element $a\in R$ such that there is a $b\in R$ with $ab=ba=1$.

## Ideal
Let $\mathcal{I}$ be some subring of $R$. Then we say it is a **left ideal** if $R\mathcal{I} = \mathcal{I}$, we say it is a **right ideal** if $\mathcal{I}R=\mathcal{I}$ and we say it is a **two-sided ideal** if it is both a left and a right ideal.
In a commutative ring, these are equivalent, and we say that $\mathcal{I}$ is an **ideal**.
An ideal is **proper** if it is not equal to $R$.

A (left/right) ideal is **maximal** if it is a proper ideal such that it is not contained in any other proper ideals.
## Local Ring
A **local ring** is a commutative [[Ring|ring]] with a unique [[Ring#Ideal|maximal ideal]].

**Proposition:** Let $R$ be a ring. Then it is local if and only if $1\neq 0$ and the set of non-[[Ring#Unit|units]] is closed under addition.
>[!proof]-
>"$\Rightarrow$": Assume that $1=0$, then $R$ is the zero ring, which tells us that the only (left) ideal is $R$ itself, and therefore, there can be maximal left ideal, giving a contradiction with the fact that $R$ is a local ring. Hence, $1\neq 0$.
>Notice that [[Ring#Propositions|all non-units must be contained in a maximal ideal]], and no proper ideal may contain a unit. Therefore, the unique maximal ideal of $R$ must be precisely the set of all non-units. Hence, it must be closed under addition.
>"$\Leftarrow$": Let $\mathcal{I}$ be the set of non-units. Then, of course, $\mathcal{I}R = \mathcal{I}$, so it forms an ideal. However, since every proper ideal may only contain non-units, we find that $\mathcal{I}$ is maximal and unique.
## Propositions
**Proposition:** In a commutative ring, every non-unit is contained in a maximal ideal.
>[!proof]-
>Let $a$ be any non-unit, and notice that $aR$ is a proper ideal, since it does not contain $1$. Now define the set $I$ as the set of all proper ideals of $R$ that contain $a$, which is non-empty because it contains $aR$. Furthermore, we can turn $I$ into a poset under $\subseteq$.
>Now take any chain of ideals $\mathcal{I}_0\subsetneq \mathcal{I}_1\subsetneq \dots$, and define the union $\mathcal{I} := \cup_{n=0}\mathcal{I}_n$, and notice that it must also be proper, since none of the $\mathcal{I}_n$ contains $1$. Therefore, the chain has an upper bound $\mathcal{I}$ in $I$, which tells us that $I$ has a maximal element through [[Zorn's Lemma|Zorn's lemma]]. This maximal element is, of course, a maximal ideal, and it contains $a$.

