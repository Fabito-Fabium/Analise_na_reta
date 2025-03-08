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

1\) **_(Comutatividade da soma)_ Para cada $m, n \in \mathbb N$, temos
que $m+n = n+m$.**
<details>
<summary>Resolução.</summary>

Antes, considere a seguinte proposição:<br>
<br><br>
<strong>Proposição:</strong> Seja $m \in \mathbb N$, então $m+1 = 1+ m$.

<details>
<summary> Demonstração da proposição. </summary>

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

