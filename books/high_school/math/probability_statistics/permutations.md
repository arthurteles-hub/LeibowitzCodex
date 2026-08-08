# Permutações

# Definição

O que é <b>permutar</b>? Permutar não é nada mais nada menos do que “reorganizar”, “rearranjar” uma coleção de objetos. Por exemplo, no conjunto $A=\{1, 2, 3, 4\}$, uma permutação possível seria $\{2, 3, 1, 4\}$ ou $\{3, 1, 4, 2\}$. 

# Princípios

Na arte matemática das permutações, temos dois princípios básicos que vão formar a sustentação de todo o nosso raciocínio, são eles o <b>princípio aditivo</b> e o <b>princípio multiplicativo</b>. 

## Princípio aditivo

Esse princípio nos diz que o número de elementos do conjunto formado pela união $(\cup)$ de dois conjuntos <b>disjuntos</b> $P$ e $Q$, cada um com $i$ e $j$ elementos, respectivamente, é de $i+j$ elementos. 

Dizemos que dois conjuntos são <b>disjuntos</b> quando seus elementos são completamente diferentes entre si; e.g.: $A = \{1, 2\}$ e $B = \{3, 4\}$ são conjuntos disjuntos.

Matematicamente, podemos representar esse princípio assim: 

$$
|P \cup Q|= |P| + |Q|
$$

Com a notação de barras representando o número de elementos (cardinalidade) do respectivo conjunto.

## Princípio multiplicativo

Esse princípio diz que considerando um conjunto $P$ com $i$ elementos e um conjunto $Q$ com $j$ elementos, o <b>produto cartesiano</b> dos conjuntos, escrito como $P \cdot Q$, é o conjunto de todos os pares $(p, q)$, com $p \in P$ e $q \in Q$. O número de elementos nesse novo conjunto é calculado pela multiplicação do número de elementos em cada um dos conjuntos. 

Matematicamente: 

$$
|P \cdot Q| = |P| \cdot |Q|
$$

Esse princípio pode ser visto como uma “evolução” do princípio aditivo, por um exemplo simples. Imagine que você tem 5 camisas e 3 calças, de quantas maneiras você pode combiná-las?

Para a primeira camisa, você tem três calças, para a segunda camisa, também três calças, e depois para a quarta, e para a quinta camisa, ou seja: 

$$
3+3+3+3+3=3 \cdot 5
$$

Cada parcela da soma representa mais três possibilidades de combinar uma camisa com as três calças. 

Representando as camisas com $k$ e as calças com $c$, temos os seguintes pares ordenados: 

$$
\begin{array}{ccc}
    (k_1, c_1) & (k_1, c_2) & (k_1, c_3) \\
    (k_2, c_1) & (k_2, c_2) & (k_2, c_3) \\
    (k_3, c_1) & (k_3, c_2) & (k_3, c_3) \\
    (k_4, c_1) & (k_4, c_2) & (k_4, c_3) \\
    (k_5, c_1) & (k_5, c_2) & (k_5, c_3)
\end{array}
$$

Multiplicando o número de linhas pelo número de colunas, vemos que sim, temos 15 pares, como previsto. 

# Permutações lineares

## Permutação com objetos diferentes

Considerando uma lista de vários objetos, todos diferentes entre si $(a_1, a_2, a_3, ..., a_n)$, podemos saber de quantas maneiras podemos ordená-los utilizando o <b>fatorial</b> $(!)$, que é definido como sendo $n!=n\cdot(n-1)\cdot(n-2)\cdot ... \cdot 1$, por exemplo, de quantas maneiras podemos organizar as letras do conjunto $\{F, O, X\}$?

Sabemos que o conjunto possui 3 elementos, logo, podemos fazer isso de $3! = 3\times2\times1=6$ maneiras diferentes. Isso pode ser visualizado abaixo: 

$$
\{F, O, X\}, \{F, X, O\}, \{O, X, F\}, \{O, F, X\}, \{X, F, O\}, \{X, O, F\}
$$

## Escolhendo pequenas listas de uma lista maior

Generalizando… de quantas maneiras podemos escolher uma coleção de $k$ objetos de $n$ objetos distintos dados? Podemos tentear enxergar uma expressão universal por meio da exploração da seguinte pergunta: “De quantas formas podemos escolher uma lista de 3 números de uma lista de 4 números?”

Supondo nossa lista como a lista $\{1, 2, 3, 4\}$, podemos verificar essa quantidade percebendo que existem quatro maneiras de escolher o primeiro número, três maneiras para o segundo e duas para o terceiro, ou seja, pelo princípio multiplicativo temos $(4)_3=4\times3\times2=24$ maneiras. 

Assim, testando para mais outros casos, podemos ver que a expressão generalizada que responde essa necessidade é dada por: 

$$
(n)_k=n\cdot(n-1)\cdot...\cdot(n-k+1)
$$

Onde $n$ é a quantidade total e $k$ seria o tamanho dos “subconjuntos” que queremos formar. 

Sintetizando, podemos escrever a seguinte expressão, nos utilizando da notação do fatorial: 

$$
(n)_k=\dfrac{n!}{(n-k)!}
$$

## Objetos repetidos

E se tivéssemos que organizar uma lista com objetos repetidos, por exemplo, $\{A, B, A, C, A, T, E\}$?

Inicialmente, podemos tentar reorganizar como anteriormente, utilizando $n!$, porém isso parte do princípio que todos os elementos da lista são diferentes, o que não é verdade. 

Um raciocínio para resolver esse problema é perceber que, ao usarmos $n!$, contamos os elementos repetidos $k!$ vezes, já que, por exemplo, o grupo $\{A, B, A, C, A, T, E\}$ origina outros 5 grupos completamente idênticos a ele — já que trocando as letras “A” de lugar não muda em nada — com cada permutação dessa originando as outras permutações restantes, ou seja, esses novos “galhos” da árvore das permutações precisam ser “podados” por meio de uma divisão para que essas contagens repetidas deixem de existir. 

Por isso, de forma algébrica, escrevemos:

$$
\dfrac{n!}{k_1! \cdot ... \cdot k_j!}
$$

Onde $k_1$ é a quantidade de elementos do tipo 1, $k_2$ é a quantidade de elementos do tipo 2 e assim por diante, até $k_j$, que é a quantidade de elementos do tipo $j$. É importante frisar que a relação $k_1 + k_2+...+k_j =n$ precisa ser verdadeira para essa expressão fazer sentido. 

# Permutações circulares

Para entender o conceito de uma permutação circular, vamos imaginar a seguinte situação: temos 3 crianças, Ana, Bia e Carlos, brincando de ciranda no meio da praça. De quantas maneiras podemos organizar essa roda? 

Como são três elementos distintos, a primeira intuição seria efetuar $3!=3\times2\times1=6$, porém, vemos pela imagem abaixo uma propriedade importante: cada configuração possui alguns “espelhos”, que são as rotações da “ciranda”.

![](https://upload.wikimedia.org/wikipedia/commons/9/93/Circular_Permutations.png)

Assim como fizemos com os elementos repetidos, temos que remover essas configurações extras por meio da divisão, já que o que importa para nós é a <b>posição relativa</b> entre cada criança na ciranda. Como cada rotação não gera outros “galhos” na árvore, só precisamos dividir o fatorial pelo número de elementos. 

Refraseando para uma outra visão, podemos ver empiricamente que cada nova permutação gera na verdade, outras $n-1$ “permutações”, que são descartadas pela divisão. 

Dessa forma, temos que o total de permutações circulares possíveis de $n$ elementos é dado por: 

$$
\dfrac{n!}{n}=(n-1)!
$$

# Permutações caóticas

Ao considerarmos um conjunto de elementos, uma permutação desse conjunto é dita ser <i>caótica</i> se todos os elementos estão em posições diferentes do conjunto "original". Por exemplo, na lista $\{1, 2, 3, 4\}$, a permutação $\{2, 4, 1, 3\}$ é caótica, enquanto a permutação $\{1, 3, 2, 4\}$ não o é, pois o “1” está na sua posição original. 

Por meio do <b>Princípio da Inclusão-Exclusão</b> (PIE), podemos saber que a quantidade de permutações caóticas de um determinado conjunto $\{1, 2, 3, 4, ..., n\}$ é dada por: 

$$
\begin{align*}
D_n &= n!\left(\dfrac{1}{0!}-\dfrac{1}{1!}+\dfrac{1}{2!}-\dfrac{1}{3!}+...+(-1)^n\cdot\dfrac{1}{n!} \right) \\\\
&= n!\left(\sum_{i=0}^n \dfrac{1}{i!}\cdot (-1)^i\right)
\end{align*}
$$

<aside>

É importante notar que o termo $(-1)^n$ funciona como uma “condicional” para determinar se o último termo será uma soma ou uma subtração, conforme visto na <a href="/books/high_school/math/probability_statistics/counting_methods.html" target="_blank">discussão sobre o PIE</a>.

</aside>

Para demonstrar isso, vamos definir $A_k$ como sendo conjunto de todas permutações que o elemento $k$ está em sua posição natural, ou seja, a posição $k$. Como fixamos o elemento $k$ na sua posição inicial, só precisamos agora permutar $n-1$ elementos, ou seja, concluímos que a quantidade de permutações em que $k$ permanece na posição original é dada por $|A_k|=(n-1)!$. 

Agora, podemos perceber que $A_k\cap A_j$ é o conjunto de todas as permutações que os elementos $k$ e $j$ continuam nas suas posições originais: como agora dois elementos estão fixos, temos que a quantidade de permutações é dada por $|A_k\cap A_j|=(n-2)!$. Esse padrão é importante, pois é o mesmo padrão do PIE: quando somamos $|A_k|+|A_j|$, há algumas permutações que contamos em excesso e, por isso, retiramos a intersecção, ou seja, é um PIE “disfarçado”. 

Tendo agora essa visão, podemos aplicar o PIE, obtendo que o número de permutações caóticas $D_n$ é dado por: 

$$
D_n=n!-\left(n!-\dfrac{n!}{2!}+\dfrac{n!}{3!}-\dfrac{n!}{4!}+...+(-1)^{n-1}\cdot\dfrac{n!}{n!}\right)
$$

Já que, como $n!$ é o número total de permutações, e a expressão que encontramos são todas as permutações <b>não-caóticas</b>, o resultado dessa subtração será o número de permutações caóticas. 

Colocando $n!$ em evidência, finalmente chegamos na nossa expressão final, que pode ainda ser condensada em notação de somatório, como visto anteriormente.

$$
D_n=n!\left(\dfrac{1}{0!}-\dfrac{1}{1!}+\dfrac{1}{2!}-\dfrac{1}{3!}+...+(-1)^n\cdot\dfrac{1}{n!} \right)
$$

# Referências

1. MORGADO, A. C. O. et al. Análise Combinatória e Probabilidade. 9. ed. Rio de Janeiro: SBM, 2006