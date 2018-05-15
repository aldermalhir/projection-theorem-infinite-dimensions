---
title: The Besicovitch-Federer projection theorem is false in every infinite dimensional Banach space
author: David Bate (joint with Mariana Csörnyei and Bobby Wilson)
---

# The Besicovitch-Federer projection theorem

The projection theorem is a fundamental result in classical geometric measure theory.

::: definition
Rectifiable metric spaces
:::

::: theorem
Besicovitch-Federer projection theorem
:::

Its strength has made it an important part of many research topics.
Therefore, it is very natural to generalise it to non-Euclidean spaces.
We will be interested in its generalisation to infinite dimensional Banach spaces.
Note that such a generalisation is also important even in the language of metric spaces, since any separable metric space can be biLipschitz embedded into $c_0$.

# A projection theorem in infinite dimensional Banach spaces

## What is a projection?
Although orthogonal projections are only present in Hilbert space, continuous linear functions into some Euclidean space do provide a good notion of a projection.

## What do we mean by "almost every" projection?
The difficulty in formulating the projection theorem in infinite dimensions is how to interpret "almost every" projection.
Although there are not analogues to the Lebesgue measure in infinite dimensions, there are reasonable notions of a "null set" in this setting, which is sufficient for our purposes.
Two examples are Aronszajn and Haar null sets.

## De Pauw's result
Thus, we may ask if the corresponding generalisation of the Besicovitch-Federer projection theorem is true... and we see that it is not.

::: theorem
There exists a purely 1-unrectifiable $S\subset \ell_2$ with $\Ho(S) < \infty$ such that $|T(S)| >0$ for all $T$ in a non Aronszajn null set of projections $T \colon \ell_2 \to \R$.

That is, the Besicovitch-Federer projection theorem is false for Aronszajn almost every projection in $\ell_2$.
:::

Questions:

- De Pauw's set of directions *is* Haar null.  Does there exist a counter example for Haar null sets?
- Even if the answer is yes, what if there is a stronger notion of null set?
- What about other Banach spaces?

## A complete answer
::: theorem
In any separable infinite dimensional Banach space $X$, there exists a purely 1-unrectifiable $E\subset X$ with $\Ho(E)<\infty$ such that $|T(E)|>0$ for *every* continuous linear $0 \neq T \colon X \to \R$.
:::

# Construction of the set $E$ in $\ell_2$.
Fix an orthonormal basis $e_0, e_1, \ldots$ of $\ell_2$, a positive sequence $\alpha =(1,\alpha_1,\alpha_2,\ldots )\in \ell_2 \setminus \ell_1$ and a sequence $M_n \in \mathbb N$.

Let $g \colon \mathbb R \to [0,1)$ be defined by
$$g(t) = \begin{cases} 0 & t \in [0,1/2)\\
                     1/2 & t \in [1/2, 1) \end{cases}$$
and extend periodically to $\mathbb R$.  We also define $f_n \colon \R \to \R$ by
$$f_n(t) = M_n^{-1} g(M_n t)$$
and
$$f = \sum_{n=0}^{\infty} \alpha_n f_n e_n.$$
Finally, we define $E = f([0,1])$.

# Unrectifiability of $E$

The discontinuities in the construction of $E$ suggest that $E$ will be purely unrectifiable.  However, there are two delicate points.

1. We must consider vertical (i.e. orthogonal to $e_0$) curves.
2. There is a scaling factor of $\alpha_n$ at each stage that could allow Lipschitz curves to appear.

::: lemma
For any Borel $S\subset [0,1]$,
$$\Ho(\{f(t) : t\in S\}) \leq \|\alpha\|_2.$$
:::

::: proof
A direct calculation from the construction of $E$.
:::

Note that this implies $\Ho(E) < \infty$.

We will choose $\|\alpha\|_2 \leq 3/2$.

To see that $E$ is purely unrectifiable, suppose that $\gamma \colon A \subset \R \to E$ has positive measure image.

- By a result of Kirchheim, for any $\epsilon>0$, we may suppose that $\gamma$ is $1+\epsilon$-biLipschitz.  For simplicity, suppose $\epsilon=0$.  By measure theory, there exists $s_0$ a density point of $A$. Set $x_0 = \gamma(s_0)$
- A small ball $B=B(x_0,r) \cap \gamma(A)$ has measure $2r$.  By the previous lemma, since $\|\alpha\|_2 < 3/2$, $B$ must contain points to the left and to the right of $x_0$.
- At any scale at which the distance of $x_0\cdot e_0$ to the jump is less than $\alpha_n/M_n$, $B$ must contain a point on the other side of the jump.
- By the Borel-Cantelli lemma, this happens infinitely often provided $\alpha \not \in \ell_1$.  Since the size of the gap is comparable to its distance from $x_0$, $s_0$ cannot be a density point of $A$. (Note, we require some minor technical assumptions on $\alpha_n$ and $M_n$ so that these events are independent.)

# Projections of $E$

By Cauchy-Schwarz, any $0\neq T \in \ell_2'$ is given by coordinatewise multiplication by $0\neq (\beta_0, \beta_1,\ldots) \in \ell_2$.

Applying $T$ on $\ell_2$ is equivalent to applying the following operations:

1.  Apply the map $P(x_0,x_1,\ldots) = (x_0, \sum_{i>0} \beta_i x_i) \in \R^2$.
2.  Project onto the line $(\beta_0,1)$.

-  After the first operation, the image of $P(E)$ is precisely
   $$\alpha_0 t, \sum_{i>0} \alpha_n \beta_n f_n(t)$$
   which can be covered by a curve of length $\sum_n M_n (\alpha_n \beta_n)/M_n$.
-  By Cauchy-Schwarz, this is summable and so $P(E)$ is rectifiable.
   Moreover, the projection of $P(E)$ onto the $x$ axis is $[0,1]$ and so has positive measure.
-  Thus, the projection onto $(t_0,1)$ has positive measure *unless $P(E)$ is contained in the line orthogonal to $(\beta_0,1)$*.

We will show that this is not the case by demonstrating that $P(E)$ has two distinct approximate tangents.

First note, if $\beta_n =0$ for all $n>0$, $\beta_0 \neq 0$ and so $T$ maps $E$ onto $[0,1]$.  Otherwise, fix $n>0$ such that $\beta_n \neq 0$.

- Let $t \in [0,1]$ be such that $P(f(t))$ has an approximate tangent, let $I$ be the interval of width $1/M_n$ on which $f_n$ is linear and choose $\pm$ such that $t':= t \pm 1/2M_n \in I$.
Also, we may choose $t$ such that this tangent is not vertical, say with slope $s$.
- Since the $f_m$ are linear on $I$ for $m<n$ and periodic with period $1/2M_n$ for $m>n$, the slope of the tangent at $t'$ is equal to $s$ except for the contribution from $f_n$.
- Thus, the value of this slope is $s \pm \beta_n \neq s$.

# Modifications for other Banach spaces

1.  By using Dvoretzky's theorem and the Dvoretzky-Rogers lemma, we are able to find a subspace sufficiently close to $\ell_2$ to construct $E$.
2. The fact that $E$ is purely unrectifiable is similar to before.
3. When considering the image under an arbitrary projection, the key point is to observe that the two applications of Cauchy-Schwarz are inverses of each other and that the argument can be modified to hold in this generality.
