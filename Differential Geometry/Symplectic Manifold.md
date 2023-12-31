## Definition
Recall that a $2$-form is an antisymmetric $(0,2)$-[[Tangent Space#Tensors|tensor]]. Moreover, it is equivalent to an asymmetric linear map $V\to V^*$, given the base vector space $V$.

On a manifold $M$, if a $2$-form $\omega$ is closed, i.e., $\mathrm{d}\omega = 0$, and the corresponding maps $\tilde{\omega}_p\colon T_pM\to T_p^*M$ is bijective, we say that $\omega$ is a **symplectic form**. We then say that the pair $(M,\omega)$ is a **symplectic manifold**.

A diffeomorphisms $f\colon M\to N$ between symplectic manifolds $(M,\omega)$ and $(N,\eta)$ is a **symplectomorphism** if $f^*\eta = \omega$.
## Propositions
**Proposition:** A symplectic manifold has even dimension.
>[!proof]-
>(inspired by https://planetmath.org/everysymplecticmanifoldhasevendimension)
>Since a manifold shares its dimension with its tangent space at any of its points, we will restrict ourselves to the vector space $V := T_pM$ and $\omega_p$ for some $p\in M$.
>Take any non-zero vector $v_0\in V$. Due to the bijectivity of $\tilde{\omega}_p$, we know that there must be some vector $w_0\in V$ such that $\omega_p(v_0,w_0) = 1$. Notice, in particular, that $w_0$ must be non-zero and linearly independent of $v_0$, due to the antisymmetry of $\omega$. From here, we generate a two-dimensional subspace $V_0 := \mathrm{span}(v_0,w_0)$.
>Now, define $W_0 := \{w\in V\ |\ \omega_p(v,w) = 0\text{ for all }v\in V_0\}$. We would like to show that $V = V_0 \oplus W_0$, since this would imply that $\omega = \omega_0 + \omega_0'$, with $\omega_0 = \omega|_{V_0}$ and $\omega_0' = \omega|_{W_0}$, where both of these forms are themselves symplectic.
>Firstly, it is straightforwardly found that $V_0 \cap W_0 = \{0\}$, due to the fact that $\omega_p(v_0,w_0) = 1$.
>Now, for any vector $v\in V$, define $\alpha = \omega_p(v_0,v)$ and $\beta = \omega_p(w_0,v)$, and $v' = \alpha w_0 - \beta v_0 \in V_0$. Now, we want to prove that $v-v'\in W_0$. This follows quite directly, since
>$$\omega_p(v_0,v-v') = \alpha - \alpha = 0,$$
>$$\omega_p(w_0,v-v') = \beta - \beta = 0.$$
>Therefore, $v-v' \in W_0$, which proves that $V = V_0 \oplus W_0$.
>Now, we can separate $\omega_p$ into two symplectic forms on $V_0$ and $W_0$.
>It holds that $\mathrm{dim}(V) = \mathrm{dim}(V_0) + \mathrm{dim}(W_0) = \mathrm{dim}(W_0) + 2$. If $W_0$ is $\{0\}$, our result follows trivially. If $W_0$ is non-trivial, we may repeat the process to find a $V_1$, a $V_2$, etc., each of which has dimension $2$.
>Since $V$ is finite-dimensional, we know that this process must terminate at some point. Hence, the dimension of $V$ must be $2n$ for some natural number $n$, hence even. Therefore, $T_pM$ is even-dimensional, which proves that $M$ is, too.
## Examples
### The cotangent bundle
Let $M$ be any manifold, and $T^*M$ its cotangent bundle. Then, for any chart $\varphi\colon U\to \mathbb{R}^m$, every point in $T^*U$, i.e., $(x,\xi)$ with $x\in U$ and $\xi\in T_x^*M$, is given by $(x,\sum_{i=1}^m \xi_i (\mathrm{d}\varphi_i)_x)$. Hence, we find a chart $\tilde{\varphi}\colon T^*U\to \mathbb{R}^{2m}$ with $\tilde{\varphi}(x,\xi) = \varphi(x) \oplus (\xi_1,\dots, \xi_m)$.
We define a $2$-form $\omega = \sum_{i=1}^m \mathrm{d}\tilde{\varphi}_i\wedge\mathrm{d}\tilde{\varphi}_{m+i}$. We would like to show that this $2$-form is the same independently of our choice of chart.
>[!proof]-
>Indeed, choosing any other chart $\chi\colon V\to \mathbb{R}^m$, we know that
>$$(\mathrm{d}\varphi_i)_x = \sum_{j=1}^m \frac{\partial \varphi_i}{\partial \chi_j} (x)\ (\mathrm{d}\chi_j)_x,$$
>therefore,
>$$\xi = \sum_{i=1}^m \xi_i \sum_{j=1}^m \frac{\partial \varphi_i}{\partial \chi_j} (x)\ (\mathrm{d}\chi_j)_x = \sum_{j=1}^m \left(\sum_{i=1}^m \frac{\partial \varphi_i}{\partial \chi_j} (x)\xi_i\right)(\mathrm{d}\chi_j)_x,$$
>and so,
>$$\tilde{\chi}(x,\xi) = \tilde{\chi}(x)\oplus \left(\sum_{i=1}^m \frac{\partial \varphi_i}{\partial \chi_1} (x)\xi_i,\dots, \sum_{i=1}^m \frac{\partial \varphi_i}{\partial \chi_m} (x)\xi_i\right).$$
>Therefore,
>$$\sum_{i=1}^m\tilde{\chi}_{m+i}\mathrm{d}\tilde{\chi}_i = \sum_{i,j,k=1}^m \frac{\partial \varphi_j}{\partial \chi_i} (x)\xi_j\frac{\partial\chi_i}{\partial\varphi_k}\mathrm{d}\varphi_k = \sum_{i=1}^m  \xi_i\mathrm{d}\varphi_i = \sum_{i=1}^m\tilde{\varphi}_{m+i}\mathrm{d}\tilde{\varphi}_i$$
>is invariant of chart. Since $\omega$ is nothing but (minus) the exterior derivative of the above expression, we find that it is invariant, itself.

This allowed us to extend $\omega$ to a global $2$-form. $\omega$ is called the *canonical form*.
Notice that $\mathrm{d}\omega = 0$ holds and it is trivially non-degenerate, so this means that $\omega$ is a symplectic form over $T^*M$.