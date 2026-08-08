# Sistemas lineares

# Sistemas lineares

Para compreendermos os conceitos sobre os <b>sistemas lineares</b>, é necessário primeiro nos debruçarmos sobre a noção de <b>equação linear</b>. Definimos uma equação da forma

$$
\alpha_1x_1 + \alpha_2x_2 + ... + \alpha_nx_n = \beta, \text{com }\alpha, \beta \in \mathbb{R}, \text{e } n \ge 1
$$

como uma <b>equação linear</b>. Além disso, se a n-upla $(b_1, b_2, ..., b_n) \in \mathbb{R}^n$ satisfizer a relação ao fazermos $x_1 = b_1$, $x_2 = b_2$, ..., $x_n = b_n$, dizemos que esta n-upla é uma <b>solução</b> da equação linear.

Definimos um <b>sistema de equações</b> $S$ de $m$ equações e $n$ incógnitas, com $m, n \ge 1$, como um conjunto de equações lineares da forma

$$
S:
\begin{cases}
\alpha_{11}x_1 + ... + \alpha_{1n}x_n &= \beta_1 \\
\alpha_{21}x_1 + ... + \alpha_{2n}x_n &= \beta_2 \\
\dots \\
\alpha_{m1}x_1 + ... + \alpha_{mn}x_n &= \beta_m \\
\end{cases}
$$

Se $m = n$, podemos dizer que $S$ é um <i>sistema linear de ordem $n$</i>. Além disso, uma n-upla $(b_1, b_2, ..., b_n) \in \mathbb{R}^n$ é <b>solução</b> do sistema $S$ se esta é solução de cada uma das $m$ equações simultaneamente.

## Sistemas equivalentes

Dizemos que dois sistemas $S_1$ e $S_2$ são <b>equivalentes</b> (denotado por $S_1 \sim S_2$) se seus conjuntos de soluções são iguais. De fato, um sistema $S_2$ equivalente a um sistema $S_1$ pode ser obtido por meio de uma sequência de aplicações das seguintes operações:

<aside>

1. Permutar duas equações de $S_1$
2. Multiplicar uma das equações de $S_1$ por $\lambda \in \mathbb{R}, \lambda \neq 0$
3. Somar uma das equações deste sistema a outra equação deste mesmo sistema

</aside>

Estas operações são chamadas <b>operações elementares</b>.

Dados três sistemas lineares $S_1, S_2, S_3$, valem ainda as propriedades:

<aside>

1. $S_1 \sim S_1$ (reflexividade)
2. $S_1 \sim S_2 \implies S_2 \sim S_1$ (simetria)
3. $S_1 \sim S_2$ e $S_2 \sim S_3 \implies S_1 \sim S_3$ (transitividade)

</aside>

<aside>

<b>Teorema</b> — As operações elementares preservam o conjunto solução de um sistema linear.

</aside>

<aside>

<b>Demonstração</b> — Considere um sistema linear $S$. Permutar duas equações não altera o conjunto solução, pois a ordem das equações é irrelevante para a simultaneidade das condições impostas.

Além disso, multiplicar uma equação por $\lambda \neq 0$ produz uma equação equivalente, pois

$$
a_1x_1 + ... + a_nx_n = b
$$

é satisfeita se, e somente se,

$$
\lambda a_1x_1 + ... + \lambda a_nx_n = \lambda b
$$

também o é.

Por fim, se substituímos uma equação pela soma dela com outra, qualquer solução do sistema original continua satisfazendo a nova equação, pois a soma de igualdades válidas permanece válida. Reciprocamente, como a operação pode ser revertida pela subtração da equação adicionada, o conjunto solução permanece inalterado.

Logo, todas as operações elementares preservam o conjunto solução do sistema.

</aside>

<aside>

<b>Teorema</b> — A relação de equivalência entre sistemas lineares é reflexiva, simétrica e transitiva.

</aside>

<aside>

<b>Demonstração</b> — Considere os seguintes raciocínios para cada propriedade a seguir.

Todo sistema possui o mesmo conjunto solução que ele próprio, portanto $S_1 \sim S_1$ (reflexividade). Além disso, se $S_1 \sim S_2$, então ambos possuem o mesmo conjunto solução. Logo, $S_2$ possui o mesmo conjunto solução que $S_1$, isto é, $S_2 \sim S_1$ (simetria). Por fim, se $S_1 \sim S_2$ e $S_2 \sim S_3$, então os três sistemas possuem o mesmo conjunto solução. Portanto, $S_1 \sim S_3$ (transitividade).

</aside>

Por estas operações podemos simplificar sistemas complexos para outros mais simples e de mais fácil resolução.

# Referências

1. CALLIOLI, Carlos Alberto; DOMINGUES, Hygino H.; COSTA, Roberto da. <i>Álgebra Linear e Aplicações</i>. 4ª edição revisada. São Paulo: Atual, 1983.