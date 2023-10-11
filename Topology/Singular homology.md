## Definition
Let $$\Delta_n = \left\{(x_0,\dots,x_n)\in\mathbb{R}^{n+1}\ \middle|\ \forall i(x_i\geq 0), \sum_{i=0}^nx_i = 1\right\}.$$
A *singular $n$-simplex* of a [[Topological space|topological space]] $X$ is a continuous map $\sigma\colon \Delta_n\to X$. The set of singular $n$-simplices is denoted $\mathcal{S}(X)_n = \mathrm{Top}(\Delta_n,X)$. The *group of singular $n$-chains in $X$ with coefficients in $A$* is then $C_n(X;A) := A[\mathcal{S}(X)_n]$, with $A$ any Abelian group. This defines a functor $C_n(-;A)\colon \mathrm{Top}\to \mathrm{Ab}$.

For $0\leq i\leq n$, define the *$i$-th face map* as $d_i\colon C_n(X;A)\to C_{n-1}(X;A)$ induced by the map $\mathcal{S}(X)_n\to \mathcal{S}(X)_{n-1}$ with $\sigma\mapsto \left((x_0,\dots,x_{n-1})\mapsto \sigma(x_0,\dots,x_{i-1},0,x_i,\dots,x_{n-1})\right)$. Then define the *boundary map* as
$$\partial_n = \sum_{i=0}^n (-1)^id_i.$$
It is readily derived that $\partial_{n-1}\circ\partial_n = 0$, so this gives us a [[Chain Complex|chain complex]] in $\mathrm{Ab}$. The *$n$-th (singular) homology group of $X$* is then the chain homology of degree $n$, denoted $H_n(X;A)$.

As before, $H_n(-;A)$ is a functor.
## Properties of homologies
### $H_0(X;A)$
Notice that for $\sigma\in\mathcal{S}(X)_1$, it is equivalent to some curve $\gamma\colon [0,1]\to X$. We find that $\partial_1(\sigma) = \sigma(1) - \sigma(0)$, so in $H_0(X;A)$, we have that $[x] = [y]$ if and only if there is a path connecting the two. Hence, $H_0(X;A)$ is precisely the free Abelian group of $A$ over the path connected components of $X$.
### $H_1(X;A)$
For path-connected $X$, there exists an isomorphism $\pi_1(X,x_0)^\text{ab} \cong H_1(X;\mathbb{Z})$.