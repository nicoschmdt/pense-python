## 19.3 - Expressões geradoras

Expressões geradoras são semelhantes às abrangências de listas, mas com parênteses em vez de colchetes:

```python
>>> g = (x**2 for x in range(5))
>>> g
<generator object <genexpr> at 0x7f4c45a786c0>
```

O resultado é um objeto gerador que sabe como fazer iterações por uma sequência de valores. No entanto, ao contrário de uma abrangência de listas, ele não calcula todos os valores de uma vez; espera pelo pedido. A função integrada next recebe o próximo valor do gerador:

```python
>>> next(g)
0
>>> next(g)
1
```

Quando você chega no fim da sequência, next cria uma exceção StopIteration. Também é possível usar um loop for para fazer a iteração pelos valores:

```python
>>> for val in g:
...     print(val)
4
9
16
```

O objeto gerador monitora a posição em que está na sequência, portanto o loop for continua de onde next parou. Uma vez que o gerador se esgotar, ele continua criando StopException:

```python
>>> next(g)
StopIteration
```

As expressões geradoras muitas vezes são usadas com funções como sum, max e min:

```python
>>> sum(x**2 for x in range(5))
30
```
