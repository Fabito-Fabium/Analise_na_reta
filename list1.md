---
layout: default
title: "Lista 1"
permalink: /list1/
---

#### Exercício 1:

**Como vimos, existe uma função injetora
    $s: \mathbb N \rightarrow \mathbb N$, tal que $s(n) = n+1$, em que
    $s(n)$ chama-se *sucessor* de $n$. A partir disso, podemos definir a
    operação *soma* em $\mathbb N$, que satisfaz a seguinte lei de
    recursão:**

>**s1) Para todo $n \in \mathbb N$, temos que $n+1 = s(n)$;**

>**s2) Para cada $m, n \in \mathbb N$, temos que
        $n + s(m) = s(n+m)$.**

**Também podemos definir a operação de produto em $\mathbb N$, que
satisfaz a seguinte lei de recursão:**

>**p1) Para todo $n\in \mathbb N$, temos que $n\cdot 1 = n$;**

>**p2) Para cada $m, n \in \mathbb N$, temos que
        $n\cdot s(m) = nm+n$.**

**Mostre que valem as seguintes propriedades:**

a\) **_(Comutatividade da soma)_ Para cada $m, n \in \mathbb N$, temos
que $m+n = n+m$.**
<div class="box">
<details>
<summary>Resolução.</summary>

Antes, considere a seguinte proposição:<br>
<br>
<p style="margin-left:2%; margin-right:2%;">
<strong>Proposição:</strong> Seja $m \in \mathbb N$, então $m+1 = 1+ m$.
</p>

<details style="margin-left:2%; margin-right:2%;">
<summary > Demonstração da proposição. </summary>

Considere $S \subset \mathbb N$ tal que, 
 
$$S = \{m \in \mathbb N; m+1=1+m\}.$$
Note que $1 \in S$, já que $(1) + 1 = 2 = 1 + (1)$;
 
Vejamos agora que $s(S) \subset S$. Seja $m \in S$, então:

$$
\begin{aligned}
  s(m)+1 &= (m+1) + 1, \quad &&\text{(Definição da função sucessor)}\\
  &= (1+m) + 1, \quad &&\text{(Visto que $m \in S$)} \\
  &= 1 + (m + 1), \quad &&\text{(Associatividade da soma em $\mathbb N$)}\\
  &= 1 + s(m). \quad &&\text{(Definição da função sucessor)}
\end{aligned} 
$$

Deste modo, já que $1 \in S$ e $s(S) \in S$, pelo Princípio da
Indução, temos que $S = \mathbb N$, como queríamos. $\square$
</details>
<br>
<strong>Dem:</strong> Considere $S \subset \mathbb N$ tal que
$S = \{m \in \mathbb N; m+n = n+m, n\in \mathbb N\}$. Da proposição anterior, temos que $1 \in S$, visto que $1 + n = n + 1$.
 Vejamos que $s(S) \subset S$. Tomando $m \in S$,

$$
\begin{align*}
  s(m)+n &= (m+1) + n, \quad &&\text{(Definição da função sucessor)}\\
  &= m + (1+n), \quad &&\text{(Associatividade da soma em $\mathbb N$)} \\
  &= m + (n+1), \quad &&\text{(Proposição anterior)}\\
  &= (m+n) + 1, \quad &&\text{(Associatividade da soma em $\mathbb N$)}\\
  &= (n + m) + 1, \quad &&\text{(Visto que $m \in S$)}\\
  &= n + (m+1), \quad &&\text{(Associatividade da soma em $\mathbb N$)}\\
  &= n + s(m). \quad&&\text{(Definição da função sucessor)}
\end{align*}
$$

Visto que $1 \in S$ e $s(S) \subset S$, pelo Princípio da Indução, temos $S=\mathbb N$
, como queríamos. $\square$

</details>
</div>

b) **_(Lei do cancelamento da soma)_ Para cada $m, n, p \in \mathbb N $, se $m+p = n+ p$, então $m=n$.**
<details>
<summary>Resolução.</summary>

<strong>Dem: </strong> Seja $S \subset \mathbb N $ tal que 

$$
\begin{align*}
S = \{p \in \mathbb N  ; (m+p=n+p) \implies m=n, \quad m,n 
\in \mathbb N \}.
\end{align*}
$$

Ora, $1 \in S$, já que, se $m+1 = n+1$, então $s(m) = s(n)$, e, como $s$ é injetora por definição, então $m=n$. Vejamos que $s(S) \subset S$. Toman
do $p \in S$ e $m+s(p) = n + s(p)$,

$$
\begin{align*}
  m+s(p)&=n+s(p),\\
  m+(p+1) &=n+(p+1), \quad &&\text{(Definição da função sucessor)}\\
  (m+p) + 1 &= (n+p) + 1, \quad &&\text{(Associatividade da soma em 
  $ \mathbb N $)}\\
  s(m+p)&=s(n+p), \quad &&\text{(Definição da função sucessor)}\\
  m+p &=n+p, \quad &&\text{(Injetividade da função sucessor)}\\
  m &= n. \quad &&\text{(Já que $p \in S$)}
\end{align*}
$$

Deste modo, como $1 \in S$ e $s(S) \subset S$, pelo Princípio da Indução, temos $S = \mathbb N $. $\square$

</details>

 c) **_(Comutatividade do produto)_ Para cada $m, n \in \mathbb N $, temos que $mn = nm$.**

<details> <summary>Resolução.</summary> 
Antes, considere as seguintes proposições:

<br>

<p style="margin-left:2%; margin-right:2%;" >
<strong> Proposição 1: </strong>  Seja $n \in \mathbb N $, 
$n\cdot 1 = 1 \cdot n$.
</p>

<details style="margin-left:2%; margin-right:2%;">
<summary>Demonstração da Proposição 1.</summary> 

Seja $T \subset \mathbb N$ tal que $T = \{n \in \mathbb N ; n\cdot 1
=1\cdot n\}$, queremos mostrar que $T = \mathbb N$. Ora, $1 \in T$, já que pela defini
ção do produto em $\mathbb N$, $(1)\cdot 1 = 1 = 1 \cdot(1)$. Vejamos que $s(T) \subset T$
. Tomando $n \in T$, temos que:


$$
\begin{align*}
  s(n)\cdot 1 &= s(n), \quad&&\text{(Definição do produto em $\mathbb N$)}\\
  &=n + 1, \quad&&\text{(Definição da função sucessor)}\\
  &=1\cdot n + 1, \quad&&\text{(Da definição do produto e sabendo que $n \in T$
  , $n = n\cdot 1 = 1 \cdot n$)}\\
  &= 1\cdot s(n). \quad &&\text{(Definição do produto em $\mathbb N$, $m\cdot s(n) = mn+m$)}
\end{align*}
$$
Portanto, como $1 \in T$ e $s(T) \subset T$, segue do Princípio da Indução que $T=\mathbb N$
. $\square$

</details>


<p style="margin-left:2%; margin-right:2%;">
<strong> Proposição 2: </strong>  (Distributiva comutada) 
Para cada $m, n, p \in \mathbb N $, temos que 
$$(n+p)m = nm+pm.$$
</p>

<details style="margin-left:2%; margin-right:2%;" > 
<summary>Demonstração da Proposição 2.</summary> 

 Considere $R=\{m \in \mathbb N ; (n+p)m = nm + pm, \quad n,p \in \mathbb N \}$
 . Note que $1 \in R$, visto que, da definição de produto, $(n+p)\cdot 1 = n + p = n\cdot 1 + p\cdot 1$. Vejamos que $s(R) \subset R$. Assumindo $
m \in R$, temos que:

$$
\begin{align*}
  (n+p)s(m) &= (n+p)m + (n+p), \quad &&\text{(Definição do produto em $\mathbb N$)}\\
  &= (nm + pm) + (n+p), \quad &&\text{(Visto que $m \in R$, $(n+p)m = nm + pm$)}\\
  &= nm + (pm + (p+n)), \quad &&\text{(Associatividade e comutatividade da soma em $
  \mathbb N$)}\\
  &= nm + (n + (pm + p)), \quad &&\text{(Associatividade e comutatividade da soma em $
  \mathbb N$)}\\
  &= (nm + n) + (pm + p), \quad &&\text{(Associatividade da soma em $\mathbb N$)}\\
  &= n\cdot s(m) + p \cdot s(m). \quad &&\text{(Definição do produto em $\mathbb N$)}
\end{align*}
$$

Sendo assim, já que $1 \in R$ e $s(R) \subset R$, 
segue do Princípio da Indução que $R = \mathbb N$. $\square$

</details> 
<br>

<strong> Dem: </strong>  Seja $S = \{n \in \mathbb N  | m\cdot n = n \cdot m, \quad m \in \mathbb N \}$.
 Vejamos que $S = \mathbb N$. Da proposição 1, temos que $1 \in S$. Para verificar que $s(S) 
\subset S$, suponhamos que $n \in S$, tendo assim:

$$
\begin{align*}
  m\cdot s(n) &= mn + m, \quad &&\text{(Definição do produto em $\mathbb N$)}\\
    &= nm + m, \quad &&\text{(Visto que $n \in S$, $mn = nm$)}\\
    &= nm + 1m, \quad &&\text{(Da proposição 1, $m=m\cdot 1 = 1 \cdot m$)}\\
    &= (n + 1)m, \quad &&\text{(Distributiva comutada)}\\
    &= s(n) \cdot m. \quad &&\text{(Definição da função sucessor)}
\end{align*}
$$

Deste modo, como $1 \in S$ e $s(S) \subset S$, do Princípio da Indução, temos q
ue $S = \mathbb N $, como queríamos. $\square$

</details> 