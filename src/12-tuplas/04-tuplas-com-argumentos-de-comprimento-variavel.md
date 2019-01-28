## 12.4 - Tuplas com argumentos de comprimento variável

As funções podem receber um número variável de argumentos. Um nome de parâmetro que comece com `*` reúne vários argumentos em uma [tupla](09-glossario.md#tupla). Por exemplo, `printall` recebe qualquer número de argumentos e os exibe:

```python
def printall(*args):
    print(args)
```

O parâmetro com o prefixo `*` pode ter qualquer nome que você goste, mas `args` é o convencional. É assim que a função funciona:

```python
>>> printall(1, 2.0, '3')
(1, 2.0, '3')
```

O complemento de reunir é espalhar. Se você tiver uma sequência de valores e quiser passá-la a uma função como argumentos múltiplos, pode usar o operador `*`. Por exemplo, o `divmod` recebe exatamente dois argumentos; ele não funciona com uma tupla:

```python
>>> t = (7, 3)
>>> divmod(t)
TypeError: divmod expected 2 arguments, got 1
```

No entanto, se você espalhar a tupla, aí funciona:

```python
>>> divmod(*t)
(2, 1)
```

Muitas das funções integradas usam tuplas com argumentos de comprimento variável. Por exemplo, `max` e `min` podem receber qualquer número de argumentos:

```python
>>> max(1, 2, 3)
3
```

Mas sum, não:

```python
>>> sum(1, 2, 3)
TypeError: sum expected at most 2 arguments, got 3
```

Como exercício, escreva uma função chamada `sumall` que receba qualquer número de argumentos e retorne a soma deles.
