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

<strong> Dem: </strong> Da definição de soma em $ \mathbb Z $, temos que,

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

<details class="box"> <summary>Produto</summary> 
Considere as seguintes proposições:

<div class="box">
<b>Proposição 1: </b> Se $(a', b) \sim (a,b)$, então

$$
\begin{align*}
[(a,b)] \oplus [(c,d)] = [(a',b')] \oplus [(c,d)]
\end{align*}
$$

<details> <summary>Demonstração da proposição.</summary> 
Da hipótese, $a'+b = a+b'$, sendo assim,

$$
\begin{align*}
c+d&=c+d,\\
(c+d)(a'+b)&=(c+d)(a'+b),\quad
&&\text{(Lei do cancelamento do produto em $ \mathbb N $)}\\
c(a'+b) + d(a'+b) &= c(a'+b) + d(a'+b),\quad
&&\text{(Distributiva comutada em $ \mathbb N $)}\\
c(a+b') + d(a'+b) &= c(a'+b) + d(a+b'),\quad
&&\text{(Visto que $a'+b = a+b'$)}\\
(ca+cb') + (da'+db) &= (ca'+cb) + (da+db'),\quad
&&\text{(Distributiva em $ \mathbb N $)}\\
(ac+b'c) + (a'd+bd) &= (a'c+bc) + (ad+b'd),\quad
&&\text{(Comutatividade do produto em $ \mathbb N $)}\\
ac+(b'c + (a'd+bd)) &= a'c+(bc + (ad+b'd)),\quad
&&\text{(Associativa da soma em $ \mathbb N $)}\\
ac+((bd+a'd) + b'c) &= a'c+((b'd+ad)+bc),\quad
&&\text{(Comutatividade da soma em $ \mathbb N $)}\\
(ac+bd)+(a'd + b'c) &= (a'c+b'd)+(ad+bc),\quad
&&\text{(Associatividade da soma em $ \mathbb N $)}\\
(ac+bd,ad+bc)&\sim(a'd + b'c, a'c+b'd),\quad
&&\text{(Definição de $\sim$)}\\
[(ac+bd,ad+bc)]&=[(a'd + b'c, a'c+b'd)],\\
[(a,b)]\otimes[(c,d)] &= [(a',b')]\otimes[(c,d)].\quad
&&\text{(Definição do produto em $ \mathbb Z $)}
\end{align*}
$$

Com isto, temos o que queríamos. $\square$
</details> 
</div>

<div class="box">

<b>Proposição 2: </b> Se $(c, d) \sim (c',d')$, então

$$
\begin{align*}
[(a,b)]\otimes [(c, d)] = [(a,b)] \otimes [(c',d')]
\end{align*}
$$

<details> <summary>Demonstração da proposição.</summary> 
Da hipótese $c+d' = c'+d$, portanto, análogo a proposição anterior,

$$
\begin{align*}
a+b &= a+b,\\
(a+b)(c+d') &= (a+b)(c+d'),\\
a(c+d') + b(c+d') &= a(c+d') + b(c+d'),\\
a(c+d') + b(c'+d) &= a(c'+d) + b(c+d'),\\
(ac + ad')+(bc'+bd) &= (ac'+ad) +(bc + bd'),\\
(ac + ad')+(bc'+bd) &= (ac'+ad) +(bc + bd'),\\
(ac+bd) + (ad' +bc') &= (ac'+bd') + (ad + bc),\\
(ac+bd , ad + bc) &\sim (ac'+bd', ad' +bc'),\\
[(ac+bd , ad + bc)] &= [(ac'+bd', ad' +bc')],\\
[(a,b)] \otimes [(c,d)] &= [(a,b)] \otimes [(c',d')]. \\
\end{align*}
$$

Com isto, temos o que queríamos. $\square$
</details> 
</div>


<b>Dem: </b> De (I) e (II), temos que valem as proposições
anteriores, portanto, como

$$
\begin{align*}
[(a,b)]\otimes[(c,d)] = [(a',b')]\otimes[(c,d)],
\end{align*}
$$

e, reescrevendo a proposição 2, temos que

$$
\begin{align*}
[(a',b')]\otimes[(c,d)] = [(a',b')]\otimes[(c',d')],
\end{align*}
$$

da transitividade da igualdade de classes, temos que

$$
\begin{align*}
[(a,b)]\otimes[(c,d)] = [(a',b')]\otimes[(c',d')].
\end{align*}
$$

Como queríamos. $\square$

</details> 

</details> 

b) **Vale a comutatividade da soma e do produto.**
<details class="box"> <summary>Resolução.</summary> 

<details class="box"> <summary>Soma</summary> 
<strong> Dem: </strong> Ora, note que
$$
\begin{align*}
[(a,b)]\oplus[(c,d)] &= [(a+c, b+d)],\\
&=[(c+a, d+b)],\quad 
\text{(Comutatividade da soma em $ \mathbb N $)}\\
&=[(c,d)] \oplus [(a,b)]. \square
\end{align*}
$$
</details> 

<details class="box"> <summary>Produto</summary> 
<strong> Dem: </strong> Da definição de produto em $ \mathbb Z $,
$$
\begin{align*}
[(a,b)]\otimes[(c,d)] &= [(ac+bd, ad+bc)],\\
&=[(ca+db, da+cb)],\quad 
\text{(Comutatividade do produto em $ \mathbb N $)}\\
&=[(ca+db, cb+da)], \quad
\text{(Comutatividade da soma em $ \mathbb N $)}\\
&=[(c,d)] \otimes [(a,b)]. \square
\end{align*}
$$
</details> 


</details> 

c) **Vale a associatividade da soma e do produto.**
<details class="box"> <summary>Resolução.</summary>

Sejam $A, B, C \in \mathbb Z, $ tais que $A= [(a,b)] $,
$B = [(c,d)] $ e $C = [(e,f)] $.

<details class="box"> <summary>Soma</summary> 
<strong> Dem: </strong> 

Ora, da defnição de soma em $ \mathbb Z $ e 
das propriedades da soma em $ \mathbb N $
segue que,
$$
\begin{align*}
A \oplus ( B \oplus C) &= [(a,b)] \oplus [(c+e, d+f)],
\quad &&\text{(Definição da soma em $ \mathbb Z $)}\\
&= [(a+(c+e), b+(d+f))],
\quad &&\text{(Definição da soma em $ \mathbb Z$)}\\
&=[((a+c)+e, (b+d)+f)],
\quad &&\text{(Associatividade em $ \mathbb N $)}\\
&=[(a+c, b+d)]\oplus[(e,f)],\\
&=([(a,b)]\oplus[(c,d)])\oplus[(e,f)],\\
&=(A\oplus B) \oplus C.
\end{align*}
$$

Como queríamos. $\square$

</details> 

</details> 

d) **Vale a lei do cancelamento da soma e do produto.**
<details class="box"> <summary>Resolução.</summary> </details> 

e) **Vale a distributiva.**
<details class="box"> <summary>Resolução.</summary> </details> 

f) **Para qualquer $a,b \in \mathbb N $ tem-se que 
$ [(a, a)] = [(b, b)] $ é o elemento neutro da soma,
que será denotado por $0$.**
<details class="box"> <summary>Resolução.</summary> </details> 

g) **Para qualquer**