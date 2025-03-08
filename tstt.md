
> # Fundamentos de Análise - Lista 1.

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

>1\) **_(Comutatividade da soma)_ Para cada $m, n \in \mathbb N$, temos
que $m+n = n+m$.**
<details>
<summary>Demonstração.</summary>

$a\land b\preceq a$ because $a\land(a\land b)=(a\land a)\land b = a\land b$.
Symmetrically, $a\land b\preceq b$ also.

If $c\preceq a$ and $c\preceq b$, then $a\land c=c$ and $b\land c=c$.
In particular, $(a\land b)\land c=a\land(b\land c)=a\land c=a$, meaning $c\preceq(a\land b)$ as well, showing that $a\land b$ is the greatest lower bound of $\{a,b\}$.

The argument for $a\lor b=\sup\{a, b\}$ is entirely dual. $\qquad\square$

##
</details>

