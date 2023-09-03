---
aliases:
 - Model
---
Most of this page has been taken from *Sets, models and proofs* by Ieke Moerdijk and Jaap van Oosten.
## Definition
Let $L$ be a [[Language|language]]. A **theory** in $L$ is a set $T$ of $L$-sentences.

An $L$-structure $M$ is a **model** of $T$ if $M\vDash \varphi$ for every $\varphi\in T$.

If a theory admits a model, it is called *consistent*.
## Propositions
**Theorem:** (compactness theorem) Let $T$ be some theory of a language $L$. If every finite $T'\subseteq T$ is consistent, then $T$ is also consistent.

The compactness theorem was proven by Anatoly Maltsev in 1936.