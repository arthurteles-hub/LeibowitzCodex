# Regras de derivação

<aside>

É perceptível que se utilizar da definição de derivação sempre que se fazer necessário calcular uma derivada é algo trabalhoso e demorado. Por isso, podemos nos utilizar das <b>regras de derivação</b>, propriedades do cálculo de derivadas — muitas delas derivadas das propriedades de limites — que facilitam nosso trabalho e diminuem nosso esforço.

</aside>

# Derivada de uma função constante

A primeira dessas propriedades, e provavelmente a mais direta, é que a derivada de uma função constante é nula.

<aside>

<b>Demonstração (derivada de uma função constante)</b> — Seja $f: \mathbb{R} \to \mathbb{R}$ uma função constante com lei de formação $f(x) = c, \forall c$. 

Pela definição de derivada, temos: 

$$
\begin{align*}
    \lim_{h \to 0}\left(\dfrac{f(x + h) - f(x)}{h}\right) &= \lim_{h \to 0}\left(\dfrac{c-c}{h}\right) \\\\ 
    &= \lim_{h \to 0}\left(\dfrac{0}{h}\right) \\\\ 
    &= 0.
\end{align*}
$$

Note que a divisão do segundo passo é possível pois $h \neq 0$. 

</aside>

# Função potência

Dada uma função $f(x)=x^n$, sua derivada será $f'(x)=nx^{n-1}$ para todo $n \in \mathbb{R}$. 

Por exemplo, dada uma função $f(x)=x^4$, sua derivada será $f'(x)=4x^3$. 

É possível demonstrar a validade dessa afirmação para $n \in \mathbb{N}$ pelo binômio de Newton e jogos de álgebra, tanto para $n \in \mathbb{R}$ por meio da **diferenciação implícita** e da **diferenciação logarítmica**, mostradas mais adiante. 

## Prova 1 — Binômio de Newton

<aside>

Seja $f(x)=x^n$ uma função. Por definição, temos que sua derivada $f'(x)$ é dada pelo limite:

$$
f'(x)=\lim_{h \rightarrow 0} \dfrac{(x + h)^n - x^n}{h}
$$

Expandindo o minuendo do numerador por meio do binômio de Newton, temos que: 

$$
\begin{align*}
    (x+h)^n &= {n \choose 0}x^n + {n \choose 1}x^{n-1} \cdot h + {n \choose 2} x^{n-2} \cdot h^2 + ... + {n \choose n} h^n \\\\ 
    &= \dfrac{n!}{0!(n-0)!} x^n + \dfrac{n!}{1!(n-1)!}x^{n-1}\cdot h + \dfrac{n!}{2!(n-2)!}
    \cdot h^2 + ...+ \dfrac{n!}{n!(n-n)!} \cdot h^n \\\\ 
    &= \dfrac{n!}{n!} x^n + \dfrac{n!}{(n-1)!} x^{n-1} \cdot h + \dfrac{n!}{2(n-2)!} \cdot h^2 + ... + h^n \\\\ 
    &= x^n + nhx^{n-1} + \dfrac{n!}{2(n-2)!} \cdot h^2 + ... + h^n
\end{align*}
$$

Substituindo a expansão no numerador do limite original, temos: 

$$
\begin{align*} 
    (x+h)^n - x^n &= x^n + nhx^{n-1} + \dfrac{n!}{2(n-2)!} \cdot h^2 + ... + h^n - x^n \\\\
    &= nhx^{n-1} + \dfrac{n!}{2(n-2)!} \cdot h^2 + ... + h^n
\end{align*}
$$

Colocando $h$ em evidência e simplificando a fração, chegamos no limite: 

$$
\lim_{h \rightarrow 0} nx^{n-1} = nx^{n-1}
$$

Como queríamos demonstrar.

</aside>

## Prova 2 — Diferenciação implícita e logarítmica

<aside>

Seja $f(x)=y=x^n$. Logo, temos que: 

$$
\begin{align*}
\ln y &= \ln x^n \\\\
\ln y &= n \ln x \\\\ 
\dfrac{y'}{y} &= n\cdot \dfrac{1}{x} \\\\ 
y' &= y \cdot \dfrac{n}{x} \\\\  
y' &= nx^{n-1}
\end{align*}
$$

Como queríamos demonstrar. Os conceitos de derivação implícita e derivação logarítmica estão descritos mais adiante nesta seção.

</aside>

# Multiplicação por uma constante

Dadas duas funções $g(x)$ e $f(x)$ e uma constante $c \in \mathbb{R}$, de forma que $g(x)=cf(x)$, a derivada de $g(x)$ é dada pelo produto entre $c$  e $f'$. 

Essa propriedade pode ser demonstrada de forma relativamente simples. 

<aside>

$$
\begin{align*}
g'(x)&=\lim_{h \rightarrow 0} \dfrac{g(x+h)-g(x)}{h}=\lim_{h \rightarrow 0} \dfrac{cf(x+h) - cf(x)}{h}\\\\
&= \lim_{h \rightarrow 0}\dfrac{c[f(x+h) - f(x)]}{h}=c\lim_{h \rightarrow 0} \dfrac{f(x+h)-f(x)}{h}=cf'(x)
\end{align*}
$$

</aside>

O último passo é justificado por meio das propriedades de limites (limite do produto entre uma função e uma constante).

# Regra da soma ou da diferença

Ao derivarmos uma função formada pela soma de duas outras funções, sua derivada será a soma das derivadas das funções que a formam, isto é

$$
F(x)=f(x) + g(x) \implies F'(x)=f'(x) + g'(x)
$$

<aside>

<b>Demonstração (derivada da soma de duas funções)</b> — Sejam $f(x)$ e $g(x)$ funções diferenciáveis. Temos, pela definição de derivada: 

$$
\begin{align*}
    \lim_{h \to 0}\left(\dfrac{f(x+h)+g(x+h)-f(x)-g(x)}{h}\right) &= \lim_{h \to 0}\left(\dfrac{f(x+h)-f(x)+g(x+h)-g(x)}{h}\right) \\\\
    &= \lim_{h \to 0}\left(\dfrac{f(x+h)-f(x)}{h} + \dfrac{g(x+h)-g(x)}{h}\right)
\end{align*}
$$

Como $f$ e $g$ são ambas diferenciáveis, temos que os limites $\lim_{h \to 0}\left(\dfrac{f(x+h)-f(x)}{h}\right)$ e $\lim_{h \to 0}\left(\dfrac{g(x+h)-g(x)}{h}\right)$ existem. Logo, pela propriedade do limite da soma, segue que 

$$
\begin{align*}
    \lim_{h \to 0}\left(\dfrac{f(x+h)-f(x)}{h} + \dfrac{g(x+h)-g(x)}{h}\right) &= \lim_{h \to 0}\left(\dfrac{f(x+h)-f(x)}{h}\right) + \lim_{h \to 0}\left(\dfrac{g(x+h)-g(x)}{h}\right) \\\\
    &= f'(x) + g'(x) 
\end{align*}
$$

Como queríamos demonstrar.

</aside>

# Regra do produto

Quando derivamos uma certa função $F(x)$ composta pelo produto de outras duas funções, a saber, $f(x)$ e $g(x)$, podemos dizer: 

$$
F'(x)=f'(x)g(x)+f(x)g'(x)
$$

<aside>

<b>Demonstração (derivada do produto de duas funções)</b> — Sejam $f$ e $g$ diferenciáveis. Pela definição de derivada, temos: 

$$
\begin{align*}
    \lim_{h \to 0}\left(\dfrac{f(x+h)g(x+h)-f(x)g(x)}{h}\right) &= \lim_{h \to 0}\left(\dfrac{f(x+h)g(x+h)-f(x)g(x+h)+f(x)g(x+h)-f(x)g(x)}{h}\right) \\\\
    &= \lim_{h \to 0}\left(\dfrac{g(x+h)[f(x+h)-f(x)]+f(x)[g(x+h)-g(x)]}{h}\right) \\\\
    &= \lim_{h \to 0}\left(g(x+h) \cdot \dfrac{f(x+h)-f(x)}{h} + f(x) \cdot \dfrac{g(x+h)-g(x)}{h}\right)
\end{align*}
$$

Como $f$ e $g$ são diferenciáveis e portanto, também contínuas, segue que 

$$
\begin{align*}
    \lim_{h \to 0}\left(g(x+h) \cdot \dfrac{f(x+h)-f(x)}{h} + f(x) \cdot \dfrac{g(x+h)-g(x)}{h}\right) &= f'(x)g(x) + f(x)g'(x) \\\\ 
    &\therefore (fg)'=f'g + fg'
\end{align*}
$$

</aside>

# Regra do quociente

Para encontrar a derivada de uma certa função $F(x)=\dfrac{f(x)}{g(x)}, g(x) \neq 0$, temos que 

$$
F'(x)=\dfrac{g(x)f'(x)-f(x)g'(x)}{[g(x)]^2}
$$

<aside>

<b>Demonstração (derivada do quociente de duas funções)</b> — Sejam $f$ e $g$ diferenciáveis com $g \neq 0$. Pela definição de derivada: 

$$
\begin{align*}
    \lim_{h \to 0}\left(\dfrac{\dfrac{f(x+h)}{g(x+h)} - \dfrac{f(x)}{g(x)}}{h}\right) &= \lim_{h \to 0}\left(\dfrac{g(x)f(x+h)-f(x)g(x+h)}{hg(x)g(x+h)}\right) \\\\
    &= \lim_{h \to 0}\left(\dfrac{g(x)f(x+h)-f(x)g(x+h)}{h} \cdot \dfrac{1}{g(x)g(x+h)}\right) \\\\
    &= \lim_{h \to 0}\left(\dfrac{g(x)f(x+h)-g(x)f(x)+g(x)f(x)-f(x)g(x+h)}{h} \cdot \dfrac{1}{g(x)g(x+h)}\right) \\\\
    &= \lim_{h \to 0}\left(\dfrac{g(x)[f(x+h)-f(x)]-f(x)[g(x+h)-g(x)]}{h} \cdot \dfrac{1}{g(x)g(x+h)}\right) \\\\
    &= \lim_{h \to 0}\left(\left[g(x) \cdot \dfrac{f(x+h)-f(x)}{h} - f(x) \cdot \dfrac{g(x+h)-g(x)}{h}\right] \cdot \dfrac{1}{g(x)g(x+h)}\right)
\end{align*}
$$

Como $f$ e $g$ são diferenciáveis e, portanto, contínuas, vale que: 

$$
\begin{align*}
    \lim_{h \to 0}\left(\left[g(x) \cdot \dfrac{f(x+h)-f(x)}{h} - f(x) \cdot \dfrac{g(x+h)-g(x)}{h}\right] \cdot \dfrac{1}{g(x)g(x+h)}\right) &= \dfrac{f'g-fg'}{g^2}
\end{align*}
$$

</aside>

# Regra da cadeia

A regra da cadeia possui uma demonstração matemática mais complexa, mas uma utilidade imensa, servindo de base para a resolução de problemas como por exemplo a derivação de funções exponenciais, explorada mais adiante — essa propriedade nos permite encontrar a derivada de funções compostas.

Dada uma função $F(x)=(f \circ g)(x) = f(g(x))$, temos que sua derivada é dada por

$$
F'(x)=f'(g(x)) \cdot g'(x)
$$

<aside>

Daqui em diante é interessante a utilização da notação de Leibniz <!-- ("Leibnitz" de novo) Acho que você estava confundindo Leibniz com Leibowitz hehe --> em algumas — várias — situações pela sua maior densidade informacional. Se não estiver familiarizado com a notação batizada em sua homenagem, recomendamos que faça uma pequena visita à seção "Notações para derivada" <a href="/books/higher_education/math/calculus_one/derivatives_concepts.html" target="_blank">deste manuscrito</a>.

</aside>

Ou ainda, de forma provavelmente mais didática: 

$$
\dfrac{dy}{dx}=\dfrac{dy}{du} \cdot \dfrac{du}{dx}
$$

Com $y$ sendo minha função original, $u$ sendo a minha função “interna”, tratada como variável, e finalmente $x$, a minha verdadeira variável. 

<aside>

<b>Exemplo</b> — Definindo a função $y=f(x)=\sqrt{5x-8}$, podemos encontrar sua derivada através da regra da cadeia. 

Neste exemplo, chamamos $u=5x-8$. Assim, pela regra da cadeia: 

$$
\begin{align*}
\dfrac{dy}{dx}=\dfrac{dy}{du} \cdot \dfrac{du}{dx} &= \dfrac{1}{2}u^{-1/2} \cdot 5 \\\\ 
&= \dfrac{1}{2} \cdot \dfrac{1}{\sqrt{5x - 8}} \cdot 5 \\\\ 
&= \dfrac{5}{2\sqrt{5x-8}}
\end{align*}
$$

</aside>

## Demonstrações

<aside>

<b>Demonstração (regra da cadeia, adaptada de MathStackExchange)</b> — Sejam $f$ e $g$ funções e $a \in \mathbb{R}$. Definimos uma função $\phi : \mathbb{R} \to \mathbb{R}$ tal que: 

$$
\phi(t)=
\begin{cases}
    \dfrac{f(t) - f(g(a))}{t-g(a)} & t \neq g(a) \\\\
    f'(g(a)) & t = g(a)
\end{cases}
$$

Por construção, $\phi$ é contínua em $g(a)$. Além disso, $g$ é contínua em $a$ por ser diferenciável em $a$. Dessa forma, $\phi(g)$ é contínua em $a$. 

Perceba que, $\forall x \neq a$ vale 

$$
\dfrac{f(g(x)) - f(g(a))}{x-a} = \phi(g(x)) \cdot \dfrac{g(x)-g(a)}{x-a}
$$

e, portanto, 

$$
\begin{align*}
    (f(g))'(a) &= \lim_{x \to a}\left(\dfrac{f(g(x)) - f(g(a))}{x-a}\right) \\\\
    &= \lim_{x \to a}\left(\phi(g(x))\right) \cdot \lim_{x \to a}\left(\dfrac{g(x)-g(a)}{x-a}\right) \\\\ 
    &= \phi(g(a)) \cdot g'(a) \\\\ 
    &= f'(g(a)) \cdot g'(a)
\end{align*}
$$

Como queríamos demonstrar.

</aside>

<aside>

<b>Demonstração (regra da cadeia, alternativa)</b> — Sejam $f$ e $g$ contínuas, com $g$ diferenciável em $x$ e $f$ diferenciável em $g(x)$. Definimos a função $F(x) = (f \circ g)(x)$. Dessa forma, pela definição de derivada, temos que 

$$
\begin{align*}
    F'(x) = \lim_{h \to 0} \dfrac{F(x+h) - F(x)}{h} &= \lim_{h \to 0} \dfrac{f(g(x+h)) - f(g(x))}{h} \\\\ 
    \therefore F'(x) &= \lim_{h \to 0} \dfrac{f(g(x+h)) - f(g(x))}{h} \cdot \dfrac{g(x+h) - g(x)}{g(x+h)-g(x)} \\\\ 
    \therefore F'(x) &= \lim_{h \to 0} \dfrac{f(g(x+h)) - f(g(x))}{g(x+h) - g(x)} \cdot \dfrac{g(x+h)-g(x)}{h} \\\\ 
    \therefore F'(x) &= f'(g(x)) \cdot g'(x)
\end{align*}
$$

</aside>

# Referências 

1. GUIDORIZZI, Hamilton Luiz. Um curso de cálculo. 5.ed., reimpr. Rio de Janeiro: LTC, 2011. 530 p. LTC
2. STEWART, James. Cálculo. Volume 1. 6. ed. São Paulo: Cengage Learning, 2009.