# Práticas, regras e técnicas úteis 

<aside>

Este documento servirá como um compêndio de algumas regras, técnicas e práticas que podem ser úteis em algumas situações, acelerando o processo de derivação e economizando tempo e esforço. 

</aside>

# Derivação implícita

A <b>derivação implícita</b> é uma técnica muito útil para derivar funções oriundas de equações que relacionam $x$ e $y$, pois nem sempre é fácil escrever $y$ diretamente em função de $x$. Quando isso acontece, precisamos usar a derivação implícita: derivamos os dois membros da equação em relação a $x$ enquanto tratamos $y$ como uma função de $x$ ainda desconhecida.

Por exemplo, considere a equação $x^2+y^2=1$, a equação de um círculo. É fácil ver que podemos explicitar $y=f(x)$ por meio de uma simples reescrita: 

$$
x^2+y^2 = 1 \Rightarrow y = \sqrt{1-x^2}
$$

Mas e se tivermos uma equação como $\sin{(x+y})=y²\cos{x}$? Nesse caso, como encontrar a derivada de $y$? Começaremos derivando ambos os membros em relação a $x$.

$$
\begin{align*}
\dfrac{d}{dx}(\sin{(x+y)})&=\dfrac{d}{dx}(y^2 \cos x)\\\\
\cos{(x+y)} \cdot (1 + y') &= 2y \cdot y' \cos{x} + y^2 (- \sin x)\\\\
\cos{(x+y)} + \cos{(x+y)}y' &= 2y \cos{x} \cdot y' - y^2 \sin{x}\\\\
\end{align*}
$$

Perceba que sempre aplicamos a regra da cadeia ao derivarmos uma expressão que envolve $y$, pois ela é uma função de $x$. 

$$
\begin{align*}
[\cos{(x+y)} - 2y \cos{x}]y' &= -y^2 \sin{x} - \cos{(x+y)}\\\\
y'&=\dfrac{y^2 \sin{x} + \cos{(x+y)}}{2y\cos{x} - \cos{(x+y)}}
\end{align*}
$$

Essa estratégia de derivação se mostra muito útil em problemas das mais variadas áreas, como Física, Química e Economia — quando sabemos a relação entre as variáveis de forma implícita, e seria trabalhoso demais colocar uma em função da outra. 

Se quisermos encontrar a expressão original de $y$, poderemos nos utilizar das técnicas de integração e equações diferenciais, que veremos no decorrer dos próximos cursos — livretos — de Cálculo.

# Derivação logarítmica

A <b>derivação logarítmica</b> é uma prática muito eficiente quando se mostra necessário derivar funções formadas por uma grande quantidade de expressões, mais comumente produtos, quocientes e potências. 

Ela consiste apenas em aplicar o logaritmo natural na equação da função, simplificar e derivar implicitamente, extraindo a derivada ao final. 

Por exemplo, vamos encontrar a derivada da função $f(x)=\dfrac{x²\sqrt[3]{5x-10}}{(x-2)^2}$.

Primeiro, vamos aplicar o logaritmo natural nos dois lados da equação e simplificar: 

$$
\begin{align*}
    \ln|y|&=\ln\left|\dfrac{x^2 \sqrt[3]{5x-10}}{(x-2)^2}\right|\\
    &=\ln|x² \cdot \sqrt[3]{5x-10}| - \ln|(x-2)^2|
\end{align*}
$$

Perceba que estamos considerando o <b>módulo da expressão</b> pois a função logaritmo não está definida para números negativos. Além disso, pode-se demonstrar que $(\ln{|x|})' = (\ln{x})' = \dfrac{1}{x}$. 

$$
\begin{align*}
    \ln |y|&= \ln |x²|+\ln|\sqrt[3]{5x-10}| - 2\ln|x-2|\\
    \ln |y|&= 2\ln|x| + \dfrac{1}{3} \ln |5x-10| - 2\ln|x-2|\\
\end{align*}
$$

Com a expressão simplificada, derivamos ambos os lados da equação em relação a $x$. 

$$
y' \cdot \dfrac{1}{y}=2 \cdot \dfrac{d}{dx} \ln x + \dfrac{1}{3} \cdot \dfrac{d}{dx} \ln(5x-10) - 2 \cdot \dfrac{d}{dx}\ln (x-2)
$$

Perceba que ignoramos completamente a função módulo necessária depois da derivada: o motivo está na derivação de $\ln|y|$.

Ao derivar $\ln |y|$, a regra da cadeia nos dá:

$$
\dfrac{d}{dx}\ln |y| = \dfrac{1}{|y|} \cdot \text{sgn}(y) \cdot y'
$$

Mas como $\dfrac{1}{|y|} \cdot \text{sgn}(y)=\dfrac{1}{y}$, temos que o resultado final simplifica para $\dfrac{1}{y} \cdot y'$.

Essa relação é válida para os casos de $y > 0$ e $y < 0$ — quando $y=0$, a derivada não existe.

Finalizando essa observação importante e retornando ao objetivo principal, podemos pela regra da cadeia encontrar as derivadas procuradas e continuar a simplificação.

$$
\begin{align*}
    y' \cdot \dfrac{1}{y} &= 2 \cdot \dfrac{1}{x} + \dfrac{1}{3} \cdot \dfrac{1}{5x-10} \cdot 5 - 2 \cdot \dfrac{1}{x-2}\\\\
    &= \dfrac{2}{x} + \dfrac{1}{3(x-2)} - \dfrac{2}{x-2}\\\\
    &= \dfrac{2}{x} - \dfrac{5}{3(x-2)}\\\\
\end{align*}
$$

Por fim, multiplicando ambos os lados por $y$: 

$$
\begin{align*}
    y'&=\left(\dfrac{x^2 \sqrt[3]{5x-10}}{(x-2)^2}\right)\left(\dfrac{2}{x} - \dfrac{5}{3(x-2)}\right)\\\\
    y'&= \dfrac{2x \sqrt[3]{5x-10}}{(x-2)^2} - \dfrac{5x^2 \sqrt[3]{5x-10}}{3(x-2)^3} \\\\
    y'&= \dfrac{(6x^2-12x) \cdot \sqrt[3]{5x-10}-5x² \sqrt[3]{5x-10}}{3(x-2)^3}\\\\
    y'&= \dfrac{(x^2-12x) \cdot \sqrt[3]{5x-10}}{3(x-2)^3}
\end{align*}
$$

Veja como essa técnica poupou tempo ao evitar que aplicássemos repetidas vezes as regras do produto, quociente e da cadeia! 

# Regra de L’Hôpital

Enquanto o simples rearranjo algébrico pode levantar indeterminações em alguns limites, a <b>regra de L’Hôpital</b> nos ajuda a tratar de forma simples dois tipos de indeterminações, a saber, as de tipos $\dfrac{0}{0}$ ou $\dfrac{\infty}{\infty}$. 

A regra estabelece que, se supormos duas funções, $f(x)$ e $g(x)$, diferenciáveis em um intervalo aberto $I$, com $g'(x) \neq 0$ — exceto em um dado $a \in I$, possivelmente —, e uma das seguintes situações ocorrerem,

$$
\begin{array}{ccc}
    \lim_{x \rightarrow a} f(x) = 0 & \text{e} &\lim_{x \rightarrow a} g(x)=0\\
    \\
    & \text{ou} &
    \\
    \\
    \lim_{x \rightarrow a} f(x) = \pm \infty & \text{e} &\lim_{x \rightarrow a} g(x)= \pm\infty,
\end{array}
$$

podemos concluir que $\lim_{x \rightarrow a} \dfrac{f(x)}{g(x)} = \lim_{x \rightarrow a} \dfrac{f'(x)}{g'(x)}$.

Para fins ilustrativos, vamos calcular o seguinte limite: $\lim_{x \rightarrow 2} \dfrac{x - 2}{x^2 - 4}$. 

Podemos perceber que se substituirmos diretamente, teremos uma indeterminação do tipo $\dfrac{0}{0}$. O próximo passo é derivar o numerador e o denominador, para levantar essa indeterminação. Derivando-os, chegamos em: 

$$
\begin{align*}
\lim_{x \rightarrow 2} \dfrac{1 - 0}{2x - 0} &= \lim_{x \rightarrow 2} \dfrac{1}{2x}\\\\
&= \dfrac{1}{2(2)}\\\\
&=\dfrac{1}{4}
\end{align*}
$$

Simples, prático, eficiente. Essa regra é extremamente útil, e irá nos poupar horas de trabalho.

# Referências 

1. GUIDORIZZI, Hamilton Luiz. Um curso de cálculo. 5.ed., reimpr. Rio de Janeiro: LTC, 2011. 530 p. LTC
2. STEWART, James. Cálculo. Volume 1. 6. ed. São Paulo: Cengage Learning, 2009.