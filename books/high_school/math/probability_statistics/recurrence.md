# Recorrências

# Sequências

Para entendermos o que são recorrências, primeiro temos que saber o que são <b>sequências</b>. 

Uma <b>sequência</b> é definida como uma função $f:\mathbb{N} \to \mathbb{R}$. Assim, se chamarmos cada termo $f(n)$ por $a_n$, podemos dizer que uma sequência é uma lista organizada no formato $(a_1, a_2, ..., a_n, ...)$. É importante deixar claro que as sequências podem ser finitas ou infinitas. 

Várias sequências são bem conhecidas, temos, por exemplo, os números naturais, os números pares e também os números ímpares.

$$
\begin{array}{c}
    N=(1, 2, 3, 4, ...) \\
    P=(0, 2, 4, 6, 8, ...) \\
    I=(1, 3, 5, 7, 9, ...) \\
\end{array}
$$

# Recorrências

Uma <b>recorrência</b> é definida como uma expressão matemática que relaciona o próximo termo de uma sequência com os termos anteriores. 

Por meio das recorrências, podemos classificar as mais variadas sequências que possuem comportamentos previsíveis. Dentre elas, temos dois tipos notáveis: as <b>progressões aritméticas</b> e as <b>progressões geométricas</b>. 

As <b>progressões aritméticas</b> são geradas quando somamos um número $r$ no termo atual $a_n$ para obter o próximo termo, $a_{n+1}$. Por exemplo, as sequências dos números naturais, dos pares e dos ímpares são progressões aritméticas.

As <b>progressões geométricas</b>, por sua vez, são construídas quando multiplicamos um número $r$ no termo atual $g_n$, para assim gerarmos o próximo termo, $g_{n+1}$. Por exemplo, a sequência das potências naturais de dois é uma progressão geométrica. 

## Resolvendo recorrências

<b>Resolver uma recorrência</b> significa encontrar uma expressão fechada que nos fornece qualquer termo da sequência a partir do termo inicial. Embora possamos resolver progressões aritméticas e geométricas de uma maneira bem direta, nem todas as recorrências possuem essa facilidade. 

Como podemos <b>resolver uma progressão aritmética</b>? Um método interessante é a utilização das chamadas "somas telescópio". Vamos encontrar uma solução geral para uma progressão aritmética dessa forma: 

<aside>

Primeiro, é necessário escrever todos os termos da sequência, partindo de $a_2$  até chegar em $a_n$, com equações mostrando qual o seu valor. 

$$
\begin{align*}
    a_2 &= a_1+r \\
    a_3 &= a_2+r \\
    a_4 &= a_3+r \\
    &(...) \\
    a_{n-1} &= a_{n-2}+r \\
    a_n &= a_{n-1}+r
\end{align*}
$$

Depois disso, soma-se todas as equações, cancelando os termos conforme necessário.

$$
a_2=a_1+r\\a_3=a_2+r\\a_4=a_3+r\\(...)\\a_{n-1}=a_{n-2}+r\\a_n=a_{n-1}+r
$$

Por fim, uma expressão geral é obtida no final do processo.

$$
a_{n}=a_1+(n-1)r
$$

</aside>

Ou seja, agora podemos saber qualquer termo de uma progressão aritmética sabendo o termo inicial e a razão ($r$) da progressão, o número que somando o termo atual produz o próximo termo.

Agora, como podemos encontrar a solução de uma progressão geométrica? Um raciocínio semelhante ao utilizado na solução da progressão aritmética pode ser empregado, chegando, por fim, na expressão abaixo: 

$$
g_n=g_1\cdot q^{n-1}
$$

Um fato interessante é que podemos deduzir uma fórmula para nos dar a soma dos primeiros $n$ termos de uma P.G. que tem sua razão $q$, diferente de 1:  

$$
S_n=g_1\cdot\dfrac{q^n-1}{q-1}
$$