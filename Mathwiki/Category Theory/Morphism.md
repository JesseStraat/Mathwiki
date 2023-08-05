In a [[Category|category]], a **morphism** is an arrow between [[Object|objects]]. Its precise nature varies between categories, but in the context of set-theoretical categories, it is usually a function that preserves an object's characteristics.
## Special morphisms
### Isomorphisms
An **isomorphism** is a morphism $f\colon A\to B$ such that there exists a $g\colon B\to A$ with $f\circ g = 1_B$ and $g\circ f = 1_A$.
Notice that $g$, the *inverse* of $f$ is uniquely determined. Indeed, if there were to exist an $h$ with the same properties, then $g = g\circ f\circ h = h$.
If such an isomorphism exists, we say that $A$ and $B$ are *isomorphic*, and we write $A\cong B$.
### Monomorphisms
For $f\colon A\to B$, we say that it is a **monomorphism** if for any two arrows $g,h\colon C\to A$, we have that $f\circ g = f\circ h$ implies $g = h$.
The dual concept of a monomorphism is an [epimorphism](#Epimorphisms)
### Epimorphisms
For $f\colon A\to B$, we say that it is a **epimorphism** if for any two arrows $g,h\colon B\to C$, we have that $g\circ f = h\circ f$ implies $g = h$.