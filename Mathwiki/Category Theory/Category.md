## Definition
 A **category** $\mathcal{C}$ consists of:
 - A collection of *[[Object|objects]]* $\mathrm{Ob}(\mathcal{C})$;
 - A collection of *[[Morphism|morphisms]]* $\mathrm{Mor}(\mathcal{C})$ (also called *arrows*);
 - Maps $\mathrm{dom}\colon \mathrm{Mor}(\mathcal{C})\to\mathrm{Ob}(\mathcal{C})$, the *domain map* and $\mathrm{cod}\colon \mathrm{Mor}(\mathcal{C})\to\mathrm{Ob}(\mathcal{C})$, the *codomain map*, i.e., to each morphism we associate a *domain* and a *codomain* (notation: $f\colon A\to B$, being equivalent to $\mathrm{dom}(f)=A$ and $\mathrm{cod}(f)=B$);
 - For each pair $f\colon A\to B$ and $g\colon B\to C$, there is a morphism $g\circ f\colon A\to C$ (the *composition* of $g$ and $f$; sometimes we neglect the $\circ$ symbol $gf := g\circ f$);
 - For every object $A$ a morphism $1_A\colon A\to A$ (the *identity morphism* on $A$),
such that the following axioms hold:
1. For any three morphisms $f\colon A\to B$, $g\colon B\to C$ and $h\colon C\to D$, we have *associativity of composition* $h\circ(g\circ f) = (h\circ g)\circ f =: h\circ g\circ f$;
2. For each $f\colon A\to B$, we have $f\circ 1_A = f = 1_B\circ f$;
For any objects $X,Y$, the collection of morphisms with domain $X$ and codomain $Y$, known as the **hom-set**, is denoted $\mathcal{C}(X,Y)$.
## Special categories
- A **groupoid** is a category in which all morphisms are [[Morphism#Isomorphisms|isomorphic]].
- A category is called a **complete category** if it has all [[Limit|small limits]].
## Examples
### Opposite categories
Given a category $\mathcal{C}$, the **opposite category** $\mathcal{C}^{op}$ shares its objects with $\mathcal{C}$, but $\mathcal{C}^{op}(X,Y) := \mathcal{C}(Y,X)$.
#### The duality principle
The *duality principle* dictates that if a certain claim holds in $\mathcal{C}$, then its *dual* (i.e., the same claim with each concept replaced by its dual) holds in $\mathcal{C}^{op}$. For example, if a morphism is monomorphic in $\mathcal{C}$, then its corresponding opposite morphism is epimorphic in $\mathcal{C}^{op}$.
### Functor category
The category whose objects are [[Functor|functors]] $F\colon \mathcal{C}\to\mathcal{D}$ and whose morphisms are [[Natural Transformation|natural transformations]] $\mu\colon F\Rightarrow G$ is called the *functor category* $[\mathcal{C},\mathcal{D}]$.
### $\mathrm{Grp}$
The category of groups, $\mathrm{Grp}$, has groups as its objects and group homomorphisms as its morphisms.
### Pre-orders
A *pre-order* is, in essence, a [[Smallness#Category theory|small category]] in which there are no parallel arrows, i.e., no two arrows with coinciding domain and codomain. A *poset* is a pre-order in which there are no non-trivial isomorphisms.
### $\mathrm{Cat}$
The category consisting of [[Smallness#Category theory|small categories]] as objects and [[Functor|functors]] as morphisms is called $\mathrm{Cat}$. The restriction of this category to small categories is necessary to avoid set-theoretic problems, such as Russell's paradox.
The "category of categories" itself cannot possibly be a category. However, it can be a $2$-category.
### $\mathrm{Diff}$
The category of [[Differentiable Manifold|smooth manifolds]] has [[Differentiable Manifold#Morphisms|smooth maps]] as its morphisms. There exists an [[Functor#Endofunctor|endofunctor]] $T\colon \mathrm{Diff}\to \mathrm{Diff}$ that associated to each smooth manifold its [[Vector Bundle#Tangent Bundle|tangent bundle]].
### $\mathrm{Set}$
The category of sets has sets as objects and functions as its morphisms.

**Proposition:** In $\mathrm{Set}$, a morphism is injective if and only if it is [[Morphism#Monomorphisms|monomorphic]].
> [!proof]- Proof
>	Any injection is trivially monomorphic.
>	Let $f\colon A\to B$ monomorphic, and take any $a_0, a_1\in A$ and assume that $f(a_0) = f(a_1)$. Then each of these is a morphism $a_0,a_1\colon \{*\}\to A$ such that $f\circ a_0 = f\circ a_1$. However, this then implies that $a_0=a_1$ in the sense of morphisms, and therefore, $a_0 = a_1$ in the sense of elements of $A$. Hence, $f$ is injective.

Similarly, a morphism is surjective if and only if it is [[Morphism#Epimorphisms|epimorphic]].