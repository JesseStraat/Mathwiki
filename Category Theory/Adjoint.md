---
aliases:
 - Left adjoint
 - Right adjoint
---
## Definition
Let $\mathcal{C},\mathcal{D}$ be some categories with functors $L\colon \mathcal{C}\to\mathcal{D}$, $R\colon \mathcal{D}\to\mathcal{C}$. We say that these are **adjoint** if for all objects $C$ in $\mathcal{C}$ and $D$ in $\mathcal{D}$, there exists a bijection $\mathcal{C}(C,RD) \to \mathcal{D}(LC,D)$. We then say that $L$ is **left adjoint** and $R$ is **right adjoint**. We write $L\dashv R$.
## Propositions
**Proposition:** The left adjoint and right adjoint are dual concepts.
>[!proof]-
>Take categories $\mathcal{C}, \mathcal{D}$, a functor $L\colon\mathcal{C}\to\mathcal{D}$ and a functor $R$ such that $L\dashv R$. Therefore, for all objects $C,D$, we have $\mathcal{C}(C,RD)\cong \mathcal{D}(LC,D)$. Hence, $\mathcal{C}^{op}(R^{op}D,C)\cong \mathcal{D}^{op}(D,L^{op}C)$. We conclude that $R^{op}\dashv L^{op}$.

**Theorem:** Right adjoint functors preserve limits.
https://ncatlab.org/nlab/show/adjoints+preserve+%28co-%29limits