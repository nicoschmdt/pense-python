## 3.2 - Funções matemáticas

O Python tem um [módulo](13-glossario.md#módulo) matemático que oferece a maioria das funções matemáticas comuns. Um módulo é um arquivo que contém uma coleção de funções relacionadas.

Antes que possamos usar as funções em um módulo, precisamos importá-lo com uma [instrução de importação](13-glossario.md#instrução-de-importação):

```python
>>> import math
```

Esta instrução cria um [objeto de módulo](13-glossario.md#objeto-de-módulo) chamado math (matemática). Ao se exibir o objeto de módulo, são apresentadas informações sobre ele:

```python
>>> math
<module 'math' (built-in)>
```

O objeto de módulo contém as funções e variáveis definidas no módulo. Para acessar uma das funções, é preciso especificar o nome do módulo e o nome da [função](13-glossario.md#função), separados por um ponto. Este formato é chamado de [notação de ponto](13-glossario.md#notação-de-ponto).


```python
>>> ratio = signal_power / noise_power
>>> decibels = 10 * math.log10(ratio)
>>> radians = 0.7
>>> height = math.sin(radians)
```

O primeiro exemplo usa math.log10 para calcular a proporção de sinal e de ruído em decibéis (assumindo que signal\_power e noise\_power tenham sido definidos). O módulo matemático também oferece a função log, que calcula logaritmos de base e.

O segundo exemplo encontra o seno de radians. O nome da variável indica que sin e outras funções trigonométricas (cos, tan etc) recebem argumentos em radianos. Para converter graus em radianos, divida por 180 e multiplique por π:


```python
>>> degrees = 45
>>> radians = degrees / 180.0 * math.pi
>>> math.sin(radians)
0.707106781187
```

A expressão math.pi recebe a variável pi do módulo matemático. Seu valor é uma aproximação de ponto flutuante de π, com precisão aproximada de 15 dígitos.

Se souber trigonometria, você pode verificar o resultado anterior comparando-o com a raiz quadrada de 2 dividida por 2:

```python
>>> math.sqrt(2) / 2.0
0.707106781187
```
