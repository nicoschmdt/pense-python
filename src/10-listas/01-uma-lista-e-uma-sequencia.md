## 10.1 - Uma [lista](14-glossario.md#lista) é uma sequência

Como uma string, uma lista é uma sequência de valores. Em uma string, os valores são caracteres; em uma lista, eles podem ser de qualquer tipo. Os valores em uma lista são chamados de elementos, ou, algumas vezes, de itens.

Há várias formas para criar uma lista; a mais simples é colocar os elementos entre colchetes (`[` e `]`):

```python
[10, 20, 30, 40]
['crunchy frog', 'ram bladder', 'lark vomit']
```

O primeiro exemplo é uma lista de quatro números inteiros. O segundo é uma lista de três strings. Os elementos de uma lista não precisam ser do mesmo tipo. A lista seguinte contém uma string, um número de ponto flutuante, um número inteiro e (olhe só!) outra lista:

```python
['spam', 2.0, 5, [10, 20]]
```

Uma lista dentro de outra lista é uma [lista aninhada](14-glossario.md#lista-aninhada).

Uma lista que não contém elementos é chamada de lista vazia; você pode criar uma com colchetes vazios [].

Como já se poderia esperar, podemos atribuir uma lista de valores a variáveis:

```python
>>> cheeses = ['Cheddar', 'Edam', 'Gouda']
>>> numbers = [42, 123]
>>> empty = []
>>> print(cheeses, numbers, empty)
['Cheddar', 'Edam', 'Gouda'] [42, 123] []
```
