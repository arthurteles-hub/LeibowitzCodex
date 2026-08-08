# Diferenciais 

# Diferenciais

A interpretação geométrica da derivada permite o estudo do Cálculo sob a ótica dos chamados <b>diferenciais</b>, incluindo a interpretação da notação $\dfrac{dy}{dx}$ como um quociente. 

Para melhor ilustrar e facilitar nosso entendimento desse conceito, vamos considerar a função $y = f(x) = x^2 + 3x$. Podemos relacionar os incrementos $\Delta y$ e $\Delta x$ por meio da equação 

$$
\Delta y = f(x + \Delta x) = \Delta x(2x+3) + (\Delta x)^2 
$$

Note que, quando fazemos $\Delta x \to 0$, o termo $(\Delta x)^2$ torna-se desprezível. Com efeito, para qualquer função $f(x)$, o incremento $\Delta y$ é da forma 

$$
\Delta y = m\Delta x + q(\Delta x)
$$

com $q(\Delta x)$ sendo uma função composta de termos quadráticos e de ordens superiores, que se tornam desprezíveis quando fazemos o incremento em $x$ tender para zero. O termo linear que resta, $m \Delta x$, é chamado <b>diferencial de $y$</b> ou <b>diferencial de $f$ em $x$</b>. Denotamos esse termo por $dy$ ou $df$. Quando $\Delta x \to 0$, representamos esse termo por $dx$. 

De fato, temos que o coeficiente $m$ da equação linear é $f'(x)$, a derivada da função $f$. Logo, isso motiva a escrita 

$$
dy = f'(x) \cdot dx \iff \dfrac{dy}{dx}=f'(x)
$$

Essa conclusão pode ser tirada também pela análise de que a razão $\dfrac{dy}{dx}$ é o coeficiente angular da reta tangente no ponto $(x, f(x))$, que pode ser facilmente visualizado.

O ato de tomar incrementos finitos e analisar sua razão para escalas infinitesimais é a clássica interpretação geométrica da derivada num ponto, com uma reta secante se tornando a reta tangente.

# Regras de derivação

De forma bem interessante, é possível escrever as conhecidas regras de derivação na notação de diferenciais.    

<aside>

<b>Teorema</b> — Sejam $f$ e $g$ funções definidas em um intervalo fechado $[a, b]$ possuindo diferenciais em um $x \in [a,b]$. Logo, $f + g$, $f-g$, $fg$ e $f/g$ possuem diferenciais nesse mesmo $x$, valendo

$$
\begin{align*}
    d(f+g) &= df + dg \\ 
    d(f-g) &= df - dg \\ 
    d(fg) &= fdg + gdf \\ 
    d(f/g) &= \dfrac{gdf - fdg}{g^2} \\ 
    d(f^n) &= nf^{n-1}df \\ 
    d(c) &= 0, \forall x \in \mathbb{R}
\end{align*}
$$

com $f$ e $g$ calculadas em $x$. Além disso, também valem as relações: 

$$
\begin{align*}
    d(x^n) &= nx^{n-1} \cdot dx \\ 
    d(\sin{x}) &= \cos{x} \cdot dx \\ 
    d(\cos{x}) &= -\sin{x} \cdot dx \\ 
    d(\tan{x}) &= \sec^2{x} \cdot dx \\ 
    d(\sec{x}) &= \sec{x}\tan{x} \cdot dx \\ 
    d(\csc{x}) &= -\csc{x}\cot{x} \cdot dx \\ 
    d(\cot{x}) &= -\csc^2{x} \cdot dx \\ 
    d(e^x) &= e^x \cdot dx \\ 
    d(a^x) &= a^x \ln{a} \cdot dx \\ 
    d(\ln{x}) &= \dfrac{1}{x} dx \\ 
    d(\log_a{x}) &= \dfrac{1}{\ln{a}}\dfrac{1}{x}dx \\
    d(\arcsin{x}) &= \dfrac{1}{\sqrt{1-x^2}}dx, -1 \lt x \lt 1 \\
    d(\arccos{x}) &= -\dfrac{1}{\sqrt{1-x^2}}dx, -1 \lt x \lt 1 \\ 
    d(\arctan{x}) &= \dfrac{1}{1+x^2} dx, x \in \mathbb{R}
\end{align*}
$$

</aside>

Além destas regras fundamentais, a regra da cadeia também pode ser escrita por meio de diferenciais. 

<aside>

<b>Teorema</b> — Seja $y = F(x)$, com $x \in [a,b]$, definida como a composta das funções $y = f(u)$ e $u = g(x)$. Isto é, $F(x) = f \circ g$. 

Se em um $x$ particular $g$ tem um diferencial $du = ndx$ e se, no correspondente valor $u = g(x)$, $f$ tem um diferencial $dy = mdu$, então $F$ tem uma diferencial $dF$ em $x$ da forma 

$$
dF = mndx = f'(u)g'(x) dx
$$

</aside>

Além disso, ao considerarmos funções implícitas, percebemos que podemos encontrar diferenciais normalmente e apenas relacioná-los para obtermos a derivada regular ou a derivada da função inversa. Por exemplo, para $x^2 + y^2 = 1$, temos $2xdx + 2ydy = 0$ e, por consequência, 

$$
\begin{align*}
    \dfrac{dy}{dx} &= -\dfrac{x}{y} \\ 
    \dfrac{dx}{dy} &= -\dfrac{y}{x}
\end{align*}
$$

Esses resultados concordam com os obtidos pelo processo regular da derivação implícita.

# Aplicações numéricas

Como previamente discutido, podemos visualizar que, na equação 

$$
\Delta y = m \Delta x + q(\Delta x) = f'(x) \Delta x+ q(x)
$$

nosso valor para $\Delta y$ fica cada vez mais próximo de $f'(x) \Delta x$ à medida que diminuímos $\Delta x$. Esse fato fornece uma boa ferramenta para a aproximação numérica de valores de funções. Por exemplo, como podemos aproximar o valor de $\sqrt{50}$. 

Tome $y = \sqrt{x}$ com $x = 49$. Logo, temos um $y = 7$. Além disso, temos $\Delta x = 1$. Assim, podemos escrever

$$
\Delta y = \dfrac{1}{2}x^{-1/2} \Delta x = \dfrac{1}{2\sqrt{49}}\cdot 1 = 0.0714
$$

e, portanto, $\sqrt{50} \approx 7 + 0.0714 = 7.0714$. Com efeito, temos um erro da ordem de $10^{-4}$.

# Referências 

1. GUIDORIZZI, Hamilton Luiz. Um curso de cálculo. 5.ed., reimpr. Rio de Janeiro: LTC, 2011. 530 p. LTC
2. KAPLAN, Wilfred; LEWIS, Donald J. Cálculo e Álgebra Linear. v. 1. Rio de Janeiro: Livros Técnicos e Científicos, 1972