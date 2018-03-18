## 6.1 - Valores de retorno

A chamada de função gera um valor de retorno, que normalmente atribuímos a uma variável ou usamos como parte de uma expressão.

```python
e = math.exp(1.0)
height = radius * math.sin(radians)
```

As funções que descrevemos, por enquanto, são todas nulas. Resumindo, elas não têm valores de retorno; mais precisamente, o seu valor de retorno é None.

Neste capítulo veremos (finalmente) como escrever funções com resultados. O primeiro exemplo é area, que devolve a área de um círculo com o raio dado:

```python
def area(radius):
    a = math.pi * radius**2
    return a
```

Já vimos a instrução return, mas em uma função com resultado ela inclui uma expressão. Esta instrução significa: “Volte imediatamente desta função e use a seguinte expressão como valor de retorno”. A expressão pode ser arbitrariamente complicada, então poderíamos ter escrito esta função de forma mais concisa:

```python
def area(radius):
    return math.pi * radius**2
```

Por outro lado, variáveis temporárias como a, tornam a depuração mais fácil.

Às vezes, é útil ter várias instruções de retorno, uma em cada ramo de uma condicional:

```python
def absolute_value(x):
    if x < 0:
        return -x
    else:
        return x
```

Como essas instruções return estão em uma condicional alternativa, apenas uma é executada.

Logo que uma instrução de retorno seja executada, a função termina sem executar nenhuma instrução subsequente. Qualquer código que apareça depois de uma instrução return, ou em qualquer outro lugar que o fluxo da execução não atinja, é chamado de código morto.

Em uma função com resultado, é uma boa ideia garantir que cada caminho possível pelo programa atinja uma instrução return. Por exemplo:

```python
def absolute_value(x):
    if x < 0:
        return -x
    if x > 0:
        return x
```

Essa função é incorreta porque se x for 0, nenhuma condição é verdade, e a função termina sem chegar a uma instrução return. Se o fluxo de execução chegar ao fim de uma função, o valor de retorno é None, que não é o valor absoluto de 0:

```python
>>> absolute_value(0)
None
```

A propósito, o Python oferece uma função integrada chamada abs, que calcula valores absolutos.

Como exercício, escreva uma função compare que receba dois valores, x e y, e retorne 1 se x &gt; y, 0 se x == y e -1 se x &lt; y.
