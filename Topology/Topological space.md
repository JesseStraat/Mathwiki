## Definition
A **topological space** is a set $X$ together with a set $\mathscr{T}\subseteq \mathcal{P}(X)$ such that:
1. $\emptyset\in\mathscr{T}$ and $X\in\mathscr{T}$;
2. $\mathscr{T}$ is closed under union;
3. $\mathscr{T}$ is closed under finite intersection.
We say that $\mathscr{T}$ is the *topology* of $X$, and elements of $\mathscr{T}$ are called *open subsets* of $X$.
Moreover, a subset of $X$ such that its complement is open is called *closed*. Subsets that are both open and closed are *clopen*

We say that some collection of open sets $\mathscr{B}$ is a *base* of the topology if every open set can be formed as a union of some subset of $\mathscr{B}$. Any collection of subsets of $X$ induces a topology of which it is a base.
## Special topologies
### Metric spaces
A **metric space** is a set $X$ together with a map $d\colon X\times X\to \mathbb{R}_{\geq 0}$ such that
1. $d(x,y) = 0$ if and only if $x = y$;
2. $d(x,y) = d(y,x)$;
3. $d(x,z) \leq d(x,y) + d(y,z)$ (the *triangle inequality*).
This induces a topology on $X$ called the *metric topology*, with base
$$\mathscr{B}_d = \{B_r(x)\ |\ x\in X, r>0\},$$
with $B_r(x) = \{y\in X\ |\ d(x,y) < r\}$ the *open balls*.
We say that a topological space $(X, \mathscr{T})$ is *metrisable* if there exists a function $d\colon X\times X\to \mathbb{R}_{\geq 0}$ such that $X$ together with $d$ is a metric space, and $d$ generates $\mathscr{T}$ as the metric topology.