# Matrizes

# Matrizes

Matrizes (reais) são objetos matemáticos formados por uma dupla sequência de números reais arranjados em uma tabela de $m$ linhas e $n$ colunas. Estas matrizes são assim chamadas "matrizes m por n", sendo escritas como uma tabela entre parênteses ou colchetes.

$$
A_1 =
\begin{pmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{pmatrix}
$$

Numa matriz, cada número é denominado <b>elemento</b>, <b>termo</b> ou <b>entrada</b> da matriz, podendo ser representado de forma genérica por, por exemplo, $a_{ij}$ — o termo $a$ da linha $i$ e coluna $j$. Esta representação dos elementos de forma genérica estende-se para matrizes também. Por exemplo, podemos escrever $A = (a_{ij})_{m \times n}$ se quisermos representar uma matriz $A$ com $m$ linhas e $n$ colunas.

$$
A_2 =
\begin{pmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{pmatrix}
$$

É importante mencionar que $(a_{ij})$ é denominado <b>termo geral</b> da matriz $A$, além de que as matrizes são comumente denotadas por letras maiúsculas do nosso alfabeto latino. Por fim, é interessante ainda ressaltar que matrizes com mesmo número de linhas e colunas são chamadas <b>quadradas</b> e, caso contrário, <b>retangulares</b>. Particularmente, quando $m = 1$ ou $n = 1$, recebem a denominação de <b>matrizes linha</b> e <b>matrizes coluna</b>, respectivamente.

Note ainda que podemos tratar matrizes $1 \times 1$ como números reais. Na notação matemática usual, representamos o conjunto das matrizes reais $m \times n$ por $M_{m \times n}(\mathbb{R})$. Como exemplo, podemos afirmar que

$$
A =
\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}
\in M_{2 \times 2} (\mathbb{R})
$$

## Operações com matrizes

Dentro do conjunto $M_{m \times n} (\mathbb{R})$ estão definidas algumas operações, sendo elas <b>adição</b>, <b>multiplicação por um número real (escalar)</b> e a <b>multiplicação entre duas matrizes</b>. Antes de descrevermos como essas operações são usualmente definidas, pode ser interessante destacar que duas matrizes $A$ e $B$ são iguais se, e somente se, seus elementos são iguais.

### Adição

Sejam $A$ e $B$ matrizes $m \times n$. Denotamos a matriz soma por $C = A + B$, valendo, por definição:

$$
A + B =
\begin{pmatrix}
a_{11} + b_{11} & a_{12} + b_{12} & ... & a_{1n} + b_{1n} \\
a_{21} + b_{21} & a_{22} + b_{22} & ... & a_{2n} + b_{2n} \\
... & ... & ... & ... \\
a_{m1} + b_{m1} & a_{m2} + b_{m2} & ... & a_{mn} + b_{mn}
\end{pmatrix}
$$

Ou seja, para somar duas matrizes, basta somar elemento a elemento.

Para essa operação valem algumas propriedades. Considere $A, B, C \in M_{m \times n} (\mathbb{R})$.

<table>
    <tr>
        <th>Nome</th>
        <th>Propriedade</th>
    </tr>
    <tr>
        <td>$A + (B+C) = (A+B)+C$</td>
        <td>propriedade associativa</td>
    </tr>
    <tr>
        <td>$A + B = B + A$</td>
        <td>propriedade comutativa</td>
    </tr>
    <tr>
        <td>$\exists O \in M_{m \times n} | A + O = A, \forall A$</td>
        <td>existência de elemento neutro</td>
    </tr>
    <tr>
        <td>$\exists (-A) | A+(-A)=O, \forall A$</td>
        <td>existência do elemento oposto para qualquer matriz</td>
    </tr>
</table>

<aside>

<b>Teorema</b> — A adição de matrizes é associativa.

</aside>

<aside>

<b>Demonstração</b> — Sejam $A=(a_{ij}), B=(b_{ij})$ e $C=(c_{ij})$. Então,

$$
[A+(B+C)]_{ij} = a_{ij} + (b_{ij}+c_{ij})
$$

e

$$
[(A+B)+C]_{ij} = (a_{ij}+b_{ij})+c_{ij}
$$

Como a adição em $\mathbb{R}$ é associativa,

$$
a_{ij} + (b_{ij}+c_{ij}) = (a_{ij}+b_{ij})+c_{ij}
$$

para todos os índices $i,j$. Portanto,

$$
A+(B+C) = (A+B)+C.
$$

</aside>

<aside>

<b>Teorema</b> — A adição de matrizes é comutativa.

</aside>

<aside>

<b>Demonstração</b> — Temos

$$
(A+B)_{ij} = a_{ij}+b_{ij}
$$

e

$$
(B+A)_{ij} = b_{ij}+a_{ij}.
$$

Como a adição de números reais é comutativa,

$$
a_{ij}+b_{ij}=b_{ij}+a_{ij},
$$

segue que

$$
A+B=B+A.
$$

</aside>

<aside>

<b>Teorema</b> — Existe matriz neutra para a adição.

</aside>

<aside>

<b>Demonstração</b> — Considere a matriz nula

$$
O=(0)_{m \times n}.
$$

Então,

$$
(A+O)_{ij}=a_{ij}+0=a_{ij}.
$$

Logo,

$$
A+O=A.
$$

</aside>

<aside>

<b>Teorema</b> — Toda matriz possui elemento oposto.

</aside>

<aside>

<b>Demonstração</b> — Dada $A=(a_{ij})$, definimos

$$
-A=(-a_{ij}).
$$

Então,

$$
(A+(-A))_{ij}=a_{ij}+(-a_{ij})=0.
$$

Portanto,

$$
A+(-A)=O.
$$

</aside>

### Produto por escalar

Dada uma matriz $A_{m \times n}$ e um $\lambda \in \mathbb{R}$, o produto entre $A$ e $\lambda$ é denotado por $\lambda \cdot A$ ou ainda $\lambda A$ e é definido por

$$
\lambda A =
\lambda
\begin{pmatrix}
a_{11} & a_{12} & ... & a_{1n} \\
a_{21} & a_{22} & ... & a_{2n} \\
... & ... & ... & ... \\
a_{m1} & a_{m2} & ... & a_{mn}
\end{pmatrix}
=
\begin{pmatrix}
\lambda a_{11} & \lambda a_{12} & ... & \lambda a_{1n} \\
\lambda a_{21} & \lambda a_{22} & ... & \lambda a_{2n} \\
... & ... & ... & ... \\
\lambda a_{m1} & \lambda a_{m2} & ... & \lambda a_{mn}
\end{pmatrix}
$$

Isto é, o produto entre uma matriz e um número real $\lambda$ retorna uma matriz em que os elementos da matriz original foram multiplicados por $\lambda$.

Para esta operação valem as seguintes propriedades:

<table>
    <tr>
        <th>Nome</th>
        <th>Propriedade</th>
    </tr>
    <tr>
        <td>$(\alpha \beta) A = \alpha(\beta A)$</td>
        <td>propriedade associativa</td>
    </tr>
    <tr>
        <td>$(\alpha + \beta)A = \alpha A + \beta A$</td>
        <td>propriedade distributiva 1</td>
    </tr>
    <tr>
        <td>$\alpha (A + B) = \alpha A + \alpha B$</td>
        <td>propriedade distributiva 2</td>
    </tr>
    <tr>
        <td>$1A = A$</td>
        <td>existência de elemento neutro</td>
    </tr>
</table>

<aside>

<b>Teorema</b> — Valem as propriedades do produto por escalar.

</aside>

<aside>

<b>Demonstração</b> — Todas seguem diretamente das propriedades dos números reais.

Por exemplo,

$$
[(\alpha+\beta)A]_{ij}=(\alpha+\beta)a_{ij}
$$

e

$$
(\alpha A+\beta A)_{ij}=\alpha a_{ij}+\beta a_{ij}.
$$

Como

$$
(\alpha+\beta)a_{ij}=\alpha a_{ij}+\beta a_{ij},
$$

segue que

$$
(\alpha+\beta)A=\alpha A+\beta A.
$$

As demais propriedades demonstram-se analogamente.

</aside>

### Produto entre duas matrizes

Dadas duas matrizes $A_{m \times n}$ e $B_{n \times p}$, definimos o produto $A \cdot B$ (também denotado por $AB$) como uma operação que produz uma matriz $C_{m \times p}$ com termo geral

$$
c_{ik} = \sum_{j = 1}^n a_{ij} \cdot b_{jk} = a_{i1} \cdot b_{1k} + ... + a_{in} \cdot b_{nk}
$$

De forma mais visual, temos que cada elemento $c_{ik}$ da nova matriz é formado a partir da multiplicação (e soma) elemento a elemento da linha $i$ da matriz $A$ e da coluna $k$ da matriz $B$.

Como exemplo, observe o produto abaixo.

$$
\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}_{2 \times 2}
\cdot
\begin{pmatrix}
5 & 4 \\
2 & 1
\end{pmatrix}_{2 \times 2}
=
\begin{pmatrix}
1 \cdot 5 + 2 \cdot 2 & 1 \cdot 4 + 2 \cdot 1 \\
3 \cdot 5 + 4 \cdot 2 & 3 \cdot 4 + 4 \cdot 1
\end{pmatrix}_{2 \times 2}
$$

No produto entre matrizes valem as seguintes propriedades. Considere $A_{m \times n}, B_{n \times p}, C_{p \times q}$.

<table>
    <tr>
        <th>Nome</th>
        <th>Propriedade</th>
    </tr>
    <tr>
        <td>$A(BC) = (AB)C$</td>
        <td>propriedade associativa</td>
    </tr>
    <tr>
        <td>$A(B+C) = AB + AC$</td>
        <td>propriedade distributiva em relação à adição</td>
    </tr>
</table>

<aside>

<b>Teorema</b> — O produto de matrizes é associativo.

</aside>

<aside>

<b>Demonstração</b> — Considere o elemento $(i,k)$ de $A(BC)$:

$$
[A(BC)]_{ik}
=
\sum_{j=1}^n a_{ij}(BC)_{jk}
=
\sum_{j=1}^n a_{ij}\left(\sum_{r=1}^p b_{jr}c_{rk}\right).
$$

Logo,

$$
[A(BC)]_{ik}
=
\sum_{j=1}^n\sum_{r=1}^p a_{ij}b_{jr}c_{rk}.
$$

Por outro lado,

$$
[(AB)C]_{ik}
=
\sum_{r=1}^p (AB)_{ir}c_{rk}
=
\sum_{r=1}^p\left(\sum_{j=1}^n a_{ij}b_{jr}\right)c_{rk}.
$$

Assim,

$$
[(AB)C]_{ik}
=
\sum_{r=1}^p\sum_{j=1}^n a_{ij}b_{jr}c_{rk}.
$$

Como as somas finitas podem ser reordenadas,

$$
[A(BC)]_{ik}=[(AB)C]_{ik}.
$$

Portanto,

$$
A(BC)=(AB)C.
$$

</aside>

<aside>

<b>Teorema</b> — O produto de matrizes é distributivo em relação à adição.

</aside>

<aside>

<b>Demonstração</b> — Temos

$$
[A(B+C)]_{ik}
=
\sum_{j=1}^n a_{ij}(b_{jk}+c_{jk}).
$$

Pela distributividade dos números reais,

$$
[A(B+C)]_{ik}
=
\sum_{j=1}^n a_{ij}b_{jk}
+
\sum_{j=1}^n a_{ij}c_{jk}.
$$

Logo,

$$
[A(B+C)]_{ik}=(AB)_{ik}+(AC)_{ik}.
$$

Portanto,

$$
A(B+C)=AB+AC.
$$

</aside>

Note que a multiplicação entre matrizes não é comutativa, ao contrário do produto usual entre números reais. De fato, $A \cdot B \neq B \cdot A$ de forma geral.

## Matrizes inversíveis

Para fins de concisão, nesta seção serão consideradas apenas matrizes quadradas de ordem $n$.

Perceba que o produto entre matrizes possui um elemento neutro. Esta matriz especial é denominada <b>matriz identidade</b>, possuindo a forma

$$
I_n =
\begin{pmatrix}
1 & 0 & 0 & ... & 0 \\
0 & 1 & 0 & ... & 0 \\
0 & 0 & 1 & ... & 0 \\
... & ... & ... & ... & ... \\
0 & 0 & 0 & ... & 1
\end{pmatrix}_{n \times n}
$$

Por ser elemento neutro dessa operação, esta matriz satisfaz a relação $AI_n = I_nA = A, \forall A$.

<aside>

<b>Teorema</b> — A matriz identidade é elemento neutro da multiplicação matricial.

</aside>

<aside>

<b>Demonstração</b> — Seja $A=(a_{ij})$. Então,

$$
(AI_n)_{ij} = \sum_{k=1}^n a_{ik}(I_n)_{kj}.
$$

Como $(I_n)_{kj}=1$ quando $k=j$ e $0$ caso contrário, resta apenas o termo $k=j$:

$$
(AI_n)_{ij}=a_{ij}.
$$

Logo,

$$
AI_n=A.
$$

De maneira análoga prova-se que

$$
I_nA=A.
$$

</aside>

Dizemos ainda que certa matriz $A$ é <b>inversível</b> se, e somente se, existe uma matriz $B$ tal que $AB = BA = I_n$. Se esta matriz existe, $B$ é denominada <b>matriz inversa de $A$</b> e denotada por $A^{-1}$.

<aside>

<b>Teorema</b> — Se uma linha ou coluna de uma matriz é nula, esta matriz não é inversível.

</aside>

<aside>

<b>Demonstração</b> — Suponha que a linha $i$ de $A$ seja nula. Então, para qualquer matriz $B$, a linha $i$ de $AB$ também será nula, pois

$$
(AB)_{ij}=\sum_{k=1}^n a_{ik}b_{kj}
$$

e todos os $a_{ik}$ são iguais a zero.

Logo, $AB$ não pode ser igual à matriz identidade, pois a identidade possui todos os elementos da diagonal principal iguais a $1$. Portanto, $A$ não é inversível.

O caso de coluna nula é análogo.

</aside>

<aside>

<b>Teorema</b> — Se $A$ e $B$ são inversíveis, então $AB$ também é inversível e

$$
(AB)^{-1}=B^{-1}A^{-1}.
$$

</aside>

<aside>

<b>Demonstração</b> — Temos que

$$
(AB)(B^{-1}A^{-1}) = A(BB^{-1})A^{-1} = AI_nA^{-1} = AA^{-1} = I_n
$$

Além disso,

$$
(B^{-1}A^{-1})(AB) = B^{-1}(A^{-1}A)B = B^{-1}I_nB = B^{-1}B = I_n
$$

Logo, $B^{-1}A^{-1}$ é a inversa de $AB$.

</aside>

<aside>

<b>Teorema</b> — Se $A$ é inversível, então

$$
(A^{-1})^{-1}=A.
$$

</aside>

<aside>

<b>Demonstração</b> — Pela definição da matriz inversa,

$$
AA^{-1}=A^{-1}A=I_n.
$$

Assim, $A$ é inversa de $A^{-1}$. Portanto,

$$
(A^{-1})^{-1}=A.
$$

</aside>

Se uma matriz $A$ é inversível, é possível determinar sua inversa por meio da aplicação de <b>operações elementares em suas linhas</b>, embora estas operações também estejam definidas para suas colunas.

De fato, essas operações são idênticas às operações elementares definidas para sistemas lineares. Como será visto adiante, sistemas lineares podem ser representados por matrizes, ou seja, podem ser escritos em uma <b>forma matricial</b>.

São operações elementares, de uma matriz $A$ qualquer, permutar duas de suas linhas; multiplicar uma linha por um $\lambda \in \mathbb{R}$, com $\lambda \neq 0$ e somar uma linha em outra.

De forma semelhante, se uma matriz $B$ pode ser obtida a partir de um número finito de operações elementares em $A$, dizemos que $A$ é <b>equivalente</b> a $B$ e denotamos esta relação por $A \sim B$. Valem as mesmas propriedades para a semelhança entre sistemas lineares.

<aside>

<b>Teorema</b> — Sistemas associados a matrizes equivalentes são equivalentes.

</aside>

<aside>

<b>Demonstração</b> — Sejam $A$ e $A'$ matrizes equivalentes. Logo, sabemos que $A' = MA$, com $M$ sendo um produto de matrizes elementares e, consequentemente, inversível. 

Os sistemas $(I)$ e $(II)$ que tem $A$ e $A'$ como matrizes ampliadas podem ser escritos respectivamente como $NX = B$ e $N'X = B'$, com $N$ e $N'$ as matrizes de coeficientes e $B$ e $B'$ as matrizes formadas pela última coluna das matrizes ampliadas.

Como $N' = MN$ e $B' = MB$, $NX = B \iff MNX = MB \iff N'X = B'$.

Isto significa que os sistemas $(I)$ e $(II)$ são equivalentes, pois toda matriz 

$$
X =
\begin{pmatrix}
x_1 \\ \vdots \\ x_n    
\end{pmatrix}
$$

que seja solução de $(I)$ será solução de $(II)$ e vice-versa.

</aside>

<aside>

<b>Teorema</b> — Uma matriz $A$ é inversível se, e somente se, $A \sim I_n$. As mesmas operações que transformam $A$ em $I_n$ transformam $I_n$ em $A^{-1}$.

</aside>

<aside>

<b>Demonstração</b> — Cada operação elementar sobre as linhas de uma matriz corresponde à multiplicação à esquerda por uma matriz elementar inversível.

Se uma sequência de operações transforma $A$ em $I_n$, então existem matrizes elementares $E_1,\dots,E_k$ tais que

$$
E_k \cdots E_1 A = I_n.
$$

Logo, temos que $A^{-1}=E_k \cdots E_1.$ Assim, $A$ é inversível.

Se $A$ é inversível, podemos aplicar <b>eliminação de Gauss-Jordan</b> para reduzir $A$ à identidade por operações elementares. Portanto, $A \sim I_n$. 

Além disso, aplicando as mesmas operações à matriz identidade obtemos precisamente $A^{-1}$. 

</aside>

Uma <b>matriz elementar</b> $E$ é uma matriz que, quando multiplicada por uma certa matriz $A$ qualquer, executa uma operação elementar nas linhas de $A$. A matriz correspondente a operação que será executada é produzida ao realizar esta operação elementar na matriz identidade de mesma ordem que $A$.

Por exemplo, considere a operação "permutar a linha 1 pela linha 2". Considerando uma matriz quadrada de ordem dois, temos que a matriz elementar correspondente é da forma: 

$$
E = 
\begin{pmatrix}
    0 & 1 \\ 
    1 & 0 
\end{pmatrix}
$$

De fato, considerando uma matriz $A$ de ordem dois qualquer, vemos que: 

$$
EA =
\begin{pmatrix}
    a & b \\ 
    c & d 
\end{pmatrix}
\begin{pmatrix}
    0 & 1 \\ 
    1 & 0
\end{pmatrix}
= 
\begin{pmatrix}
    c & d \\ 
    a & b 
\end{pmatrix}
$$

Uma consequência interessante é que dada uma matriz elementar qualquer $E_1$, esta é inversível e possui inversa $E_2$. Esta matriz inversa produz a operação inversa realizada por $E_1$.

# Eliminação de Gauss-Jordan

## Matrizes escalonadas 

Uma matriz escalonada é uma matriz cujo primeiro elemento não-nulo de cada linha, lidas da esquerda para a direita, está mais a direita que o elemento correspondente da linha acima. Estes elementos são chamados <b>pivôs</b>. Consequentemente, teremos ou linhas nulas (inteiramente formadas por zeros) ou linhas com apenas zeros à esquerda do pivô. 

$$
A = 
\begin{pmatrix}
    3 & 2 & 1 \\ 
    0 & 4 & 1 \\ 
    0 & 0 & 2
\end{pmatrix}
$$

Pela relação entre matrizes e sistemas lineares, um sistema é dito escalonado se sua matriz de coeficientes é escalonada. Uma consequência disso é a fácil resolução por substituições sucessivas. 

Toda matriz escalonada é semelhante a uma matriz inversível (cf. demonstração do teorema anterior), com o processo da aplicação de operações elementares nessa matriz para torná-la escalonada sendo denominado <b>eliminação de Gauss-Jordan</b> ou simplesmente <b>eliminação gaussiana</b>. 

A eliminação gaussiana pode ser utilizada também para a dedução da <b>inversa</b> de uma determinada matriz, para a determinação do posto de uma matriz e também do determinante de uma matriz quadrada. 

Uma prática comum para o cálculo da inversa $A^{-1}$ de uma matriz $A$ é a escrita de $A$ ao lado da matriz identidade de mesma ordem. Após isso, executa-se a eliminação gaussiana em $A$ para transformá-la na identidade, enquanto as mesmas operações são realizadas na identidade ao lado. Ao final do processo, a matriz $A^{-1}$ estará ao lado da matriz $I_n$.

<aside>

<b>Exemplo</b> — Calcule a inversa da matriz $A$ abaixo pelo método da eliminação gaussiana.

$$
A = 
\begin{pmatrix}
    1 & 4 & 2 \\ 
    0 & 1 & 2 \\ 
    0 & 0 & 1 
\end{pmatrix}
$$

Partindo da configuração inicial, podemos efetuar as operações elementares $L_2 - 2L_3 \to L_2$ (subtrair da segunda linha o dobro da terceira e substituir na segunda linha), $L_1 - 2L_3 \to L_1$ (subtrair da primeira linha o dobro da terceira e substituir na primeira linha) e $L_1 - 4L_2 \to L_1$ (subtrair da primeira linha o quádruplo da segunda e substituir na primeira linha), obtendo a sequência abaixo.

$$
\left(
\begin{array}{ccc|ccc}
    1 & 4 & 2 & 1 & 0 & 0 \\ 
    0 & 1 & 2 & 0 & 1 & 0 \\ 
    0 & 0 & 1 & 0 & 0 & 1 
\end{array}
\right) 
$$

$$
\left(
\begin{array}{ccc|ccc}
    1 & 4 & 2 & 1 & 0 & 0 \\ 
    0 & 1 & 0 & 0 & 1 & -2 \\ 
    0 & 0 & 1 & 0 & 0 & 1 
\end{array}
\right) 
$$

$$
\left(
\begin{array}{ccc|ccc}
    1 & 4 & 0 & 1 & 0 & -2 \\ 
    0 & 1 & 0 & 0 & 1 & -2 \\ 
    0 & 0 & 1 & 0 & 0 & 1 
\end{array}
\right) 
$$

$$
\left(
\begin{array}{ccc|ccc}
    1 & 0 & 0 & 1 & -4 & 6 \\ 
    0 & 1 & 0 & 0 & 1 & -2 \\ 
    0 & 0 & 1 & 0 & 0 & 1 
\end{array}
\right) 
$$

Perceba que à esquerda temos a matriz identidade, enquanto à direita temos uma nova matriz, a matriz inversa de $A$.

</aside>

# Sistemas de Cramer

Considere um sistema linear $S$ de $m$ equações e $n$ incógnitas, da forma

$$
S :
\begin{cases}
a_{11}x_1 + ... + a_{1n}x_n = b_1 \\
... \\
a_{m1}x_1 + ... + a_{mn}x_n = b_m
\end{cases}
$$

Note que, se formarmos as matrizes

$$
A =
\begin{pmatrix}
a_{11} & a_{12} & ... & a_{1n} \\
a_{21} & a_{22} & ... & a_{2n} \\
... & ... & ... & ... \\
a_{m1} & a_{m2} & ... & a_{mn} \\
\end{pmatrix} \text{ } \text{ }
X =
\begin{pmatrix}
x_1 \\ x_2 \\ ... \\ x_n
\end{pmatrix} \text{ } \text{ }
B =
\begin{pmatrix}
b_1 \\ b_2 \\ ... \\ b_m
\end{pmatrix}
$$

podemos escrever $S$ na sua <b>forma matricial</b>, sendo uma equação $AX = B$. Nesta equação $A$ é denominada <b>matriz de coeficientes</b> do sistema $S$.

Por sua vez, um <b>sistema de equações de Cramer</b> é um sistema linear tal que $A$ seja inversível. Portanto, nesses sistemas de solução única, temos que

$$
X=A^{-1}B
$$

<aside>

<b>Teorema</b> — Um sistema de Cramer possui solução única dada por

$$
X=A^{-1}B
$$

</aside>

<aside>

<b>Demonstração</b> — Considere o sistema matricial

$$
AX=B
$$

Como $A$ é inversível, multiplicamos ambos os lados por $A^{-1}$:

$$
A^{-1}AX=A^{-1}B
$$

Pela associatividade do produto matricial,

$$
(A^{-1}A)X=A^{-1}B
$$

Como $A^{-1}A=I_n$,

$$
I_nX=A^{-1}B
$$

Logo,

$$
X=A^{-1}B
$$

A unicidade segue da unicidade da matriz inversa.

</aside>

# Cadeias de Markov 

Um <b>processo de Markov</b> é um modelo probabilístico para sistemas que podem assumir um dentre vários estados e que a transição de um estado para outro é probabilística, regida por uma <b>matriz de transição</b>. 

Um componente chave de um processo markoviano é o chamado <b>vetor de probabilidades</b>, uma matriz coluna em que cada entrada armazena a probabilidade do sistema assumir um estado num dado tempo. Além disso, a sequência anterior de estados não influencia na sequência de estados futuros: sistemas que contêm essa influência são não-markovianos, possuindo uma característica chamada <b>memória</b>.

Convém delimitar de forma clara a diferença entre um processo de Markov (o modelo matemático) e as <b>cadeias de Markov</b>, as sequências de estados produzidas por processos markovianos.

<aside>

<b>Definição (Processo de Markov, Boldrini)</b> — Um processo aleatório de Markov é um processo que pode assumir estados $a_1, ..., a_r$ de tal modo que a probabilidade de transição de um estado $a_j$ para um estado $a_i$ seja $p_{ij}$, um número que só depende de $a_j$ e $a_i$.

</aside>

<aside>

<b>Definição (Matriz estocástica, Boldrini)</b> — A matriz de probabilidades de transição, também conhecida por matriz estocástica, é dada por 

$$
T = 
\begin{pmatrix}
    p_{11} & p_{12} & \dots & p_{1r} \\ 
    p_{21} & p_{22} & \dots & p_{2r} \\ 
    \vdots & \vdots &  & \vdots \\ 
    p_{r1} & p_{r2} & \dots & p_{rr}
\end{pmatrix}
$$

com $p_{ij} \ge 0$. Além disso, toda coluna deve somar 1.

</aside>

<aside>

<b>Definição (Vetor de probabilidades, Boldrini)</b> — O vetor de probabilidades é aquele cuja i-ésima linha dá a probabilidade de ocorrência do estado $a_i$ após $n$ transições:

$$
\begin{pmatrix}
    p_1^{(n)} \\ 
    \vdots \\ 
    p_r^{(n)}
\end{pmatrix}
$$

Consequentemente, temos que após $n$ passos, 

$$
T^n \cdot 
\begin{pmatrix}
    p_1^{(1)} \\ 
    \vdots \\ 
    p_r^{(1)}
\end{pmatrix}
= 
\begin{pmatrix}
    p_1^{(n)} \\ 
    \vdots \\ 
    p_r^{(n)}
\end{pmatrix}
$$

</aside>

É possível prever uma espécie de "último estado" do processo markoviano, isto é, um vetor de probabilidades que serve como ponto de chegada para todos os outros dados iterações suficientes, caso a matriz de transição $T$ atenda algumas conduções.

<aside>

<b>Definição (Matriz regular, Boldrini)</b> — Uma matriz de probabilidades de transição é <b>regular</b> se alguma de suas potências possuem todos os seus elementos não-nulos.

</aside>

<aside>

<b>Teorema</b> — Se a matriz $T_{r \times r}$ das probabilidades de transição é regular, então: as potências $T^n$ aproximam-se de uma matriz $P$, isto é, cada elemento de $T^n$ aproxima-se do elemento correspondente em $P$; todas as colunas de $P$ são iguais, dadas por um vetor coluna 

$$
V = 
\begin{pmatrix}
    p_1 \\ 
    \vdots \\ 
    p_r
\end{pmatrix}
$$

com $p_i \gt 0 \forall i$; para qualquer vetor de probabilidades inicial 

$$
V_1 = 
\begin{pmatrix}
    p_1^{(1)} \\ 
    \vdots \\ 
    p_r^{(1)}
\end{pmatrix}
$$

o vetor de probabilidades $T^nV_1$ aproxima-se de $V$; o vetor $V$ é o único que satisfaz a equação $TV = V$, isto é, $V$ é um <a href="/books/higher_education/math/linear_algebra/eigenvalues.html" target="_blank">autovetor</a> de $T$.

</aside>

Após esta base matemática, é interessante a discussão de algum exemplo para exercitarmos estes conceitos.

Imagine que numa determinada região do Brasil, observa-se que, caso o ano seja chuvoso, a probabilidade que o ano seguinte também seja chuvoso é de $\dfrac{1}{4}$ e a probabilidade que o ano seguinte seja seco é de $\dfrac{3}{4}$. Por outro lado, caso o ano em curso seja seco, a probabilidade que o ano seguinte também seja seco é de $\dfrac{1}{2}$, com a probabilidade de um ano chuvoso sendo $\dfrac{1}{2}$.

Dessa forma, temos a seguinte matriz de transição:

$$
T = 
\begin{pmatrix}
    \frac{1}{4} & \frac{1}{2} \\ 
    \frac{3}{4} & \frac{1}{2}
\end{pmatrix}
$$

Além disso, o vetor de probabilidades correspondente é da forma

$$
\begin{pmatrix}
    p_c^{(n)} \\ 
    p_s^{(n)}
\end{pmatrix}
$$

com o primeiro termo sendo a probabilidade de chuva no n-ésimo ano e o segundo termo sendo a probabilidade de seca no n-ésimo ano.

Podemos ver que $T$ é regular e, portanto, as probabilidades a longo prazo são dadas por 

$$
\begin{pmatrix}
    \frac{1}{4} & \frac{1}{2} \\ 
    \frac{3}{4} & \frac{1}{2}
\end{pmatrix}
\begin{pmatrix}
    p_c \\ p_s
\end{pmatrix}
= 
\begin{pmatrix}
    p_c \\ p_s
\end{pmatrix}
$$

isto é, pelo sistema

$$
\begin{cases}
    p_c = \frac{1}{4}p_c + \frac{1}{2}p_s \\ 
    p_s = \frac{3}{4}p_c + \frac{1}{2}p_s 
\end{cases}
\iff 
\begin{cases}
    p_s = \frac{3}{2}p_c \\
    p_s + p_c = 1
\end{cases}
$$

que possui como soluções $p_c = \dfrac{2}{5}$ e $p_s = \dfrac{3}{5}$. Consequentemente, temos que a longo prazo, dois em cada cinco anos serão chuvosos, enquanto três em cada cinco anos serão secos.

## Genética mendeliana

Uma aplicação interessante dos processos de Markov é o estudo de problemas que envolvam a genética. Com efeito, podemos modelar a evolução genética de uma população através de uma adaptação probabilística do quadro de Punnett.

Como exemplo, vamos representar por $G$ o gene dominante e por $g$ o gene recessivo. Pelos nossos conhecimentos de genética mendeliana, definimos indivíduos $GG$ como dominantes neste alelo, híbridos se forem $Gg$ e recessivos caso $gg$.

Ao escrever o quadro de Punnett de cada um dos possíveis cruzamentos ($GG \times GG$, $gg \times gg$, ...) e calcular as probabilidades dos alelos genéticos resultantes (da prole), podemos construir a tabela abaixo (denotando indivíduos dominantes por $d$, recessivos por $r$ e híbridos por $h$).

$$
\begin{array}{c|c}
    & d \times d & r \times r & d \times r & d \times h & r \times h & h \times h \\ 
    \hline
    d & 1 & 0 & 0 & 0.5 & 0 & 0.25 \\ 
    h & 0 & 0 & 1 & 0.5 & 0.5 & 0.5 \\ 
    r & 0 & 1 & 0 & 0 & 0.5 & 0.25
\end{array}{}
$$

(Isto é, um cruzamento $d \times d$ produz sempre $d$, um cruzamento $d \times h$ produz metade $d$ e metade $h$ e assim por diante)

Essa tabela pode ser reescrita como a matriz de transição de nosso processo de Markov.

$$
T = 
\begin{pmatrix}
    1 & 0 & 0 & 0.5 & 0 & 0.25 \\ 
    0 & 0 & 1 & 0.5 & 0.5 & 0.5 \\ 
    0 & 1 & 0 & 0 & 0.5 & 0.25
\end{pmatrix}
$$

Nosso vetor de estado, então, será da forma

$$
\begin{pmatrix}
    p_d^{(1)} \cdot p_d^{(1)} \\ 
    p_r^{(1)} \cdot p_d^{(1)} \\ 
    2p_d^{(1)} \cdot p_r^{(1)} \\ 
    2p_d^{(1)} \cdot p_h^{(1)} \\ 
    2p_r^{(1)} \cdot p_h^{(1)} \\ 
    p_h^{(1)} \cdot p_h^{(1)}
\end{pmatrix}
$$

com os produtos por dois sendo necessários para levar em conta a equivalência de dois casos, por exemplo, que o cruzamento entre um indivíduo dominante e um recessivo é equivalente ao cruzamento entre um recessivo e um dominante: há uma simetria.

Levando tudo isso em conta, temos que o produto matricial de nosso processo markoviano é 

$$
\begin{pmatrix}
    1 & 0 & 0 & 0.5 & 0 & 0.25 \\ 
    0 & 0 & 1 & 0.5 & 0.5 & 0.5 \\ 
    0 & 1 & 0 & 0 & 0.5 & 0.25
\end{pmatrix}
\cdot 
\begin{pmatrix}
    p_d^{(1)} \cdot p_d^{(1)} \\ 
    p_r^{(1)} \cdot p_d^{(1)} \\ 
    2p_d^{(1)} \cdot p_r^{(1)} \\ 
    2p_d^{(1)} \cdot p_h^{(1)} \\ 
    2p_r^{(1)} \cdot p_h^{(1)} \\ 
    p_h^{(1)} \cdot p_h^{(1)}
\end{pmatrix}
= 
\begin{pmatrix}
    p_d^{(2)} \\ 
    p_h^{(2)} \\ 
    p_r^{(2)}
\end{pmatrix}
$$

para levar a distribuição genética atual "1" à geração seguinte "2". Convém mencionar que estamos supondo um modelo não darwiniano, sem mutações, nem predação, nem muitas outras coisas. Estamos apenas imaginando uma distribuição genética no caso mais simples, conforme estudada por Mendel em suas ervilhas.


# Referências

1. CALLIOLI, Carlos Alberto; DOMINGUES, Hygino H.; COSTA, Roberto da. <i>Álgebra Linear e Aplicações</i>. 4ª edição revisada. São Paulo: Atual, 1983.
2. BOLDRINI, José Luiz; COSTA, Sueli I. Rodrigues; FIGUEIREDO, Vera Lúcia; WETZLER, Henry G. <i>Álgebra Linear</i>. 3ª edição ampliada e revista. São Paulo: Harper & Row do Brasil, 1980.