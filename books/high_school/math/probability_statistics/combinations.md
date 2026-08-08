# Combinações

# Introdução

No quesito <b>permutações</b>, a ordem de cada elemento é importante, porém, quando passamos a estudar <b>combinações</b> de elementos, ela deixa de ser. Portanto, nesse documento estará várias coisas sobre <b>como escolher objetos sem que a ordem seja importante</b>. 

# Escolhendo “k” objetos de “n” dados

Podemos escolher $k$ objetos de $n$ dados nos utilizando da seguinte expressão: 

$$
\binom{n}{k} = \dfrac{n!}{(n-k)! \cdot k!}
$$

Lê-se “$n$ escolhe $k$”. 

Agora, por que? Bom, podemos ilustrar isso com um exemplo: de quantas maneiras podemos montar uma dupla partindo de um grupo de 3 pessoas? 

Primeiro, podemos supor que a ordem seja importante, o que nos dará a resposta de $\dfrac{3!}{(3-2)!}=6$ comissões, porém, cada comissão foi contada $2!$ vezes. 

Para visualizar melhor, vamos imaginar que temos três pessoas (Alice, Bárbara e Carlos), e vamos montar duplas com eles. Temos as seguintes ordens, supondo que a ordem seja importante: 

$$
\begin{array}{cc}
    \{A, B\} & \{B, A\} \\
    \{B, C\} & \{C, B\} \\
    \{A, C\} & \{C, A\} \\
\end{array}
$$

Porém, podemos perceber que cada dupla foi contada $2!$ vezes! 

Ou seja, na verdade, só temos realmente 3 possibilidades de duplas partindo de um trio: $\{A, B\}, \{B, C\}$ e $\{A, C\}$. Seus “espelhos” são as mesmas duplas, porém com as ordens trocadas, mas como a ordenação não importa, apenas os elementos, podemos concluir que são, de fato, as mesmas duplas. 

# Relação de Stifel

Sendo $n \ge k \ge 1$, com $n, k \in \mathbb{N}$, temos a seguinte relação: 

$$
\binom{n+1}{k}= \binom{n}{k}+ \binom{n}{k-1}
$$

Podemos demonstrar a relação por meio de duas maneiras, dois *argumentos combinatórios*, um mais algébrico e outro por *contagem dupla*. 

<aside>

Um <b>argumento combinatório</b> é uma prova que se utiliza da combinatória para provar uma identidade. Para isso, alguns métodos são utilizados, como o da <b>contagem dupla</b>: se duas relações diferentes resultam na mesma coisa, elas iguais entre si.

</aside>

## Demonstração I

Nessa demonstração serão utilizados apenas conceitos de álgebra. 

Primeiro, vamos “desempacotar” as operações: 

$$
\binom{n}{k} + \binom{n}{k-1}=\dfrac{n!}{(n-k)!k!}+\dfrac{n!}{(n-k+1)!(k-1)!}
$$

Agora, faremos o M.M.C entre as duas frações, para que seus denominadores fiquem iguais: 

$$
=\dfrac{n! \cdot(n-k+1)}{(n-k+1)\cdot k!} + \dfrac{n! \cdot k}{(n-k+1)!\cdot k!}
$$

Nos utilizando de propriedades da multiplicação, chegamos no seguinte: 

$$
=\dfrac{n! \cdot (n + 1)}{(n - k + 1) \cdot k!}
$$

Que é a mesma coisa que: 

$$
=\binom{n+1}{k}
$$

## Demonstração II

Para isso, vamos nos utilizar de um exemplo: de quantas maneiras podemos formar um grupo com $k$ pessoas, de $n+1$ pessoas disponíveis?

Bom, sabemos que isso é $\binom{n+1}{k}$, a partir do que foi visto inicialmente. 

Agora, vamos responder essa pergunta de outra maneira: vamos fixar uma pessoa da comissão, por exemplo, Carlos. Com isso, transformamos $\binom{n+1}{k}$ em $\binom{n}{k}$. 

Pelo princípio aditivo, temos que o número total de comissões possíveis é a soma do número de comissões que Carlos está (na comissão) com o número de comissões que Carlos não está. Tendo isso em vista, vamos contar essas duas possibilidades. 

Quando Carlos está na comissão, só precisamos escolher $k-1$ pessoas das $n$, logo, temos que o número de comissões é $\binom{n}{k-1}$. Quando Carlos não está fixado, ora, é o caso ordinário, que já encontramos: $\binom{n}{k}$. 

Portanto, juntando tudo, temos que: 

$$
\binom{n+1}{k} = \binom{n}{k}+\binom{n}{k-1}
$$

# Combinações com repetições

As <b>combinações com repetições</b>, também conhecidas por <b>combinações completas</b> são as combinações de $k$ elementos que podemos formar dentre $n$ elementos, sabendo que um mesmo elemento pode se repetir nessa nossa escolha. 

Podemos ilustrar isso melhor com um exemplo: De quantas maneiras podemos fazer um pedido de 4 pizzas num rodízio de 7 sabores, sabendo que podemos pedir pizzas de mesmo sabor?

Não poderia ser $\binom{7}{4}$, já que isso na verdade é a resposta para a pergunta: "De quantas maneiras podemos escolher <b>4 pizzas diferentes entre si</b> dentre as 7?"

Podemos reinterpretar essa pergunta como as soluções da seguinte equação:

$$
x_1+x_2+x_3+x_4+x_5+x_6+x_7=4
$$

A interpretação dessa equação é a seguinte: temos 7 pizzas totais que podemos escolher, mas a quantidade de pizzas do nosso pedido não pode exceder quatro. Por exemplo, podemos pedir quatro pizzas do sabor 1 e nenhuma pizza dos outros sabores.

$$
4+0+0+0+0+0+0=4
$$

Ou seja, contar a quantidade de pedidos que podemos fazer será <b>contar a quantidade de soluções</b> dessa equação. Parece muito complicado agora, mas podemos nos utilizar de uma artimanha, um <b>esquema bola-traço</b>. 

No esquema bola-traço, nós representamos cada incógnita com uma bola e cada “+” com um traço, ou seja, a situação acima ficaria assim: 

$$
\bullet\bullet\bullet\bullet|||||| 
$$

Ou seja, temos agora que responder uma outra pergunta: De quantas maneiras podemos organizar essas quatro bolinhas e esses quatro tracinhos? Se descobrirmos de quantas maneiras podemos ordenar esses elementos, podemos saber de quantas maneiras podemos pedir as pizzas. 

Podemos perceber que caímos num caso de permutação simples! Seria o equivalente de encontrar a quantidade de anagramas de uma palavra com letras repetidas. Como temos 4 bolinhas e 6 tracinhos, temos 10 elementos, o que nos dá o resultado final: 

$$
\dfrac{10!}{6!4!}=\dfrac{10\cdot 9\cdot 8\cdot 7}{4\cdot\ 3\cdot 2}=210
$$

Ou seja, podemos pedir os quatro sabores de pizza de 210 maneiras diferentes!

No caso geral, vamos perceber que sempre que vamos determinar o número de soluções inteiras não-negativas de $x_1+x_2+x_3+...+x_n=k$, quando abstraímos, teremos $k$ bolas e $n -1$ traços, o que nos mostra que o número de combinações completas de $k$ objetos dentre $n$ é 

$$
\binom{n-1}{k}=\dfrac{(n+k-1)!}{(n-1)!\cdot k!}
$$

E assim, finalmente, resolvemos e generalizamos a nossa solução! 

## Com restrições

Agora, vamos imaginar uma situação parecida: De quantas maneiras podemos pedir 20 sorvetes dentre 3 sabores, que podem se repetir, sabendo que devemos pedir no mínimo 2 sorvetes de cada sabor? 

Transformando essa situação numa equação, temos a seguinte expressão: 

$$
x+y+z=20;\\x, y,z \ge 2
$$

Aqui temos um problema, já que não podemos aplicar o método bola-traço: esse método assume que algumas incógnitas receberão o valor de 0, o que não é permitido. Para resolver essa equação, temos que nos utilizar de uma “artimanha”, uma substituição. 

$$
x=2+a\\y=2+b\\z=2+c
$$

Assim, substituindo na equação original… 

$$
2+a+2+b+2+c=20\\a+b+c+6=20\\a+b+c=14
$$

E assim, transformamos um problema com restrição que não poderíamos resolver num problema sem restrições, que podemos resolver! 

Assim, podemos encontrar que a solução é… 

$$
\binom{2}{14}=\dfrac{(2+14)!}{2!\cdot 14!}=\dfrac{16!}{14! \cdot 2}=\dfrac{16 \cdot 15}{2}=120
$$

Completamos o problema! Temos 120 maneiras de pedir os sorvetes.

# Referências

1. MORGADO, A. C. O. et al. Análise Combinatória e Probabilidade. 9. ed. Rio de Janeiro: SBM, 2006