## 7.1 - Reatribuição

Pode ser que você já tenha descoberto que é permitido fazer mais de uma atribuição para a mesma variável. Uma nova atribuição faz uma variável existente referir-se a um novo valor (e deixar de referir-se ao valor anterior).

```python
>>> x = 5
>>> x
5
>>> x = 7
>>> x
7
```

A primeira vez que exibimos x, seu valor é 5; na segunda vez, seu valor é 7.

A Figura 7.1 mostra que a reatribuição parece um diagrama de estado.

Neste ponto quero tratar de uma fonte comum de confusão. Como o Python usa o sinal de igual (=) para atribuição, é tentador interpretar uma afirmação como a = b como uma proposição matemática de igualdade; isto é, a declaração de que a e b são iguais. Mas esta é uma interpretação equivocada.

Em primeiro lugar, a igualdade é uma relação simétrica e a atribuição não é. Por exemplo, na matemática, se a=7 então 7=a. Mas no Python, a instrução a = 7 é legal e 7 = a não é.

Além disso, na matemática, uma proposição de igualdade é verdadeira ou falsa para sempre. Se a=b agora, então a sempre será igual a b. No Python, uma instrução de atribuição pode tornar duas variáveis iguais, mas elas não precisam se manter assim:

```python
>>> a = 5
>>> b = a    # a e b agora são iguais
>>> a = 3    # a e b não são mais iguais
>>> b
5
```

A terceira linha modifica o valor de a, mas não muda o valor de b, então elas já não são iguais.

A reatribuição de variáveis muitas vezes é útil, mas você deve usá-la com prudência. Se os valores das variáveis mudarem frequentemente, isso pode dificultar a leitura e depuração do código.

```python
Figura 7.1 – Diagrama de estado.
```

![Figura 7.1 – Diagrama de estado da variável x.](fig/tnkp_0701.png)
<br>_Figura 7.1 – Diagrama de estado da variável x._
