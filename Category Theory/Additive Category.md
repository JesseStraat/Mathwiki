## Definition
Recall from [[Enriched Category#$ mathrm{Ab}$-enriched category|the article on enriched categories]] that an $\mathrm{Ab}$-enriched category is a [[Category|category]] $\mathcal{C}$ such that its hom-sets are Abelian groups and its composition is bilinear. Recall also that all [[Limit#Terminal object|terminal objects]] and initial objects are zero objects, and that [[Limit#Binary product|products]] coincide with coproducts, which we call *biproducts*.

An $\mathrm{Ab}$-enriched category is called an **additive category** if it has all finite biproducts.
## Examples
### $R\mathrm{Mod}$
Let $R$ be a ring and let $R\mathrm{Mod}$ denote the category of modules over $R$. Of course, the hom-sets inherit the Abelian group structure of the codomain under addition, and bilinearity of composition follows from the requirement that morphisms must be linear. Hence, $R\mathrm{Mod}$ is an $\mathrm{Ab}$-enriched category.

Now, we want to show that $R\mathrm{Mod}$ contains all finite products. We will start with the zero object, which is, of course, the trivial module $\{0\}$. Moreover, for any two modules $M,N$, their product is given by the direct sum $M\oplus N$. Therefore, $R\mathrm{Mod}$ is an additive category.