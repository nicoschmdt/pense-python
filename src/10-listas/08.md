## 10.8 - Como excluir elementos

Há várias formas de excluir elementos de uma lista. Se souber o índice do elemento que procura, você pode usar `pop`:

```python
>>> t = ['a', 'b', 'c']
>>> x = t.pop(1)
>>> t
['a', 'c']
>>> x
'b'
```

`pop` altera a lista e retorna o elemento que foi excluído. Se você não incluir um índice, ele exclui e retorna o último elemento.

Se não precisar do valor removido, você pode usar a instrução `del`:

```python
>>> t = ['a', 'b', 'c']
>>> del t[1]
>>> t
['a', 'c']
```

Se souber o elemento que quer excluir (mas não o índice), você pode usar `remove`:

```python
>>> t = ['a', 'b', 'c']
>>> t.remove('b')
>>> t
['a', 'c']
```
O valor devolvido por `remove` é `None`.

Para remover mais de um elemento, você pode usar `del` com um índice de fatia:

```python
>>> t = ['a', 'b', 'c', 'd', 'e', 'f']
>>> del t[1:5]
>>> t
['a', 'f']
```

Como sempre, a fatia seleciona todos os elementos até, mas não incluindo, o segundo índice.
