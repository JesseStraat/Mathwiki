**Zermelo-Fraenkel set theory** (or ZF) is an axiomatic system of [[Set Theory|set theory]]. Its extension, ZFC, is the most common axiomatic system used today.
## Axioms
The following are a list of axioms in ZF set theory.
1. Axiom of extensionality: $\forall x\forall y(\forall z(z\in x \Leftrightarrow z\in y) \Rightarrow x=y)$, if two sets have the same members, then they are equal.
2. Axiom of regularity: $\forall x(\exists a(a\in x)\Rightarrow \exists y(y\in x\wedge \neg\exists z(z\in y\wedge z\in x)))$, every set has an element that is disjoint from it.
3. Axiom of pairing: $\forall x \forall y\exists z (a\in z\Leftrightarrow(a=x\vee a=y))$, for any two sets, there exists a set that contains both, denoted $\{x,y\}$.
4. Axiom of union: $\forall x\exists y\forall a(a\in y\Leftrightarrow \exists z(z\in x\wedge a\in z))$: there is a set that contains the elements of all elements of $x$, denoted $\cup x$. Conventionally, we denote also $\cup\{x,y\} = x\cup y$.
5. Axiom schema of replacement: For each formula $\varphi$ with free variables $u,v$, $\forall u\exists y\forall v (\varphi \Leftrightarrow y=v)\Rightarrow \forall x\exists y\forall v(v\in y\Leftrightarrow \exists u(u\in x\wedge \varphi))$: the image of a set under some map is a set.
6. Axiom schema of specification: For each formula $\varphi$ with a free variable $z$, $\forall x\exists y\forall z (z\in y\Leftrightarrow (z\in x\wedge \varphi))$: we can construct sets $y = \{z\in x\ |\ \varphi\}$. Since $\exists x (x=x)$ is valid, this also implies the existence of the empty set $\emptyset := \{z\in x\ |\ \perp\}$.
7. Axiom of infinity: $\exists N [\emptyset\in N \wedge \forall x(x\in N\Rightarrow x\cup\{x\}\in N)]$, there is a set $N$ that contains $\emptyset$ and $x\in N$ implies $x\cup \{x\}\in N$.
8. Axiom of power set: $\forall x \exists y\forall z[(\forall a (a\in z\Rightarrow a\in x))\Leftrightarrow z\in y]$, every set has a power set $\mathcal{P}(x)$.

Moreover, ZF is commonly extended to ZFC, including also the **[[Axiom of Choice|axiom of choice]]** (AC). It requires also the definition of a function and of a union, as provided later on.

9. Axiom of choice: $\forall x [\emptyset\neq x \Rightarrow \exists f [f\in (\cup x)^x\Rightarrow \forall y(y\in x\Rightarrow f(y)\in y)]]$, for a set of non-empty sets, there exists a function (dubbed "choice function") that assigns to each set an element in said set.
## Definitions
### Subset
Let $x,y$ be some sets. We say that $x$ is a subset of $y$ if $\forall a (a\in x)\Rightarrow a\in y$, denoted by $x\subseteq y$. We furthermore say that $x$ is a proper subset of $y$ if $x\subseteq y$ and $x\neq y$, denoted $x\subset y$.
### Intersection
Let $x,y$ be some sets. We define their intersection as $x\cap y = \{a\in x\ |\ a\in y\}$, well-defined through the axiom schema of specification.
### Cartesian Product
Let $x,y$ be some sets. We define their Cartesian product as $x\times y = \{\{u,\{u,v\}\}\subseteq\mathcal{P}(x\cup y)\ |\ u\in x\wedge v\in y\}$. The ordered pair $\{u,\{u,v\}\}$ is also denoted $(u,v)$.
### Function
Let $x,y$ be some sets. A subset $f$ of $x\times y$ is a **function** from $x$ to $y$ if $\forall u\exists v\forall w((u,w)\in f \Leftrightarrow v = w)$. We denote this (unique) $v$ as $v := f(u)$.
We define the sets of functions from $x$ to $y$ as $y^x = \{f\in\mathcal{P}(x\times y)\ |\ \forall u\exists v\forall w((u,w)\in f \Leftrightarrow v = w)\}$.