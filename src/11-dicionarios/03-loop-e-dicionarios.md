## 11.3 - Loop e dicionários

Se usar um [dicionário](09-glossario.md#dicionário) em uma instrução `for`, ela percorre as chaves do dicionário. Por exemplo, `print_hist` exibe cada [chave](09-glossario.md#chave) e o [valor](09-glossario.md#valor) correspondente:

```python
def print_hist(h):
    for c in h:
        print(c, h[c])
```

Isso é o que aparece:

```python
>>> h = histogram('parrot')
>>> print_hist(h)
a 1
p 1
r 2
t 1
o 1
```

Novamente, as chaves não estão em nenhuma ordem determinada. Para atravessar as chaves em ordem ascendente, você pode usar a função integrada `sorted`:

```python
>>> for key in sorted(h):
...     print(key, h[key])
a 1
o 1
p 1
r 2
t 1
```
