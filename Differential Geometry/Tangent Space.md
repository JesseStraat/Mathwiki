---
aliases:
---
## Definition
Given a [[Differentiable Manifold|manifold]] $M$, a point $p$ and the set
$$\mathcal{C}_M(p) = \{(U,f)\ |\ p\in U\text{ is open}, f\colon U\to\mathbb{R} \text{ is smooth}\}/\sim$$
where $(U_1,f_1)\sim (U_2,f_2)$ if there is a an open neighbourhood $U_3\subseteq U_1\cap U_2$ of $p$ such that $f_1|_{U_3} = f_2|_{U_3}$. Given a smooth curve $\gamma\colon (-1,1)\to M$ with $\gamma(0)=p$, the **derivative in direction $\gamma$** is then the function
$$\gamma'(0)\colon \mathcal{C}_M(p)\to \mathbb{R},\ f\mapsto \left.\frac{\mathrm{d}f(\gamma(t))}{\mathrm{d}t}\right|_{t=0}.$$
We also say that $\gamma'(0)$ is the **tangent vector of $M$ at $p$ along $\gamma$**. The set of all tangent vectors is called the **tangent space**, denoted $T_pM$.

Tangent spaces induce a [[Vector Bundle|vector bundle]] called the [[Vector Bundle#Tangent Bundle|tangent bundle]].
## Vector Field
A **vector field** $X$ on a manifold $M$ is a function that assigns to every point $p\in M$ a tangent vector $X_p\in T_pM$, such that in some neighbourhood of $p$, we can write
$$X_p = \sum_{i=1}^mf^j(p)\left(\frac{\partial}{\partial x^j}\right)_p,$$
where $f^j$ are smooth functions.
The set of all vector fields over $M$ is denoted $\mathfrak{X}(M)$, which inherits the vector space structure from the tangent spaces.
## 1-forms
Let $T_p^*M$ denote the dual space of $T_pM$, and assign to each $\left(\frac{\partial}{\partial x^j}\right)_p$ its dual vector $(\mathrm{d}x^j)_p$.
A **$1$-form** $\omega$ on $M$ is a function that assigns to each point $p$ a covector $\omega_p\in T_p^*M$ such that in some neighbourhood of $p$, we have
$$\omega_p = \sum_{i=1}^mf_j(p)(\mathrm{d}x^j)_p,$$
where the $f_j$ are smooth functions. The space of all $1$-forms is denoted $\Omega^1(M)$.

In terms of [[Vector Bundle|vector bundles]], we say that a $1$-form is a section of the dual to the tangent bundle.
## Tensors
Let $TM$ denote the tangent bundle of some manifold $M$. Then, the **$(m,n)$-tensor bundle** is
$$T^m_nM = TM^{\otimes m}\otimes T^*M^{\otimes n}.$$
A **$(m,n)$-tensor field** is a section of the $T^m_nM$ vector bundle. Notice, in particular, that
 - An $n$-form is a $(0,n)$-tensor field;
 - A vector field is a $(1,0)$-tensor field;
 - A smooth function is a $(0,0)$-tensor field.
## Propositions
**Proposition:** Let $M$ be a $m$-dimensional manifold and $p$ a point in $M$. The tangent space $T_pM$ is a real $m$-dimensional vector space.
>[!proof]-
>It is quite trivial to see that $T_pM$ is indeed a vector space under $(\gamma'(0)+\eta'(0))f := \gamma'(0)f+\eta'(0)f$ and $(\lambda\gamma'(0))f := \lambda(\gamma'(0)f)$.
>Now, we only need to find a basis. Let $\varphi$ be any local chart around $p$, and define $x_i = \pi_i\circ \varphi$ for $i=1,\dots, m$ and $\pi_i\colon \mathbb{R}^m\to\mathbb{R}$ the $i$-th projection map. Then, define the curve$$\gamma_i\colon (-1,1)\to M,\ t\mapsto \varphi^{-1}(x_1(p),\dots, x_i(p)+t,\dots, x_m(p)),$$
>scaling $\varphi$ if necessary. Then, we define $\left(\frac{\partial}{\partial x^i}\right)_p := \gamma_i'(0)$. For any other curve $\eta$, we see that
>$$\eta'(0)f = \left.\frac{\mathrm{d}f\circ \varphi^{-1}\circ\varphi\circ\eta(t)}{\mathrm{d}t}\right|_{t=0} = \sum_{i=1}^m \left.\frac{\partial f\circ \varphi^{-1}}{\partial x^i}\right|_{\varphi(p)}\left.\frac{x_i\circ\eta(t)}{\mathrm{d}t}\right|_{t=0} = \left(\sum_{i=1}^m \left.\frac{x_i\circ\eta(t)}{\mathrm{d}t}\right|_{t=0}\left(\frac{\partial}{\partial x^i}\right)_p\right)f.$$
>This proves that they span $T_pM$. Now, as to prove that they are linearly independent, notice that $\left(\frac{\partial}{\partial x^i}\right)_px_j = \delta^i_j$ for all $i$, so if $\sum_{i=1}^m\lambda_i\left(\frac{\partial}{\partial x^i}\right)_p = 0$, then
>$$0 = \sum_{i=1}^m\lambda_i\left(\frac{\partial}{\partial x^i}\right)_p x_j = \lambda_j.$$
