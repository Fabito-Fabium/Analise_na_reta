```math
\newcommand{\Laplace}{\mathscr{L}}
\newcommand{\bN}{\mathbb N}
\newcommand{\inN}{\in \bN}
\newcommand{\dotline}{\\.\dotfill.\\}
\newcommand{\sqn}[1]{(#1_n)_{n \in \bN}}
\newcommand{\fmm}[3]{\{#1_#2\}_{#2 \in #3}}
\newcommand{\seq}[3]{(#1_#2)_{#2 \in #3}}
\newcommand{\dfunc}[3]{#1: #2 \rightarrow #3}
\newcommand{\tozero}[1]{#1 \rightarrow 0}
\newcommand{\toinf}[1]{#1 \rightarrow \infty}
\newcommand{\limsq}[3]{\lim_{#1 \rightarrow #2} #3_#1}
\newcommand{\limif}[2]{\lim_{#1 \rightarrow \infty} #2}
\newcommand{\limzr}[2]{\lim_{#1 \rightarrow 0} #2}
\newcommand{\bC}{\mathbb C}
\newcommand{\bZ}{\mathbb Z}
\newcommand{\bR}{\mathbb R}
\newcommand{\bQ}{\mathbb Q}
\newcommand{\itr}[1]{\text{int}(#1)}
\newcommand{\parth}[1]{\left(#1\right)}
\newcommand{\chavs}[1]{\left\{#1\right\}}
\newcommand{\mdl}[1]{\left|#1\right|}
\newcommand{\xssy}[2]{\left(#1 - #2, #1 + #2\right)}
\newcommand{\floor}[1]{\left\lfloor#1\right\rfloor}
\newcommand{\ceil}[1]{\left\lceil#1\right\rceil}
\newcommand{\asbeps}[2]{|#1 - #2| < \epsilon}
\newcommand{\iffc}[1]{\overset{#1}{\iff}}
\newcommand{\impliesc}[1]{\overset{#1}{\implies}}
\newcommand{\eqc}[1]{\overset{#1}{=}}
\newcommand{\sen}{\mathrm{sen}}
```
> [!INFO]
> As you can see, the rendering in this is a bit janky (this is what I get for deciding *not* to use $\LaTeX{}$ for this).
> I had higher hopes for `<details/>` blocks, but alas.
> You might find more success rendering the markdown locally (this is at least true for me).
> 
> Should be okay, since nobody is going to read this anyway :shrug:

## 1. Preliminaries

> #### Definition 1.1.
> A $\bN, \bR$ is a subset $\Sigma\subseteq 2^X$ (that is, a set of subsets of $X$), satisfying:
> 1. If $I$ is some countable set ($0\leq|I|\leq\omega$), and $U_i\in\Sigma$ for $i\in I$, then $\bigcup_{i\in I}U_i \in \Sigma$.
> 1. If $U\in\Sigma$, then $X\setminus U\in\Sigma$.
>
> A _measurable space_ is a pair $(X, \Sigma)$, where $X$ is some set, and $\Sigma$ is a $\sigma$ -algebra over $X$.
>
> In such a situation, a subset $S\subseteq X$ is called _measurable_ iff $S\in\Sigma$.

Note, in particular, that every $\sigma$ -algebra over $X$ contains $\varnothing$ (the empty union).
Moreover, closure under complements implies that $\sigma$ -algebras over $X$ contain $X$ itself, and are closed under countable intersections as well.

> #### Definition 1.2.
> Fix a measurable space $(X, \Sigma)$.
> A _measure_ on $(X, \Sigma)$ is a function $\mu : \Sigma \to [0, \infty]$ such that:
> 1. $\mu(\varnothing) = 0$.
> 1. If $I$ is some countable set, and $U_i\in\Sigma$ for $i\in I$ such that $U_i\cap U_j=\varnothing$ for $i\neq j$, then
> ```math
> \mu\left(\bigcup_{i\in I}U_i\right) = \sum_{i\in I}\mu(U_i)
> ```
>
> Naturally, a _measure space_ is a triple $(X, \Sigma, \mu)$, where $(X, \Sigma)$ is a measurable space, and $\mu$ is a measure on $(X, \Sigma)$.

## 2. More preliminaries

> #### Definition 2.1.
> A _Boolean algebra_ is a sextuple $(A, \land, \lor, \lnot, \top, \bot)$ satisfying:
> 1. $(A, \land, \top)$ is a commutative monoid.
> 1. $(A, \lor, \bot)$ is a commutative monoid.
> 1. (_Absorption_) For all $a, b, c\in A$, we have $a \land (a\lor b) = a\lor(a\land b) = a$.
> 1. (_Distributivity_) For $a, b, c\in A$, we have
> ```math
> \begin{aligned}
>   a\land(b\lor c) &= (a\land b)\lor(a\land c) \\
>   a\lor(b\land c) &= (a\lor b)\land(a\lor c)
> \end{aligned}
> ```
> 5. (_Annihilation_) For all $a\in A$, we have $a\land\bot=\bot$, and $a\lor\top=\top$.
> 1. (_Complementation_) For all $a\in A$, we have $a\land\lnot a=\bot$ and $a\lor\lnot a=\top$.
<details>
  <summary>What is a commutative monoid?</summary>

  A _monoid_ is a triple $(M, \circ, 1)$, where $M$ is some set, $\circ : M\times M\to M$, and $1\in M$, such that
  1. Multiplication is _associative_: for $a,b,c\in M$, we have $a\circ(b\circ c) = (a\circ b)\circ c$.
  1. $1$ is a _neutral element_: for $a\in M$, we have $1\circ a = a = a\circ1$.

  A monoid is further called _commutative_ if $a\circ b=b\circ a$ for all $a, b\in M$.
</details>

Every Boolean algebra $A$ carries a canonical partial ordering $(\preceq)$ defined by

```math
a \preceq b \quad\iff\quad a\land b = a \quad\iff\quad a\lor b = b
```

The partial ordering completely determines the Boolean algebra, through _suprema_ and _infima_ (and the fact that axiom 6 completely determines $\lnot a$ from $a$).

<details>
<summary>Proof (of unique complements).</summary>

Suppose $b,b'\in A$ are both complements of some $a\in A$; that is, $a\land b=\bot$, $a\lor b=\top$, $a\land b'=\bot$, $a\lor b'=\top$.
Then,

```math
b = b\land\top = b\land(a\lor b') = (b\land a)\lor(b\land b') = \bot\lor(b\land b') = b\land b'
```

Analogously, $b' = b'\land b$. However, since conjunction is commutative, this implies $b=b\land b'=b'\land b=b'$. $\qquad\square$

##

> **Note.** Since conjunction and disjunction are symmetric, the definition of $\lnot a$ also implies $\lnot\lnot a = a$ (i.e., _double negation_).

</details>

<details>
<summary>Proof (of partial ordering being well-defined).</summary>

If $a\land b=a$, then $a\lor b = (a\land b)\lor b = b$.
Conversely, if $a\lor b = b$, then $a\land b=a\land(a\lor b) = a$.
This proves that the two definitions of the partial ordering coincide.

It remains to show that this indeed defines a partial ordering.
1. (_Reflexivity_) $a\preceq a$ for all $a\in A$, since $a\land a = a\land(a\lor\bot) = a$.
1. (_Antisymmetry_) If $a\preceq b$ (i.e., $a\land b=a$) and $b\preceq a$ (i.e., $b\land a=b$), then $a = a\land b=b\land a=b$.
1. (_Transitivity_) If $a\preceq b$ (i.e., $a\land b=a$) and $b\preceq c$ (i.e., $b\land c=b$), then $a\land c=(a\land b)\land c=a\land(b\land c)=a\land b=a$; that is, $a\preceq c$.

This completes the proof. $\qquad\square$
##
</details>

> #### Definition 2.2.
> Given a partially-ordered set $(P, \preceq)$, and a subset $S\subseteq P$, an _upper bound_ of $S$ is any $u\in P$ such that $s\preceq u$ for every $s\in S$.
> If there is an upper bound $u^*\in P$ of $S$ such that, for any other upper bound $u\in P$ of $S$, we have $u^*\preceq u$, then $u^*$ is called the _supremum_ of $S$, denoted $u^* =: \sup S$.
>
> Entirely dually, a _lower bound_ of $S$ is any $\ell\in P$ such that $\ell\preceq s$ for every $s\in S$.
> If there is a lower bound $\ell^*\in P$ of $S$ such that, for any other lower bound $\ell\in P$ of $S$, we have $\ell\preceq\ell^*$, then $\ell^*$ is called the _infimum_ of $S$, denoted $\ell^* =: \inf S$.

In a Boolean algebra, one can show that $a\lor b=\sup\{a, b\}$, and $a\land b=\inf\{a, b\}$.

<details>
<summary>Proof.</summary>

$a\land b\preceq a$ because $a\land(a\land b)=(a\land a)\land b = a\land b$.
Symmetrically, $a\land b\preceq b$ also.

If $c\preceq a$ and $c\preceq b$, then $a\land c=c$ and $b\land c=c$.
In particular, $(a\land b)\land c=a\land(b\land c)=a\land c=a$, meaning $c\preceq(a\land b)$ as well, showing that $a\land b$ is the greatest lower bound of $\{a,b\}$.

The argument for $a\lor b=\sup\{a, b\}$ is entirely dual. $\qquad\square$

##
</details>

> #### Definition 2.3.
> A Boolean algebra $A$ is _complete_ if every subset $S\subseteq A$ admits a supremum and an infimum.
>
> For a family $(a_i)_{i\in I}$ of elements of $A$, the supremum and infimum may be denoted
> ```math
> \bigvee_{i\in I}a_i := \sup_{i\in I}a_i, \qquad \bigwedge_{i\in I}a_i := \inf_{i\in I}a_i
> ```

> #### Lemma 2.4. (_de Morgan's laws_)
> Let $A$ be a Boolean algebra, and $I$ some indexing set.
> Then, $A$ has suprema of all $I$ -indexed families iff it has infima of all $I$ -indexed families.
> In such a situation, if $S = (a_i)_{i\in I}$ is a family of elements of $A$, then
> ```math
> \bigvee_{i\in I}a_i = \lnot\bigwedge_{i\in I}\lnot a_i, \qquad \bigwedge_{i\in I}a_i = \lnot\bigvee_{i\in I}\lnot a_i
> ```
> In particular, a Boolean algebra is complete iff it has arbitrary suprema.

<details>
<summary>Proof.</summary>

Let $S\subseteq A$ be some family of elements of $A$, and let $\lnot S := \{\lnot s \mid s\in S\}$ be the element-wise negation of $S$.

Since $A$ has suprema of families indexed by $I$, we can compute $u := \sup(\lnot S)$.
We will show that $\lnot u = \inf(S)$.

Suppose $\ell$ is a lower bound for $S$; that is, $\ell\preceq s$ for every $s\in S$.
Then, $\lnot\ell$ is an upper bound for $\lnot S$.
Indeed, for any $\lnot s\in\lnot S$, we have that $\lnot\ell\land\lnot s = \lnot(\ell\lor s) = \lnot s$, meaning $\lnot s\preceq\lnot\ell$.

By the universal property of $u$, this means that $u\preceq\lnot\ell$.
In other words, $\ell\preceq\lnot u$ (by the same reasoning as above).

As $\ell$ is an arbitrary lower bound of $S$, this proves that $\lnot u$ is the greatest lower bound of $S$, and hence the infimum of $S$.

As $S$ is an arbitrary family of elements of $A$, this proves $A$ has all infima. $\qquad\square$

##
</details>

> #### Example 2.5.
> The set of Boolean truth values $\Omega = \{\top, \bot\}$ defines a complete Boolean algebra.

Since Boolean algebras form an algebraic theory, they admit arbitrary products.
This employs us to construct larger Boolean algebras from $\Omega$.

> #### Example 2.6
> Given a set $X$, the power set $2^X$ can be identified with the product of $|X|$ -many copies of (the underlying set of) $\Omega$, and so admits a canonical Boolean algebra structure.
>
> Under this identification,
> 1. $S\land T := S\cap T$
> 1. $S\lor T := S\cup T$
> 1. $\lnot S := X\setminus S$
> 1. $\top := X$
> 1. $\bot := \varnothing$.

## 3. Putting the two together

> #### Lemma 3.1.
> Every $\sigma$ -algebra is a Boolean algebra.

<details>
<summary>Proof.</summary>

Since a $\sigma$ -algebra $\Sigma$ is a subset of a power set $2^X$, this follows from [Example 2.6](#example-26) after observing that $\sigma$ -algebras are closed under all Boolean algebra operations. $\qquad\square$

##
</details>

> #### Definition 3.2.
> Given a Boolean algebra $A$, an _ideal_ of $A$ is a subset $I\subseteq A$ such that
> 1. $\bot \in I$,
> 1. If $x, y\in I$, then $x\lor y\in I$,
> 1. If $a\in A$ and $z\in I$, then $a\land z\in I$.

> #### Lemma 3.3.
> Let $(X, \Sigma, \mu)$ be a measure space.
> Say that $S\in\Sigma$ is a _null set_ if $\mu(S) = 0$.
> Then, the null sets define an ideal of $\Sigma$.

<details open>
<summary>Proof.</summary>

$\mu(\varnothing) = 0$ by design, which handles axiom 1 of [Definition 3.2](#definition-32).

The other axioms follow from more general properties of a measure: for $U, V\in\Sigma$:
1. $\mu(U\cup V)\leq\mu(U)+\mu(V)$ (which implies axiom 2).
1. $\mu(U\cap V)\leq\mu(U)$ (which implies axiom 3).

These both follow from monotonicity: if $U\subseteq V$, then $\mu(U)\leq\mu(V)$.

To see this, note that if $U, V\in\Sigma$, and $U\subseteq V$, then $V\setminus U = V\cap(X\setminus U) \in \Sigma$.
Now, since $V = U \cup (V\setminus U)$, it follows that $\mu(V) = \mu(U)+\mu(V\setminus U)$, and therefore (since $\mu\geq0$) that $\mu(V)\geq\mu(U)$. $\qquad\square$

##
</details>


Given an ideal $I$ of $A$, we can define an equivalence relation on $A$ by
```math
a \sim_I b \quad\iff\quad \underbrace{(a\land\lnot b)\lor(b\land\lnot a)}_{a\oplus b}\in I
```
<details>
<summary>Proof that this defines an equivalence relation.</summary>

We need to show that the equivalence relation is reflexive, symmetric, and transitive.

Reflexivity is clear: for any $a\in I$, $a\oplus a = (a\land\lnot a)\lor(a\land\lnot a) = \bot\lor\bot = \bot$, which must always lie in $I$.

Symmetry is by design: $a\oplus b = b\oplus a$.

For transitivity, we will show that $a\oplus c = (a\oplus b)\oplus(b\oplus c)$.
Indeed, since $x,y\in I$ implies $x\oplus y = \underbrace{(x\land\lnot y)}_{\in I}\lor\underbrace{(y\land\lnot x)}_{\in I}\in I$, it follows that if $a\oplus b\in I$ and $b\oplus c\in I$, then $a\oplus c=(a\oplus b)\oplus(b\oplus c)\in I$ as well.

To see that $a\oplus c=(a\oplus b)\oplus(b\oplus c)$, we will instead show that $(A, \oplus, \bot)$ is a (commutative) monoid.
Then, $(a\oplus b)\oplus(b\oplus c) = a\oplus(b\oplus b)\oplus c = a\oplus\bot\oplus c = a\oplus c$.

We already have that $a\oplus\bot=(a\land\lnot\bot)\lor(\bot\land\lnot a) = a\lor\bot=a$, so it remains to show associativity.

To this end, notice that the right hand side of

```math
\begin{aligned}
    (a\oplus b)\oplus c &= ((a\land\lnot b)\lor(b\land\lnot a))\oplus c \\
        &= (((a\land\lnot b)\lor(b\land\lnot a))\land\lnot c)\lor(c\land \lnot((a\land\lnot b)\lor(b\land\lnot a))) \\
        &= ((a\land\lnot b\land\lnot c)\lor(\lnot a\land b\land\lnot c))\lor(c\land((\lnot a\lor b)\land(\lnot b\lor a))) \\
        &= ((a\land\lnot b\land\lnot c)\lor(\lnot a\land b\land\lnot c))\lor(c\land((\lnot a\land\lnot b)\lor(\lnot a\land a)\lor(b\land\lnot b)\lor(b\land a))) \\
        &= ((a\land\lnot b\land\lnot c)\lor(\lnot a\land b\land\lnot c))\lor(c\land((\lnot a\land\lnot b)\lor(a\land b))) \\
        &= ((a\land\lnot b\land\lnot c)\lor(\lnot a\land b\land\lnot c))\lor((\lnot a\land\lnot b\land c)\lor(a\land b\land c)) \\
        &= (a\land\lnot b\land\lnot c)\lor(\lnot a\land b\land\lnot c)\lor(\lnot a\land\lnot b\land c)\lor(a\land b\land c)
\end{aligned}
```
is invariant under permutations of $a, b, c$.
As this implies the same for the left hand side, $(a\oplus b)\oplus c = (b\oplus c)\oplus a$, which proves associativity (given commutativity). $\qquad\square$

</details>

The quotient of $A$ by this equivalence relation will be denoted by $A/I$, which is the set $A$ after identifying $a$ with $b$ whenever $a\sim_I b$.
Equivalently, $A/I$ is the set of equivalence classes of $A$.

> #### Lemma 3.4.
> If $A$ is a Boolean algebra, and $I\subseteq A$ is an ideal, then the quotient $A/I$ inherits the structure of a Boolean algebra.

<details open>
<summary>Proof.</summary>

For $a\in A$, let $[a]$ denote its equivalence class in $A/I$.
Then, the putative Boolean algebra operations are given in the most natural way:
1. $[a]\land[b] := [a\land b]$
1. $[a]\lor[b] := [a\lor b]$
1. $\lnot[a] := [\lnot a]$

That these operations satisfy the axioms of a Boolean algebra is automatic.
What isn't automatic is that these operations are well-defined.

Suppose $a\sim_Ia'$, then we need to show that
1. $a\land b\sim_Ia'\land b$
1. $a\lor b\sim_Ia'\lor b$
1. $\lnot a\sim_I\lnot a'$

(Commutativity saves us from having to check more than this.)

These follow from generally useful facts about the symmetric difference operator.

```math
a + b = c
```

> #### Claim 3.4.i.
> Conjunction distributes over symmetric difference: $(a\oplus a')\land b = (a\land b)\oplus(a'\land b)$.

<details>
<summary>Proof.</summary>

```math
\begin{align*}
    (a\land b)\oplus(a'\land b) &= ((a\land b)\land\lnot(a'\land b))\lor(\lnot(a\land b)\land(a'\land b)) \tag{definition} \\
        &= (a\land b\land(\lnot a\lor\lnot b))\lor((\lnot a\lor\lnot b)\land a'\land b) \tag{de Morgan} \\
        &= ((a\land b\land\lnot a')\lor\underbrace{(a\land b\land\lnot b)}_{=\bot})\lor((\lnot a\land a'\land b)\lor\underbrace{(\lnot b\land a'\land b)}_{=\bot}) \tag{distributivity} \\
        &= (a\land b\land\lnot a')\lor(\lnot a\land a'\land b) \tag{$\bot$ is $\lor$ -neutral} \\
        &= ((a\land\lnot a')\lor(\lnot a\land a'))\land b \tag{distributivity} \\
        &= (a\oplus a')\land b \tag{definition}
\end{align*}
```
This completes the proof. $\qquad\square$

##
</details>

In particular, if $a\oplus a'\in I$, then

```math
(a\land b)\oplus(a'\land b) = \underbrace{(a\oplus a')}_{\in I}\land b \in I
```

shows that conjunction in $A/I$ is well-defined.

> #### Claim 3.4.ii.
> Disjunction anti-distributes over symmetric difference: $(a\oplus a')\land\lnot b = (a\lor b)\oplus(a'\lor b)$.

<details>
<summary>Proof.</summary>

```math
\begin{align*}
    (a\lor b)\oplus(a'\lor b) &= ((a\lor b)\land\lnot(a'\lor b))\lor(\lnot(a\lor b)\land(a'\lor b)) \tag{definition} \\
        &= ((a\lor b)\land\lnot a'\land\lnot b)\lor(\lnot a\land\lnot b\land(a'\lor b)) \tag{de Morgan} \\
        &= (a\land\lnot a'\land\lnot b)\lor\underbrace{(b\land\lnot a'\land\lnot b)}_{=\bot}\lor(\lnot a\land\lnot b\land a')\lor\underbrace{(\lnot a\land\lnot b\land b)}_{=\bot} \tag{distributivity} \\
        &= (a\land\lnot a'\land\lnot b)\lor(\lnot a\land\lnot b\land a') \tag{$\bot$ is $\lor$ -neutral} \\
        &= ((a\land\lnot a')\lor(\lnot a\land a'))\land\lnot b \tag{distributivity} \\
        &= (a\oplus a')\land\lnot b \tag{definition}
\end{align*}
```
This completes the proof. $\qquad\square$
##
</details>

In particular, if $a\oplus a'\in I$, then

```math
(a\lor b)\oplus(a'\lor b) = \underbrace{(a\oplus a')}_{\in I}\land\lnot b\in I
```

shows that disjunction in $A/I$ is well-defined.

> #### Claim 3.4.iii
> Negation transfers over symmetric difference: $(\lnot a)\oplus a' = a\oplus(\lnot a')$.

<details>
<summary>Proof.</summary>

```math
\begin{align*}
    (\lnot a)\oplus a' &= (\lnot a\land\lnot a')\lor(a'\land\lnot(\lnot a)) \tag{definition} \\
        &= (\lnot a\land\lnot a')\lor(a\land a') \tag{double negation}
\end{align*}
```
By commutativity, the last expression is invariant under swapping $a$ and $a'$, which implies the same for $(\lnot a)\oplus a'$. $\qquad\square$

##
</details>

In particular, if $a\oplus a'\in I$, then

```math
(\lnot a)\oplus(\lnot a') = a\oplus(\lnot\lnot a') = a\oplus a' \in I
```

This concludes the proof. $\qquad\square$

##
</details>


## 4. Non-atomic CBAs

Let $(X, \Sigma, \mu)$ be a measure space, and let $L(X) := \Sigma/\mu^{-1}(0)$, where $\mu^{-1}(0)$ is the ideal of null sets from [Lemma 3.3](#lemma-33).
By [Lemma 3.4](#lemma-34), $L(X)$ defines a Boolean algebra, where the conjunction and disjunction are inherited from the intersection and union of measurable sets.

> #### Theorem 4.1.
> Let $(X, \Sigma, \mu)$ be a measure space such that $X = \bigcup_{n=0}^\infty U_n$, where $U_n\in\Sigma$ and $\mu(U_n)\lt\infty$.
> (Such a measure space is called $\sigma$ -_finite_).
>
> Then, $L(X)$ is a complete Boolean algebra.

<details open>
<summary>Proof.</summary>

We need to show that $L(X)$ admits arbitrary suprema (disjunctions) and infima (conjunctions).
Although *finite* disjunctions and conjunctions in $L(X)$ are inherited from the natural union and intersection, only an [absolute buffoon](https://www.youtube.com/watch?v=SrltwGJAiCM&t=863s) would believe that it extends to arbitrary disjunctions and conjunctions (even if the underlying $\sigma$ -algebra is a complete Boolean algebra).

For organisation purposes, we prove this theorem through a sequence of claims.

> #### Claim 4.1.i.
> $L(X)$ has suprema for all countable chains.

<details>
<summary>Proof.</summary>

> [!INFO]
> In any partially-ordered set $(P,\preceq)$, a _chain_ in $P$ is a totally-ordered subset $C\subseteq P$, meaning for all $c_1,c_2\in C$, either $c_1\preceq c_2$ or $c_2\preceq c_1$.

Suppose
```math
[V_0]\preceq[V_1]\preceq[V_2]\preceq\cdots
```
is a countable chain in $L(X)$ (with chosen representatives in $\Sigma$ for each element, by countable choice).

Then, let $V := \bigcup_{n\geq0}V_n$.
We will show that $[V] = \sup_{n\geq0}[V_n]$.

Suppose $[U]\in L(X)$ satisfies $[V_n]\preceq[U]$ ---that is, $\mu(V_n\setminus U) = 0$ ---for every $n\geq0$.
Then,
```math
\begin{align*}
    \mu(V\setminus U) &= \mu\left(\left(\bigcup_{n\geq0}V_n\right)\setminus U\right) \\
        &= \mu\left(\bigcup_{n\geq0}(V_n\setminus U)\right) \\
        &\leq \sum_{n\geq0}\underbrace{\mu(V_n\setminus U)}_{=0} \\
        &= 0
\end{align*}
```
showing that $[V]\preceq[U]$ as well. $\qquad\square$

##
</details>

> #### Claim 4.1.ii.
> $L(X)$ has suprema for all well-ordered chains.

<details>
<summary>Proof.</summary>

Since $X$ is $\sigma$ -finite, write $X = \bigcup_{n\geq0}U_n$, where $U_n\in\Sigma$ with $\mu(U_n)\lt\infty$.
By replacing $U_n$ with $\bigcup_{m\leq n}U_m$, we may assume that $U_n\subseteq U_m$ for all $n\leq m$.

Let $C\subseteq L(X)$ be a well-ordered chain, meaning that there is some ordinal $\kappa$ such that $C = \{[V_\xi] \mid 0\leq \xi \lt \kappa\}$, where $[V_\xi]\preceq[V_\zeta]$ for every $\xi\leq\zeta$.
Using choice, fix representatives for each element of $C$ as well.

Let $V_\xi^n := V_\xi\cap U_n$.
We will first show that each $C^n := \{[V_\xi^n] \mid 0\leq\xi\lt\kappa\}$ admits a supremum.

Since each $V_\xi^n$ has finite measure, bounded by $\mu(U_n)$, let $\mu^n := \sup_{0\leq\xi\lt\kappa}\mu(V_\xi^n)\in\mathbb{R}$.
Now, for each finite $m\geq1$, let
```math
\xi_m^n := \inf\left\{0\leq\xi\lt\kappa ~\middle|~\mu(V_\xi^n)\geq\mu^n-\frac1m\right\}
```
Then, the $\xi_m^n$ index a countable monotone sequence in $C^n$.
By [Claim 4.1.i](#claim-41i), we can compute the supremum of this countable sequence as the equivalence class of the union $V^n := \bigcup_{m\geq0}V_{\xi_m^n}^n$.
We will show that $[V^n]=\sup(C^n)$, for which it suffices to prove that $[V^n]$ is an upper bound of $C^n$, as it is already a supremum of a subset of $C^n$.

If $\mu(V_\xi^n) \lt \mu^n$, then $\xi\leq\xi_m^n$ for some $m\gg0$, and therefore $[V_\xi^n]\preceq [V_{\xi_m^n}^n] \preceq [V^n]$.

On the other hand, if $\mu(V_\xi^n)=\mu^n$, then $\xi_m^n\leq\xi$ for every $m\geq1$, then $[V_{\xi_m^n}^n]\preceq [V_\xi^n]$ for each $m\geq1$, implying that $[V^n]\preceq [V_\xi^n]$.
In particular, $\mu(V^n) = \mu(V^n\setminus V_\xi^n) + \mu(V^n\cap V_\xi^n) = \mu(V^n\cap V_\xi^n)$.

This means
```math
\begin{align*}
    \mu^n = \mu(V_\xi^n) &= \mu(V_\xi^n\setminus V^n) + \mu(V_\xi^n\cap V^n) \\
        &= \mu(V_\xi^n\setminus V^n) + \mu(V^n) \tag{since $[V^n]\preceq[V_\xi^n]$} \\
        &\geq \mu(V_\xi^n\setminus V^n) + \mu(V_{\xi_m^n}^n) \quad \forall m\geq1 \\
        &\geq \mu(V_\xi^n\setminus V^n) + \mu^n - \frac1m \quad \forall m\geq1 \tag{definition of $\xi_m^n$} \\
\implies\qquad \mu(V_\xi^n\setminus V^n) &\leq \frac1m \quad \forall m\geq 1 \\
\implies\qquad \mu(V_\xi^n\setminus V^n) &= 0
\end{align*}
```
and therefore that $[V_\xi^n]\preceq[V^n]$.

This completes the proof that $[V^n]$ is an upper bound of $C^n$, and is thus its supremum.

Now, we have a countable chain of suprema $[V^n]$ in $L(X)$ for $n\geq0$.
By [Claim 4.1.i](#claim-41i) again, if $V := \bigcup_{n\geq0}V^n$, then $[V] = \sup_{n\geq0}[V^n]$ in $L(X)$.
We will show, finally, that $[V] = \sup(C)$ also.
Again, to this end, it suffices to show that $[V]$ is an upper bound of $C$, as it is already a supremum of elements that precede those of $C$.

Let $V_\xi \in C$.
Since $X = \bigcup_{n\geq0}U_n$, we have similarly that $V_\xi = \bigcup_{n\geq0}V_\xi^n$.
In particular, $[V_\xi] = \sup_{n\geq0}[V_\xi^n]$.
Since $[V_\xi^n]\preceq[V]$ for every $\xi$ and every $n$, it therefore follows that $[V_\xi]\preceq[V]$ as well, as desired. $\qquad\square$

##
</details>

> #### Claim 4.1.iii.
> $L(X)$ admits arbitrary suprema.

<details>
<summary>Proof.</summary>

> [!WARNING]
> I hope you like the axiom of choice! :smiley:

Let $S\subseteq L(X)$ be arbitrary.
By the axiom of choice, enumerate the elements of $S =: \{[V_\xi] \mid 0\leq\xi\lt\kappa\}$ with ordinals.

Construct a chain $([\tilde V_\xi])_{0\leq\xi\leq\kappa}$ as follows.

1. $[\tilde V_0] := [\varnothing]$.
1. Given $[\tilde V_\xi]$, define $[\tilde V_{\xi+1}] := [\tilde V_\xi]\lor [V_\xi]$.
1. For a limit ordinal $\lambda\leq\kappa$, if we have $[\tilde V_\xi]$ for every $\xi\lt\lambda$, then define $[\tilde V_\lambda] := \sup_{\xi\lt\lambda}[\tilde V_\xi]$ to be the supremum of the chain constructed thus far, by [Claim 4.1.ii](#claim-41ii).

An invariant of this construction is that $[\tilde V_\xi] = \sup_{\zeta\lt\xi}[V_\zeta]$ for every $\xi$.

In particular, $[\tilde V_\kappa] = \sup(S)$. $\qquad\square$
##
</details>

Combining [Claim 4.1.iii](#claim-41iii) with [de Morgan's laws](#lemma-24-de-morgans-laws), this concludes the proof that $L(X)$ is a complete Boolean algebra. $\qquad\square$

##
</details>

> #### Definition 4.2.
> Given a complete Boolean algebra $A$, an _atom_ is a minimal non-bottom element of $A$; that is, $a\in A$ is an atom if $a\neq\bot$, and whenever $a'\preceq a$, either $a'=\bot$ or $a'=a$.
>
> A complete Boolean algebra $A$ is called _atomic_ if every element of $A$ is the supremum of some set of atoms.

We are finally in a position to provide an example of a complete Boolean algebra that is not atomic.

> #### Example 4.3.
> Suppose $(X, \Sigma, \mu)$ is a $\sigma$ -finite measure space such that for every $U\in\Sigma$, there exists some measurable subset $V\subseteq U$ with $\mu(V) = \frac{\mu(U)}2$.
>
> Then, $L(X)$ has no atoms.

> [!INFO]
> An example of such a measure is the [Lebesgue measure](https://en.wikipedia.org/wiki/Lebesgue_measure) on $\mathbb{R}^n$.
