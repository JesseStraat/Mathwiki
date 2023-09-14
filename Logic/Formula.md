Most of this page has been taken from *Sets, models and proofs* by Ieke Moerdijk and Jaap van Oosten.
## Definition
Let $L$ be a [[Language|language]]. Let $\mathcal{C}_L$ denote the set of all symbols and $\mathcal{C}_L^*$ the set of finite strings, i.e., sequences in $\mathcal{C}_L$ of finite length. These strings are denoted by $\langle a_1, a_2,\dots, a_n\rangle$. We furthermore define concatenation as $\langle a_1,\dots,a_n\rangle * \langle b_1,\dots,b_m\rangle = \langle a_1,\dots,a_n,b_1\dots b_m\rangle$.

The set of **terms** in $L$ is the smallest subset $T$ of $\mathcal{C}_L^*$ such that
1. If $c$ is a constant of $L$, then $\langle c\rangle \in T$;
2. If $x$ is a variable, then $\langle x\rangle\in T$;
3. Given $n$ elements of $T$ $t_1, \dots, t_n$ and an $n$-ary function $f$, then $\langle f\rangle * t_1 *\dots * t_n\in T$.
The existence of this set is guaranteed by the fact that any intersection of sets satisfying (1)-(3) must also satisfy them. Hence, by taking the intersection of all sets that satisfy these properties, we get the set of terms.
A term that does not contain variables is called *closed*.

In mathematics, we denote terms of constants and variables $\langle x\rangle$ and $\langle c \rangle$ simply by $x$ and $c$, respectively. Furthermore, we denote $\langle f\rangle * t_1\dots * t_n = f(t_1,\dots, t_n)$.

The set of **formulas** is the smallest subset $F$ of $\mathcal{C}_L^*$ such that
1. Given terms $t,s$, then $\langle =\rangle * t* s$ is in $F$;
2. Given an $n$-ary relation symbol $R$ and terms $t_1,\dots, t_n$, then $\langle R\rangle * t_1 * \dots * t_n$ is in $F$;
3. $\langle \perp\rangle\in F$;
4. Given $\varphi,\psi\in F$, the following are elements of $F$:
	- $\langle \wedge\rangle * \varphi *\psi$;
	- $\langle\vee\rangle*\varphi *\psi$;
	- $\langle\Rightarrow\rangle *\varphi*\psi$;
	- $\langle\neg\rangle*\varphi$.
5. Given $\varphi\in F$ and a variable $x$, the following are elements of $F$:
	- $\langle\forall\rangle *\langle x\rangle * \varphi$;
	- $\langle\exists\rangle * \langle x\rangle *\varphi$.
Elements formed by (1)-(3) are called *atomic formulas*. Existence of the smallest such subsets is again implied by intersection.

We denote the above formulas as $t=s$, $R(t_1,\dots, t_n)$, $\perp$, $\varphi\wedge\psi$, $\varphi\vee\psi$, $\varphi\Rightarrow\psi$, $\neg\varphi$, $\forall x \varphi$ and $\exists x \varphi$, respectively.

For simplicity, we also introduce the shorthand $\varphi\Leftrightarrow \psi := (\varphi\Rightarrow \psi)\wedge (\psi\Rightarrow \varphi)$ for any formulas $\varphi,\psi$.
## Propositions
**Proposition:** Suppose $V$ is the set of variables, $A$ the set of atomic formulas, $F$ the set of formulas, $X$ any set, and we are given maps
$$f_a\colon A\to X,$$
$$f_\wedge, f_\vee, f_\Rightarrow\colon X\times X\to X,$$
$$f_\neg\colon X\to X,$$
$$f_\forall, f_\exists\colon V\times X\to X,$$
then there is a unique map $f\colon F\to X$ such that for any $\varphi,\psi$ in $F$
$$f(\varphi) = f_a(\varphi)\quad\text{if $\varphi\in A$},$$
$$f(\varphi\wedge\psi) = f_{\wedge}(f(\varphi),f(\psi)),$$
$$f(\varphi\vee\psi) = f_\vee(f(\varphi),f(\psi)),$$
$$f(\varphi\Rightarrow\psi) = f_\Rightarrow(f(\varphi),f(\psi)),$$
$$f(\neg\varphi)=f_\neg(f(\varphi)),$$
$$f(\forall x \varphi) = f_\forall(x,f(\varphi)),$$
$$f(\exists x\varphi) = f_\exists(x,f(\varphi)).$$
>[!proof]-
>First, let us show that a function $f$ satisfying said properties must be unique. Assume that there is some other function $g$ that satisfies the properties and $f\neq g$. Then there must be a shortest formula $\varphi\in F$ such that $f(\varphi)\neq g(\varphi)$. Note, in particular, that $\varphi$ may not be an atomic formula, since $f$ and $g$ must agree on $A$.
>Now, assume $\varphi = \psi\wedge\chi$, then $\psi,\chi$ are both shorter than $\varphi$, and therefore,
>$$f(\varphi) = f_\wedge(f(\psi),f(\chi)) = f_\wedge(g(\psi),g(\chi)) = g(\varphi),$$
>which gives a contradiction. The same contradiction is easily found for all other possibilities of $\varphi$ in a parallel manner. Hence, if such an $f$ exists, it must be unique.
>
>The definition, and therefore existence, of such a function follows directly from the desired properties.