---
layout: default
title: "Lista 2"
permalink: /list2/
---


Exercícios: <a href="#ex1">1</a>

<p id="ex1"> </p>

#### Exercício 1:

**Considere as seguintes operações definidas em $ \mathbb Z $.**

<li><b>Soma: Para cada $A,B \in \mathbb Z $, tal que 
$A = [(a,b)]$ e $B = [(c, d)],$
</b></li> 

$$
\begin{align*}
A \oplus B = [(a+c, b+d)];
\end{align*}
$$

<li><b> Produto: Para cada $A,B \in \mathbb Z $, tal que 
$A = [(a,b)]$ e $B = [(c, d)],$
</b></li>

$$
\begin{align*}
A \otimes B = [(a+c, b+d)];
\end{align*}
$$

**Mostre que:**

a) **As operações de soma e produto estão bem-definidas.**
<details class="box"> <summary>Resolução.</summary> 

Sejam $(a',b') \in [(a,b)] = A $ e 
$ (c',d') \in [(c, d)] = B $, representantes das classes
$A$ e $B$, respectivamente. <br>

Como $(a',b')$ é representante
de $A$, então $(a',b') \sim (a, b)$, isto é
$a'+b = a+b'$, (I). Analogamente,
temos que $ c'+d = c+d' $, (II).

<details class="box"> <summary> Soma </summary>

Da definição de soma em $ \mathbb Z $, temos que,

$$
\begin{align*}
[(a,b)] \oplus [(c,d)] = [(a+c, b+d)].
\end{align*}
$$

Note que, somando as expressões (I) e (II), segue que,

$$
\begin{align*}
(a'+b) + (c'+d) &= (a+b') + (c+d'),\quad 
&&\text{(I) + (II)}\\
a'+(b + (c'+d)) &= a+(b' + (c+d')), \quad 
&&\text{(Associatividade da soma em $ \mathbb N $)}\\
a'+((c'+d) + b) &= a+((c+d') + b'), \quad
&&\text{(Comutatividade da soma em $ \mathbb N $)}\\
a'+(c'+(d + b)) &= a+(c+(d' + b')), \quad
&&\text{(Associatividade da soma em $ \mathbb N $)}\\
(a'+c')+(d + b) &= (a+c)+(d' + b'), \quad
&&\text{(Associatividade da soma em $ \mathbb N $)}\\
(a'+c')+(b+d) &= (a+c)+( b' + d'), \quad
&&\text{(Comutatividade da soma em $ \mathbb N $)}\\
[a'+c', b' + d'] &\sim [a+c, b+d], \quad
&&\text{(Definição de $\sim$)}\\
[(a'+c', b' + d')] &= [(a+c, b+d)],\\
[(a',b')]\oplus[(c',d')] &= [(a,b)]\oplus[(c,d)]. \quad
&&\text{(Definição da soma em $ \mathbb Z $)}\\
\end{align*}
$$
Com isto, segue que a soma é bem-definida. $\square$
</details> 

</details> 

b) **Vale a comutatividade da soma e do produto.**
<details class="box"> <summary>Resolução.</summary> </details> 

c) **Vale a associatividade da soma e do produto.**
<details class="box"> <summary>Resolução.</summary> </details> 

d) **Vale a lei do cancelamento da soma e do produto.**
<details class="box"> <summary>Resolução.</summary> </details> 

e) **Vale a distributiva.**
<details class="box"> <summary>Resolução.</summary> </details> 

f) **Para qualquer $a,b \in \mathbb N $ tem-se que 
$ [(a, a)] = [(b, b)] $ é o elemento neutro da soma,
que será denotado por $0$.**
<details class="box"> <summary>Resolução.</summary> </details> 

g) **Para qualquer**