::: ceqn
$$\begin{aligned}
            \BODY
        
\end{aligned}$$
:::

\[1\]

::: ceqn
$$\begin{aligned}
			\BODY \tag{#1}
		
\end{aligned}$$
:::

1.  **Como vimos, existe uma função injetora
    $s: \mathbb N \rightarrow \mathbb N$, tal que $s(n) = n+1$, em que
    $s(n)$ chama-se *sucessor* de $n$. A partir disso, podemos definir a
    operação *soma* em $\mathbb N$, que satisfaz a seguinte lei de
    recursão:**\

    -   **Para todo $n \in \mathbb N$, temos que $n+1 = s(n)$;**

    -   **Para cada $m, n \in \mathbb N$, temos que
        $n + s(m) = s(n+m)$.**

    **Também podemos definir a operação de produto em $\mathbb N$, que
    satisfaz a seguinte lei de recursão:**\

    -   **Para todo $n\in \mathbb N$, temos que $n\cdot 1 = n$;**

    -   **Para cada $m, n \in \mathbb N$, temos que
        $n\cdot s(m) = nm+n$.**

    **Mostre que valem as seguintes propriedades:**

    1.  **(Comutatividade da soma) Para cada $m, n \in \mathbb N$, temos
        que $m+n = n+m$.**\
        Antes, considere a seguinte proposição:\
        ..\
        **Proposição:** Seja $m \in \mathbb N$, então $m+1 = 1+ m$.\
        **Demonstração da proposição:** Considere $S \subset \mathbb N$
        tal que, $S = \{m \in \mathbb N
        ; m+1=1+m\}$. Note que $1 \in S$, já que
        $(1) + 1 = 2 = 1 + (1)$; Vejamos agora que $s(S) \subset S$.
        Seja $m \in S$, então:

        ::: ceqnalign*
        s(m)+1 &= (m+1) + 1, &&\
        &= (1+m) + 1, &&\
        &= 1 + (m + 1), &&\
        &= 1 + s(m). &&
        :::

        Deste modo, já que $1 \in S$ e $s(S) \in S$, pelo Princípio da
        Indução, temos que $S = \mathbb N$, como queríamos. $\square$\
        ..\
        **Dem:** Considere $S \subset \mathbb N$ tal que
        $S = \{m \in \mathbb N; m+n = n+m, n\in \mathbb N\}$. Da
        proposição anterior, temos que $1 \in S$, visto que
        $1 + n = n + 1$. Vejamos que $s(S) \subset S$. Tomando
        $m \in S$,\

        ::: ceqnalign*
        s(m)+n &= (m+1) + n, &&\
        &= m + (1+n), &&\
        &= m + (n+1), &&\
        &= (m+n) + 1, &&\
        &= (n + m) + 1, &&\
        &= n + (m+1), &&\
        &= n + s(m). &&
        :::

        Visto que $1 \in S$ e $s(S) \subset S$, pelo Princípio da
        Indução, temos $S=\mathbb N$, como queríamos. $\square$\

    2.  **(Lei do cancelamento da soma) Para cada
        $m, n, p \in \mathbb N$, se $m+p = n+ p$, então $m=n$.**\

    3.  **(Comutatividade do produto) Para cada $m, n \in \mathbb N$,
        temos que $mn = nm$.**\
        \

    4.  **(Distributividade) Para cada $m,n,p \in \mathbb N$, temos que
        $m(n+p) = mn + mp$.**\
        \

    5.  **(Lei do cancelamento do produto) Para cada
        $m,n,p \in \mathbb N$, se $mp=np$, então m=n.**\

    6.  **(Unicidade da identidade do produto) Para todo
        $n \in \mathbb N$, se $mn = n$, então $m = 1$**\
        \

2.  **Sejam $m, n, p \in \mathbb N$. Mostre que**

    1.  **Se $m \le n$ e $n < p$, então $m < p$.**\
        \

    2.  **Se $m < n$ e $n \le p$, então $m < p$.**\
        \

    3.  **Se $m \le n$ e $n \le p$, então $m \le p$.**\
        \
