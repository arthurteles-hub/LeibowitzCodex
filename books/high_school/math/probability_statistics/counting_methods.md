# Outros Métodos de Contagem

# Princípio da inclusão-exclusão

O <b>princípio da inclusão-exclusão (PIE)</b> nos dá uma relação matemática para encontrar o número de elementos de dois ou mais conjuntos que não são necessariamente disjuntos (ou seja, possuem uma <b>intersecção</b>). 

Na sua forma mais simples, temos dois conjuntos, $A$ e $B$: 

$$
|A\cup B|=|A|+|B|-|A \cap B|
$$

O que isso nos diz é que o número de elementos da união dos dois conjuntos é igual a soma dos elementos em cada conjunto, menos a sua intersecção (ou seja, menos as “repetições”). Podemos ilustrar isso num Diagrama de Venn. 

Esse raciocínio pode ser aplicado para qualquer número de conjuntos que quisermos e, por conta disso, esse princípio é generalizado pela expressão abaixo. 

Para os conjuntos $A_1, A_2, A_3, ... A_n$, temos que a cardinalidade de sua união é dada por:

$$
\begin{align*}
    \left|\bigcup^n_{i=1}A_i\right|&=\sum^n_{i=1}|A_i|-\sum^n_{1\le i\lt j \le n}|A_i\cap A_j| \\\\
    &+\sum^{n}_{1 \le i \lt j \lt k \le n}|A_i \cap A_j \cap A_k|-... +(-1)^{n+1}|A_1\cap ... \cap A_n|
\end{align*}
$$

Traduzindo isso para uma linguagem comum, seria basicamente um “bota-tira”, que é justamente o nome do princípio: primeiro se soma todos os elementos, depois retira-se a intersessão, depois coloca o que foi retirado mais de uma vez, depois retira-se o excesso e assim por diante, até que todos os conjuntos estejam contados apenas uma vez. 

Uma curiosidade sobre o $(-1)^{n+1}$ no final é que, se $n$ for par, o final seria uma subtração, caso contrário, será uma adição, ou seja, o $(-1)^{n+1}$ é basicamente uma “condicional” para o final do algoritmo. Isso pode ser visto no exemplo abaixo: como $n=3$, $n+1=4$, o que nos informa que o último passo é uma soma, o que é verdade.

![](https://upload.wikimedia.org/wikipedia/commons/3/3d/Inclusion-exclusion-3sets.png)

<i>Ilustração do princípio da inclusão-exclusão para três conjuntos. Domínio público, via <a href="https://commons.wikimedia.org/wiki/File:Inclusion-exclusion-3sets.png" target="_blank">Wikimedia Commons</a>.</i>

# Lemas de Kaplansky

Os <b>lemas de Kaplansky</b> nos dão uma maneira de responder as seguintes perguntas: de quantas maneiras podemos formar um subconjunto com k elementos do conjunto $\{1, 2, 3, ..., n\}$ de forma que não haja números consecutivos? E se $1$ e $n$ forem consecutivos, também?

Um detalhe interessante para se ter em mente é a definição de um <b>lema matemático</b>: também conhecido como <b>teorema auxiliar</b>, um lema é um teorema menor que é provado com o objetivo de servir de fundamento para a justificativa de algo mais extenso.

No caso de Kaplansky, isso era o <a target="_blank" href="https://clubes.obmep.org.br/blog/wp-content/uploads/2024/02/F_A-solu%C3%A7%C3%A3o-de-Kaplansky-para-o-problema-de-Lucas.pdf">Problema de Lucas</a>.

## O primeiro lema

Esse lema responde a primeira pergunta e, para entendê-lo vamos fazer um exemplo.

De quantas maneiras podemos escolher um subconjunto de três elementos do conjunto $A=\{1, 2, 3, 4, 5, 6\}$ de forma que não haja elementos consecutivos?

Ora, temos os seguintes subconjuntos: 

$$
\{1, 3, 5\}, \{1, 3, 6\}, \{1, 4, 6\}, \{2, 4, 6\}
$$

Porém, podemos nos utilizar de uma abstração para não precisar contar “na mão” todos os subconjuntos possíveis: zeros e uns. 

Substituindo cada número que foi colocado no subconjunto por um $1$ e cada número que não está no conjunto por um $0$, temos que os subconjuntos acima podem ser expressos assim: 

$$
\begin{array}{c}
    \{1, 3, 5\} = 101010 \\\\
    \{1, 3, 6\} = 101001 \\\\ 
    \{1, 4, 6\} = 100101 \\\\
    \{2, 4, 6\} = 010101    
\end{array}
$$

Ou seja, no primeiro exemplo temos que o primeiro número do conjunto $A$ está no subconjunto, o segundo não está, o terceiro está e assim por diante. Isso é uma **bijeção** entre os conjuntos: cada elemento do conjunto dos zeros e uns possui relação com apenas um elemento dos subconjuntos. 

Assim, para resolver o problema, precisamos colocar os uns e zeros de forma que eles não estejam consecutivos. Primeiro, colocamos os zeros: 

$$
[-][0][-][0][-][0][-]
$$

Agora, temos quatro espaços para colocar três uns: dois espaços entre os zeros e dois espaços no começo e no final. Isso pode parecer estranho, mas é importante perceber que $101010$ e $010101$ são “os mesmos” subconjuntos, porém com o “1” da frente deslocado para a última posição, ou seja, os elementos “dos cantos” podem assumir ambas as posições, dando +1 espaço disponível.

Assim, de quantas maneiras podemos escolher três espaços de quatro disponíveis? $\binom{4}{3}$.

Logo, temos $\binom{4}{3} = \dfrac{4!}{(4-3)!3!}=\dfrac{4\times3!}{3!}=4$ maneiras de escolher os “uns”, o que nos dá quatro subconjuntos possíveis de serem formados, o que é a resposta, como vimos acima! 

Podemos generalizar esse raciocínio para qualquer $k$ e $n$, de forma que $k\le n$, o que nos dá a expressão para o Primeiro Lema.

<aside>

O número de subconjuntos de $k$ elementos do conjunto $\{1, 2, 3, ... , n\}$ que não há elementos consecutivos é dado por:

$$
f(n,k)=\binom{n-k+1}{k}
$$

</aside>

É importante perceber que o $+1$ da expressão vem do que foi explicado acima: sempre teremos um espaço a mais para colocar um “1” e ainda obter um subconjunto válido. 

### Generalização

O primeiro lema pode ser generalizado, respondendo a pergunta: De quantas maneiras podemos montar um subconjunto de $k$ elementos de $\{1, 2, 3, ..., n\}$ de modo que a cada dois números escolhidos, haja pelo menos $r$ elementos não escolhidos para o subconjunto?

Para montar essa generalização, primeiro temos que colocar os $n-k$ zeros em sequência, formando $k+1$ espaços. Definindo $x_1$ como sendo a quantidade de uns que vamos colocar no primeiro espaço, $x_2$ como sendo a quantidade do segundo espaço e assim por diante, temos a seguinte equação: 

$$
x_1+x_2+...+x_k+x_{k+1}=n-k
$$

Utilizando algumas substituições, chegamos a equação equivalente: 

$$
y_1+y_2+...+y_{p+1}=n-p-pr-r
$$

Encontrando finalmente que a quantidade de soluções inteiras não negativas é dada por: 

$$
h(n,k)=\binom{n-(k-1)r}{k}
$$

Essa expressão é útil pois, ao invés de estarmos limitados a responder a pergunta para elementos não consecutivos, ou seja, pelo menos um elemento, podemos agora encontrar respostas para pelo menos dois elementos, três… enfim, quantos elementos nós quisermos. 

## O segundo lema

O segundo lema pode ser entendido como uma “evolução” do primeiro: agora, não queremos apenas saber a quantidade de subconjuntos que não possuem elementos consecutivos, mas sim entender isso num contexto circular. Esse lema explora o caso quando $n$ e $1$ são considerados consecutivos no conjunto $\{1, 2, 3, 4, ..., n\}$. 

Para provar o segundo lema, vamos nos utilizar de um argumento combinatório. 

Pelo príncípio aditivo, sabemos que a quantidade total de subconjuntos será a soma da quantidade de subconjuntos com o “1” presente nele com a quantidade de subconjuntos em que o “1” não está presente. 

No primeiro caso, teremos que escolher $k-1$ elementos dentre $n-3$, já que como o “1” já foi escolhido, só precisamos escolher outros $k-1$. Além disso, como o “1” está no subconjunto, $2$ e $n$ não podem estar nele, já que são consecutivos do “1”. 

Ou seja, temos que a quantidade de subconjuntos que temos essas condições é 

$$
f(n-3, k-1)=\binom{n-k-1}{k-1}
$$

No segundo caso, temos que escolher $k$ elementos dentre o conjunto $\{2, 3, 4, ..., n\}$, ou seja, é um caso ordinário, porém sem o primeiro elemento. Logo, o número de subconjuntos nesse caso é:

$$
f(n-1, k)=\binom{n - k}{k}
$$

Assim, somando os dois casos, temos que: 

$$
\begin{align*}
    \binom{n - k - 1}{k - 1}+\binom{n - k}{k}&=\dfrac{(n-k-1)!}{(k-1)!(n-2k)!}+\dfrac{(n-k)!}{k!(n-2k)!} \\\\
    &=\dfrac{(n-k-1)!k+(n-k)!}{k!(n-2k)!} \\\\
    &=(n-k-1)!\cdot\dfrac{k+(n-k)}{k!(n-2k)!} \\\\
    &=n\dfrac{(n-k-1)!}{k! \cdot(n-2k)!} \\\\
    &=\dfrac{n}{n-k}\cdot\dfrac{(n-k)!}{p!(n-2k)!}\\\\
    &=\dfrac{n}{n-k}\cdot \binom{n-k}{k}
\end{align*}
$$

# Referências

1. MORGADO, A. C. O. et al. Análise Combinatória e Probabilidade. 9. ed. Rio de Janeiro: SBM, 2006