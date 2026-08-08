# Probabilidade

# Introdução

A noção de probabilidade é bem intuitiva. Todo mundo tem uma ideia do que é ter “20% de chance” ou entender o que é a frase “1 em cada 3”, por exemplo. Assim, podemos dizer que o estudo da probabilidade vai se tratar de experimentos aleatórios. 

Um <b>experimento aleatório</b> é uma ação cujo resultado não se pode prever, por exemplo, jogar uma moeda e cair cara ou jogar um dado e cair o número 6.

# Conceitos básicos

Vamos agora começar a entrar mais a fundo! 

Precisamos ter em mente dois conceitos básicos: <b>espaço amostral</b> e <b>evento</b>. 

## Espaço amostral

Definimos um <b>espaço amostral</b> como sendo o conjunto finito de todos os resultados possíveis de um experimento aleatório, por exemplo, no experimento de jogar um dado, temos os seguintes números possíveis: 1, 2, 3, 4, 5, e 6. 

Na notação matemática, denotamos o espaço amostral pela letra grega $\Omega$, assim, poderíamos escrever a situação do dado dessa maneira: 

$$
\Omega_{\text{dado}}=\{1, 2, 3, 4, 5, 6\}
$$

## Evento

Um <b>evento</b> é qualquer subconjunto do espaço amostral. 

Assim, por exemplo, o subconjunto “cair face par” do dado seria $\{2, 4, 6\}$ e o “cair face maior que 3” seria $\{4, 5, 6\}$. 

### Calculando a probabilidade de um evento

Geralmente, quando calculamos a probabilidade de um evento acontecer, consideramos que eles são <b>equiprováveis</b> ou de <b>probabilidade uniforme</b>, ou seja, dentro do espaço amostral todos os eventos possuem a mesma probabilidade de acontecer. Matematicamente, podemos escrever: 

$$
P(\{a_i\})=\dfrac{1}{n}, \forall i
$$

com $n$ sendo o número de elementos do espaço amostral $(|\Omega|)$. 

Por conta disso, podemos calcular a possibilidade de um dado evento acontecer pela fração

$$
P(A)=\dfrac{\text{Casos favoráveis}}{\text{Casos possíveis}}
$$

Por exemplo, <b>qual a probabilidade de sair face par</b> quando lançamos um dado? 

Temos três elementos nos casos favoráveis $\{2, 4, 6\}$ e seis nos casos possíveis $\{1, 2, 3, 4, 5, 6\}$, assim, podemos achar que a probabilidade é 

$$
P(A)=\dfrac{3}{6}=\dfrac{1}{2}=50\%
$$

# Propriedades

<aside>

<b>1ª propriedade (Probabilidade do espaço amostral)</b> — A probabilidade do espaço amostral é sempre 1. Isso é até intuitivo de pensar. Se eu jogo um dado, qual a probabilidade de sair <b>qualquer coisa</b>? 100%! <b>Sempre</b> vai sair alguma coisa. Numericamente, podemos escrever que $P(\Omega)=1$, já que $\dfrac{|\Omega|}{|\Omega|}=1$. 

</aside>
    
Dessa propriedade temos um outro fato que é, também, bem importante: a soma das probabilidades de todos os eventos tem que ser igual a 1, sempre. Se você somou todas as chances e chegou em 120%, alguma coisa deu errado no meio do caminho.

<aside>

<b>2ª propriedade (Limitação)</b> — A <b>probabilidade</b> de <b>qualquer evento</b> é sempre maior ou igual a 0 e menor ou igual a 1. Já que o subconjunto pode ter nenhum elemento ($\phi$, vazio) ou ter todos os elementos ($\Omega$). Numericamente, podemos escrever $0 \le P(A) \le 1$, com $A$ sendo um evento qualquer. 
    
</aside>

<aside>

<b>3ª propriedade (Independência)</b> — A soma da probabilidade de dois <b>eventos independentes</b> ($A\cap B=\phi$) acontecerem é a soma da probabilidade dos dois eventos. 

$$
P(A\cup B)=\dfrac{|A|}{|\Omega|}+\dfrac{|B|}{|\Omega|}
$$

</aside>

# Probabilidade como uma função

Podemos definir a probabilidade como uma função $P$ que satisfaz as propriedades vistas acima, o que nos dá mais alguns fatos: 

$$
\begin{align*}
    P(\Omega - A)&=1-P(A) \\
    A\subset B &\implies P(A) \le P(B) \\
    P(A \cup B) &= P(A) +P(B)-P(A\cap B)
\end{align*}
$$

# Probabilidade condicional

Definimos a <b>probabilidade condicional</b> de um evento $A$, dado que aconteceu um evento $B$, por 

$$
P(A|B):= \dfrac{P(A \cap B)}{P(B)}
$$

Com $P(B) > 0$, obrigatoriamente. 

# Variáveis aleatórias

Formalmente, uma variável aleatória $X$ é definida como sendo uma função $X:\Omega \rightarrow \mathbb{R}$, mas podemos pensar nela como sendo uma maneira de “contar” algo que quisermos num espaço aleatório, ou seja, não temos o valor da variável de antemão: o valor depende do resultado do experimento. 

A necessidade de contar é evidente: para calcularmos algo, precisamos abstrair os subconjuntos dos eventos para quantidades, números.

Para ilustrar isso, vamos utilizar como o exemplo três lançamentos de uma moeda. Chamando as caras de $c$ e as coroas de $k$, podemos definir $X$ como sendo o número de caras nos três lançamentos. 

Vamos dizer que no primeiro trio de lançamentos, tivemos os resultados $\omega=cck$. Assim, como temos duas caras, vemos que $X(\omega)=2$. 

Jogamos a moeda três vezes e obtemos os resultados $\omega=kkk$. Não tiramos nenhuma cara! Logo, temos que $X(\omega)=0$. 
<!-- Uma variável aleatória mapeia um elemento do espaço amostral para um número real. Ou seja, dado um evento, ela pega um elemento dele e dá um número. Do jeito como estava, sendo que você usou \Omega para definir espaço amostral, parecia que ele todo estava sendo pegado. A saber, o espaço amostral desse experimento seria $\Omega = \{(a_1, a_2, a_2) | a_i \in \{c, k\}\}$, ou seja, o conjunto de todas as listas possíveis de 3 resultados de c ou k. -->

## Probabilidade com variáveis aleatórias

Podemos combinar os conceitos de probabilidade com as variáveis aleatórias e conseguir mais informações sobre nossos experimentos. Por exemplo, vamos continuar imaginando nossos três lançamentos de nossa moeda. 

Qual a probabilidade de que o número de caras seja dois? Ou seja, quanto vale $P(X=2)$? 

Podemos calcular isso relativamente rápido vendo que só temos três resultados possíveis em que isso é verdade: $\{cck\}$, $\{ckc\}$ e $\{kcc\}$. 

Agora, quantas combinações possíveis disso temos, ao total? Temos duas possibilidades para cada lançamento (cara ou coroa), logo, vemos que ao todo temos $2³=8$ resultados possíveis.

Assim, finalizamos a pergunta:

$$
P(X=2)=P(\{(cck),(ckc),(kcc)\})=\dfrac{3}{8}
$$

Temos $\dfrac{3}{8}$ de chance de que nosso lançamento tenha exatamente duas caras! 

# Esperança

A <b>esperança</b> de uma variável aleatória $X$ pode ser entendida como seu <b>valor médio esperado</b>, ou seja, depois de muitos lançamentos, essa variável irá tender para esse valor. 

Esse valor médio é calculado pela seguinte expressão: 

$$
E(X)=\sum_{x \in \text{Im}(X)}xP(X=x)
$$

Ou seja, uma média ponderada de cada probabilidade da variável aleatória $X$ assumir determinado valor $x$. A expressão $x\in \text{Im}(X)$ quer dizer que estamos utilizando todos os valores $x$ possíveis que a variável aleatória pode assumir. 

<aside>

Exemplo: Qual a esperança na situação anterior, do lançamento de uma moeda? 

Primeiro, temos que $\text{Im}(X)=\{0, 1, 2, 3\}$. Assim, temos que

$$
\begin{align*}
    E(X)&= 0\cdot P(X=0)+1\cdot P(X=1) + 2\cdot P(X=2) + 3\cdot P(X=3) \\\\
    E(X)&= 0\cdot \dfrac{1}{8}+1 \cdot \dfrac{3}{8}+ 2\cdot \dfrac{3}{8}+ 3\cdot \dfrac{1}{8}\\\\
    E(X)&= \dfrac{12}{8}=\dfrac{3}{2}=1.5
\end{align*}
$$

Ou seja, a cada três lançamentos, é esperado que saiam, em média, 1.5 caras a cada três lançamentos (que é 50% das vezes). Não é de certeza que isso aconteça, mas se executarmos o mesmo experimento várias e várias e várias vezes, a média de caras (a cada três lançamentos) será essa. 

</aside>

# Distribuições de probabilidade em variáveis aleatórias

Os eventos do conjunto universo, e por consequência o $X$ que podemos escolher, podem assumir diferentes “maneiras” de terem seus valores de probabilidade distribuídos, por exemplo, no caso de uma moeda honesta, só temos duas possibilidades com 50% de chance para cada, mas numa distribuição de notas numa classe média é esperado que tenhamos algo mais ou menos assim: 

![](https://upload.wikimedia.org/wikipedia/commons/7/74/Normal_Distribution_PDF.svg)

<i>Representação de várias distribuições gaussianas. CC-BY-SA, via <a target="_blank" href="https://commons.wikimedia.org/wiki/File:Normal_Distribution_PDF.svg">Wikimedia Commons</a>.</i>

Ou seja, se pegarmos um aluno aleatoriamente dessa classe, é muito mais provável que ela tenha tirado um “6” do que fechado a prova ou zerado ela. 

## Uniforme

Num caso de <b>distribuição uniforme</b>, todos os eventos e valores que a variável aleatória $X$ pode assumir possuem a mesma probabilidade, a mesma chance de ocorrerem.

Geralmente trabalhamos com essa distribuição nos problemas, mas nem sempre ela consegue explicar os fenômenos naturais. 

Podemos dizer que a variável aleatória $X$ é <b>uniforme</b> no conjunto $\{1, 2, 3, ..., n\}$ se $P(X=k)=\dfrac{1}{n}, \forall k=1,2,3,...,n$.

## Bernoulli

A <b>distribuição de Bernoulli</b> descreve situações em que a variável aleatória $X$ só consegue assumir dois valores distintos, por exemplo, 0 ou 1, cara ou coroa, ganhar ou perder. Dessa forma, ela é muito útil para estudar casos como o lançamento de moedas, apostas e experimentos que só possuem dois resultados possíveis.

De forma mais formal, podemos dizer que a variável aleatória $X$ é de "Bernoulli de parâmetro $p$" se ela obedece os casos abaixo: 

$$
\begin{align*}
    P(X=0)&=1-p \\\\
    P(X=1)&=p
\end{align*}
$$

Esta escrita é possível em razão da distinguibilidade dos dois resultados (só pode ocorrer um por experimento) e da existência de apenas estes dois resultados.
 
<aside>

É interessante mencionar que a <b>esperança</b> de uma variável de Bernoulli de parâmetro $p$ é justamente $p$. 

</aside>

## Binomial

A <b>distribuição binomial</b> pode ser entendida como uma extensão da distribuição de Bernoulli para situações que repetimos o mesmo experimento um número $n$ de vezes, 

Matematicamente, dizemos que uma variável aleatória $X$ é de distribuição binomial de parâmetros $(n,p)$ se 

$$
P(X=k)=\binom{n}{k}p^k(1-p)^{n-k}
$$

<aside>

Exemplo: Em $10$ lançamentos, qual a probabilidade de sair exatamente $8$ caras?

$$ 
\begin{align*}
   P(X=8)&=\binom{10}{8}\left(\dfrac{1}{2}\right)^{8}\left(1-\dfrac{1}{2}\right)^{10-8} \\\\
   &=\dfrac{10!}{(10-8)!8!}\cdot\dfrac{1}{2^8}\cdot\dfrac{1}{2^2} \\\\
   &=\dfrac{10!}{2!8!}\cdot \dfrac{1}{2^{10}} \\\\
   &=\dfrac{45}{2^{10}}
\end{align*}

$$

Dos $2^{10}$ lançamentos possíveis, apenas $45$ deles possuem exatamente 8 caras.

</aside>

### Esperança da binomial

Como podemos calcular a esperança de uma binomial? 

Pela <b>definição</b> de esperança, temos que: 

$$
E(X)=\sum_{k=0}^{n}k\binom{n}{k}p^k(1-p)^{n-k}
$$

Ou simplesmente, 

$$
E(X)=np
$$

Como podemos demonstrar esta relação simples a partir da binomial? Vamos começar pela definição de esperança e ir trabalhando com ela. 

$$
\sum_{k=0}^{n}k\binom{n}{k}p^k(1-p)^{n-k}=np
$$

Primeiro, vamos reescrever o primeiro membro com o índice na parte de baixo sendo $k=1$, já que quando $k=0$, o termo resultante é zero e isso não altera nossa soma. 

$$
\sum_{k=1}^{n}k\binom{n}{k}p^k(1-p)^{n-k}
$$

Por meio de propriedades binomiais, temos que $k \binom{n}{k}=n \binom{n-1}{k-1}$. 

$$
\sum_{k=1}^{n}n\binom{n-1}{k-1}p^k(1-p)^{n-k}
$$

Agora, vamos reescrever espertamente $p^k$ como $p\cdot p^{k-1}$.

$$
\sum_{k=1}^{n}n\binom{n-1}{k-1}p\cdot p^{k-1}(1-p)^{n-k}
$$

Reorganizando… 

$$
\sum_{k=1}^{n}np\binom{n-1}{k-1}p^{k-1}(1-p)^{n-k}
$$

Como $np$ é um termo constante, podemos jogar ele para fora do somatório. 

$$
np\sum_{k=1}^{n}\binom{n-1}{k-1}p^{k-1}(1-p)^{n-k}
$$

Agora, vamos nos utilizar de uma propriedade de somatório para deslocar o índice da operação. 

$$
np\sum_{k=0}^{n-1}\binom{n-1}{k}p^{k}(1-p)^{n-1-k}
$$

E pronto! Perceba que o somatório que chegamos é um Binômio de Newton! 

Ou seja, podemos reduzir esse somatório para a expressão $[p+(1-p)]^{n-1}$, que, simplificando, chegamos em $1^{n-1}$. Como 1 elevado a qualquer coisa continua sendo 1, chegamos no resultado final, $np$.

# Variância e desvio padrão

<aside>

Em construção...

</aside>

# Referências

1. MORGADO, A. C. O. et al. Análise Combinatória e Probabilidade. 9. ed. Rio de Janeiro: SBM, 2006