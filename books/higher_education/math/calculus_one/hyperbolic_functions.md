# Funções hiperbólicas 

# Funções hiperbólicas

Ao considerarmos a circunferência unitária, de equação $x^2 + y^2 = 1$, podemos definir as funções básicas seno e cosseno. Estas funções trigonométricas possuem funções análogas a elas ao considerarmos uma hipérbole de equação $x^2 - y^2 = 1$. 

![](https://upload.wikimedia.org/wikipedia/commons/9/9f/Hyperbolic_functions_sinh%2C_cosh%2C_tanh.png?utm_source=commons.wikimedia.org&utm_campaign=index&utm_content=original)

<i>Gráfico da hipérbole unitária com as medidas do seno hiperbólico, do cosseno hiperbólico e da tangente hiperbólica. Perceba que é uma analogia às funções trigonométricas regulares. Imagem sob CC-BY-SA, via <a href="https://commons.wikimedia.org/wiki/File:Hyperbolic_functions_sinh,_cosh,_tanh.png" target="_blank">Wikimedia Commons</a>.</i>

As funções hiperbólicas possuem diversas aplicações na física, química e na engenharia, permitindo, por exemplo, a modelagem de sistemas relativísticos ou de sólitons, ondas especiais que sofrem efeitos mínimos de dissipação energética. 

![](https://upload.wikimedia.org/wikipedia/commons/5/50/Soliton_interaction.gif?utm_source=commons.wikimedia.org&utm_campaign=index&utm_content=original)

<i>Sólitons interagindo — perceba que estas ondas não alteram sua forma nem sua velocidade ao longo do tempo. GIF sob CC-BY-SA, via <a href="https://commons.wikimedia.org/wiki/File:Soliton_interaction.gif" target="_blank">Wikimedia Commons</a>.</i>

Estas funções, seno hiperbólico ($\sinh$) e cosseno hiperbólico ($\cosh$), além de todas as outras funções derivadas destas, podem ser escritas de forma algébrica. 

$$
\begin{align*}
    \sinh{x} &= \dfrac{e^x - e^{-x}}{2} \\\\
    \cosh{x} &= \dfrac{e^x + e^{-x}}{2} \\\\
    \tanh{x} &= \dfrac{\sinh{x}}{\cosh{x}} \\\\
    \text{csch }x &= \dfrac{1}{\sinh{x}} \\\\
    \text{sech }x &= \dfrac{1}{\cosh{x}} \\\\
    \text{cotgh }x &= \dfrac{1}{\tanh{x}}
\end{align*} 
$$
<!-- Aqui você tinha feito "ctgh", sendo que no resto do texto fez "cotgh". Tente manter somente uma. -->
Além disso, valem as propriedades a seguir. 

$$
\begin{align*}
    \sinh{0} =& 0 \\\\
    \sinh{-x} &= -\sinh{x} \\\\
    \cosh{-x} &= \cosh{x} \\\\
    \cosh^2{x} -& \sinh^2{x} = 1 \\\\
    1 - \tanh^2&{x} = \text{sech }^2 x \\\\ 
    \sinh{x + y} &= \sinh{x}\cosh{y} + \sinh{y}\cosh{x} \\\\
    \cosh{x + y} &= \cosh{x}\cosh{y} + \sinh{x}\sinh{y}
\end{align*}
$$

# Derivadas de funções hiperbólicas 

Todas as funções hiperbólicas são contínuas e diferenciáveis em seu domínio. Abaixo estão demonstradas suas derivadas.

## Funções regulares e recíprocas

<aside>

<b>Demonstração (Derivada do seno hiperbólico)</b> — Pelas propriedades de linearidade, derivada da soma e regra da cadeia, temos: 

$$
\begin{align*}
    \sinh{x} &= \dfrac{e^x - e^{-x}}{2} \\\\
    \therefore (\sinh{x})' &= \dfrac{1}{2}(e^x - e^{-x})' \\\\
    \therefore (\sinh{x})' &= \dfrac{1}{2}(e^x + e^{-x}) \\\\
    \therefore (\sinh{x})' &= \cosh{x}
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (Derivada do cosseno hiperbólico)</b> — Pelas propriedades de linearidade, derivada da soma e regra da cadeia, temos: 

$$
\begin{align*}
    \cosh{x} &= \dfrac{e^x + e^{-x}}{2} \\\\
    \therefore (\cosh{x})' &= \dfrac{1}{2}(e^x + e^{-x})' \\\\ 
    \therefore (\cosh{x})' &= \dfrac{1}{2}(e^x - e^{-x}) \\\\
    \therefore (\cosh{x})' &= \sinh{x}
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (Derivada da tangente hiperbólica)</b> — Pela regra do quociente, temos: 

$$
\begin{align*}
    \tanh{x} &= \dfrac{\sinh{x}}{\cosh{x}} \\\\ 
    \therefore (\tanh{x})' &= \dfrac{(\sinh{x})' \cdot \cosh{x} - \sinh{x} \cdot (\cosh{x})'}{\cosh^2{x}} \\\\
    \therefore (\tanh{x})' &= \dfrac{\cosh^2{x} - \sinh^2{x}}{\cosh^2{x}} \\\\
    \therefore (\tanh{x})' &= \dfrac{1}{\cosh^2{x}} \\\\
    \therefore (\tanh{x})' &= \text{sech}^2x
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (Derivada da cossecante hiperbólica)</b> — Pela regra do quociente, temos: 

$$
\begin{align*}
    \text{csch }x &= \dfrac{1}{\sinh{x}} \\\\ 
    \therefore (\text{csch }x)' &= \left(\dfrac{1}{\sinh{x}}\right)' \\\\
    \therefore (\text{csch }x)' &= \dfrac{(1)' \cdot \sinh{x} - 1 \cdot (\sinh{x})'}{\sinh^2{x}} \\\\ 
    \therefore (\text{csch }x)' &= \dfrac{-\cosh{x}}{\sinh^2{x}} \\\\ 
    \therefore (\text{csch }x)' &= -\text{cotgh }x \cdot \text{csch }x 
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (Derivada da secante hiperbólica)</b> — Pela regra do quociente temos: 

$$
\begin{align*}
    \text{sech }x &= \dfrac{1}{\cosh{x}} \\\\ 
    \therefore (\text{sech }x)' &= \left(\dfrac{1}{\cosh{x}}\right)' \\\\
    \therefore (\text{sech }x)' &= \dfrac{(1)' \cdot \cosh{x} - 1 \cdot (\cosh{x})'}{\cosh^2{x}} \\\\ 
    \therefore (\text{sech }x)' &= \dfrac{-\sinh{x}}{\cosh^2{x}} \\\\ 
    \therefore (\text{sech }x)' &= -\tanh{x} \cdot \text{sech }x
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (Derivada da cotangente hiperbólica)</b> — Pela regra do quociente, temos: 

$$
\begin{align*}
    \text{cotgh }x &= \dfrac{1}{\tanh{x}} \\\\ 
    \therefore (\text{cotgh }x)' &= \left(\dfrac{1}{\tanh{x}}\right)' \\\\ 
    \therefore (\text{cotgh }x)' &= \dfrac{(1)' \cdot \tanh{x} - 1 \cdot (\tanh{x})'}{\tanh^2{x}} \\\\ 
    \therefore (\text{cotgh }x)' &= \dfrac{-\text{sech}^2x}{\tanh^2{x}} \\\\ 
    \therefore (\text{cotgh }x)' &= -\text{csch}^2x
\end{align*}
$$

</aside>

## Funções inversas

Pela propriedade previamente demonstrada no códice sobre <a href="/books/higher_education/math/calculus_one/derivatives_inverses.html" target="_blank">derivadas inversas</a>, podemos facilmente encontrar as derivadas das funções inversas trigonométricas.

<aside>

<b>Demonstração (Derivada do arco seno hiperbólico)</b> — Aplicando a propriedade previamente explorada, além do análogo hiperbólico para a relação fundamental da trigonometria, obtemos: 

$$
\begin{align*}
    (\text{arcsinh }x)' &= \dfrac{1}{\cosh(\text{arcsinh }x)} \\\\ 
    \therefore (\text{arcsinh }x)' &= \dfrac{1}{\sqrt{x^2 + 1}}, \forall x \in \mathbb{R}
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (Derivada do arco cosseno hiperbólico)</b> — Pela propriedade previamente explorada, além do análogo hiperbólico para a relação fundamental trigonométrica, temos: 

$$
\begin{align*}
    (\text{arccosh }x)' &= \dfrac{1}{\sinh{\text{arccosh }x}} \\\\ 
    \therefore (\text{arccosh }x)' &= \dfrac{1}{\sqrt{x^2 - 1}}, \forall x \gt 1
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (Derivada do arco tangente hiperbólico)</b> — Através da propriedade previamente explorada, além do análogo hiperbólico para a relação fundamental da trigonometria, obtemos: 

$$
\begin{align*}
    (\text{arctgh }x)' &= \dfrac{1}{\text{sech}^2(\text{arctgh }x)} \\\\ 
    \therefore (\text{arctgh }x)' &= \dfrac{1}{1 - x^2}, \forall |x| \lt 1
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (Derivada do arco cossecante hiperbólico)</b> — Por meio da propriedade previamente explorada e da relação hiperbólica análoga a relação fundamental trigonométrica, temos: 

$$
\begin{align*}
    (\text{arccsch }x)' &= \dfrac{1}{-\text{cotgh}(\text{arccsch }x) \cdot x} \\\\ 
    \therefore (\text{arccsch }x)' &= \dfrac{1}{|x| \sqrt{x^2 + 1}}, \forall x \neq 0
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (Derivada do arco secante hiperbólico)</b> — Por meio da propriedade previamente explorada e da análoga relação hiperbólica a relação fundamental da trigonometria, obtemos: 

$$
\begin{align*}
    (\text{arcsech }x)' &= \dfrac{1}{-\tanh{\text{arcsech }x} \cdot x} \\\\ 
    \therefore (\text{arcsech }x)' &= \dfrac{1}{-x \sqrt{1 - x^2}}, \forall x \in (0, 1) \\\\ 
\end{align*}
$$

</aside>

<aside>

<b>Demonstração (Derivada do arco cotangente hiperbólico)</b> — Por meio da propriedade previamente explorada e da análoga relação das funções hiperbólicas, que é análoga a relação trigonométrica fundamental, temos: 

$$
\begin{align*}
    (\text{arcctgh }x)' &= \dfrac{1}{\text{sech}^2(\text{arcctgh }x)} \\\\ 
    \therefore (\text{arcctgh }x)' &= \dfrac{1}{1 - x^2}, \forall |x| \gt 1
\end{align*}
$$

</aside>

# Referências

1. STEWART, James. Cálculo. Volume 1. 6. ed. São Paulo: Cengage Learning, 2009.