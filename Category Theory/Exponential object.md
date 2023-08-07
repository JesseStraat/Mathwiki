---
aliases:
 - Cartesian closed category
---
## Definition
Given a [[Category|category]] $\mathcal{C}$ with [[Limit#Binary product|binary products]], and [[Object|objects]] $X,Y$, the **exponential object** is an object $X^Y$ in $\mathcal{C}$ equipped with an evaluation [[Morphism|morphism]] $ev\colon X^Y\times Y\to X$ that is universal, i.e., for every object $Z$ and morphism $f\colon Z\times Y\to X$, there exists a unique map $\hat{f}\colon Z\to X^Y$ such that the following diagram commutes:
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
    X^Y\times Y\arrow[r,"ev"] & X\\
    Z\times Y\arrow[u,dashed,"{(\hat{f},1_Y)}"]\arrow[ru,swap,"f"]
\end{tikzcd}
\end{document}
```
In other words, the map $\mathcal{C}(Z, X^Y)\to \mathcal{C}(Z\times Y, X)$ with $\hat{f}\mapsto ev\circ (\hat{f},1_Y)$ is bijective. A category is **cartesian closed** if it has finite products and the exponential exists for all objects.

Given a cartesian closed category $\mathcal{C}$, we can construct for any object $Z$ an exponentiation endofunctor $(-)^Z\colon \mathcal{C}\to\mathcal{C}$ through $X\mapsto X^Z$ and for $f\colon X\to Y$, we choose $f^Z\colon X^Z\to Y^Z$ as the unique morphism
```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\usepackage{amssymb}
\begin{document}
\Large
\begin{tikzcd}
	X^Z\times X\arrow[r,"ev"]\arrow[d,swap,dashed,"{(f^Z,1_X)}"] & X\arrow[d,"f"]\\
	Y^Z\times X\arrow[r,swap,"ev"] & Y
\end{tikzcd}
\end{document}
```

One can see that in a cartesian closed category, the exponential endofunctor $(-)^Z$ is the [[Adjoint|right adjoint]] to the product endofunctor $(-)\times Z$ for all $Z$.
## Examples
### $\mathrm{Set}$
In $\mathrm{Set}$, the exponential object is given by $X^Y = \mathrm{Set}(Y,X)$ with $ev(f,y) = f(y)$. Indeed, for any $f\colon Z\times Y\to X$, we define $\hat{f}(z) = f(z,\cdot)$, such that $ev\circ (\hat{f},1_Y) = f$.
$\mathrm{Set}$ is cartesian closed.
## Propositions
**Proposition:** Given any objects $X,Y,Z$ in some category, we have the following isomorphisms:
1. If $X^Z\times Y^Z$ and $(X\times Y)^Z$ exist, they are isomorphic;
2. If $(X^Z)^Y$ and $X^{Y\times Z}$ exist, they are isomorphic;
3. If the category is cartesian closed and $X\times (Y+Z)$ and $(X\times Y)+(X\times Z)$ exist, they are isomorphic;
4. If we have a terminal object $1$, then $1^X$ exists and $1^X\cong 1$.
>[!proof]-
>1. We have unique $f_X\colon (X\times Y)^Z\to X^Z$ and $f_Y\colon (X\times Y)^Z\to Y^Z$ such that the following commute:
>	```tikz
>	\usepackage{tikz-cd}
>	\usepackage{amsmath}
>	\usepackage{amssymb}
>	\begin{document}
>	\Large
>	\begin{tikzcd}
> 	   X^Z\times Z\arrow[r,"ev"] & X\\
> 	   (X\times Y)^Z\times Z\arrow[u,dashed,"{(f_X,1_Z)}"]\arrow[ru,swap,"\pi_X\circ ev"]
>	\end{tikzcd}
>	\end{document}
>	```
>	```tikz
>	\usepackage{tikz-cd}
>	\usepackage{amsmath}
>	\usepackage{amssymb}
>	\begin{document}
>	\Large
>	\begin{tikzcd}
> 	   Y^Z\times Z\arrow[r,"ev"] & Y\\
> 	   (X\times Y)^Z\times Z\arrow[u,dashed,"{(f_Y,1_Z)}"]\arrow[ru,red,swap,"\pi_Y\circ ev"]
>	\end{tikzcd}
>	\end{document}
>	```
>	Now assume that we have the following diagram:
>	```tikz
>	\usepackage{tikz-cd}
>	\usepackage{amsmath}
>	\usepackage{amssymb}
>	\begin{document}
>	\Large
>	\begin{tikzcd}
>		&X^Z&\\
>		A\arrow[ur,"\alpha"]\arrow[dr,swap,"\beta"]\arrow[rr,red,"h"] & & (X\times Y)^Z\arrow[ul,swap,"f_X"]\arrow[dl,"f_Y"]\\
>		&Y^Z&
>	\end{tikzcd}
>	\end{document}
>	```
>	where the red arrow represents a morphism $h$ that may or may not exist. In this proof, we will show that there is only one possible candidate for $h$, and then we show that the commutative diagram indeed commutes.
>	Taking the binary product with $Z$ everywhere gives us the diagram
>	```tikz
>	\usepackage{tikz-cd}
>	\usepackage{amsmath}
>	\usepackage{amssymb}
>	\begin{document}
>	\Large
>	\begin{tikzcd}
>		&X^Z\times Z\arrow[d,"ev"]&\\
>		&X&\\
>		A\times Z\arrow[uur,"{(\alpha,1_Z)}"]\arrow[ddr,swap,"{(\beta,1_Z)}"]\arrow[rr,red,swap,"{(h,1_Z)}",
>		rounded corners,
>		to path={|- ([yshift=-17ex]\tikztostart.south)
>						-| (\tikztotarget) [near end]\tikztonodes
>		}] & X\times Y \arrow[u,"\pi_X"]\arrow[d,"\pi_Y"]& (X\times Y)^Z\times Z\arrow[uul,swap,"{(f_X,1_Z)}"]\arrow[ddl,"{(f_Y,1_Z)}"]\arrow[l,"ev"]\\
>		&Y&\\
>		&Y^Z\times Z\arrow[u,"ev"]&
>	\end{tikzcd}
>	\end{document}
>	```
>	From the binary product, we find that there is a unique $\varphi\colon A\times Z \to X\times Y$ such that
>	```tikz
>	\usepackage{tikz-cd}
>	\usepackage{amsmath}
>	\usepackage{amssymb}
>	\begin{document}
>	\Large
>	\begin{tikzcd}
>		&X^Z\times Z\arrow[d,"ev"]&\\
>		&X&\\
>		A\times Z\arrow[r,dashed,"\exists !\varphi"]\arrow[uur,"{(\alpha,1_Z)}"]\arrow[ddr,swap,"{(\beta,1_Z)}"]\arrow[rr,red,swap,"{(h,1_Z)}",
>		rounded corners,
>		to path={|- ([yshift=-17ex]\tikztostart.south)
>						-| (\tikztotarget) [near end]\tikztonodes
>		}] & X\times Y \arrow[u,"\pi_X"]\arrow[d,"\pi_Y"]& (X\times Y)^Z\times Z\arrow[uul,swap,"{(f_X,1_Z)}"]\arrow[ddl,"{(f_Y,1_Z)}"]\arrow[l,"ev"]\\
>		&Y&\\
>		&Y^Z\times Z\arrow[u,"ev"]&
>	\end{tikzcd}
>	\end{document}
>	```
>	so in particular, if $h$ exists, then $\varphi = ev\circ (h,1_Z)$. The universal property now gives us that there exists a unique $h$ such that $\varphi = ev\circ (h,1_Z)$ holds. Hence, we have found the unique candidate for $h$. However, we have not yet guaranteed that $f_X\circ h = \alpha$ and $f_Y\circ h = \beta$. We have the following commutative diagram:
>	```tikz
>	\usepackage{tikz-cd}
>	\usepackage{amsmath}
>	\usepackage{amssymb}
>	\begin{document}
>	\Large
>	\begin{tikzcd}
>		X^Z\times Z \arrow[r,"ev"] & X & X^Z\times Z\arrow[l,"ev"]\\
>		A\times Z\arrow[u,"{(\alpha,1_Z)}"]\arrow[r,"\varphi"]\arrow[rr,dashed,bend right,swap,"{(h,1_Z)}"] & X\times Y\arrow[u,"\pi_X"] & (X\times Y)^Z\times Z \arrow[u,"{(f_X,1_Z)}"]
>	\end{tikzcd}
>	\end{document}
>	```
>	Importantly, notice that $ev\circ (\alpha,1_Z) = ev\circ (f_X\circ h,1_Z) = \pi_X\circ \varphi$. However, the universality condition says that $\alpha$ is the unique morphism such that $ev\circ (\alpha,1_Z) = \pi_X\circ \varphi$, such that $\alpha = f_X\circ h$. Analogously, we can find that $f_Y\circ h = \beta$. This now proves that
>	```tikz
>	\usepackage{tikz-cd}
>	\usepackage{amsmath}
>	\usepackage{amssymb}
>	\begin{document}
>	\Large
>	\begin{tikzcd}
>		&X^Z&\\
>		A\arrow[ur,"\alpha"]\arrow[dr,swap,"\beta"]\arrow[rr,dashed,"\exists !h"] & & (X\times Y)^Z\arrow[ul,swap,"f_X"]\arrow[dl,"f_Y"]\\
>		&Y^Z&
>	\end{tikzcd}
>	\end{document}
>	```
>	and hence, $(X\times Y)^Z \cong X^Z\times Y^Z$.
>2. Notice that we have a map $ev\circ (ev,1_Z)\colon (X^Z)^Y\times Y\times Z\to X$. Now, assume that there is some object $A$ with a morphism $f\colon A\times Y\times Z\to X$. Then there exist unique morphisms $g\colon A\times Y\to X^Z$ and $\hat{g}\colon A\to (X^Z)^Y$ such that the following diagram commutes:
>	```tikz
>	\usepackage{tikz-cd}
>	\usepackage{amsmath}
>	\usepackage{amssymb}
>	\begin{document}
>	\Large
>	\begin{tikzcd}
>		& A\times Y\times Z \arrow[r,"f"]\arrow[d,dashed,swap,"{(g,1_{Z})}"]\arrow[dl,dashed,swap,"{(\hat{g}, 1_{Y\times Z})}"] & X\\
>		(X^Z)^Y\times Y\times Z \arrow[r,swap,"{(ev,1_Z)}"] & X^Z\times Z \arrow[ur,swap,"ev"] &
>	\end{tikzcd}
>	\end{document}
>	```
>	Hence, we have that $(X^Z)^Y \cong X{Y\times Z}$.
>3. The binary product endofunctor is left adjoint, and therefore preserves colimits.
>4. Take any object $A$, then there is a unique $f\colon A\to 1$. Then there is a unique $\hat{f}\colon A\to 1^X$ such that the following commutes:
>	```tikz
>	\usepackage{tikz-cd}
>	\usepackage{amsmath}
>	\usepackage{amssymb}
>	\begin{document}
>	\Large
>	\begin{tikzcd}
>		1^X\times X\arrow[r,"ev"] & 1\\
>		A\times X \arrow[ur,swap,"f\circ\pi_A"]\arrow[u,dashed,"{(\hat{f},1_X)}"]
>	\end{tikzcd}
>	\end{document}
>	```
>	Assume now that there is any other $g\colon A\to 1^X$. Then, of course, $ev\circ (g,1_X)\colon A\times X\to 1$, and therefore, $ev\circ(g,1_X) = f\circ\pi_A$. The universality property then implies that $\hat{f}=g$. Hence, there is a unique morphism $A\to 1^X$, which tells us that $1^X$ is a terminal object, and therefore, $1^X\cong 1$.
