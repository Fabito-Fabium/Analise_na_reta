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
<div class="box">
<strong>Proposição:</strong> Seja $m \in \mathbb N$, então $m+1 = 1+ m$.
<details>
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
</div>

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
<details class="box">
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

<details class="box"> <summary>Resolução.</summary> 
Antes, considere as seguintes proposições:

<div class="box">
<strong> Proposição 1: </strong>  Seja $n \in \mathbb N $, 
$n\cdot 1 = 1 \cdot n$.

<details>
<summary>Demonstração da Proposição 1.</summary> 

Seja $T \subset \mathbb N$ tal que $T = \{n \in \mathbb N ; n\cdot 1
=1\cdot n\}$, queremos mostrar que $T = \mathbb N$. Ora, $1 \in T$, 
já que pela definição do produto em $\mathbb N$, $(1)\cdot 1 = 
1 = 1 \cdot(1)$. Vejamos que $s(T) \subset T$.
 Tomando $n \in T$, temos que:


$$
\begin{align*}
  s(n)\cdot 1 &= s(n), \quad&&\text{(Definição do produto em $\mathbb N$)}\\
  &=n + 1, \quad&&\text{(Definição da função sucessor)}\\
  &=1\cdot n + 1, \quad&&\text{(Da definição do produto e sabendo que $n
   \in T$  , $n = n\cdot 1 = 1 \cdot n$)}\\
  &= 1\cdot s(n). \quad &&\text{(Definição do produto em $\mathbb N$, $m\cdot s(n) = mn+m$)}
\end{align*}
$$
Portanto, como $1 \in T$ e $s(T) \subset T$, segue do Princípio da Indução que $T=\mathbb N$. $\square$

</details>
</div>

<div class="box">
<strong> Proposição 2: </strong>  <i>(Distributiva comutada)</i> 

Para cada $m, n, p \in \mathbb N $, temos que 
$$(n+p)m = nm+pm.$$

<details> 
<summary>Demonstração da Proposição 2.</summary> 

 Considere $R=\{m \in \mathbb N ; (n+p)m = nm + pm, \quad n,p 
 \in \mathbb N \}$. Note que $1 \in R$, visto que, da definição de produto,
  $(n+p)\cdot 1 = n + p = n\cdot 1 + p\cdot 1$. Vejamos que $s(R) 
  \subset R$. Assumindo $m \in R$, temos que:

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
</div>
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

d) **_(Distributividade)_ Para cada $m,n,p \in \mathbb N $, 
temos que $m(n+p) = mn + mp$.**

<details class="box"> <summary>Resolução.</summary>

<strong> Dem: </strong>  Ora, da <i>distributiva comutada</i>, demonstrada no item anterior, temos que, para cada 
$m,n,p \in \mathbb N $, $(n+p)m = nm +pm$. Portanto,
$$
\begin{align*}
  m(n+p) &= (n + p)m, \quad &&\text{(Comutatividade do produto 
  em $ \mathbb N $)}\\
  &= nm + pm, \quad &&\text{(Distributiva comutada)}\\
  &= mn + mp. \quad &&\text{(Comutatividade do produto em $ \mathbb N $)}
\end{align*}
$$

Com isto, temos o que queríamos. $\square$

</details> 

e) **_(Lei do cancelamento do produto)_ Para cada $m,n,p \in \mathbb N $, se $mp=np$, então m=n.**

<details class="box"> <summary>Resolução.</summary> 

Antes, mostraremos a unicidade da identidade do produto em $ \mathbb N $.

<div class="box">

<strong> Proposição: </strong>  <i>(Unicidade da identidade do produto)</i> 
Para todo $n \in N$, se $mn = m$, então $m = 1$

<details> 
<summary>Demonstração da proposição:</summary> 

 A fim de absurdo, 
suponhamos que $m \neq 1$, isto é, existe $k \in \mathbb N $
tal que $m = s(k)$, 
ou seja $mn = n$ pode ser reescrito como:

$$
\begin{align*}
  n &= s(k) \cdot n,\\
  &= n\cdot s(k), \quad &&\text{(Comutatividade do produto em 
  $ \mathbb N $)}\\
  &= nk + n. \quad &&\text{(Definição do produto em 
  $ \mathbb N $)} \tag{$\star$}
\end{align*}
$$

Porém, como visto em aula, para cada $x,y \in \mathbb N $, $x\neq x + y$,
 sendo assim, ($\star$) é um absurdo. Deste modo, temos o que queríamos.
$\square$
</details> 

</div>

<br>
<strong> Dem: </strong>  Considere os conjuntos 

$$
\begin{align*}
S=&\{p \in \mathbb N 
 ; mp = np \implies m = n, \quad m,n \in \mathbb N \}, \\
 T =& \{m \in \mathbb N  ; mp=np\implies m=n,\quad n \in 
 \mathbb N , p\in S\}.
\end{align*}
$$

 Por construção, segue que $T \subset S$. 
Ora, $1 \in T$, já que, da 
unicidade da identidade no produto e da proposição 1 do item c, 
$1\cdot p = np \implies n = 1$. Vejamos que $s(T) \subset T$, 
supondo que $m \in T$ e escolhendo $n \in \mathbb N $ e $p \in S$
 de tal forma que $s(m)p = np$, queremos mostrar que $s(m) = n$,
  sendo assim,

$$
\begin{align*}
  s(m) p &= np,\\
  p\cdot s(m) &= pn, \quad &&\text{(Comutatividade do produto 
  em $ \mathbb N $)}\\
  pm + p &= pn. \quad &&\text{(Definição do produto 
  em $ \mathbb N $)} \tag{1}
\end{align*}
$$

Note que, se $n = 1$, $p = p + pm$, o que por $(\star)$, teremos um absurdo. Portanto $n \neq 1$, ou seja, existe 
$\omega \in \mathbb N $ tal que 
$n = s(\omega)$. Sendo assim, (1) pode ser reescrito da seguinte forma:

$$
\begin{align*}
  pm + p &= pn = p\cdot s(\omega),\\
  pm + p &= p\omega + p, \quad &&\text{(Definição do produto em 
  $ \mathbb N $)}\\
  pm &= p\omega, \quad &&\text{(Lei do cancelamento da soma 
  em $ \mathbb N $)}\\
  mp &= \omega p, \quad &&\text{(Comutatividade do produto 
  em $ \mathbb N $)} \\
  m &= \omega, \quad &&\text{(Já que $p \in S$ e $m \in T$)}\\
  s(m) &= s(\omega), \quad && \text{(Injeção da função sucessor)}\\
  s(m) &= n. \quad &&\text{(Já que $n = s(\omega)$)}
\end{align*}
$$
Dito isto, já que como $1 \in T$ e $s(T) \subset T$, segue do Princípio da Indução que $T = \mathbb N $, mais ainda, $T \subset S \subset \mathbb N $, 
mas como $T = \mathbb N $
, segue que $S= \mathbb N $, como queríamos. $\square$
</details>

f) **_(Unicidade da identidade do produto)_ Para todo $n \in \mathbb N $,
se $mn = n$, então $m = 1$.**

<details class="box"> <summary>Resolução.</summary> 
Demonstrado como proposição em (1e).
</details> 

#### Exercício 2:

**Sejam $m, n, p \in \mathbb N $. Mostre que:**

a) **Se $m \le n$ e $n < p$, então $m < p$.**
<details class="box"> <summary>Resolução.</summary> 

<strong> Dem: </strong>  Da hipótese, temos que $n < p$, isto é, 
$p = n + k$ para algum $k \in \mathbb N $. Ademais, 
$m \le n \equiv (n = m) \lor (n = m + \omega)$ para 
algum $\omega \in \mathbb N $. Com isto,
 suponhamos que $n = m$, portanto $p = n + k = m +k$, isto é $m < p$; 
 Agora, suponhamos que $n = m + \omega$,
$$
\begin{align*}
  p &= n + k, \quad &&\text{(Da hipotese)}\\
  &= (m + \omega) + k, \quad &&\text{(Visto que $n = m+ \omega$)}\\
  &= m + (\omega + k) = m + k_1, \quad &&k_1 \in \mathbb N 
\end{align*}
$$
Isto é, $m < p$.

Em resumo, temos que,

$$(n = m) \land (n<p) \implies m < p,$$
e também
$$(m < n) \land (n<p)\implies m < p.$$
Portanto, das propriedades dos conectivos lógicos e tendo em mente
que para cada $a, b \in \mathbb N $, $a<b$, $a>b$ ou $a=b$, exclusivamente,
então,

 $$(m \le n) \land (n < p) \implies m < p.$$
 
 Como queríamos. $\square$ 
</details>
