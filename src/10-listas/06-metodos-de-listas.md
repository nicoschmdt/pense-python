## 10.6 - Métodos de listas

O Python oferece métodos que operam em listas. Por exemplo, `append` adiciona um novo [elemento](14-glossario.md#elemento) ao fim de uma [lista](14-glossario.md#lista):

```python
>>> t = ['a', 'b', 'c']
>>> t.append('d')
>>> t
['a', 'b', 'c', 'd']
```

`extend` toma uma lista como argumento e adiciona todos os elementos:

```python
>>> t1 = ['a', 'b', 'c']
>>> t2 = ['d', 'e']
>>> t1.extend(t2)
>>> t1
['a', 'b', 'c', 'd', 'e']
```

Este exemplo deixa t2 intocado.

`sort` classifica os elementos da lista em ordem ascendente:

```python
>>> t = ['d', 'c', 'e', 'b', 'a']
>>> t.sort()
>>> t
['a', 'b', 'c', 'd', 'e']
```

A maior parte dos métodos de listas são nulos; eles alteram a lista e retornam None. Se você escrever t = t.sort() por acidente, ficará desapontado com o resultado.
