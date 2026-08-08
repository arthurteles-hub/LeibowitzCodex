# Espaços vetoriais 

# Espaços vetoriais 

Chamamos espaços vetoriais todos os conjuntos $V \neq \emptyset$ munidos com duas operações ("adição" e "multiplicação por escalar"). Além disso, estas operações devem satisfazer cada uma algumas propriedades. Podemos, então, escrever a seguinte definição. 

<aside>

<b>Definição (Callioli, Espaço vetorial)</b> — Dizemos que um conjunto $V \neq \emptyset$ é um espaço vetorial sobre $\mathbb{R}$ quando, e somente quando, por um lado, existe uma adição $(u, v) \longmapsto u + v$ em $V$ de forma que: 

1. $u + v = v + u, \forall u, v \in V$ (comutatividade)
2. $u + (v + w) = (u + v) + w, \forall u, v, w \in V$ (associatividade)
3. $\exists o \in V | u + o = u, \forall u \in V$ (existência de elemento neutro)
4. $\forall u \in V, \exists (-u) \in V | u + (-u) = o$ (existência de elemento oposto)

Além disso, deve estar definida neste conjunto uma operação de multiplicação por escalar, isto é, a cada par $(\alpha, u) \in \mathbb{R} \times V$ está associado um único elemento de $V$. Este elemento único é indicado por $\alpha u$. Esta operação deve satisfazer as seguintes condições para quaisquer $u, v \in V$ e $\alpha, \beta \in \mathbb{R}$.

1. $\alpha(\beta u) = (\alpha \beta)u$ 
2. $(\alpha + \beta)u = \alpha u + \beta u$ 
3. $\alpha (u + v) = \alpha u + \alpha v$ 
4. $1u = u$

</aside>

Note que ao definirmos um espaço vetorial, o fizemos <i>sobre</i> um dado conjunto numérico (os números reais). No entanto, também é possível fazer isso em relação aos números complexos (com as mesmas propriedades continuando a valer). Sendo assim, o que é este objeto matemático que estamos definindo nosso conjunto especial sobre? Eles recebem o nome de <b>corpos</b>. 

De forma sucinta, os corpos são conjuntos munidos das operações de adição e multiplicação de forma que, enquanto a adição seja comutativa, associativa, admita elemento neutro e elemento oposto, a multiplicação deve ser associativa, comutativa, possuir elemento neutro, uma operação inversa e, além disso, ser distributiva. Podemos citar como exemplo de corpos os números reais, os racionais e os números complexos. 

Assim, quando um conjunto $V$ satisfaz os axiomas acima descritos, este recebe a classificação de <b>espaço vetorial</b> sobre o corpo escolhido. Seus elementos são denominados então <b>vetores</b> e os elementos do corpo escolhido <b>escalares</b>. Além disso, valem imediatamente a partir destes axiomas as seguintes propriedades. 

<aside>

1. Dado um espaço vetorial $V$, seu elemento neutro $o$ é único
2. Dado um espaço vetorial $V$, o vetor oposto é único para cada vetor $a \in V$
3. $\forall \alpha \in \mathbb{R}, \alpha o = o$
4. $\forall u \in V, 0u = o$ 
5. $\alpha u = 0 \iff \alpha = 0$ ou $u = 0$
6. $\forall \alpha \in \mathbb{R}$ e $\forall u \in V$, $(-\alpha)u = \alpha(-u) = -(\alpha u)$
7. Quaisquer que sejam $\alpha, \beta \in \mathbb{R}$ e $u \in V$, $(\alpha - \beta)u = \alpha u - \beta u$
8. Quaisquer que sejam $\alpha \in \mathbb{R}$ e $u, v \in V$, $\alpha(u - v) = \alpha u - \alpha v$ 
9. Dados $\beta, \alpha_1, ..., \alpha_n \in \mathbb{R}$ e $u_1, ..., u_n \in V$, então 

$$
\beta \left(\sum_{j=1}^n \alpha_j u_j \right) = \sum_{j = 1}^n (\beta \alpha_j)u_j
$$

</aside>

## Subespaço vetorial 

De forma sucinta, um subespaço vetorial é um subconjunto de um espaço vetorial que, ao ser munido das mesmas operações de seu conjunto "pai", tornar-se também um espaço vetorial. Definimos: 

<aside>

<b>Definição (Callioli, Subespaço vetorial)</b> — Seja $V$ um espaço vetorial sobre $\mathbb{R}$. Um subespaço vetorial de $V$ é um subconjunto $W \subset V$, tal que: 

1. $o \in W$
2. $\forall u,v \in W, u + v \in W$ 
3. $\alpha \in \mathbb{R}, \forall u \in W \implies \alpha u \in W$ 

</aside>

Por consequência das hipóteses, temos diretamente que se $W$ é subespaço vetorial de $V$, que é um espaço vetorial sobre $\mathbb{R}$, então $W$ é também um espaço vetorial sobre $\mathbb{R}$. Além disso, temos que a intersecção de dois subespaços de um espaço vetorial é também um subespaço vetorial. 

Interessantemente, podemos definir uma operação <b>soma</b> para dois subespaços. 

<aside>

<b>Definição (Callioli, Soma de subespaços)</b> — Sejam $U$ e $V$ subespaços vetoriais de um espaço vetorial $W$. Indicaremos por $U+V$ e chamaremos de <b>soma de $U$ com $V$</b> o seguinte subconjunto de W: 

$$
U + V = \{u + v | u \in U, v \in V\}
$$

Desta operação decorre imediatamente que $U + V = V + U$, $U + {o} = U$ e $U \subset U + V$ e $V \subset U + V$. Além disso, $U + V$ também é um subespaço vetorial de $W$. 

No caso especial em que $U \cap V = \{o\}$, denotamos a soma de $U$ e $V$ como $U \oplus V$ e a denominamos <b>soma direta</b> dos subespaços $U$ e $V$. Se $U$ e $V$ forem subespaços de um dado espaço vetorial $W$ de forma que sua soma direta for o espaço $W$, dizemos que $U$ e $V$ são suplementares (ou que um é suplementar do outro e vice-versa). 

Além disso, temos que $W = U \oplus V \iff \forall w \in W$ existir uma única decomposição $w = u + v$, com $u \in U$ e $v \in V$. 

</aside>

# Base e dimensão

## Combinações lineares

Ao considerarmos um espaço vetorial $V$ sobre $\mathbb{R}$, podemos tomar um subconjunto $S = {v_1, v_2, ..., v_n} \in V$. Temos que o conjunto $[S]$ formado por todos os vetores da forma 

$$
\alpha_1v_1 + \alpha_2v_2 + ... + \alpha_nv_n
$$

com $\alpha_1, ..., \alpha_n \in \mathbb{R}$ é chamado <b>subespaço gerado por $S$</b>. Cada vetor membro deste subespaço gerado é chamado <b>combinação linear de $S$</b> ou dos vetores $v_1, ..., v_n$. 

## Base e dimensão

A noção de <i>gerar</i> um espaço vetorial a partir de um conjunto de vetores nos introduz à noção de <b>base</b>. Chamamos conjunto <b>base</b> de um espaço vetorial $V$ o conjunto de vetores pertencentes à $V$ tais que o conjunto de todas as suas combinações lineares é o conjunto $V$. O número mínimo de vetores necessários para gerar o espaço $V$ é denominado <b>dimensão</b> do espaço vetorial $V$. Existem espaços vetoriais de dimensão finita ("finitamente gerados") ou infinita ("infinitamente gerados"). 

A base de um espaço vetorial na realidade ainda necessita de uma outra condição: ser <b>linearmente independente</b>. Dizemos que um conjunto de vetores 

$$
L = \{u_1, u_2, ..., u_n\}
$$

é linearmente independente (LD) caso a combinação linear destes vetores resulte no vetor nulo e, e somente se, todos os coeficientes $\alpha$ forem nulos, isto é, só existe a chamada "solução trivial". Caso contrário, isto é, caso exista uma outra solução de forma que pelo menos um $\alpha_i \neq 0$, dizemos que o conjunto é <b>linearmente dependente</b> (LD). Por consequência dessa restrição, não é difícil perceber que a <b>dimensão</b> de um espaço vetorial é simplesmente a cardinalidade (a quantidade de elementos) de sua base.

É importante ainda ressaltar que embora nos referimos a "base" de um espaço vetorial no singular, pode-se definir múltiplas bases para o mesmo espaço vetorial, entretanto, sua cardinalidade (e portanto, a dimensão) será sempre a mesma. Este resultado é referido como <b>teorema da invariância</b>.  

### Dimensão da soma de dois subespaços 

É possível mostrar ainda que a dimensão da soma de dois subespaços (de dimensão finita) de um espaço vetorial de dimensão finita é dada por

$$
\dim{(U + V)} = \dim{U} + \dim{V} - \dim{(U \cap V)}
$$
<!-- Olha só, é exatamente como é a probabilidade da união de dois eventos não mutuamente excludentes! -->

## Bases ordenadas e mudança de base

Por padrão, a ordem dos vetores em uma base não importa para nosso tratamento com espaços vetoriais, em decorrência de estarmos tratando com conjuntos. Entretanto, fixar a ordem das bases (e por isso definir bases <i>ordenadas</i>) nos permite criar a noção de <b>coordenadas</b> num espaço vetorial. 

De fato, se tivermos um vetor $u$ expresso pela equação 

$$
\alpha_1 v_1 + \alpha_2 v_2 + ... + \alpha_n v_n = u
$$

com $(v_1, v_2, ..., v_n)$ formando uma base ordenada $B$ do espaço vetorial, dizemos que os escalares $(\alpha_1, \alpha_2, ..., \alpha_n)$ são as coordenadas do vetor $u$ em relação à base $B$. Por questões de brevidade, daqui em diante nesta seção iremos escrever "base" ao invés de "base ordenada". 

Uma propriedade interessante está presente um espaço vetorial de dimensão $n$. Ao considerarmos duas bases deste espaço, por exemplo, $B = \{u_1, ..., u_n\}$ e $C = \{v_1, ..., v_n\}$, temos que existe uma única coleção de escalares $a_{ij}$ tal que 

$$
\begin{cases}
    v_1 = \alpha_{11}u_1 + ... + \alpha_{n1}u_n \\ 
    ... \\ 
    v_n = \alpha_{1n}u_1 + ... + \alpha_{nn}u_n
\end{cases}
$$

Assim, podemos definir uma <b>matriz de mudança de base</b> de $B$ para $C$ com esta coleção de escalares. 

$$
P =
\begin{pmatrix}
    \alpha_{11} & \alpha_{12} & ... & \alpha_{1n} \\ 
    \alpha_{21} & \alpha_{22} & ... & \alpha_{2n} \\ 
    ... & ... & ... & ... \\ 
    \alpha_{n1} & \alpha_{n2} & ... & \alpha_{nn} \\ 
\end{pmatrix}
$$

Dessa forma, basta multiplicar pela esquerda esta matriz com as coordenadas de um dado vetor na base $B$ para obter uma matriz coluna com as coordenadas deste mesmo vetor na base $C$. 

# Referências

1. CALLIOLI, Carlos Alberto; DOMINGUES, Hygino H.; COSTA, Roberto da. <i>Álgebra Linear e Aplicações</i>. 4ª edição revisada. São Paulo: Atual, 1983.