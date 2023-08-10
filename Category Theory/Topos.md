## Definition
If a [[Category|category]] $\mathcal{C}$ has [[Limit|finite limits]], is [[Exponential object|Cartesian closed]] and has a [[Subobject|subobject classifier]], then it is called an **(elementary) topos**.
## Examples
### $\mathrm{Set}$ as a topos
We already know that $\mathrm{Set}$ is Cartesian closed and complete. However, it also has a subobject classifier, being $\Omega = \{\mathrm{True},\mathrm{False}\}$, and $t(*) = \mathrm{True}$. Indeed, given any injection $f\colon X\to Y$, we have $$\varphi_X(y) = \begin{cases} \mathrm{True}\quad&\text{if $y\in fX$,}\\ \mathrm{False}\quad&\text{otherwise.}\end{cases}$$
For this reason, $\Omega$ is sometimes called the **object of truth values**.