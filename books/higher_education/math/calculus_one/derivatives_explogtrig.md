# Derivando funções transcendentais

# Introdução

Dizemos que funções que não podem ser expressas por meio de uma soma finita de polinômios, como <b>senos</b>, <b>exponenciais</b> e <b>logarítmicas</b>, são funções <b>transcendentais</b>, pois elas transcendem a álgebra<!--Adicionar aqui um adendo: "embora possam ser expressas por meio de Séries infinitas" (daí coloca um link para ir para página de séries). Do jeito que estava está impreciso por não incluir esse detalhe-->. De fato, abaixo veremos como podemos derivar essas funções citadas acima, funções trigonométricas, exponenciais e logarítmicas, e suas regras de derivação correspondentes.

# Derivando funções exponenciais

As funções exponenciais formam um problema único no estudo do cálculo, pois obter sua derivada mostra-se algo um pouco mais complexo, que iremos abordar ao longo dessa seção.

Antes de tudo, chamamos função exponencial toda função $f(x)=b^x$, com $b > 0$ e $b \neq 1$. 

Tendo isso em mente, vamos tentar derivá-la por meio da definição. Assim, temos que: 

$$
\begin{align*}
    f'(x)&=\lim_{h \rightarrow 0} \dfrac{b^{x + h} - b^x}{h}\\
    &=\lim_{h \rightarrow 0} \dfrac{b^x \cdot b^h - b^x}{h}\\
    &=b^x \cdot \lim_{h \rightarrow 0}\dfrac{b^h - 1}{h}
\end{align*}
$$

Perceba que não temos informação o suficiente para derivar uma função exponencial de base qualquer pois ainda não sabemos como calcular o último limite — só temos uma única informação, **ele é uma constante**, o limite não depende de $x$. 

Chegamos ao fato de que o limite dessa função é proporcional a uma constante que não sabemos, ainda, seu valor. Chegamos a uma barreira.

Para derrubá-la, vamos primeiro imaginar duas bases, a saber, $b_1 = 2$ e $b_2 = 3$. Iremos substituí-las na função do interior do limite que não conseguimos resolver. 

Assim, definimos duas funções, $p(h)$ e $g(h)$, com $b=b_1$ e $b=b_2$, respectivamente. 

Note que quando calculamos o limite dessas duas funções, $\lim_{h \rightarrow 0} p(h)$ e $\lim_{h \rightarrow 0} g(h)$, ambos são bem próximos de 1, sugerindo a existência de uma base cujo limite é exatamente esse valor. 

Vamos batizar essa base **especial** chamando-a $e$.

Na matemática, esse número é conhecido por **número de Euler** ou **número neperiano**, em homenagem aos matemáticos Leonhard Euler e John Napier.

![](images/limits/limits_super_convenient.png)

<i>Seria super conveniente...</i>

Seria conveniente utilizar $e$ como nossa base, pois nossa expressão original, complicada, se tornaria algo simples e prático. 

Dessa forma, quando $b=e$, o limite se torna:

$$
\begin{align*}
    f'(x)&=e^x \cdot \lim_{h \rightarrow 0} \dfrac{e^h-1}{h} \\
    &=e^x
\end{align*}
$$

Ou seja, a derivada da **função exponencial natural** — $f(x)=e^x$ — é ela própria. 

<aside>

<b>Demonstração do limite "conveniente"</b> — Para encontrar o limite $\lim_{h \to 0}\left(\dfrac{e^h-1}{h}\right)$, iremos nos utilizar do limite exponencial fundamental. 

Dessa forma, fazendo $t = \dfrac{1}{e^h-1}$, segue que $\dfrac{1}{t} = e^h - 1$. Realizando a mudança de variável no limite, de $h$ para $t$: 

$$
\begin{align*}
    \lim_{t \to \infty} \left(\dfrac{\dfrac{1}{t}}{\ln\left({1 + \dfrac{1}{t}}\right)}\right) &= \lim_{t \to \infty} \left(\dfrac{1}{t\ln\left({1 + \dfrac{1}{t}}\right)}\right) \\\\
    &= \lim_{t \to \infty} \left(\dfrac{1}{\ln\left(\left(1+\dfrac{1}{t}\right)^t\right)}\right)
\end{align*}
$$

Por definição, sabe-se que $\lim_{t \to \infty} \left(1 + \dfrac{1}{t}\right)^{t} = e$. Além disso, pela continuidade da função logarítmica em todo seu domínio: 

$$
\begin{align*}
    \lim_{t \to \infty} \left(\dfrac{1}{\ln\left(\left(1+\dfrac{1}{t}\right)^t\right)}\right) &= \lim_{t \to \infty} \left(\dfrac{1}{\ln{e}}\right) = \dfrac{1}{1} = 1.
\end{align*}
$$

</aside>

“Mas e as outras bases?”, alguém pode se questionar, mas não se preocupe, pois esse número que encontramos é justamente a chave que irá permitir a superação de nossa barreira no cálculo da derivada de uma exponencial qualquer. 

E se reescrevêssemos nossa função exponencial de base geral **mudando a sua base** para nosso número especial? Isso pode ser feito da seguinte maneira:

$$
b^x=(e^{\log_e{b}})^x
$$

Lembrando que isso pode ser feito por uma propriedade fundamental dos logaritmos: $p^{\log_p{k}}=p$.

Voltando a nossa igualdade original, podemos continuar a simplificá-la:

$$
\begin{align*}
b^x&=(e^{\log_e{b}})^x\\\\
&=e^{x \cdot \log_e{b}}\\\\
&=e^{x \cdot \ln{b}}
\end{align*}
$$

Em questões de notação, podemos reescrever $\log_e$ como $\ln$ — este é o logaritmo natural. 

Todo esse processo de reescrita foi para possibilitar a aplicação da regra da cadeia em nossa função. Assim, derivando $b^x$ pela regra da cadeia, nós obtemos que: 

$$
\begin{align*}
    \dfrac{d}{dx}(b^x) &=\dfrac{d}{dx}(e^{x \cdot \ln{b}}) \\
    &= e^{x \cdot \ln{b}} \cdot \ln b \\
    &= b^x \cdot \ln b
\end{align*}
$$

Conseguimos o que queríamos! 

Por fim, é importante salientar que este resultado é também válido para qualquer função $b^{f(x)}$, isto é:

$$
\dfrac{d}{dx}b^{f(x)}=b^{f(x)} \cdot  \ln{b} \cdot f'(x)
$$

Essa regra será bastante útil em situações de funções exponenciais compostas. 

# Derivando funções logarítmicas

Podemos denominar **função logaritmo** toda função $f(x)=\log_bx$, com todas as restrições numéricas necessárias para que o logaritmo exista, como por exemplo, que $b>0$ e $b\neq 1$. Em especial, podemos calcular a derivada da função logaritmo natural como base para o caso geral. 

<aside>

<b>Demonstração (derivada da função logaritmo)</b> — Pela definição de derivada, temos: 

$$
\begin{align*}
    \lim_{h \to 0}\left(\dfrac{\ln{(x+h)}-\ln{x}}{h}\right) &= \lim_{h \to 0}\left(\dfrac{\ln{\left(\dfrac{x+h}{x}\right)}}{h}\right) \\\\
    &= \lim_{h \to 0}\left(\dfrac{\ln{\left(1 + \dfrac{h}{x}\right)}}{h}\right)
\end{align*}
$$

Fazendo $t = \dfrac{h}{x}$, temos: 

$$
\begin{align*}
    \lim_{h \to 0}\left(\dfrac{\ln{\left(1 + \dfrac{h}{x}\right)}}{h}\right) &= \lim_{t \to 0}\left(\dfrac{\ln\left(1 + t\right)}{xt}\right) \\\\
    &= \lim_{t \to 0}\left(\dfrac{1}{xt}\ln\left(1 + t\right)\right) \\\\
    &= \dfrac{1}{x} \cdot \lim_{t \to 0} \left(\left(1 + t\right)^{1/t}\right)
\end{align*}
$$

Como a função $\ln(1+t)^{1/t}$ é contínua em todo o seu domínio, podemos escrever: 

$$
\dfrac{1}{x} \cdot \lim_{t \to 0} \left(\left(1 + t\right)^{1/t}\right) = \dfrac{1}{x} \cdot \ln\left(\lim_{t \to 0}\left(1+t\right)^{1/t}\right)
$$

Note que o limite $\lim_{t \to 0}\left(1+t\right)^{1/t}$ é um limite fundamental, valendo $\lim_{t \to 0}\left(1+t\right)^{1/t} = e$. Portanto: 

$$
\begin{align*}
    \dfrac{1}{x} \cdot \lim_{t \to 0} \left(\left(1 + t\right)^{1/t}\right) &= \dfrac{1}{x} \cdot \ln{e} \\\\
    &=\dfrac{1}{x}
\end{align*}
$$

</aside>

<aside>

<b>Corolário (derivada da função logaritmo, base qualquer)</b> — Pela propriedade da mudança de base de logaritmos, segue-se que: 

$$
\begin{align*}
\log_ax = \dfrac{\ln x}{\ln a} \implies \dfrac{d}{dx}(\log_a{x}) &= \dfrac{d}{dx}\left(\dfrac{\ln{x}}{\ln{a}}\right) \\\\    
&= \dfrac{1}{\ln{a}} \dfrac{d}{dx}\ln{x} \\\\
&= \dfrac{1}{x\ln{a}}
\end{align*}
$$

</aside>

# Derivadas de funções trigonométricas

Todas as funções trigonométricas podem ser reconstruídas por meio de recombinações das funções seno e cosseno. Tendo isso em vista, abaixo estarão as suas derivadas pela definição e em seguida uma lista das derivadas das outras funções.

## Derivando a função seno

<aside>

<b>Demonstração (derivada da função seno)</b> — Pela definição de derivada, temos: 

$$
\lim_{h \to 0}\left(\dfrac{\sin{(x+h)}-\sin{x}}{h}\right)
$$

Em seguida, pela identidade do seno da soma de dois arcos, segue que: 

$$
\begin{align*}
    \lim_{h \to 0}\left(\dfrac{\sin{(x+h)}-\sin{x}}{h}\right) &= \lim_{h \to 0}\left(\dfrac{\sin{x}\cos{h} + \cos{x}\sin{h}-\sin{x}}{h}\right) \\\\
    &= \lim_{h \to 0}\left(\dfrac{\sin{x}(\cos{h}-1) + \cos{x} \sin{h}}{h}\right) \\\\
    &= \lim_{h \to 0}\left(\sin{x} \cdot \dfrac{\cos{h}-1}{h} + \cos{x} \cdot \dfrac{\sin{h}}{h}\right)
\end{align*}
$$

Pela continuidade das funções trigonométricas, pelo limite fundamental e pelo limite acima calculado, portanto, podemos escrever, através da propriedade do limite da soma: 

$$
\begin{align*}
    \lim_{h \to 0}\left(\sin{x} \cdot \dfrac{\cos{h}-1}{h} + \cos{x} \cdot \dfrac{\sin{h}}{h}\right) &= \lim_{h \to 0}\left(\sin{x}\cdot\dfrac{\cos{h}-1}{h}\right) + \lim_{h \to 0}\left (\cos{x} \cdot \dfrac{\sin{h}}{h}\right) \\\\
    &= \sin{x} \cdot \lim_{h \to 0}\left(\dfrac{\cos{h} - 1}{h}\right) + \cos{x} \cdot \lim_{h \to 0}\left(\dfrac{\sin{h}}{h}\right) \\\\
    &= \sin{x} \cdot 0 + \cos{x} \cdot 1 \\\\
    &= \cos{x}
\end{align*}
$$

</aside>


## Derivando a função cosseno

Antes de derivar a função cosseno, precisamos ter em mente o <b>limite trigonométrico fundamental</b>, <a href="/books/higher_education/math/calculus_one/limits.html" target="_blank">visto anteriormente</a>, e o seguinte limite: 

$$
\lim_{h \to 0} \left(\dfrac{\cos{h} - 1}{h}\right) = 0
$$

<aside>

<b>Demonstração</b> — Pela definição de derivada, temos: 

$$
\begin{align*}
    \lim_{h \to 0}\left(\dfrac{\cos{h} - 1}{h}\right) &= \lim_{h \to 0}\left(\dfrac{\cos^2{h}-1}{h \cdot (\cos{h} +1)}\right) \\\\
    &= \lim_{h \to 0}\left(\dfrac{-\sin^2{h}}{h \cdot (\cos{h} + 1)}\right) \\\\
    &= -\lim_{h \to 0}\left(\dfrac{\sin{h}}{h} \cdot \dfrac{\sin{h}}{\cos{h} + 1}\right)
\end{align*}
$$

Como as funções trigonométricas são contínuas, o limite direito existe e pode ser calculado por substituição direta. O limite no lado esquerdo da multiplicação é o limite trigonométrico fundamental.

Dessa forma, pela propriedade do limite do produto: 

$$
\begin{align*}
    -\lim_{h \to 0}\left(\dfrac{\sin{h}}{h} \cdot \dfrac{\sin{h}}{\cos{h} + 1}\right) &= -\left[\lim_{h \to 0}\left(\dfrac{\sin{h}}{h}\right) \cdot \lim_{h \to 0} \left(\dfrac{\sin{h}}{\cos{h} + 1}\right) \right] \\\\
    &= -\left[1 \cdot 0\right] \\\\
    &= 0.
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (derivada da função cosseno)</b> — Pela definição de derivada, temos: 

$$
\lim_{h \to 0} \left(\dfrac{\cos{(x+h)}-\cos{x}}{h}\right)
$$

Pela identidade do cosseno da soma, segue que: 

$$
\begin{align*}
    \lim_{h \to 0} \left(\dfrac{\cos{(x+h)}-\cos{x}}{h}\right) &= \lim_{h \to 0} \left(\dfrac{\cos{x}\cos{h}-\sin{x}\sin{h}-\cos{x}}{h}\right) \\\\ 
    &= \lim_{h \to 0}\left(\dfrac{\cos{x}(\cos{h}-1)-\sin{x}\sin{h}}{h}\right) \\\\
    &= \lim_{h \to 0}\left(\cos{x}\cdot\dfrac{\cos{h}-1}{h}-\sin{x}\cdot\dfrac{\sin{h}}{h}\right)
\end{align*}
$$

Pelos mesmos motivos vistos na prova da derivada da função seno, podemos utilizar a propriedade do limite da soma e logo em seguida utilizar as identidades associadas aos limites. Além disso, iremos nos utilizar do limite fundamental do cosseno, visto anteriormente.

$$
\begin{align*}
    \lim_{h \to 0}\left(\cos{x}\cdot\dfrac{\cos{h}-1}{h}-\sin{x}\cdot\dfrac{\sin{h}}{h}\right) &= \lim_{h \to 0}\left(\cos{x}\cdot\dfrac{\cos{h}-1}{h}\right) - \lim_{h \to 0}\left(\sin{x}\cdot\dfrac{\sin{h}}{h}\right) \\\\
    &= \cos{x} \cdot \lim_{h \to 0}\left(\dfrac{\cos{h}-1}{h}\right) - \sin{x} \cdot \lim_{h \to 0}\left(\dfrac{\sin{h}}{h}\right) \\\\
    &= -\sin{x}
\end{align*}
$$

</aside>

## Derivando a função tangente

A função tangente pode ser derivada tanto por primeiros princípios como pela regra do quociente.

<aside>

<b>Demonstração (derivada da função tangente, regra do quociente)</b> — Tome $f(x) = \tan(x) = \dfrac{\sin{x}}{\cos{x}}$. 

Portanto, pela regra do quociente, temos: 

$$
\begin{align*}
    f'(x) &= \dfrac{\cos{x}\cos{x}-\sin{x}(-\sin{x})}{\cos^2{x}} \\\\
    \therefore f'(x) &= \dfrac{\cos^2{x} + \sin^2{x}}{\cos^2{x}} = \dfrac{1}{\cos^2{x}} \\\\
    \therefore f'(x) &= \sec^2{x}
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (derivada da função tangente, primeiros princípios)</b> — Pela definição de derivada, temos: 

$$
\begin{align*}
    f'(x) &= \lim_{h \to 0} \dfrac{\tan{(x+h)-\tan{x}}}{h}
\end{align*}
$$

Pela identidade trigonométrica da tangente da diferença de dois arcos, temos que $\tan{(x+h)}-\tan{x} = \tan{h} \cdot (1 + \tan{(x+h)}\cdot \tan{x})$.

Dessa forma, substituindo no limite, obtemos: 

$$
\begin{align*}
    f'(x) &= \lim_{h \to 0} \dfrac{\tan{h}(1 + \tan{(x+h)}\cdot \tan{x})}{h} \\\\
    \therefore f'(x) &= \lim_{h \to 0}\dfrac{\tan{h}}{h} \cdot \lim_{h \to 0} [1 + \tan{(x+h)}\cdot \tan{x}]
\end{align*}
$$

A propriedade do limite do produto pode ser aplicada pois $\lim_{h \to 0}\dfrac{\tan{h}}{h} = 1$ e $\lim_{h \to 0} [1 + \tan{(x+h)}\cdot \tan{x} = 1 + \tan^2{x}$.

Portanto, obtemos: 

$$
\begin{align*}
    f'(x) &= 1 \cdot (1 + \tan^2{x}) \\\\ 
    \therefore f'(x) &= \sec^2{x}
\end{align*}
$$

Como queríamos demonstrar.

<i>Observação: o limite $\lim_{h \to 0}\dfrac{\tan{h}}{h} = 1$ possui demonstração geométrica de forma similar ao limite fundamental.</i> 

</aside>

## Derivando a função cossecante 

<aside>

<b>Demonstração (derivada da cossecante, regra do quociente)</b> — Pela regra do quociente, obtemos: 

$$
\begin{align*}
    (\csc{x})' &= \left(\dfrac{1}{\sin{x}}\right)' \\\\
    \therefore (\csc{x})' &= -\dfrac{\cos{x}}{\sin^2{x}} \\\\ 
    \therefore (\csc{x})' &=  -\cot{x} \cdot \csc{x}
\end{align*}
$$

Como queríamos demonstrar.

</aside>


## Derivando a função secante

<aside>

<b>Demonstração (derivada da secante, regra do quociente)</b> — Pela regra do quociente, obtemos: 

$$
\begin{align*}
    (\sec{x})' &= \left(\dfrac{1}{\cos{x}}\right)' \\\\
    \therefore (\sec{x})' &= \dfrac{\sin{x}}{\cos^2{x}} \\\\
    \therefore (\sec{x})' &= \tan{x} \cdot \sec{x}
\end{align*}
$$

</aside>

## Derivando a função cotangente 

<aside>

<b>Demonstração (derivada da cotangente, regra do quociente)</b> — Pela regra do quociente, obtemos: 

$$
\begin{align*}
    (\cot{x})' &= \left(\dfrac{1}{\tan{x}}\right)' \\\\
    \therefore (\cot{x})' &= -\dfrac{\sec^2{x}}{\tan^2{x}} \\\\
    \therefore (\cot{x})' &= -\csc^2{x}
\end{align*}
$$

</aside>

# Referências 

1. GUIDORIZZI, Hamilton Luiz. Um curso de cálculo. 5.ed., reimpr. Rio de Janeiro: LTC, 2011. 530 p. LTC
2. STEWART, James. Cálculo. Volume 1. 6. ed. São Paulo: Cengage Learning, 2009.