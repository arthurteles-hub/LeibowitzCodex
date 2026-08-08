# Introdução às derivadas

# Introdução

![São Paulo Metro](https://upload.wikimedia.org/wikipedia/commons/0/00/Metro_de_S%C3%A3o_Paulo%2C_Luz_Station%2C_Brazil.jpg)

<i><span title="botão metrô" style="cursor:pointer" onclick="const a = this._a || (this._a = new Audio('/books/higher_education/math/calculus_one/images/metro-sao-paulo.mp3')); a.paused ? a.play() : a.pause();">🎶🎹🎶🎹</span>Próxima estação, next station, Butantã... (Imagem sob CC-BY-SA, via <a href="https://commons.wikimedia.org/wiki/File:Metro_de_S%C3%A3o_Paulo,_Luz_Station,_Brazil.jpg" target="_blank">Wikimedia Commons</a>)</i>

A linha 1-Azul do metrô de São Paulo, também conhecida como Linha Norte-Sul, é a mais antiga linha do sistema do metrô, inaugurada em 1974. Também é uma das maiores e mais movimentadas, com milhões de passageiros atravessando os 20 quilômetros de trilhos todos os dias pelos mais variados motivos. A capital não poderia viver sem ela. 

Sua extensão tem um preço: ela consegue ser extremamente lenta em horários de pico, mas incrivelmente rápida fora do <i>rush</i> — alguns minutos separam a "Liberdade" do "Paraíso".

Vamos imaginar que a coordenação do sistema mediu a **velocidade média** da linha, em horário de pico, como sendo aproximadamente 32 km/h. Por padrão, calculamos essa grandeza pela expressão:

$$
V_m=\dfrac{\text{Espaço percorrido}}{\text{Tempo gasto}}
$$

Podemos nos perguntar: seria essa medida realmente precisa? Ela realmente representa a velocidade do trem analisado pelo percurso? Bom, não necessariamente. O trem poderia estar mais devagar no começo, ou mais rápido no fim, ou o contrário, ou ainda ter demorado demais numa estação pela dificuldade em fechar as portas. 

A velocidade média é uma péssima medida se quisermos medir a velocidade do sistema em tempos específicos. 

Mas perceba que podemos tornar nossa medida cada vez melhor ao subdividir nossa medida em várias medidas com espaços de tempo cada vez menores: quanto menor o espaço de tempo considerado, mais próximos estaremos da velocidade real em torno de um instante específico. 

Essa visualização de uma **taxa de mudança** em tempos cada vez menores nos leva naturalmente ao conceito de **derivada**, que veremos adiante.

# Definição



Definimos derivada como o limite da **taxa de variação média** de uma função quando o intervalo $h$ entre os valores da nossa variável (tempo, espaço, …) se torna cada vez mais próximo de zero, ou seja, estamos medindo o quão “sensível” a função é em resposta a uma pequena mudança no seu valor de entrada. 

De maneira mais formal, podemos definir que a derivada de uma certa função $f(x)$, denotada por $f'(x)$, é dada por:

$$
f'(x)=\lim_{h \rightarrow 0} \dfrac{f(x+h) - f(x)}{h}
$$

Perceba que esse limite nos retornará uma função cuja variável ainda é $x$:  no nosso exemplo acima, podemos calcular a velocidade da ferrovia em qualquer instante que quiséssemos.

Uma propriedade notável é que **toda função que é diferenciável**, isto é, possui uma derivada, é uma função contínua. O oposto, no entanto, nem sempre é verdade — muitas funções são contínuas mas não possuem derivadas, como por exemplo as **funções modulares**, que possuem limites laterais diferentes no ponto do “bico”.

<aside>

É importante salientar que é perfeitamente possível que a derivada de uma função seja também diferenciável. A derivada da derivada é chamada “derivada segunda” de $f$, denotada por $f''$ ou $f^{(2)}$. A derivada dessa derivada é a “derivada terceira” e assim por diante. 

</aside>

De forma geral, as três razões possíveis de uma função deixar de ser diferenciável num dado ponto são a presença de “bicos”, a descontinuidade de uma função naquele ponto ou ainda que a reta tangente no ponto analisado é uma reta vertical — razão que será justificada na seção seguinte.

## Interpretação geométrica

Ainda é possível uma interpretação geométrica da derivada — uma função que nos fornece o coeficiente angular da reta tangente à nossa função original em qualquer ponto que quisermos. Esse relacionamento pode ser deduzido a partir do próprio cálculo de um coeficiente angular dada uma reta e dois pontos: 

$$
m=\dfrac{y-y_0}{x-x_0}=\dfrac{\Delta y}{\Delta x}
$$

Percebe que o cálculo do coeficiente angular é uma taxa de variação entre $y$ e $x$?

## Interpretando o sinal da derivada

Dessa forma, se em um dado ponto $a$ temos $f'(a)>0$, podemos concluir que a função $f$ é **crescente em torno desse ponto**, pois a taxa de variação entre $y$ e $x$ é **positiva** — quando aumentamos $x$, aumentamos $y$.

O oposto acontece quando $f'(a)<0$, com $f$ decrescente em torno daquele ponto, característica indicada pela sua taxa de variação **negativa** — quando aumentamos $x$, diminuímos $y$.

O último caso, $f'(a)=0$, marca um ponto de **máximo**, **mínimo** ou ainda de **inflexão** — a mudança de $x$ não afeta $y$ nas proximidades daquele ponto. Veremos isso com mais detalhes adiante.

## Exemplos

Por fim, vamos a um exemplo! Qual seria a derivada da função $f(x)=x^2$? 

Nos utilizando da definição dada, podemos calcular o limite. 

$$
\begin{align*}
f'(x)&=\lim_{h \rightarrow 0} \dfrac{(x+h)^2 - x^2}{h}\\\\
f'(x)&=\lim_{h \rightarrow 0}\dfrac{x^2+2xh+h²-x²}{h}\\\\
f'(x)&=\lim_{h \rightarrow 0}\dfrac{h(2x + h)}{h}\\\\
f'(x)&=\lim_{h \rightarrow 0}2x+h\\\\
f'(x)&=2x
\end{align*}
$$

Esse padrão irá se repetir muitas vezes ao derivarmos pela definição — rearranjar a expressão com o objetivo de nos livrar do denominador $h$ e chegar numa expressão que, no final, podemos ignorar completamente essa variável, afinal, **ela tente a zero**, torna-se infinitamente pequena.

Que tal um outro exemplo, mais aplicado à realidade? Vamos dizer que numa vidraria é produzida uma certa quantidade $Q(t)$ (em kg) de vidro temperado, em função de um dado tempo $t$, em horas, aproximada pela função

$$
Q(t)=3t^2-10t
$$

Qual seria a **velocidade de produção** da fábrica? Podemos calcular a velocidade de produção em torno de um dado tempo derivando a função pela definição:

$$
\begin{align*}
Q'(t)&=\lim_{h \rightarrow 0} \dfrac{3(t+h)^2-10(t+h)-3t²+10t}{h}\\\\
Q'(t)&=\lim_{h \rightarrow0}\dfrac{3(t^2+2th+h^2)−10t−10h−3t^2+10t}{h}\\\\
Q'(t)&=\lim_{h \rightarrow 0}\dfrac{6ht+3h^2-10h}{h}\\\\
Q'(t)&=\lim_{h \rightarrow 0}6t-10+3h\\\\
Q'(t)&=6t-10
\end{align*}
$$

Ou seja, poderíamos dizer que a velocidade de produção é de $6t-10$ **quilogramas de vidro por hora** em um dado instante $t$. Por exemplo, quando $t=3$, temos que a velocidade é de

$$
Q'(3)=6 \times 3 - 10 = 8 \text{kg/h}
$$

Em outro instante, por exemplo, quando $t=1$,

$$
Q'(1)=-4 \text{kg/h}
$$

Uma produção que na verdade perde quilos de vidros a cada hora, indicando, talvez, perda de material ou uma paralisação por algum outro motivo.

# Notações para derivada

Ao longo dos anos, diversas notações para representar a função derivada foram desenvolvidas, com as mais conhecidas sendo as de **Newton**, **Leibniz** e **Lagrange**. Enquanto a primeira é utilizada mais nos campos da Física, as duas últimas são mais gerais, podendo ser encontradas em uma variedade de contextos.

A notação de Newton, nomeada em homenagem a Isaac Newton, físico inglês, é comumente utilizada na física para representar as funções derivadas de uma função cujo domínio é o tempo. 

Por exemplo, sendo $y(t)$ uma função da altura de um corpo no decorrer do tempo, $\dot{y}$ seria sua primeira derivada — a velocidade — e $\ddot{y}$ sua segunda derivada, a aceleração. Por praticidade, essa notação não é muito utilizada para derivadas de ordem superior. 

Uma notação um pouco mais explícita é a de Lagrange. Para uma certa função $f(x)$, escrevemos sua derivada de primeira ordem como $f'$ ou $f^{(1)}$, a de segunda ordem como $f''$  ou $f^{(2)}$ e assim por diante. É um meio termo entre as notações de Newton e Leibnitz. 

Por sua vez, a notação de Leibnitz é a mais explícita e detalhada de todas as comumente utilizadas, identificando inclusive a variável que a função está sendo derivada. Para uma certa função $f(x)$, podemos denotar sua derivada em relação à variável $x$ por $\dfrac{df}{dx}$ ou $\dfrac{d}{dx}f(x)$.

# Referências 

1. GUIDORIZZI, Hamilton Luiz. Um curso de cálculo. 5.ed., reimpr. Rio de Janeiro: LTC, 2011. 530 p. LTC
2. STEWART, James. Cálculo. Volume 1. 6. ed. São Paulo: Cengage Learning, 2009.