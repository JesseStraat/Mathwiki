Most of this page has been taken from *Sets, models and proofs* by Ieke Moerdijk and Jaap van Oosten.
## Definition
Let $L$ be a [[Language|language]]. For a [[Formula|formula]] $\varphi$, variable $x$ and term $t$, we define the *substitution of $t$ for $x$ in $\varphi$* $\varphi[t/x]$ recursively as
$$\langle\rangle[t/x] = \langle\rangle,$$
$$(\psi\circ\chi)[t/x] = (\psi[t/x]\circ \chi[t/x])\quad\text{for $\circ\in\{\Rightarrow,\wedge,\vee\}$},$$
$$(\neg\psi)[t/x] = \neg\psi[t/x],$$
$$(\circ y\psi)[t/x] = \circ y\psi[t/x]\quad\text{for $y\neq x$ a variable, $\circ\in\{\exists,\forall\}$},$$
$$(\circ x\psi)[t/x] = \circ x\psi\quad\text{for $\circ\in\{\exists,\forall\}$},$$
if $\varphi$ is an atomic formula, we define inductively
$$(x * s)[t/x] = t*s[t/x],$$
$$(a*s)[t/x] = a*s[t/x]$$
for $a$ a symbol. This now defines a unique map that sends any formula to a new formula.

Let $\varphi$ be any $L$-formula. Let $x$ be a variable that occurs on the $i$-th position of $\varphi$. Given any variable $t$ not in $\varphi$, we say that $x$ is *bound* at the $i$-th position in $\varphi$ if the $i$-th element of $\varphi[t/x]$ is $x$. Otherwise, it is *free*. If a formula has no free variables, it is called *closed* or a **sentence**.

Conventionally, we require that variables must either be bound or free at *every* occurrence in a formula. Moreover, each occurrence of a variable may only be bound once.

An $L$-**structure** is a nonempty set $M$ together with
- For each constant $c$ of $L$ an element $c^M$ of $M$, 
- For each $n$-ary function $f$ of $L$ a function $f^M\colon M^n\to M$,
- For each $n$-ary relation symbol $R$ of $L$ a subset $R^M\subseteq M^n$.
Now, we induce an expanded language $L_M$ which, in addition to all symbols of $L$, also contains a constant $m$ for each $m\in M\setminus \mathrm{con}(L)^M$.

Given any closed term $t$ of $L_M$, we inductively define an element $t^M\in M$. For $t$ a constant, we have already defined it, so we only need to cover the case where $t=f(t_1,\dots,t_n)$, in which case $t^M = f^M(t_1^M,\dots,t_n^M)$.

We will now define what it means for a sentence $\varphi$ in $L_M$ to be true in $M$, denoted $M\vDash\varphi$. For $t_1,\dots,t_n$ closed terms and $R$ an $n$-ary relation symbol, we define for atomic formulas
- $M\vDash\perp$ never holds,
- $M\vDash (t_1=t_2)$ if $t_1^M=t_2^M$,
- $M\vDash R(t_1,\dots, t_n)$ if $(t_1^M,\dots,t_n^M)\in R^M$,

and for $\psi, \chi$ formulas and $x$ a variable

- $M\vDash (\psi\wedge\chi)$ if $M\vDash \psi$ and $M\vDash\chi$,
- $M\vDash(\psi\vee\chi)$ if $M\vDash\psi$ or $M\vDash\chi$ (in the inclusive sense),
- $M\vDash(\psi\Rightarrow\chi)$ if $M\vDash\chi$ whenever $M\vDash\psi$,
- $M\vDash(\neg\psi)$ if $M\vDash\psi$ is false,
- $M\vDash(\forall x\psi)$ if $M\vDash \psi[m/x]$ for all $m\in M$,
- $M\vDash(\exists x\psi)$ if $M\vDash\psi[m/x]$ for some $m\in M$.

An $L$-formula $\varphi$ is called *valid* if $M\vDash \varphi$ for all $L$-structures $M$.