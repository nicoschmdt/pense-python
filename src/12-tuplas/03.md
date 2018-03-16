## 12.3 - Tuplas como valores de retorno

Falando estritamente, uma função só pode retornar um valor, mas se o valor for uma tupla, o efeito é o mesmo que retornar valores múltiplos. Por exemplo, se você quiser dividir dois números inteiros e calcular o quociente e resto, não é eficiente calcular x/y e depois x%y. É melhor calcular ambos ao mesmo tempo.

A função integrada divmod toma dois argumentos e devolve uma tupla de dois valores: o quociente e o resto. Você pode guardar o resultado como uma tupla:

```python
>>> t = divmod(7, 3)
>>> t
(2, 1)
```

Ou usar a atribuição de tuplas para guardar os elementos separadamente:

```python
>>> quot, rem = divmod(7, 3)
>>> quot
2
>>> rem
1
```

Aqui está um exemplo de função que retorna uma tupla:

```python
def min_max(t):
    return min(t), max(t)
```

`max` e `min` são funções integradas que encontram os maiores e menores elementos de uma sequência. `min_max` calcula ambos e retorna uma tupla de dois valores.
