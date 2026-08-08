# Derivando funções inversas

# Inversibilidade 

Para derivar funções inversas, primeiro precisamos ser introduzidos às noções de inversibilidade. Considere os seguintes teoremas.

<aside>

<b>Definição (Guidorizzi, função injetora)</b> — Dizemos que $f$ é uma <b>função injetora</b> se, para qualquer $s$ e $t$ pertencentes ao domínio de $f$ vale 

$$
s \neq t \implies f(s) \neq f(t)
$$

</aside>

<aside>

<b>Definição (Guidorizzi, função inversa)</b> — Suponha uma função $f$ injetora. Como para cada $x \in \text{Im}f$ existe um único $y \in D_f$ tal que $f(y) = x$, é possível definir uma função $g$ injetora tal que

$$
g(x) = y \iff f(y) = x
$$

Se $f$ é tal que construir uma $g$ é possível, $f$ é denominada <b>inversível</b> e $g$ é a <b>função inversa de $f$</b>. Além disso, podemos denotá-la por $f^{-1}$. 

</aside>

<aside>

<b>Teorema (Guidorizzi, derivada da função inversa)</b> — Seja $f$ uma função inversível, com função inversa $g$. Se $f$ for derivável em $q = g(p)$, com $f'(q) \neq 0$, e se $g$ for contínua em $p$, então $g$ será derivável em $p$. 

</aside>

<aside>

<b>Demonstração</b> — Note que vale a igualdade 

$$
\dfrac{g(x)-g(p)}{x-p} = \dfrac{g(x)-g(p)}{f(g(x)) - f(g(p))} = \dfrac{1}{\dfrac{f(g(x)) - f(g(p))}{g(x)-g(p)}}, x \neq p
$$

Fazendo $u = g(x)$, pela continuidade de $g$ em $p$, $u \to q$ para $x \to p$. Então, 

$$
\lim_{x \to p} \dfrac{g(x)-g(p)}{x-p} = \lim_{u \to q} \dfrac{1}{\dfrac{f(u)-f(q)}{u-q}}
$$

Como $\lim_{u \to q} \dfrac{f(u)-f(q)}{u-q} = f'(q)=f'(g(p))$, resulta

$$
g'(p) = \lim_{x \to p} \dfrac{g(x)-g(p)}{x-p} = \dfrac{1}{f'(g(p))}
$$

Portanto, $g$ é derivável em $p$ e $g'(p) = \dfrac{1}{f'(g(p))}$. 

<b>Demonstração alternativa</b> — Derivando implicitamente a equação, podemos, por meio da cadeia, alcançar a expressão desejada.

$$
\begin{align*}
    [f(g(x))]' &= x' \\\\
    f'(g(x)) \cdot g'(x) &= 1
    g'(x) &= \dfrac{1}{f'(g(x))}
\end{align*}
$$

</aside>

# Derivando as funções inversas trigonométricas

Para encontrar as funções inversas trigonométricas, podemos tanto aplicar o método da derivação implícita diretamente como utilizar o teorema exposto previamente. 

## Derivando a função arco seno

<aside>

<b>Demonstração (derivada do arco seno)</b> — Pelo teorema anterior, podemos escrever

$$
\begin{align*}
    (\arcsin{x})' &= \dfrac{1}{\sin{(\arcsin{x})'}} \\\\
    \therefore (\arcsin{x})' &= \dfrac{1}{\cos{(\arcsin{x})}}
\end{align*}
$$

Pela relação fundamental da trigonometria, podemos concluir que 

$$
(\arcsin{x})' = \dfrac{1}{\sqrt{1 - x^2}}
$$

</aside>

## Derivando a função arco cosseno 

<aside>

<b>Demonstração (derivada do arco cosseno)</b> — Pelo teorema anterior, podemos escrever

$$
\begin{align*}
    (\arccos{x})' &= \dfrac{1}{(\cos{\arccos{x}})'} \\\\
    (\arccos{x})' &= -\dfrac{1}{\sin{\arccos{x}}}
\end{align*}
$$

Pela relação fundamental da trigonometria, podemos concluir que 

$$
(\arccos{x})' = -\dfrac{1}{\sqrt{1 - x^2}}
$$

</aside>

## Derivando a função arco tangente

<aside>

<b>Demonstração (derivada do arco tangente)</b> — Pelo teorema anterior, podemos escrever 

$$
\begin{align*}
    (\arctan{x})' &= \dfrac{1}{(\tan \arctan{x})'} \\\\
    \therefore (\arctan{x})' &= \dfrac{1}{\sec^2\arctan{x}}
\end{align*}
$$

Pela relação fundamental da trigonometria, concluimos que

$$
(\arctan{x})' = \dfrac{1}{x^2 + 1}
$$

</aside>

## Derivando a função arco secante

<aside>

<b>Demonstração (derivada do arco secante)</b> — Pelo teorema anterior, podemos escrever: 

$$
\begin{align*}
    (\text{arcsec }{x})' &= \dfrac{1}{(\sec{\text{arcsec }x})'} \\\\
    \therefore (\text{arcsec }{x})' &= \dfrac{1}{(\sec{\text{arcsec }{x}})(\tan{\text{arcsec }{x}})} \\\\
    \therefore (\text{arcsec }{x})' &= \dfrac{1}{|x| \sqrt{x^2 - 1}}
\end{align*}
$$

Este último passo é possível pela simplificação da primeira parcela e da aplicação da identidade fundamental trigonométrica. Note que o módulo é necessário nessa expressão para manter o sinal positivo na fração, pois é verificável que a taxa de variação do arco secante é estritamente positiva em seu domínio.

</aside>

## Derivando a função arco cossecante 

<aside>

<b>Demonstração (derivada do arco cossecante)</b> — Pelo teorema anterior, podemos escrever: 

$$
\begin{align*}
    (\text{arccsc }{x})' &= \dfrac{1}{(\csc \text{arccsc }x)'} \\\\
    \therefore (\text{arccsc }{x})' &= -\dfrac{1}{|x|\sqrt{x^2 - 1}} \\\\
\end{align*}
$$

Este último passo é realizado após a aplicação da regra da cadeia e da identidade fundamental trigonométrica. Após simplificar e rearranjar os termos ao final, vale a pena notar o módulo no denominador. Este módulo possui a mesma justificativa da derivada anterior: manter o sinal <b>negativo</b> por todo o domínio, como é possível verificar na prática.

</aside>

## Derivando a função arco cotangente

<aside>

<b>Demonstração (derivada do arco cotangente)</b> — Pelo teorema anterior, podemos escrever 

$$
\begin{align*}
    (\text{arccot }{ x})' &= -\dfrac{1}{\csc^2{\text{arccot }{ x}}} \\\\
    \therefore (\text{arccot }{ x})' &= \dfrac{1}{1 + x^2}
\end{align*}
$$

Esta conclusão pode ser feita a partir da identidade trigonométrica $\csc^2{x} = 1 + \cot^2{x}$. Basta substituir, simplificar e organizar os termos. 

</aside>

# Referências 

1. GUIDORIZZI, Hamilton Luiz. Um curso de cálculo. 5.ed., reimpr. Rio de Janeiro: LTC, 2011. 530 p. LTC
2. STEWART, James. Cálculo. Volume 1. 6. ed. São Paulo: Cengage Learning, 2009.